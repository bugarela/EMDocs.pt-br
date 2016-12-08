---
title: "Considerações sobre aplicativo"
description: "Este artigo fornece um conjunto de considerações de design para aplicativos que devem ser usadas em um cenário Traga seu próprio dispositivo."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 4b871c74-fec8-45e2-8b45-6ef0e62f7cc6
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 2e00204f4be8183fdb8502e13b1ef06d1b7df084


---


# <a name="app-considerations"></a>Considerações sobre aplicativo

Considerações sobre aplicativo para BYOD podem variar de acordo com recursos, restrições e metas da empresa. As empresas devem avaliar seus aplicativos atuais, as tecnologias usados para desenvolver aplicativos, os requisitos para os aplicativos executados em qualquer dispositivo e quais aplicativos é essencial que os usuários possam acessar de qualquer local. Embora os aplicativos modernos não usem recursos de modo tão intensivo quanto os aplicativos baseados em Windows para fins de provisionamento e implantação, ainda há um custo associado ao seu desenvolvimento e manutenção.

Há padrões para aplicativos desenvolvidos especificamente para cenários BYOD, e você deve avaliar se seus aplicativos atuais têm esses padrões e decidir se adaptará esses aplicativos a um cenário BYOD ou fornecerá uma experiência herdada para que os usuários acessem-nos em seus dispositivos. Você pode usar a lista a seguir para identificar esses padrões:

- Entender o usuário: qual problema você está tentando resolver com este aplicativo? O problema é relevantes para o usuário? A experiência do usuário com o aplicativo e o que usuários obterão usando o aplicativo são considerações importantes.
- Simplicidade: os usuários devem se sentir confortáveis ao aprender a usar aplicativos de forma independente e com orientação mínima. Os usuários devem poder percorrer as opções sem se perder.
- Agilidade para atualizar: a estratégia para aplicativos móveis é fornecer aos usuários a possibilidade de usá-los imediatamente e fornecer comentários para aperfeiçoar os aplicativos. Enviar um aplicativo perfeito na primeira versão não é viável para aplicativos móveis. Você deve tornar o ciclo de liberação mais ágil e responder rapidamente aos comentários. Forneça agora e faça alterações contínuas em todo o ciclo de vida do aplicativo.
- Desempenho: embora aplicativos tradicionais baseados no Windows possam ser mais robustos por serem executados em PCs, os usuários tendem a pressupor que aplicativos baseados em Windows usam mais recursos. Aplicativos móveis devem ser criados para economizar recursos. Você deve se concentrar no que precisa disponibilizar ao usuário para oferecer a melhor experiência de usuário possível.

Para saber mais sobre as considerações gerais ao criar aplicativos móveis, leia [10 considerações ao criar aplicativos móveis para negócios](https://www.microsoft.com/en-gb/developers/articles/week01jan14/10-considerations-when-creating-mobile-apps-for-business).

## <a name="experience"></a>Experiência

Para fornecer uma melhor experiência do usuário com base na plataforma em que os aplicativos serão executados e na estratégia de implantação, a empresa deve identificar quais aplicativos deve ser publicados e como. Se for identificado que há um ambiente heterogêneo e alguns dispositivos receberão suporte da empresa, uma estratégia seria publicar aplicativos através do portal da empresa. Por fim, decisões de negócios conduzirão as considerações para a experiência do usuário. A empresa está disposta a desenvolver aplicativos que forneçam a mesma experiência independentemente da plataforma? Ou a empresa fornecerá treinamento aos usuários para usar esses aplicativos em plataformas diferentes sem ter a mesma experiência?
Considere o custo e o retorno sobre o investimento para cada caso mencionado no parágrafo anterior. Pode ser viável consolidar todos os aplicativos em uma página de portal da web principal que forneça a mesma experiência, mas os aplicativos se comportem de modo diferente de acordo com a plataforma.

Considerando que aplicativos para usuários remotos devem executar em mais de uma plataforma, ser o mais leve possível e exigir acesso mínimo a dispositivos dos usuários, você deve restringir suas opções a aplicativos baseados na web e aplicativos modernos. A seção ajudará você a determinar qual experiência de aplicativo deve ser usada para sua solução.

### <a name="app-experience-options-advantages-and-disadvantages"></a>Opções de experiência de aplicativo — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens de cada opção de experiência no aplicativo:

- Baseado na Web
    - Vantagens
        - Amplamente disponíveis em muitas plataformas
        - Criptografia disponível usando o protocolo HTTPS
        - Tecnologia desenvolvida
        - Fácil de usar
        - Não precisa ser instalado em dispositivos dos usuários
    - Desvantagens
        - Não tem a aparência nativa de um aplicativo móvel
        - Pode exigir componentes de terceiros (por exemplo, Flash) a serem instalados em dispositivos dos usuários
        - Suscetível a vulnerabilidades do navegador
- Moderno
    - Vantagens
        - Aparência moderna
            - Experiência mais rica para os usuários finais
            - Controles de segurança estabelecidos pelo desenvolvedor
            - Utiliza APIs do sistema operacional local
            - Pode ser executado em plataformas diferentes
            - Não depende do navegador da Web para ser executado
    - Desvantagens
        - Requer a instalação de dispositivos dos usuários.
        - Exige uma infraestrutura de back-end para implantar os aplicativos nos dispositivos dos usuários.
        - Pode exigir que os desenvolvedores aumentam seu conhecimento para desenvolver aplicativos usando esse novo formato.


### <a name="app-requirements-considerations"></a>Requisitos do aplicativo — considerações

Avalie os aplicativos que serão ajustados para serem usados por usuários remotos em seus dispositivos e certifique-se de que esses requisitos sejam apresentados aos usuários. Veja abaixo uma lista de requisitos de aplicativo e considerações sobre cada requisito:

- **Acesso à Internet/acesso ao serviço de nuvem** Se os aplicativos exigirem acesso à Internet para funcionar, considere os seguintes pontos:
    - Os aplicativos devem ser capazes de transferir os dados criptografados.
    - Os aplicativos devem consumir largura de banda mínima.
    - Avalie a possibilidade de usar os Serviços de Notificação por Push do Windows para atualizações.
    - Os aplicativos devem ser capazes de interagir com um servidor proxy, caso a empresa use esse tipo de tecnologia para permitir o acesso à Internet.
    - Os aplicativos devem ser capazes de usar conexão Wi-Fi com os dispositivos móveis.
- **Coletar informações do usuário** Se os aplicativos exigirem coleta de informações dos usuários para funcionar, considere os seguintes pontos:
    - Os aplicativos devem indicar detalhadamente quais informações serão coletadas dos usuários e os usuários devem concordar com essa coleta.
    - Se informações particulares forem ser transferidos, certifique-se de que os dados estejam criptografados.
    - Se informações particulares forem ser armazenadas em dispositivos dos usuários, certifique-se de que os dados estejam criptografados.
- **Integração com redes sociais** Se os aplicativos exigirem integração com redes sociais para serem executados, considere os seguintes pontos:
    - Avalie o método de autenticação que será usado para habilitar a autenticação de aplicativos com redes sociais.
    - Verifique o nível de integração com redes sociais para evitar a vazamento de dados para um público mais amplo.
    - Garanta que o aplicativo informe em detalhes quais informações serão compartilhadas pelo usuário na rede social em questão.
    - Certifique-se de que os dados enviados para o provedor de rede social estejam criptografados.

Para melhorar a experiência do usuário, você também deve classificar todos os aplicativos de acordo com os padrões da equipe de desenvolvimento para reduzir a necessidade de os usuários percorrerem centenas de aplicativos.

## <a name="platform"></a>Plataforma

Ao lidar com a experiência do usuário, é normal avaliar plataformas diferentes e determinar a qual sua empresa deseja dar suporte. Muitas vezes, permitir que os usuários usem seus próprios dispositivos significa ter um ecossistema heterogêneo, e a TI talvez não esteja pronta para dar suporte a um ecossistema assim.

Cada plataforma tem diferentes requisitos de assinatura e publicação de aplicativos, o que afeta diretamente os recursos de TI, pois a TI precisa avaliar todo o ciclo de vida para os aplicativos executados em uma plataforma específica. Você também precisará acessar os requisitos de plataforma de aplicativos para uma solução de infraestrutura BYOD. A seção a seguir inclui considerações importantes sobre requisitos de plataforma do aplicativo.

### <a name="app-platform-requirements-considerations"></a>Requisitos da plataforma do aplicativo — considerações

Veja abaixo uma lista de requisitos de plataforma do aplicativo e considerações sobre cada requisito:

- Infraestrutura de back-end
    - Avalie se estender aplicativos para uso por usuários remotos afetará o desempenho geral do servidor de aplicativo.
    - Com base nessa avaliação, verifique a necessidade de atualizar servidores, aumentar o número de servidores ou virtualizar servidores.
- Capacidade de suporte
    - Defina quais plataformas (como Windows, iOS e Android) terão suporte pela empresa.
        - Se a empresa decidir adotar todas as plataformas, defina os limites de suporte para cada plataforma.
    - Estabeleça os cenários que terão ou não suporte pela empresa. Por exemplo: sua empresa pode decidir não oferecer suporte a dispositivos que foram desbloqueados.
- Plataforma de sistema operacional
    - Defina as restrições de cada sistema operacional para executar os aplicativos da empresa.
    - Defina os requisitos mínimos para aplicativos em cada sistema operacional ao qual a empresa decidir dar suporte.
    - Teste os aplicativos em cada sistema operacional para verificar se eles têm comportamento semelhante em cada. Documente as diferenças.

Como parte da estratégia para dar suporte a várias plataformas, você deve definir como os aplicativos serão consumidos nessas plataformas. Usando o Microsoft Intune, você pode habilitar os usuários a consumir aplicativos usando o [Portal da empresa](http://apps.microsoft.com/windows/app/company-portal/4b1dff1a-e76f-4fdd-a993-9c59048c3768). Essa funcionalidade não está disponível apenas para Windows, mas também para outras [plataformas](http://blogs.technet.com/b/windowsintune/archive/2013/11/25/windows-intune-company-portals-for-ios-and-android-now-available.aspx). Ao considerar quais aplicativos devem ser acessados por usuários através do portal da empresa, leve em consideração os dois tipos de aplicativos que podem estar disponíveis através do portal da empresa:

- Aplicativos de sideload: aplicativos LOB modernos desenvolvido e publicados para o portal da empresa em que o conteúdo é hospedado.
- Aplicativos de link profundo: links para aplicativos na Microsoft Store (ou Apple Marketplace, para aplicativos iOS) armazenados no Gerenciador de Configurações, que os usuários acessam através do portal da empresa.

Aplicativos de link profundo podem reduzir a sobrecarga administrativa redirecionando os usuários para a Windows Store na versão mais recente, em vez de gerenciar e publicar atualizações ao portal da empresa. O uso da Microsoft Store para implantar aplicativos também pode levar a algumas perguntas, como:

- Você pode usar sua infraestrutura atual para implantar esses aplicativos por meio da Windows Store?
- Qual é o papel que a Windows Store desempenha no processo de implantação de aplicativo?
- Todos os aplicativos precisam vir da Windows Store?

As respostas irão variar de acordo com o estado atual da estratégia de implantação da empresa e como ele precisa evoluir no caso de o uso da Windows Store ser escolhido. Lembre-se de que a Windows Store é um sistema de distribuição digital e é a plataforma de distribuição principal para aplicativos modernos no Windows 10, Windows 8.1, Windows 8 e Windows RT. No entanto, é possível usar a Windows Store para listar os aplicativos de área de trabalho certificados para execução em dispositivos baseados em Windows 8. Para saber mais sobre aplicativos sideload, confira [Experimente: Sideload de aplicativos da Windows Store](https://technet.microsoft.com/windows/jj874388.aspx).

## <a name="deployment"></a>Implantação

Para lidar com as considerações sobre aplicativos que serão implantados para os usuários, é necessário entender os requisitos relacionados ao acesso corporativo. Cenários de implantação incluem os aplicativos que precisam estar sempre conectados aos recursos da empresa, embora os usuários não precisem ter acesso a outros recursos corporativos ou não precisam de acesso completo a todos os recursos corporativos enquanto dentro da rede corporativa. Verifique as opções de implantação para cada aplicativo e avalie qual método é preferido para sua empresa. A seção a seguir inclui as opções de implantação mais comuns que podem ser usadas como parte de uma linha de base de decisão.

### <a name="deployment-options-advantages-and-disadvantages"></a>Opções de implantação — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens de cada opção de implantação:

- Baseado local
    - Vantagens
        - Todos os controles de segurança estão localizado fisicamente local, e a TI tem controle total
        - A TI pode executar a proteção do servidor que contém a função de implantação
        - Fornece recursos mais granulares de auditoria, registro em log e relatórios
    - Desvantagens
        - Custo mais alto para manter quando comparado a uma solução de nuvem
        - Falta de integração com serviços de nuvem
        - Difícil de implantar os aplicativos para dispositivos não gerenciados
        - Difícil de controlar opções de implantação para dispositivos que não estão local
- Baseado em nuvem
    - Vantagens
        - Os aplicativos podem ser instalados em qualquer lugar
        - Capacidade de implantação em várias plataformas
        - Aplicativos mais fáceis de implantar para dispositivos não gerenciados que uma solução local
    - Desvantagens
        - Recursos de emissão de relatórios limitados para aplicativos que consomem dispositivos locais
        - Falta de gerenciamento centralizado e controle de implantação
- Híbrido (parte local e parte na nuvem)
    - Vantagens
        - Aplicativos mais fáceis de implantar para dispositivos não gerenciados que uma solução local.
        - A TI ainda tem controle total sobre a parte do local da função de implantação.
        - Integração entre dispositivos locais e gerenciados em nuvem em um único local.
        - Mais fácil de controlar as opções de implantação em várias plataformas que em uma solução local.
    - Desvantagens
        - Normalmente exige uma assinatura do serviço de nuvem.
        - A integração com a solução de implantação local pode variar de acordo com o serviço de nuvem.

### <a name="app-deployment-requirements-considerations"></a>Requisitos para implantação do aplicativo — considerações

Você também precisará acessar requisitos para implantação de aplicativos para uma solução de infraestrutura BYOD. A lista a seguir inclui algumas considerações importantes sobre a implantação de aplicativo:

- Permissões
    - Certifique-se de que o nível de permissões que os usuários devem ter para instalar aplicativos não seja intrusivo. Por exemplo, você não deve exigir que o usuário seja o administrador de um dispositivo para instalar aplicativos.
    - Se um aplicativo usar arquivos ou pastas temporários, certifique-se de que não exigir permissões de nível administrativo para lidar com esses objetos.
- Certificate
    - Se a implantação de aplicativo exigir um certificado em dispositivos dos usuários, certifique-se de que os dispositivos sejam capazes de acessar a lista de certificados revogados (CRL) para validar a autenticidade do certificado.
    - Se um certificado for instalado durante o processo de instalação do aplicativo, certifique-se de que os usuários estejam cientes disso e sejam solicitados a aprovar.
    - Defina qual certificado será usado. Se o certificado for emitido por uma autoridade de certificação (AC) interna, verifique se os dispositivos dos usuários têm o certificado de autoridade de certificação instalado primeiro e depois instale os certificados dos aplicativos. Se o certificado for emitido por uma AC pública de terceiros, certifique-se de que o dispositivo seja capaz de validar esse certificado pela Internet. Se a validação falhar, certifique-se de que os usuários fiquem cientes do motivo da falha e evitem a instalação por motivos de segurança.
- Agente MDM (Mobile Device Management, gerenciamento de dispositivo móvel)
    - Se aplicativos exigirem um agente MDM para serem instalado em dispositivos de usuários antes da instalação de aplicativos, certifique-se de que os usuários estejam cientes disso e sejam solicitados a dar consentimento.
    - Se o agente MDM precisar ser instalado, certifique-se de que o processo de instalação seja fácil de seguir e use recursos mínimos do sistema.

Usando o System Center 2012 R2 Configuration Manager, a TI pode identificar e licenciar usuários específicos por meio do recurso de descoberta de usuário no Configuration Manager e, em seguida, adicionar usuários a uma coleção personalizada que sincronizará essas contas de usuário com o Microsoft Intune. Isso também ajudará na implantação desses aplicativos.
A atualização do aplicativo também deve ser incluída nas considerações de implantação do aplicativo. Depois que os aplicativos são instalados, as atualizações de aplicativos devem ser detectadas automaticamente e os usuários devem ser notificados no aplicativo da Windows Store. O System Center 2012 R2 oferece recursos para as empresas terem seus próprios armazenamentos de aplicativos corporativos e permite que os usuários instalem aplicativos LOB a partir desse armazenamento. Para saber mais sobre o armazenamento de aplicativos corporativos, confira Estudo de caso de design: aplicativo corporativo de linha de negócios da Windows Store

[VPN acionada automaticamente no Windows 10](http://blogs.technet.com/b/canitpro/archive/2016/01/26/step-by-step-enabling-apps-to-auto-trigger-vpns-in-windows-10.aspx) pode ser usada para permitir que os aplicativos acessem recursos corporativos. Esse recurso permite que a TI defina uma lista de aplicativos predefinidos para conectarem-se automaticamente a redes corporativas abrindo uma conexão VPN quando o aplicativo é iniciado. Você pode definir os aplicativos que deseja disponibilizar para acionamento automático e restringir o acesso remoto com base na identidade do usuário e na identidade do computador do qual o usuário está acessando o recurso. Para saber mais sobre a VPN acionada automaticamente, confira [Novidades no Acesso Remoto do Windows Server 2012 R2](https://technet.microsoft.com/library/dn383589.aspx).

Se sua empresa estiver adotando Windows Phone e desejar permitir que os usuários usem aplicativos LOB para essa plataforma, deve começar com Noções básicas sobre o processo de registro de aplicativo. As empresas devem seguir algumas etapas para estabelecer uma conta da empresa, cadastrar os dispositivos e distribuir os aplicativos a seus dispositivos registrados. Para saber mais sobre a implantação de aplicativos do Windows Phone, confira [Company app distribution for Windows Phone](https://msdn.microsoft.com/library/windowsphone/develop/jj206943(v=vs.105).aspx) (Distribuição do aplicativo corporativo para Windows Phone).

## <a name="storage-and-network"></a>Armazenamento e rede

Considerações de aplicativos de armazenamento e rede podem ter um impacto em servidores de aplicativos e dispositivos. As perguntas a seguir surgirão quando você começar a considerar esses dois componentes principais para aplicativos:

- Os aplicativos armazenarão algo no armazenamento de usuários?
    - Nesse caso, quais são os requisitos de armazenamento para aplicativos ao armazenar informações nos dispositivos dos usuários? Os dados são criptografados pelos aplicativos ou pelo sistema operacional?
- Os aplicativos lidarão com informações confidenciais em trânsito por meio da rede com ou sem fio?
    - Nesse caso, os dados serão criptografados?

A seção a seguir inclui considerações importantes para os requisitos de armazenamento e rede do aplicativo.

### <a name="app-storage-and-network-requirementsconsiderations"></a>Requisitos de armazenamento e rede de aplicativos — considerações

Use a lista a seguir para entender as vantagens e desvantagens de cada armazenamento de aplicativo, além de requisitos e considerações de rede:

- Espaço em disco
    - Se o processo de implantação do aplicativo precisar usar mais espaço do que o aplicativo requer (devido a arquivos temporários), certifique-se de que isso seja bem documentado e que os usuários estejam cientes e sejam solicitados a dar consentimento.
    - Certifique-se de que todos os arquivos temporários e pastas armazenados em dispositivos de armazenamento dos usuários durante o processo de implantação sejam removidas depois que um aplicativo for instalado.
- Privacidade de dados
    - Se um aplicativo armazenar informações particulares da empresa ou do usuário no armazenamento de dispositivo dos usuários, certifique-se de que os usuários estejam cientes e sejam solicitados a dar consentimento.
        - Se o aplicativo armazenar informações particular, certifique-se de que os arquivos sejam criptografados em dispositivos dos usuários.
    - Se os aplicativos transferirem informações particulares da empresa ou usuários através da rede, certifique-se de que o processo de transferência seja criptografado.
- Backup
    - Se os aplicativos armazenarem arquivos temporários no armazenamento do dispositivo dos usuários durante a operação normal de confirmação para depois confirmar no banco de dados do servidor, certifique-se de que haja um mecanismo de backup para salvar os arquivos em caso de falha de aplicativos, de o dispositivo ficar sem energia e realização de preparações para qualquer circunstância desconhecida que possa levar à perda de dados.
    - Certifique-se de que os dados de backup também estejam protegidos contra usuários ou processos não autorizados.
    - Se a rede de usuário perder a conectividade com o servidor de aplicativo, certifique-se de que os aplicativos tenham um processo de backup para evitar perda de dados.
- Infraestrutura de back-end
    - Avalie as necessidades de atualização, expansão ou virtualização de servidores de armazenamento de back-end.
    - Certifique-se de que a infraestrutura de back-end tenha vários caminhos de rede para acessar os dispositivos dos usuários.
    - Certifique-se de que a solução de borda local seja capaz de lidar com vários ISPs para evitar que os usuários que estão chegando da nuvem percam a conectividade com local servidores de aplicativos.

Ao considerar os aplicativos a serem usado na infraestrutura BYOD, você também pode aproveitar a Virtual Desktop Infrastructure (VDI) do Windows Server 2012 R2. Os usuários podem executar remotamente aplicativos do Windows 8 como se estivessem sendo executados em seu dispositivo local, inclusive videoclipes, filmes, streaming de vídeo e aplicativos com muitos elementos gráficos. A experiência do usuário pode ser aprimorada no Windows Server 2012 R2 com o Microsoft RemoteFX. O Windows Server 2012 R2 inclui codec e melhorias de streaming de mídia e oferece a melhor experiência possível ao usuário em diferentes condições da rede, contrabalançando a resolução da experiência com a largura de banda disponível quando necessário. Além disso, com o aplicativo de Área de Trabalho Remota Microsoft, os usuários podem se conectar a seus aplicativos e dados corporativos de uma variedade de plataformas, inclusive Windows, Windows RT, iOS, Mac OS X e Android.

Se você considerar o uso de VDI para permitir que usuários de BYOD acessem aplicativos corporativos, entenda primeiro os tipos de implantações disponíveis para VDI:

- Com base em máquina virtual: máquinas virtuais do Windows 8 em execução em uma infraestrutura Hyper-V. Nesse caso, você deve usar os Serviços de Área de Trabalho Remota para fornecer aos usuários conectividade remota a máquinas virtuais. Você pode usar o cenário de implantação baseado em máquina virtual com coleções de máquina virtual em pool ou pessoais.
- Baseado em sessão: os usuários conectam-se aos Serviços de Área de Trabalho Remota (RDS) no Windows Server 2012 R2 e executam os aplicativos em sessões do Windows Server 2012 R2. Somente RDS é necessário para esse tipo de implantação.
A experiência de armazenamento para a VDI foi aprimorada no Windows Server 2012 R2 com camadas de armazenamento e eliminação de duplicação de dados online. Essa funcionalidade permite que a TI crie volumes de armazenamento que otimizam automaticamente locais de dados em discos e localizam os blocos de dados mais acessados nos discos maior desempenho. Você também pode aproveitar os seguintes recursos de armazenamento no Windows Server 2012 R2 para a VDI:
- Várias opções de armazenamento: suporte para conexão direta, conexão à rede, em cluster ou armazenamento SAN de máquinas virtuais; utiliza a eliminação de duplicação de disco online para reduzir drasticamente os requisitos de armazenamento.
- Compartilhamento de verdade: distribui dinamicamente largura de banda da CPU e o uso do disco por outras máquinas virtuais e sessões, garantindo que nenhuma máquina virtual ou sessão monopolizes recursos ou diminua a experiência para outros usuários do sistema.


Para saber mais sobre VDI no Windows Server 2012 R2, confira [Novidades sobre Serviços de Área de Trabalho Remota no Windows Server 2012 R2](https://technet.microsoft.com/library/dn283323.aspx).

A decisão de qual aplicativo de implantação e experiência serão usados para seu design de infraestrutura BYOD deve ser equilibrada com o custo total de propriedade (TCO). Para entender melhor o TCO para adoção de VDI, recomendamos que você leia [Análise do TCO para VDI para ambientes de trabalho de escritório](http://www.intel.in/content/www/in/en/data-center-efficiency/data-center-efficiency-vdi-tco-analysis-for-office-worker-environments-report.html).

## <a name="security"></a>Segurança 

Considere o uso de um ciclo de vida de desenvolvimento de segurança para todos os aplicativos que serão consumidos por usuários que estão usando seus próprios dispositivos. A segurança deve ser incorporada em todas as fases do processo de desenvolvimento e todas as possíveis ameaças devem ser levadas em consideração. [STRIDE](https://msdn.microsoft.com/magazine/cc163519.aspx) e outras estratégias de segurança podem ser incorporadas ao ciclo de vida de desenvolvimento usando o [Microsoft Security Development Lifecycle (SDL)](https://www.microsoft.com/security/sdl/process/requirements.aspx) (Ciclo de vida de desenvolvimento de segurança). Como a infraestrutura atual será integrada à estratégia geral de segurança para BYOD é uma consideração importante. O ambiente atual é capaz de fornecer uma base segura para aplicativos? A empresa precisa adquirir soluções de terceiros seguras para mitigar qualquer vulnerabilidade potencial criada por essa nova adoção?

Considerações de segurança são importantes para os aplicativos que serão consumidos pelos usuários usando seus próprios dispositivos. É recomendável usar coleções personalizadas com base em grupos de segurança do Active Directory para limitar os usuários de destino a alguns aplicativos com requisitos de acesso específicos, limitando os usuários que podem instalá-los. A segurança também pode ser utilizada para aprimorar a experiência do usuário, permitindo que os usuários usem o mesmo nome de usuário e senha para acessar recursos corporativos, o que podem ser feito usando AD FS. A segurança também é importante ao projetar a implantação para esses aplicativos. Você deve adquirir e implantar certificados e chaves de sideload antes de habilitar o registro de usuário. Trabalhe em coordenação com outras equipes para simplificar o processo de certificação do aplicativo.



<!--HONumber=Nov16_HO4-->


