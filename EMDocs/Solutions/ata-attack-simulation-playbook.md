---
title: "Manual de simulação de ataques de análise avançada de ameaça"
description: "Este guia ajudará os clientes a aprenderem sobre roubo de credencial contra um sistema operacional Windows, como usar ferramentas de pesquisa disponíveis publicamente para realizar essas ações e como Microsoft ATA detecta essas ameaças."
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 03/13/2017
ms.topic: solution
ms.prod: 
ms.service: advanced-threat-analytics
ms.technology: techgroup-identity
ms.assetid: da5eda7c-29bb-429f-9366-72495667c010
ms.reviewer: v-craic
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cff5b87f6c5d0b9aa987631fefe5bf74e3a43862
ms.openlocfilehash: 41672ccdbd2c868add70e423b7dbc8048713259b
ms.lasthandoff: 03/14/2017


---

# <a name="advanced-threat-analytics-attack-simulation-playbook"></a>Manual de simulação de ataques de análise avançada de ameaça

Este guia ajudará você a aprender sobre roubo de credenciais como Pass-the-Hash, Pass-the-Ticket, Over-Pass-the-Hash e como usar ferramentas de pesquisa disponíveis publicamente para realizar essas ações. Este manual de simulação é baseado em um cenário de build com ferramentas para a Internet válidas usados pelos invasores. O objetivo é mostrar como pensar como um invasor (em gráficos), se mover dentro de um ambiente com credenciais roubadas e como usar o Microsoft Advanced Threat Analytics (ATA) para detectar essas atividades em seu ambiente.

Este guia mostrará os seguintes cenários de ataque:

- Reconhecimento de DNS
- Enumeração dos serviços de diretório
- Enumeração da Sessão SMB
- Coleta de credenciais (lsass.exe)
- Overpass-the-Hash
- Pass-the-Ticket
- Execução remota de código
- Skeleton Key
- Sincronização do controlador de domínio

> [!IMPORTANT]
> As etapas fornecidas neste guia devem ser executadas em um ambiente de laboratório e não em produção.

## <a name="configuring-your-lab-environment"></a>Configurando seu ambiente de laboratório

É recomendável seguir estas instruções, incluindo os testes no final.  Há configurações a se fazer, especificamente quatro computadores, três usuários e software de pesquisa a se baixar da Internet.

Visite [Avaliações do Advanced Threat Analytics](http://aka.ms/ataeval), para obter diretrizes sobre como instalar ATA e obter uma cópia de avaliação de 90 dias. 

> [!IMPORTANT]
> Este guia foi criado com base em ATA versão 1.7.


### <a name="scenario"></a>Cenário

Neste exemplo de laboratório, JeffV é um administrador de sua própria estação de trabalho.  Vários departamentos de TI ainda têm sua população de usuários com privilégios de administrador.  Nesses cenários, os ataques de elevação local não são necessárias como o adversário já tem acesso de administrador no ambiente do que executar suas operações de pós infiltração. 
 
No entanto, mesmo quando os departamentos de TI reduzem os privilégios usando contas não administrativas, outras formas de ataques (conhecido como vulnerabilidades de aplicativos, 0 dias e similares) são executadas para alcançar o escalonamento de privilégio local. Nesse caso, este guia pressupõe que o adversário obteve escalonamento de privilégio local no PC vítima.  Neste laboratório fictício, isso foi obtido por meio de um email de spearphishing para JeffV, conforme explicado em mais detalhes posteriormente neste guia.


### <a name="servers-and-workstations"></a>Servidores e estações de trabalho

A seguir são listados os computadores que você precisará e as configurações usadas neste exercício.  Esses são todos configurados como VMs convidadas (máquinas virtuais) no Windows 10 Hyper-V.  Se você seguir esse caminho e é recomendável que você faça, certifique-se que as VMs sejam colocadas no mesmo comutador virtual.

| FQDN | SO | IP | Finalidade |
| --- | --- | --- | --- |
| DC1.contoso.local | Windows Server 2012 R2 | 192.168.10.10 | Controlador de domínio com ATA e Gateway de Lightweight (LWGW) instalados |
| ATACenter.contoso.local | Windows Server 2012 R2 | 192.168.10.20 | Centro de ATA |
| Admin-PC.contoso.local | Windows 7 Enterprise | 192.168.10.30 | PC do Admin |
| Victim-PC.contoso.local | Windows 7 Enterprise | 192.168.10.31 | PC da vítima |

O domínio para este laboratório é chamado "CONTOSO. LOCAL". Criar o domínio e, em seguida, ingressar no domínio nesses computadores. Depois que todas as quatro máquinas estão funcionando e integradas ao domínio, vá para a próxima seção para adicionar alguns usuários fictícios ao ambiente.


### <a name="users-configuration"></a>Configuração do Usuário

Agora você criará funções diferentes para assistência técnica e administradores de domínio.  A intenção de criar essas funções é fornecer a separação de funções, no entanto você aprenderá neste guia que isso não é suficiente para impedir o roubo de credenciais, movimentação lateral ou escalonamento de domínio, porque entender as dependências de segurança fora desses dois grupos em um ambiente é complicado. 

Primeiro, crie os seguintes usuários no domínio: 

| Nome | Membros | Finalidade |
| --- | --- | --- |
| Suporte técnico | RonHD | Gerencia os clientes da contoso.local. |

Agora, crie o seguinte grupo de segurança com um membro específico:

| Nome Completo | SAMAccount | Finalidade |
| --- | --- | --- |
| Jeff Vítima | JeffV | A vítima de outro ataque de spearphishing muito eficaz |
| Ron HD | RonHD | Ron é o "cara"; no departamento de TI da Contoso.  RonHD é um membro do "suporte técnico"; grupo de segurança. |
| Nuck Chorris | NuckC | Até agora, considerado inexistente.  Na Contoso, ele é o nosso *administrador de domínio*. |

> [!IMPORTANT]
> Antes de prosseguir, certifique-se que *RonHD* esteja adicionado como um membro do grupo de segurança de *suporte técnico*.


Nuck Chorris, administrador de domínio da Contoso, usa a estação de trabalho do *PC de Admin*. O grupo de segurança do *suporte técnico* (que o *RonHD* é membro) também gerencia o computador *NuckC*.  Isso pode ser configurado usando [Grupos Restritos](https://support.microsoft.com/kb/279301). As propriedades do grupo do administrador devem ser semelhantes a tela a seguir:

![Propriedades do Admin](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig1.png)

Além disso, como em muitos ambientes de TI, *JeffV* foi adicionado como um administrador no seu próprio dispositivo (*PC vítima*).  Isso foi feito de propósito e será explicado posteriormente neste artigo. As propriedades do grupo do administrador local devem ser semelhantes a tela a seguir:

![Propriedades do Admin 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig2.png)


### <a name="security-research-tools"></a>Ferramentas de pesquisa de segurança

Para configurar este laboratório, você precisará baixar e instalar as ferramentas abaixo em *c:\Tools.* no computador *PC vítima*:

- [Mimikatz](https://github.com/gentilkiwi/mimikatz)
- [PowerSploit](https://github.com/PowerShellMafia/PowerSploit)
- [PsExec](https://technet.microsoft.com/en-us/pxexec) 
- [NetSess.exe](http://www.joeware.net/freetools)

A pasta de ferramentas deve ser semelhante a tela a seguir:

![Propriedades do Admin](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig3.png)


> [!IMPORTANT]
> Essas ferramentas são apenas para fins de pesquisa.  A Microsoft não tem essas ferramentas, nem pode assegurar seu comportamento.  Essas ferramentas só devem ser executadas em um ambiente de laboratório de teste.

Para fins deste laboratório, desligue todos os antivírus no computador *PC vítima*. Embora desativar o antivírus possa parecer que isso desviou os resultados, é importante observar que o código-fonte para essas ferramentas está disponível gratuitamente, o que significa que os invasores podem modificar para escapar da detecção por assinatura de antivírus. Também é importante observar que, assim que um adversário alcança o administrador local em um computador, evasão de antivírus se torna muito possível.  A meta nesse ponto é proteger o restante da organização. Um comprometimento de computador não deve levar ao escalonamento de domínio e certamente não ao comprometimento de domínio.

### <a name="environment-topology"></a>Topologia do ambiente

Neste ponto, seu código deve ser similar ao seguinte:

![Topologia](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig4.png)

Como mencionado anteriormente neste guia, há funções diferentes para *Admins. do domínio* e *Suporte Técnico*, no entanto, durante a demonstração, você verá esse vínculo de dependência de segurança (nesse caso, o usuário *RonHD*) que é o que um adversário precisa para assumir prontamente todo o ambiente com ferramentas de pesquisa.

### <a name="helpdesk-simulation"></a>Simulação de Suporte Técnico

Para simular um cenário comum de suporte técnico, em que a equipe de suporte técnico está conectada em diferentes computadores, faça logon com *RonHD* no *PC vítima* e, em seguida, faça logon novamente como *JeffV*.  Use o mecanismo de "Mudar usuário" para simular o gerenciamento de credenciais com privilégios nesta estação de trabalho.

![Mudar usuário](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig5.png)


Existem outras maneiras de simular esse fluxo de trabalho de gerenciamento neste laboratório, como a criação de contas de serviço de script em lotes, tarefas agendadas e sessão RDP ou 'Executar como' na linha de comando.  Em operações seguras algo (nem sempre um alguém) deve gerenciar esses recursos e o gerenciamento significa privilégios de administrador local. Para fins deste laboratório e otimizar o tempo, a rota mais rápida para simular esse fluxo de trabalho foi selecionada.

> [!IMPORTANT]
> Não faça logoff ou reinicie o *PC vítima* neste ponto, pois isso apagará as credenciais *do RonHD* da memória e exigirá aplicar o cenário de *suporte técnico* novamente. 

A tabela a seguir resume as credenciais que são salvas em cada computador:

| Computador | Credenciais salvas no computador |
| --- | --- |
| PC do Admin | - NuckC |
| PC vítima | -JeffV e RonHD (causa pela imposição do cenário de suporte técnico) |

Neste ponto, o ambiente de laboratório está pronto. O estado atual do laboratório está em uma posição em que é uma exploração ausente (#1ea) de comprometimento do domínio.  Em seguida, você verá que um compromisso único normalmente é proveniente dos ativos menos privilegiados do seu ambiente contra os aplicativos de Internet de um adversário altamente motivado e não parará.  É aí que a metodologia de [supor uma violação](https://blogs.msdn.microsoft.com/azuresecurity/2015/10/19/an-insiders-look-at-the-security-of-microsoft-azure-assume-the-breach/) é abordada.

## <a name="executing-the-attack"></a>Executando o ataque

Nesta seção deste guia, você usará as ferramentas do mundo real e simular as atividades de pós-infiltração de um adversário.

### <a name="beachhead-via-spearphish"></a>Beachhead via spearphish

Para esta simulação de ataque, pressupõe-se que o adversário obteve privilégios de administrador local em um computador no ambiente.  Enquanto isso pode ser obtido por meio de métodos diferentes, geralmente isso é obtido por meio de campanhas de spearphshing contra uma organização. 

No [Relatório de Inteligência de Segurança da Microsoft, Volume 21](https://www.microsoft.com/security/sir/default.aspx), dois grupos diferentes de atores foram abordados, PROMETHIUM e NEODYNIUM. Ambos os grupos de atividades participam de spearphishing para entrar em seus ambientes de destino.  Por quê?  Email é uma maneira rápida de escapar defesas de rede em uma organização, da perspectiva do invasor. A imagem a seguir tem um exemplo real de um email com spearphishing e respondido pelo Centro de inteligência contra ameaça da Microsoft.

![Email de Spearphising](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig6.png)


Em um ambiente seguro, a perda de um único host não deve levar ao comprometimento de todo um domínio ou floresta.  Detectar a próxima etapa do adversário é fundamental no mundo "pós-violação".

### <a name="reconnaissance"></a>Reconhecimento

Depois que um adversário humano obtiver presença em um ambiente, o reconhecimento (também chamado de recon) começa.  Nesta fase, o adversário gasta tempo pesquisando o ambiente: detecção de configurações, computadores de interesse, enumerar grupos de segurança e outros objetos do active directory de seu interesse, etc. para pintar uma imagem para si mesmo do seu ambiente.

#### <a name="dns-reconnaissance"></a>Reconhecimento de DNS

Uma das primeiras coisas que os muitos adversários farão é tentar receber todo o conteúdo do DNS e o Microsoft ATA pode detectar essa ação.

No PC vítima você iniciará o reconhecimento de DNS através do logon usando as credenciais de JeffV, que é o PC e o usuário que o adversário acabou de comprometer e execute os seguintes comandos: 
    
    nslookup
    ls -d contoso.local

Os resultados devem ser similares à tela a seguir:

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig7.png)

Neste laboratório, o DNS está configurado para bloquear essa operação de despejo DNS em relação ao domínio. Infelizmente, embora, com muita frequência, esse evento é ignorado ou perdido no ruído de rede, impedindo que os defensores da rede perceber que um adversário atingiu algum nível de acesso em seu ambiente e está nas fases de início de um ataque mais direcionada.

Microsoft ATA ajuda a detectar esse tipo de ataque ao sinalizar uma atividade suspeita do DNS, conforme mostrado abaixo:

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig8.png)

Como ATA continuamente a analisar o tráfego DNS, ele pode ver a solicitação de despejo, seja bem-sucedida ou não.  Ele ainda fornece a capacidade de aprender com esse evento no futuro, caso a atividade suspeita seja legítima e vinda de um dispositivo de verificação de DNS aprovado.

Nesse caso o adversário é impedido do que seria uma grande vitória para eles: ao realizar um despejo DNS, busca outras técnicas de reconhecimento.

> [!IMPORTANT]
> Detectar falhas pode ser tão criterioso quanto a detecção de ataques com êxito em um ambiente.
 
No alerta de ATA mostrado acima, você pode perceber a bolha azul na atividade suspeita, isso significa que a ATA está aprendendo constantemente, com base em dados consumidos e do analista.  Os comentários do analista ajudam a remover positivos verdadeiros e a reduzir o ruído ao longo do tempo, personalizando ATA e suas detecções de atividades suspeitas para seu ambiente.

#### <a name="directory-services-enumeration"></a>Enumeração dos serviços de diretório

[Protocolo Remoto do Gerenciador de Conta de Segurança (SAMR)](https://msdn.microsoft.com/library/cc245477.aspx) fornece funcionalidade de gerenciamento para usuários e grupos em um domínio.  Saber que a relação entre usuários, grupos e privilégios pode ser extremamente importante para um adversário.  Qualquer usuário autenticado pode executar esses comandos. Para obter mais informações sobre configurações de SAMR e restringir tal reconhecimento somente para usuários que são membros do grupo de Administradores Locais, consulte [este documento](https://gallery.technet.microsoft.com/SAMRi10-Hardening-Remote-48d94b5b#content).

#### <a name="enumerate-all-users-and-groups"></a>Enumerar todos os usuários e grupos

Enumerar os usuários e grupos é muito útil para um adversário.  Conhecer os nomes de usuário e os nomes dos grupos pode vir a ser útil.  Como um invasor, você deseja obter o máximo de informações durante a fase de reconhecimento.

Para simular a enumeração de usuários e grupos, você deve usar a conta comprometida do *JeffV* para efetuar o logon no *PC vítima*. Depois de conectado, você tentará chamar todos os usuários de domínio e grupos usando os seguintes comandos:

    net user /domain
    net group /domain

Um exemplo de como é o resultado do primeiro comando é mostrado na imagem a seguir:

![Usuário Net](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig9.png)

Um exemplo de como é o resultado do segundo comando é mostrado na imagem a seguir:

![Grupo Net](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig10.png)

O motivo pelo qual essas operações tem êxito, sem qualquer problema, é porque elas foram realizadas usando credenciais legítimas. O problema agora é que o invasor agora conhece todos os usuários e grupos no ambiente. Sem uma ferramenta como o Microsoft ATA, esta ação provavelmente passaria despercebida.

Para essa operação, Microsoft ATA sinaliza um alerta que mostra o ataque e também exibe os dados que o invasor foi capaz de obter.

![Reconhecimento](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig11.png)

#### <a name="enumerate-high-privileged-accounts"></a>Enumerar contas com alto privilégio

Neste ponto o invasor armazena a lista de usuários e a lista de grupos.  Mas saber quem está em qual grupo também é importante, especialmente para grupos altamente privilegiados como *Administradores Corporativos* e *Admins. do domínio*. Para obter essas informações no seu ambiente de laboratório, faça logon como *JeffV* no *PC vítima* e execute o comando a seguir:

    net group “domain admins” /domain

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![Grupo Net 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig12.png)

O invasor agora tem todos os usuários e grupos e sabe quais usuários pertencerão ao grupo altamente privilegiado de *Admins. do domínio*. Em um cenário do mundo real, a probabilidade de que o ataque continuará a escalonar e tentará obter os Administradores Corporativos é muito alta, já que não há nenhum limite de segurança entre *Administradores Corporativos* e *Admins. do domínio*.

> [!IMPORTANT]
> Para obter mais informações sobre limites de segurança entre florestas e domínios, administradores de empresa e Admins. do domínio e outros privilégios de "nível&0;", consulte [Protegendo material de referência com acesso privilegiado](http://www.aka.ms/tier0).

Para obter a lista de membros do grupo *administradores corporativos* em seu laboratório, execute o seguinte comando *PC vítima*:

    net group “enterprise admins” /domain

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![Grupo Net 3](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig13.png)

No exemplo mostrado acima, há uma única conta no grupo *administradores corporativos*. Nesse caso isso não é uma informação muito útil pois é apenas o padrão, mas o invasor tem que muito mais conhecimento sobre suas contas e identificar qual usuário ele quer comprometer.

### <a name="smb-session-enumeration"></a>Enumeração da sessão SMB

Agora o invasor sabe que eles desejam comprometer as credenciais, no entanto, com as informações atuais não exatamente sabem como comprometer essas credenciais. Usando a enumeração de SMB eles podem obter o local exato em que essas contas altamente interessantes estão expostas.

Todos os usuários autenticados devem se conectar ao controlador de domínio para o processo de política de grupo (em SYSVOL) tornando a enumeração de SMB uma ferramenta valiosa para os invasores. Isso torna os Controladores de domínio (DC) alvos primários para a execução da enumeração de SMB.

Nesta parte do laboratório, você usará *NetSess*, a primeira ferramenta de pesquisa baixada da Internet.  *NetSess* é uma ferramenta de linha de comando para enumerar sessões de NetBIOS em um computador local ou remoto especificado.  

Enumerar quem está conectado a um computador específico, neste caso o controlador de domínio, no *PC vítima*, vá para o local no qual NetSess está salvo localmente e execute o seguinte comando:

    NetSess.exe dc1.contoso.local

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![NetSess](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig14.png)

Esse tipo de reconhecimento é difícil de detectar com controles de segurança tradicionais, como um firewall. O que aumenta a probabilidade de êxito desse ataque é o fato de que o protocolo SMB é amplamente usado por empresas de TI e é um protocolo que depende do Active Directory para várias operações. Microsoft ATA é capaz de detectar a atividade de enumeração da sessão SMB e disparar um alerta para notificar as contas que foram expostas.

Microsoft ATA permite que você obtenha os dados relevantes que o invasor tem acesso, ele identifica o computador de origem, a conta de origem, bem como as contas expostas e os endereços IP no momento da enumeração do adversário. Você pode ver um exemplo na tela a seguir:

![SMB](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig15.png)

Os dados que o Microsoft ATA oferece a você são vitais para aumentar a conscientização da segurança, o que ajuda você a estar mais preparado para responder aos ataques.

### <a name="lateral-movement"></a>Movimentação lateral

A meta dessa fase é acessar o endereço IP que foi descoberto anteriormente (192.168.10.30), em que as credenciais do computador *do NuckC* estã expostas. Para executar esta ação, você enumerará credenciais na memória localizadas no *PC vítima*. Lembre-se que o *PC vítima* não está apenas exposto às credenciais do *JeffV*, existem muitas outras contas que podem ser úteis para um invasor. 


Para extrair as credenciais do *PC vítima*, você usará mimikatz, outra ferramenta de pesquisa baixada da Internet. Em um prompt de comandos com privilégios elevados no *PC vítima*, vá para a pasta Ferramentas em que *Mimikatz* está salvo e execute o seguinte comando:

    mimikatz.exe “privilege::debug” “sekurlsa::logonpasswords” “exit” >> c:\temp\victim-pc.txt

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![mimikatz](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig16.png)

O comando acima executará mimikatz, que, em seguida, coletará credenciais na memória.  A ferramenta escreverá isso em um arquivo de texto denominado "pc-vítima.txt". Abra o arquivo "pc-vítima.txt" para ver o que você pode encontrar.

A próxima etapa é analisar a saída de despejo de credencial *do mimikatz* e para fazer isso, você precisa abrir o arquivo, "pc-vítima.txt" no bloco de notas.  O arquivo terá uma aparência diferente pois senhas diferentes foram usadas, sistemas operacionais potencialmente diferentes com configurações padrões habilitadas ou não, portanto, não se assuste se ele não parecer exatamente como o exemplo a seguir.

![Saída](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig17.png)

De acordo com o resultado de exemplo, o invasor encontrou as credenciais do JeffV, o que permitirá que ele personifique o JeffV. O invasor também encontrou a conta do computador, que, como uma conta de usuário, pode ser adicionada ao grupo do *Administrador Local* de outros computadores e outros grupos de segurança com alto privilégio.  Isso não é útil nesse cenário, mas você deve sempre se lembrar que *Contas de Computador* pode mapear a privilégios em outro lugar também.

No exemplo a seguir será observado que o invasor também descobriu uma conta potencialmente interessante, *RonHD*. Lembre-se que *RonHD* estava conectado ao *PC vítima* durante a fase de configuração. Essa credencial foi exposta ao [processo LSA](https://msdn.microsoft.com/library/windows/desktop/aa378327%28v=vs.85%29.aspx) na memória, o qual mimikatz deu a visibilidade do invasor. O usuário *RonHD* não apareceu listado quando você enumerou os usuários em *Admins. do domínio* ou *Administradores Corporativos*, mas agora têm acesso a suas credenciais.

![Nslookup](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig18.png)

Também vale a pena observar que em alguns casos, o despejo de mimikatz poderia revelar as senhas em texto sem formatação, quando o ambiente não está atualizado ou não configurado para impedir o [WDigest](https://blogs.technet.microsoft.com/kfalde/2014/11/01/kb2871997-and-wdigest-part-1/). Um ambiente atualizado, seguindo as práticas recomendadas, retornará um campo vazio de *senha*.   

Como um invasor, o próximo passo natural é verificar se a conta de *RonHD* tem qualquer valor e para isso o invasor fará alguns reconhecimentos nessa conta. Para simular isso do seu laboratório, execute o seguinte comando no *PC vítima*:

    net user ronhd /domain

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![Domínio do usuário net](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig19.png)

Com base nesse resultado, o invasor aprenderá que *RonHD* é um membro do *Suporte Técnico*. A conta *do RonHD* acabou de ser tornar interessante para o invasor.  No entanto, uma maior análise é necessária para ver se a conta tem privilégios administrativos em outros computadores. Afinal de contas, faria pouco sentido usá-la para se mover lateralmente para outro computador apenas para descobrir que ela tem menos privilégio em comparação ao que o invasor já tem.

Com base nisso, a próxima etapa é enumerar os membros de um computador remoto. Nesta etapa, você usará *PowerSploit*, uma série de módulos do PowerShell usado por testadores de penetração. Abra uma sessão do PowerShell e vá até o local em que *PowerSploit* está salvo localmente no *PC vítima*.  No console do PowerShell, execute o comando a seguir:

    Import-Module .\PowerSploit.psm1
    Get-NetLocalGroup 192.168.10.30

O primeiro comando é usado para importar o módulo de *PowerSploit* para a memória e o segundo comando é para executar uma das funções fornecidas pelo módulo, nesse caso, *Get-NetLocalGroup*.

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![PowerShell](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig20.png)

O IP 192.168.10.30 é o endereço IP descoberto da fase de enumeração SMB, como já mostrado anteriormente neste guia. O invasor simplesmente encontrou o seguinte: 

- O IP 192.168.10.30 está conectado ao *PC Admin* (a resolução do nome foi feita via PowerSploit)
- “Contoso.local/Administradores de Domínio” e “Contoso.local/Suporte Técnico” são membros do *Grupo de Administradores*

*RonHD* é um membro do grupo de *Suporte Técnico*, portanto *RonHD* pode fornecer ao invasor privilégios de *Administrador* no *PC Admin* (no qual o invasor sabe que *NuckC* está, por causa de reconhecimento anterior).  
O invasor usou esse [pensamento gráfico](https://blogs.technet.microsoft.com/johnla/2015/04/26/defenders-think-in-lists-attackers-think-in-graphs-as-long-as-this-is-true-attackers-win/) para descobrir as relações na rede. Esse tipo de mentalidade é algo que os defensores precisam adotar para tratar novas ameaças para redes corporativas. 

Agora é hora de usar o *RonHD* para realizar o movimento lateral, usando o ataque [Overpass-the-Hash](). Se o invasor estiver em um ambiente que não desabilitou WDigest, será o fim do jogo, pois eles tem a senha em texto sem formatação.  Mas, para os propósitos deste laboratório, a suposição é que você não sabe/têm acesso à senha em texto sem formatação.

Usando uma técnica chamada Overpass-the-Hash você pode levar o NTLM hash e usá-lo para obter um tíquete de concessão de tíquete (TGT) via o Kerberos\Active Directory.  Com um TGT você pode disfarçar o Ron**HD e acessar qualquer recurso do domínio ao qual*RonHD* tenha acesso.  

Copie o NTLM hash *de RonHD* do pc-vítima.txt, coletado anteriormente (da "Ação: despejo de credenciais do PC vítima"). Em seguida, vá para o *PC vítima*, acesse o local em que *mimikatz* está armazenado no sistema de arquivos e execute os seguintes comandos:

    Mimikatz.exe “privilege::debug” “sekurlsa::pth /user:RonHD /ntlm:[ntlm hash] /domain:contoso.local” “exit”

Certifique-se de substituir o *[ntlm hash]* pelo valor de NTLM colado do pc-vítima.txt.

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![mimikatz 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig21.png)

Uma nova sessão de prompt de comando é aberta e esse novo prompt de comando injetou as credenciais *do RonHD*. Para confirmar se você pode ler o conteúdo do C$ do *PC Admin*, (algo que *JeffV* não deveria ser capaz de fazer), execute o comando abaixo na nova sessão de linha de comando:

    dir \\admin-pc\c$
   
Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![Dir](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig22.png)

O resultado desse comando comprova que agora você tem acesso a unidade C do *PC Admin*. Agora, você validará que o novo prompt de comando que você abriu, injetou o tíquete *do RonHD* e que você não configurou incorretamente os privilégios de leitura do *JeffV*.

Em seguida, você inspecionará os tíquetes no prompt de comando de overpass-the-hash. No novo prompt de comando que foi aberto por causa do ataque de overpass-the-hash, execute o seguinte comando:

    klist

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![klist](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig23.png)

Como você pode ver, agora você está personificando o *RonHD* nesse prompt de comando, que valida que você usou sua credencial legítima para obter acesso a seu *PC Admin*.

Neste ponto, você deve ter notado que Microsoft ATA gerou um alerta sobre uma implementação de protocolo incomum, conforme mostrado abaixo. Isso acontece porque overpass-the-hash usa NTLM e, portanto, RC4. Da perspectiva do defender, você aprenderá que no *PC vítima*, a conta do RonHD autenticou com êxito o controlador de domínio.  Em seguida, você pode começar nossa investigação.

![Protocolo incomum](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig24.png) 

### <a name="domain-escalation"></a>Escalonamento de domínio

Agora, o invasor tem acesso ao *PC Admin*, um computador que foi identificado no reconhecimento como um vetor de ataque, para comprometer *NuckC*, que é uma conta com privilégio alto. O invasor agora deseja se mover para o *PC Admin*, elevando seus direitos dentro do domínio.

Para fazer isso o invasor coletará credenciais executando um ataque de [Pass-the-Hash](https://www.microsoft.com/security/sir/strategy/default.aspx#!pass_the_hash_defenses), que permitirá o movimento para o *PC Admin*.   

Do novo prompt de comando, em execução no contexto de *RonHD*, vá para a parte do sistema de arquivos em que mimikatz está localizado na biblioteca e execute o seguinte comando:

    xcopy mimikatz \\admin-pc\c$\temp

Em seguida, execute mimiKatz remotamente para exportar todos os tíquetes de Kerberos do *PC Admin*, usando o comando a seguir:

    psexec.exe \\admin-pc -accepteula cmd /c (cd c:\temp ^& mimikatz.exe “privilege::debug” “sekurlsa::tickets /export” ^& “exit”)

Copie esses tíquetes de volta para o *PC vítima*, usando o comando a seguir:

    xcopy \\admin-pc\c$\temp c:\temp\tickets

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![XCopy](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig25.png) 

Essa operação mostrou que o invasor copiou com êxito a ferramenta *mimikatz* para o *PC Admin*. O invasor executou com êxito o mimikatz remotamente, exportando todos os tíquetes de Kerberos do *PC Admin*.  Por fim, o invasor copiou novamente os resultados para o *PC vítima*e agora tem as credenciais *do NuckC*, sem a necessidade de explorar seu computador.

A próxima etapa é localizar o *NuckC* TGT. Para fazer isso você precisa localizar os arquivos de kirbi que não são do *NuckC* (ou seja. “ADMIN-PC$”), exclua aqueles e mantenha os tíquetes de *NuckC*.

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![Gerenciador](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig26.png) 

Neste momento, o invasor pode passar o tíquete para a memória e usá-lo para obter acesso a recursos, como se estivesse no *NuckC*. O invasor está pronto para importá-los para o *PC vítima* da memória, para obter as credenciais para acessar recursos confidenciais. Essa operação é feita por meio do ataque [Pass-the-Ticket](https://blogs.technet.microsoft.com/windowsserver/tag/pass-the-ticket/).

Em um prompt de comandos com privilégios elevados, em que *mimikatz* está localizado no sistema de arquivos, execute o seguinte comando:

    mimikatz.exe “privilege::debug” “kerberos::ptt c:\temp\tickets” “exit”

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![privilégio de mimikatz](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig27.png) 

Verifique se os tíquetes *NuckC@krbtgt-CONTOSO.LOCAL* foram importados com êxito, conforme ilustrado no exemplo acima.

eext você deve validar que as permissões de privilégios estão na sessão de prompt de comando. Para fazer isso, execute o seguinte no mesmo prompt de comandos com privilégios elevados:

    klist

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![klist 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig28.png) 

O invasor agora importou com êxito o tíquete coletado para a sessão e agora aproveitará o novo privilégio e acessará a unidade C: do controlador de domínio. Execute o seguinte comando no prompt de comando para o qual as permissões foram importadas:

    dir \\dc1\c$

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![dir 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig29.png) 

O invasor está agora, para todas as intenções e finalidades, em *NuckC*. Somente os administradores devem ser capazes de acessar a raiz do controlador de domínio.  O invasor está usando credenciais legítimas e pode acessar recursos legítimos e executar executáveis legítimos. 

A maioria dos departamentos de TI estariam cegos para esta atividade de pós-infiltração que está acontecendo em seu ambiente.  Microsoft ATA é capaz de detectar isso, conforme mostrado na imagem abaixo:

![Infiltração](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig30.png) 

Como você pode ver, Microsoft ATA detectou que os tíquetes de Nuck Chorris foram roubados do *PC ADMIN* e movidos para o *PC VÍTIMA*.  ATA também mostra quais recursos foram acessados usando os tíquetes roubados.  Você não apenas se tornou ciente do ataque, mas também obteve informações sobre onde começar a investigação. A imagem abaixo mostra também que ATA é capaz de ver os recursos acessados com o Pass-the-Ticket associado:

![Recursos](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig31.png) 

Essas informações são altamente importantes e devem ser focadas, como defensor de uma rede. O invasor acessou CIFS, usando o comando “dir \\dc1\c$”.  O invasor enviou uma solicitação LDAP para o local DC1, para fins de CIFS.  O [KRBTGT](https://technet.microsoft.com/library/dn745899%28v=ws.11%29.aspx) foi usado para se comunicar com DC1 e autenticar (um processo necessário para acessar a unidade c$ do DC) diretamente.  A partir disso, podemos, como os defensores, afirmar que a atividade de aprovação de tíquete levou ao acesso direto ao computador DC1.

Neste ponto, a maioria dos adversários tentará realizar uma execução remota de código em relação a um DC. Isso é essencial, porque ao fazer as modificações na própria camada de identidade pode ser extremamente difícil de detectar sua presença. Para simular isso, execute comandos remotos para adicionar um usuário no domínio e adicioná-los ao grupo de segurança dos *Administradores*, usando credenciais legítimas do NuckC.  Tudo isso pode ser feito usando as ferramentas internas, sem a necessidade de software mal-intencionado ou ferramentas de pesquisa.

No local em que o PsExec está localizado no *PC vítima*, execute os seguintes comandos:

    psexec \\dc1 -accepteula net user /add InsertedUser pa$$w0rd1
    psexec \\dc1 -accepteula net localgroup “Administrators” InsertedUser /add

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![psexec](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig32.png) 

O invasor acabou de criar uma conta de usuário e tornou a conta um *Administrador*. Você exerceu claramente os privilégios do *Admin. de domínio* que você tem agora, por meio de execução remota de código.  Não é só isso, você pode criar mais *Admins. de domínio*, remover admins. de domínio.  

Microsoft ATA detectou a execução remota no DC1 do *PC vítima*.  Na tela do exemplo abaixo, ATA está detectando as tentativas bem-sucedidas e com falha do adversário.

![execução remota](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig33.png) 

### <a name="domain-dominance"></a>Predominância de domínio

O invasor alcançou a dominância do domínio, ele pode executar qualquer código, como administrador e acessar qualquer recurso no domínio.
 
No entanto, para garantir a persistência de dominância do domínio, backdoors e outros mecanismos são colocados em prática, como apólices de seguro, caso o método original de ataques fosse descoberto ou uma credencial reiniciada aleatoriamente. Neste ponto, a suposição é que o invasor deseja criar o melhor backdoor no controlador de domínio, uma maneira de criar instantaneamente usuários privilegiados do *Admin*, esse método é conhecido como Skeleton Key. 

A próxima etapa é injetar o ataque Skeleton Key no DC1. Primeiro, você deve copiar *mimikatz* no DC. Observe que nessa fase é importante saber se o controlador de domínio é um computador de 32 bits ou 64 bits.  O exemplo usa um computador de 64 bits, modifique-a para as necessidades do seu ambiente específico.

    xcopy x64\mimikatz.exe \\dc1\c$\temp\

Em seguida, você usará *PsExec* para executá-lo remotamente e implantará Skeleton Key, usando o comando a seguir:

    PsExec \\dc1 -accepteula cmd /c (cd c:\temp ^& mimikatz.exe “privilege::debug” “misc::skeleton” ^& “exit”)

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![PSExec2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig34.png) 

O invasor "colocou um patch" no binário de LSASS.exe com o Skeleton Key.  Neste ponto, o invasor poder utilizar o Skeleton Key. Para simular isso, abra um prompt de comando como *JeffV*.  Primeiro, você validará que não há nenhum tíquete de outros usuários. Essa etapas são apenas para confirmar exatamente o que está acontecendo. Do *PC vítima*, como *JeffV*, execute o comando a seguir:

    klist

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![klist nucko](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig35.png) 

Conforme mostrado no exemplo acima, nenhum tíquete com privilégio alto está lá.  Isso significa que todos os comandos que o invasor executará somente deverão ter os privilégios que *JeffV* tem. Agora, você tentará autenticar o DC1, tentando mapear o C$ de DC1.  Você usará uma senha incorreta, de propósito, para ilustrar que nem toda senha funcionará. No mesmo prompt de comando limpo, execute o comando a seguir:

    net use k: \\dc1\c$ wrongpassword /user:Administrator@contoso.local

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![net use](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig36.png) 

Conforme mostrado no exemplo, esse comando falhou, como esperado.  Mas é nesse momento que Skeleton Key será usado. Você testará o mesmo comando novamente, mas agora com a Chave Mestre, que você acabou de adicionar a cada conta autenticada no DC1, em que injetou a Skeleton Key. No prompt de comando, execute o comando a seguir, mas desta vez usando a chave mestra "mimikatz":

    net use k: \\dc1\c$ mimikatz /user:Administrator@contoso.local

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![net use 2](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig37.png) 

Com a chave mestra, "mimikatz" (codificada), o invasor poderá obter privilégios de administrador.  Essa chave não é a senha da conta, uma maneira de atingir o DC1, usando o processo de patch e autenticar qualquer usuário como administrador (ou qualquer outro grupo de segurança). Observe que há 2 senhas ativas para cada conta agora:

- A senha de usuário/admin criada e original.
- Uma Skeleton Key mestre  

Microsoft ATA será capaz de detectar essa atividade, conforme mostrado no exemplo a seguir:

![Skeleton key](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig38.png) 

Até agora, tudo o que o invasor fez no controlador de domínio requereu a execução de códigos arbitrários no DC.  ATA detectou essas ações aumentando o respectivo sinalizador de atividade suspeita, bem como fornecer informações para remedição ao defensor da rede. No entanto, um invasor talvez queira continuar a invasão executando mais ataques ocultos, um que não execute código arbitrário no DC (sem *PsExec* ou injetando a Skeleton Key no processo LSASS diretamente).
*Mimikatz*, a ferramenta de pesquisa de escolha nessa área, tem uma funcionalidade chamada "DC Sync".  Isso permite que o invasor, com credenciais de administrador de domínio, replique qualquer credencial para eles, como se fosse um DC.

Abra o prompt de comando que tenha as credenciais *do NuckC*, vá para o prompt de comando e certifique-se de que o tíquete do NuckC ainda está injetado na sessão, conforme mostrado no exemplo a seguir:

![tíquete](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig39.png) 

Agora que você sabe que está trabalhando no console do correto, você pode emular o invasor e tentar obter as credenciais máximas do domínio: o [KRBTGT](https://technet.microsoft.com/library/dn745899.aspx#Sec_KRBTGT).  O motivo por que você precisa usar essa conta, é porque com essa conta, você pode assinar suas próprias permissões.

No prompt de comando validado de *NuckC* no *PC vítima*, vá até onde mimikatz está localizado no sistema de arquivos e execute o seguinte comando:

    mimikatz.exe “lsadump::dcsync /domain:contoso.local /user:krbtgt “exit” >> krbtgt-export.txt

Um exemplo de como o resultado desse comando é mostrado na imagem a seguir:

![lsadump](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig40.png) 

Depois que o invasor abre o "krbtgt-export.txt", ele terá os detalhes de KRBTGT necessários.  Abra o arquivo “krbtgt export.txt" para o qual você acabou de exportar o hash, conforme mostrado no exemplo a seguir:

![KRBTGT](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig41.png) 

Neste ponto, o invasor tem tudo de que precisa para assinar qualquer TGT, para qualquer recurso, usando o hash NTLM roubado, sem nunca voltar para o DC.  Com isso, o invasor pode se tornar qualquer pessoa, a qualquer momento que ele então desejar (até que a própria conta de KRBTGT seja reiniciada, duas vezes).

Microsoft ATA é capaz de identificar esse tipo de ataque, conforme mostrado no exemplo a seguir:

![Ataque](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig42.png) 

Microsoft ATA não apenas detectou o ataque, mas também forneceu as informações necessárias para executar as ações corretivas.

Usar o KRBTGT para assinar tíquetes falsos é conhecido como um ataque de tíquete dourado, que também é detectado pelo ATA.  No entanto, para fins de escopo e detecções baseada em assinatura, está fora do escopo deste guia.

## <a name="conclusion"></a>Conclusão

Microsoft ATA fornece informações e ideias em defesa de rede, que não estão disponíveis em outro lugar.  Microsoft ATA transforma o plano de identidade em uma ferramenta de detecção poderosa que descobre atividades pós-infiltração em seu ambiente.  Microsoft ATA ajuda você a digerir eventos macro e transformá-los rapidamente em histórias coesas de ataque.

![Conclusão](./media/ata-attack-simulation-playbook/ata-attack-simulation-playbook-fig43.png) 

Microsoft ATA fornece as informações necessárias e a inteligência para o mundo "de supor uma violação", em que descobrir atividades pós-infiltração é obrigatório.  Firewalls, mecanismos antivírus, serviços de detecção de intrusão e serviços de prevenção de intrusão, todos tentam manter a pessoa mal-intencionada fora do ambiente, mas ficam mais ou menos cegos depois que a pessoa mal-intencionada entra no ambiente, quando ferramentas com credenciais legítimas são usadas maliciosamente.  No mundo de segurança cibernética, é crucial entender essas atividades mal-intencionadas. 

Para obter mais informações sobre Microsoft ATA, visite a página de [Microsoft ATA](https://www.microsoft.com/cloud-platform/advanced-threat-analytics) ou envie um email para ataeval@microsoft.com.




