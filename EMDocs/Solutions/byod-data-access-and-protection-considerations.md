---
# required metadata

title: Considerações de acesso e proteção de dados
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 181eb917-119d-4e56-8ead-1182b1dc5cab

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Considerações de acesso e proteção de dados

Perda de dados confidenciais é um risco de operação para qualquer empresa e, com o surgimento de BYOD, as informações residem em mais locais do que nunca. Isso resulta em um cenário de mias ameaças e mais riscos que devem ser reduzidos corretamente. Devido a uma variedade de regulamentos legislativos, corporativos e do setor que controlam a proteção de dados confidenciais, a proteção de dados pode ser um processo complexo. É importante levar esses requisitos legais, políticas corporativas internas e regulamentos do setor em conta.
Como parte da estratégia de infraestrutura de BYOD, é essencial que, depois que as políticas e classificações de dados tiverem sido definidas, os dados sejam fisicamente localizados, colocados em níveis de classificação adequados e tenham as configurações de segurança apropriadas. A TI precisa de uma maneira de validar as identidades dos usuários e pode desejar aplicar condições adicionais sobre os tipos de dispositivos que podem acessar as informações e os aplicativos fornecidos pela empresa.

## Armazenamento

Como os dados serão armazenados em dispositivos dos usuários pode afetar diretamente como você escolhe abordar o acesso e a proteção de dados para BYOD. A criptografia de dados deve ser considerada e os dispositivos devem permitir à TI controlar quando a criptografia de dados é ativada e para quais tipos de dados. As empresas devem examinar suas políticas e regulamentos para entender quais tipos de dados podem sair do datacenter e ficar em repouso no armazenamento de dispositivos remotos. Criptografia de dados em repouso no armazenamento do datacenter é fundamental. Se a sua empresa ainda não estiver executando essa tarefa, ela deve ser considerada como parte da estratégia de uma infraestrutura de BYOD. Idealmente, os dados devem ser criptografados em todo o caminho.

Com o Windows Server 2012 R2, é possível criptografar os dados em repouso nos dispositivos dos usuários usando Pastas de Trabalho. Os administradores de TI podem usar as pastas de trabalho para obter mais controle sobre dados corporativos e dispositivos dos usuários e centralizar dados de trabalho para que eles possam ser aplicados a processos e ferramentas apropriados para manter a conformidade da empresa. Isso pode variar de simplesmente ter uma cópia dos dados se o usuário sair da empresa até uma ampla variedade de recursos, como backup, retenção, classificação e criptografia automatizada. Se você decidir usar [Pastas de Trabalho](https://technet.microsoft.com/library/dn265974.aspx), certifique-se de que os servidores que hospedam os compartilhamentos de sincronização sejam bem planejados da perspectiva do desempenho. Leia [Considerações sobre desempenho para implantações de Pastas de Trabalho](http://blogs.technet.com/b/filecab/archive/2013/11/01/performance-considerations-for-large-scale-work-folders-deployments.aspx) para saber mais.

Se você pensar no armazenamento como um recipiente de conteúdo, é possível obter um ótimo valor ao proteger o consumo desse conteúdo. Vazamento de dados pode ser evitado através da aplicação de diretivas que afetam como o conteúdo que reside no armazenamento que será usado pelo usuário final. O [AD RMS (Active Directory Rights Management Services)](https://technet.microsoft.com/library/hh831554.aspx) pode ser usado para ampliar a estratégia de segurança para sua organização protegendo documentos que usem IRM (Gerenciamento de Direitos de Informação). O AD RMS permite que indivíduos e administradores especifiquem, por meio de políticas de IRM, permissões de acesso a documentos, pastas de trabalho e apresentações. Isso ajuda a evitar que informações confidenciais sejam impressas, encaminhadas ou copiadas por pessoas não autorizadas. Depois que a permissão para um arquivo for restrita usando o IRM, as restrições de acesso e uso são aplicadas, independentemente de onde as informações estão, porque a permissão para um arquivo é armazenada no arquivo em si.

Se sua empresa quiser usar uma solução baseada em nuvem para proteção de arquivos, também será possível usar o [Azure Rights Management](https://technet.microsoft.com/en-us/library/jj585026.aspx). O Azure Rights Management pode proteger as informações confidenciais da empresa usando criptografia, identidade e políticas de autorização, a fim de ajudar a proteger arquivos e emails, e funciona em vários dispositivos — PCs, tablets e telefones. As informações podem ser protegidas tanto em sua organização quanto fora dela, pois essa proteção permanece com os dados, mesmo quando eles saem dos limites da organização. 

Outras tecnologias de armazenamento disponíveis no sistema operacional Windows também podem ser usadas para melhorar a proteção geral dos dados, como o BitLocker para criptografia de unidade e o [EFS (Encrypting File System)](https://technet.microsoft.com/library/cc700811.aspx) para criptografia de arquivo. Use a tabela a seguir para ver as vantagens e desvantagens da proteção de armazenamento. Tenha em mente que essas opções não se excluem mutuamente. Em outras palavras, a decisão de design pode concluir que você precisa de todas essas opções em sua solução de infraestrutura BYOD para proteção de armazenamento.

### Opções de proteção de armazenamento — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens de cada opção de proteção de armazenamento:

- EFS (Encrypting File System, sistema de arquivos com criptografia)
    - Vantagens
        - Fornece criptografia no nível do arquivo
        - O processo de criptografia é transparente para os usuários, pois a criptografia não ocorre no nível do aplicativo (ocorre no nível do sistema de arquivos).
        - Oferece recursos de backup com um agente de recuperação de chave
        - Disponível em todas as versões com suporte do sistema operacional Windows
        - Pode ser habilitado usando a Política de Grupo.
        - Em conformidade com os requisitos de criptografia do Suite B definidos pela Agência de Segurança Nacional para atender às necessidades dos órgãos do governo dos Estados Unidos para proteção de informações confidenciais
    - Desvantagens
        - Se o proprietário de dados não estiver disponível e você não tiver o agente de recuperação de chave, não será possível descriptografar um arquivo EFS
        - Gerenciamento de certificado deve estar estabelecido para gerenciar as chaves privadas associadas à recuperação de certificados
        - Não está disponível em outras plataformas que não sejam Windows
- BitLocker
    - Vantagens
        - Fornece o recurso de criptografia de unidade
        - Fornece integridade e verificação do sistema aproveitando o TPM (Trusted Platform Module)
        - Aumenta a proteção para minimizar ataques offline baseados em software
        - Fornece um método para verificar se a integridade inicial do arquivo de inicialização foi mantida
    - Desvantagens
        - Não está disponível em todas as versões do Windows
        - Exige o TPM versão 1.2
        - Exige que o BIOS do sistema (para computadores TPM e não TPM) deem suporte à classe de dispositivo de armazenamento em massa USB
        - Não disponível para clusters anteriores ao Windows Server 2012
- Pastas de trabalho
    - Vantagens
        - Aproveita o EFS para criptografia de arquivos.
        - Permite que a TI criptografe os dados em repouso em dispositivos dos usuários
        - Pode ser habilitado por meio da Política de Grupo por usuário ou por dispositivo
        - Integração com o Microsoft Intune, que permite apagar seletivamente dados localizados em Pastas de Trabalho nos dispositivos dos usuários
        - Pode forçar os usuários a autenticar novamente para que possam acessar dados localizados em Pastas de Trabalho
        - Permite a integração com o serviços do Microsoft Rights Management para classificação de dados
    - Desvantagens
        - Disponível somente para Windows 8.1, Windows RT 8.1 e Windows 10.
        - Exige o Windows Server 2012 R2 para hospedar compartilhamentos de sincronização
- Active Directory Rights Management Services (AD RMS)
    - Vantagens
        - Impedir que um destinatário autorizado de conteúdo restrito encaminhe, copie, modifique, imprima, envie por fax ou cole o conteúdo para uso não autorizado
        - Oferece suporte à expiração de arquivo de modo que o conteúdo de documentos não possa mais ser visualizado após um período de tempo especificado
        - Impedir que o conteúdo restrito seja copiado usando o recurso Print Screen do Microsoft Windows
    - Desvantagem
        - Requer a implantação de uma nova função de servidor (AD RMS)
        - Não restringe a cópia do conteúdo usando programas de captura de tela de terceiros
        - Não impede que o conteúdo seja perdido ou corrompido devido às ações de vírus do computador

## Rede

É essencial considerar os fatores envolvidos em permitir que os usuários usem seus dispositivos e que os dados sejam protegidos em todo o caminho entre o datacenter (local) ou nuvem e os dispositivos dos usuários. Esses fatores são destacados na figura abaixo:

![Diagrama de rede](./media/BYOD_Figure6.png)

O diagrama destaca as áreas cruciais nas quais a proteção de dados deve ser considerada para uma infraestrutura de BYOD. Essas áreas são descritas com mais detalhes na seção a seguir.

### Proteção de dados — locais e considerações
    
Use a lista abaixo para entender as considerações sobre proteção de dados de acordo com o local dos dados. Os números na lista a seguir correspondem ao diagrama anterior:

- (1) Dados em repouso no data center
    - Criptografia de armazenamento: considere uma solução de armazenamento que oferece suporte à criptografia
    - Gerenciamento de chaves: a chave usada para criptografar o armazenamento deve ter um backup e um agente de recuperação de chave deve estar disponível, caso necessário
- (2) Dados em trânsito do datacenter para a borda da rede corporativa
    - Criptografia de rede: considere usar um protocolo padrão da web para a criptografia, como SSL
    - Infraestrutura de chave pública (PKI): se sua empresa tiver uma PKI, você pode usá-la para criptografar o canal de comunicação
- (3) Dados em trânsito da borda da rede corporativa para dispositivos dos usuários
    - Criptografia de rede: considere usar um protocolo padrão da web para a criptografia, como SSL
    - PKI: como esse canal será acessado por usuários usando seus dispositivos pessoais, considere usar um certificado público, que provavelmente já terá a confiança dos dispositivos dos usuários
- (3.1) Dados em trânsito da borda da rede corporativa para o provedor de serviço de nuvem (opcional — aplica-se apenas se a sua empresa estiver usando serviços em nuvem para BYOD)
    - Criptografia de rede: considere usar um protocolo padrão da web para a criptografia, como SSL.
    - PKI: uma vez que esse canal será acessado por usuários usando seus dispositivos pessoais, considere usar um certificado público, que provavelmente já terá a confiança dos dispositivos dos usuários
    - VPN de site para site: se você tiver uma [infraestrutura de nuvem híbrida](http://blogs.technet.com/b/cloudsolutions/archive/2013/08/22/hybrid-it-infrastructure-solution-for-enterprise-it-overview.aspx) conectada a Serviços de Nuvem, considere usar a VPN site a site para manter o canal seguro disponível para uso por aplicativos localizados em dispositivos dos usuários
- (3.2) Dados em repouso no datacenter do provedor de serviço de nuvem (opcional — aplica-se apenas se a empresa estiver usando serviços em nuvem para BYOD)
    - Provedor de serviço de nuvem: considere as opções que o provedor de serviços de nuvem pode oferecer para criptografar os dados em repouso
    - Gerenciamento de chaves: verifique com o provedor de serviço de nuvem como o gerenciamento de chaves é tratado e como ocorre o processo de backup. Além disso, considere integração entre serviços de nuvem com um sistema de gerenciamento de chaves local
(4) Dados em repouso em dispositivos dos usuários
    - Criptografia de armazenamento: considere uma solução de armazenamento que oferece suporte à criptografia
    - Gerenciamento de chaves: a chave usada para criptografar o armazenamento deve ter um backup e um agente de recuperação de chave deve estar disponível, caso necessário
    - Limpeza remota: os dados que residem em dispositivos dos usuários podem ser excluídos remotamente, caso necessário

O Windows Server 2012 R2 permite o uso de [HTTPS](https://msdn.microsoft.com/library/aa767735.aspx) para publicar recursos por meio do [Proxy de aplicativo Web](https://technet.microsoft.com/library/dn280944.aspx) a fim de proteger dados em trânsito pela rede. A comunicação entre servidores back-end também poderá ser criptografada usando [IPsec](https://technet.microsoft.com/library/cc757613.aspx) ou [Criptografia SMB](http://support.microsoft.com/kb/2709568) se o tráfego de rede for totalmente baseado no [protocolo SMB](https://technet.microsoft.com/library/hh831795.aspx). Use a tabela a seguir para avaliar a opção de proteção de rede que melhor atende às suas necessidades de design para comunicação de servidor back-end.

Use a próxima seção para avaliar a opção de proteção de rede que melhor atende às suas necessidades de design para comunicação de servidor back-end.

### Opções de proteção de rede — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens de cada opção de proteção de rede:

- SSL
    - Vantagem
        - Ampla variedade de suporte de muitos dispositivos
        - Autenticação forte, privacidade de mensagens e integridade
        - Interoperabilidade
    - Desvantagem
        - Exige uma infraestrutura de certificado, a menos que você use certificados SSL públicos
- IPsec
    - Vantagens
        - Fornece criptografia de todo o datagrama IP
        - Fornece autenticação de computador
        - Amplamente compatível com muitas plataformas e disponível em todas as versões com suporte do Windows
        - Autenticação do protocolo IKE para limitar o acesso à rede a computadores confiáveis
    - Desvantagens
        - Exige uma infraestrutura de certificado, a menos que você use uma chave pré-compartilhada
        - IPsec ocorre em nível de host, assim, não pode ser controlado no nível do aplicativo
        - Difíceis de solucionar
- Criptografia SMB
    - Vantagens
        - Criptografa os dados em trânsito usando o protocolo SMB
        - Fácil de implementar na interface do usuário e por meio do Windows PowerShell
        - Flexível porque pode ser implementado por servidor ou por compartilhamento
    - Desvantagem
        - Funciona apenas para o Windows 8 e posteriores para computadores cliente e Windows Server 2012 e posteriores para computadores de servidor

## Diretório

Atributos de usuário devem ser armazenados no diretório, permitindo à TI facilmente consultar informações do usuário, como funções e grupos. Você também deve considerar como a relação entre usuários e dispositivos será controlada. Cada dispositivo desconhecido que se torne conhecido ou gerenciável pela TI também deve ter um registro no banco de dados de gerenciamento ou no diretório que permita à TI auditar o dispositivo.

Em ambientes híbridos em que haverá diferentes repositórios de autenticação, as empresas devem considerar como habilitar usuários a autenticar usando a mesma credencial, independentemente de onde eles e os aplicativos estejam localizados. Considere usar os Serviços de Federação do Active Directory (AD FS) se desejar centralizar a autenticação local, em vez de replicar a pasta com o provedor de serviço de nuvem Use a próxima seção para avaliar as opções de diretório para uma infraestrutura BYOD.

### Opções de diretório — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens de cada opção de proteção de diretório:

- Centralizado local
    - Vantagem
        - Todos os controles de segurança estão localizado fisicamente local, e a TI tem controle total
        - A TI pode executar a proteção do servidor que contém a função de diretório
        - Recursos mais avançados de auditoria e registro
    - Desvantagem
        - Custo de manutenção mais alto quando comparado aos serviços de nuvem
        - Falta de integração com serviços de nuvem
- Centralizado na nuvem
    - Vantagens
        - Menor custo de manutenção quando comparado a uma solução local
        - Mais fácil de gerenciar em relação a uma solução local
    - Desvantagens
        - Falta de personalização
        - Depende do provedor de serviço de nuvem para obter dados de auditoria e log
- Sincronização de diretórios entre local e nuvem
    - Vantagens
        - Diretório integrado local e na nuvem
        - Habilita logon único para os usuários
        - A TI ainda poderá realizar a proteção do servidor que contém a função de diretório local
        - Experiência de logon perfeita para os usuários
    - Desvantagens
        - Requer sincronização de hash de senha
        - Requer um serviço de assinatura
- Federado entre local e a nuvem
    - Vantagens
        - Diretório integrado local e na nuvem.
        - Habilita logon único para os usuários.
        - A TI ainda poderá realizar a proteção do servidor que contém a função de diretório local.
        - Experiência de logon perfeita para os usuários.
        - Mais robusta para soluções que precisam de integração com outros serviços de diretório.
        -Requer sincronização, mas não sincroniza senhas.
    - Desvantagens
        - Requer um serviço de assinatura.
        - Exige uma infraestrutura de servidor de federação.
        - Exige o certificado para proteger a comunicação entre o servidor de federação e o serviço de nuvem.

Ambientes híbridos que exigem que os usuários tenham conectividade com serviços de nuvem em seus próprios dispositivos podem aproveitar a integração entre o [Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-whatis/) e os AD DS (Serviços de Domínio do Active Directory). Em um [cenário de identidade híbrida](https://technet.microsoft.com/library/dn550987.aspx), as empresas que desejam preservar a autenticação de usuário perfeita podem escolher as seguintes opções:

- Sincronização de diretórios com sincronização de senha: usando o DirSync com [sincronização de hash de senha](https://technet.microsoft.com/library/dn246918.aspx) entre o AD DS e o Azure AD.
- Autenticação federada com logon único: atributos de usuário são sincronizados usando o DirSync. A autenticação é enviada através de federação (AD FS) e concluída no AD DS

Ao usar o Serviço de Registro de Dispositivo no Windows 8.1, um certificado é instalado em um dispositivo do usuário e um registro de dispositivo é criado no AD DS com o número de impressão digital do certificado. Esse link entre o dispositivo e o usuário permite que a TI controle os dispositivos que estão sendo registrados por cada usuário. Esse recurso não exige uma PKI corporativa. O registro de dispositivos também está disponível no Azure AD para Windows 10. Leia [Introdução ao registro de dispositivo do Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-device-registration-overview/) para obter mais informações sobre o Registro do dispositivo usando o Azure AD e Windows 10.

## Autenticação e autorização

A decisão de permitir que os usuários acessem aplicativos e dados em seus dispositivos deve garantir que os usuários sejam identificados em um processo de autenticação confiável e também que os usuários estejam autorizados a usar os recursos solicitados. As empresas devem analisar suas políticas de autenticação e autorização atuais e considerar as perguntas a seguir:

- Quais são os requisitos de autenticação para os usuários poderem acessar remotamente os aplicativos da empresa de seus dispositivos?
- A plataforma atual é capaz de implantar a autorização por usuário e por aplicativo sem reescrever os aplicativos?
- É possível impor a Multi-Factor Authentication de acordo com o local do usuário?

Autenticação e autorização são tratadas pelo AD FS em conexão com AD DS. Os dados em trânsito no datacenter também usarão o protocolo HTTPS ao se conectarem com a função de servidor de arquivos e serviços de autenticação.

Para impor enforce Multi-Factor Authentication, as empresas podem usar os recursos internos no AD FS ou usar [MFA (Azure Multi-Factor Authentication)](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication/). Aproveitando essa funcionalidade no Azure, a TI pode impor autenticação multifator a usuários que acessam os recursos da empresa na Internet. Para saber mais sobre a autenticação multifator, confira [Gerenciar riscos com a Multi-Factor Authentication adicional para aplicativos confidenciais](https://technet.microsoft.com/library/dn280949.aspx).

Para implantar a autorização por aplicativo aos usuários que acessem aplicativos de uma rede interna ou externa, a TI pode aproveitar o Proxy de aplicativo Web. Usando o Proxy de aplicativo Web, a TI pode criar regras específicas para impor a autenticação e autorização em conjunto com o AD FS. A publicação de Proxy de aplicativo Web funciona para qualquer dispositivo do usuário. É possível usar laptops, tablets ou smartphones pessoais. Além disso, os usuários não precisarão instalar software adicional em seus dispositivos para acessarem aplicativos publicados. O Proxy de aplicativo Web funciona como um proxy reverso para todos os aplicativos publicados por meio dele, e como tal, a experiência do usuário é a mesmo de dispositivos dos usuários conectados diretamente aos aplicativos. Para saber mais sobre Proxy de Aplicativo Web, confira [Visão geral de Proxy de Aplicativo Web](https://technet.microsoft.com/library/dn280944.aspx).

>[!NOTE] Se você tiver um cenário híbrido e precisar ter uma experiência tranquila de autenticação e autorização do usuário, leia o [Guia de considerações de design de identidade híbrida](http://aka.ms/azhidcg).

## Política e conformidade

Considerações de conformidade e de política devem ser uma prioridade de qualquer estratégia que adote BYOD. Algumas empresas podem ter requisitos de disco rígido que não se ajustem a esse modelo devido a normas de negócios. Uma empresa que esteja migrando para uma estratégia centrada em pessoas deve entender diretivas atuais e como essas diretivas serão afetadas pela adoção de BYOD. Considere os requisitos de classificação de dados e como a TI pode ter controle da classificação de dados, mesmo quando os dados estão em repouso no armazenamento de dispositivo. Ao pensar na classificação de dados, é importante poder classificar os dados enquanto algumas operações (como editar um arquivo) estão ocorrendo.

As políticas devem ser impostas em um local centralizado para habilitar a TI a responder rapidamente no caso de alterações ad hoc que afetem todos os usuários. Além disso, considere recursos de auditoria robustos para dispositivos móveis. Se ocorrer uma falha, é essencial que a TI possa controlar qual política foi infringida, quem a infringiu e quando isso ocorreu.
    
### Política e conformidade — recursos e considerações

Use a lista a seguir para entender as considerações de política e recursos de conformidade:

- Classificação de dados
    - Aplique a classificação de dados conforme o conteúdo é salvo e alterado.
    - A TI deve ser capaz de classificar os dados em repouso no datacenter e no dispositivo dos usuários
- Gerenciamento centralizado
    - A TI deve ser capaz de gerenciar a classificação de dados de um único local, mesmo que os dados estejam localizados em vários dispositivos
    - Ambientes de TI híbridos devem ser capazes de gerenciar recursos localizados locais e na nuvem
- Integração com serviços de diretório
    - A TI deve ser capaz de aproveitar seu serviço de diretório atual como o repositório de identidade
- Log e auditoria
    - A TI deve ser capaz de realizar auditoria de acesso a recursos e aumentar a capacidade de registro em log, quando necessário.


A aplicação de dados governança em servidores de arquivos para controlar quem pode acessar informações e auditar quem acessou as informações é essencial para BYOD. No Windows Server 2012 R2, isso pode ser realizado usando o [Controle de Acesso Dinâmico](https://technet.microsoft.com/library/dn408191.aspx), que tem base nos investimentos de infraestrutura que podem ser usados por parceiros e aplicativos de linha de negócios. Os recursos de Controle de Acesso Dinâmico podem proporcionar excelente valor para organizações que usem os Serviços de Domínio Active Directory.

Ao aproveitar os recursos de Controle de Acesso Dinâmico, você pode identificar dados usando classificação automática e manual dos arquivos. Por exemplo, você pode marcar os dados nos servidores de arquivos em toda a organização. Também é possível controlar o acesso a arquivos aplicando políticas de rede de segurança que usem políticas de acesso centrais. O Controle de Acesso Dinâmico também aproveita a proteção RMS (Rights Management Services, serviços de gerenciamento de direitos) usando criptografia RMS automática para documentos confidenciais. Por exemplo, você pode configurar o RMS para criptografar todos os documentos que contenham informações sobre HIPAA (Health Insurance Portability e Accountability Act, lei de portabilidade e responsabilidade de plano de saúde). Para investigação forense e auditoria, você pode aproveitar as políticas de auditoria centrais para relatórios de conformidade e análise forense. Você pode identificar quem acessou informações altamente confidenciais.

O Controle de Acesso Dinâmico, uma função de servidor de arquivos, habilita à TI os recursos mostrados na tabela anterior. Para saber mais sobre o Controle de Acesso Dinâmico, confira [Controle de Acesso Dinâmico: visão geral de cenários](https://technet.microsoft.com/library/hh831717.aspx).


<!--HONumber=Apr16_HO4-->


