---
# required metadata

title: Processo do Benefício do FastTrack Center para o Enterprise Mobility Suite - fases
description:
keywords:
author: 
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Processo do Benefício do FastTrack Center para o Enterprise Mobility Suite - fases
Quando você usa o [Benefício do FastTrack Center para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) para preparar o Azure Active Directory Premium, o Microsoft Intune e/ou o Azure Rights Management para uso, há várias fases envolvidas no processo. As seções a seguir descrevem cada fase do processo de integração.

Para ler sobre as outras partes do processo de integração do FastTrack, confira [Processo do Benefício do FastTrack Center para EMS (Enterprise Mobility Suite)](fasttrack-center-benefit-process-for-enterprise-mobility-suite-ems.md).


A integração tem quatro fases principais, conforme mostra a figura a seguir:


![As quatro fases do processo de integração do FastTrack](./media/ft-2-onboarding-phases.png)


## Fase Iniciar

Depois que você tiver comprado o número de licenças apropriado, siga as diretrizes do email de confirmação de compra para associar as licenças ao seu locatário existente ou novo locatário. A Microsoft verificará sua qualificação para o Benefício do FastTrack Center, e tentará entrar em contato com você para oferecer assistência com a integração. Você também pode solicitar assistência do [Centro FastTrack](http://fasttrack.microsoft.com/) se estiver pronto para implantar esses serviços em sua organização. Para solicitar assistência, entre no [FastTrack Center](http://fasttrack.microsoft.com/) (http://fasttrack.microsoft.com), acesse o painel, clique na guia Ofertas e clique em “Solicitar Assistência para o Microsoft Intune, o Azure Active Directory Premium ou o Azure Rights Management Premium”. Uma vez iniciado o suporte de integração, vamos definir uma agenda de reuniões online.

Durante essa fase, podemos discutir o processo de integração, verificar os dados e programar uma reunião inicial.

![Fase inicial da integração](./media/ft-3-initiate-phase.png)

## Fase Avaliar

Quando começar o processo de integração, a Microsoft trabalhará com você para avaliar seu ambiente de origem e os requisitos. Ferramentas serão executadas para avaliar seu ambiente e a Microsoft vai guiá-lo pela avaliação de seus navegadores de Internet, Active Directory local, sistemas operacionais de dispositivos do cliente, DNS, rede, infraestrutura e sistema de identidade para determinar se são necessárias quaisquer alterações para integração.

A Microsoft também conectará você com diretrizes sobre como gerar uma adoção bem-sucedida dos serviços qualificados.

Com base em sua configuração atual, forneceremos um plano de correção que atualizará o seu ambiente de origem para os requisitos mínimos necessários para uma integração bem-sucedida com o EMS ou seus serviços de nuvem individuais. Também configuraremos chamadas de ponto de verificação apropriadas para a fase de correção.

![Fase de avaliação da integração](./media/ft-4-assess-phase.png)

## Fase Corrigir
Se for necessário, você realizará as tarefas no plano de correção no ambiente de origem, para que você atenda aos requisitos de integração e adoção de cada serviço.

![Fase de correção da integração](./media/ft-5-remediate-phase.png)

Antes de iniciar a fase Habilitar, verificaremos em conjunto os resultados das atividades de correção para garantir que você esteja pronto para continuar.

## Fase Habilitar
Quando todas as atividades de correção estiverem concluídas, o projeto mudará para a configuração da infraestrutura básica para consumo do serviço e para o provisionamento de cada serviço de nuvem do EMS.

**Habilitar fase - principais recursos**

A integração de núcleo envolve o provisionamento de serviços e a integração de locatário e identidade. Também inclui etapas para fornecer uma base para a integração de serviços online, como o Azure Active Directory Premium, o Microsoft Intune e o Azure Rights Management Premium.

![Fase de habilitação da integração - Principais funcionalidades](./media/ft-6-enable-phase-core.png)

###Fase de habilitação - Azure Active Directory Premium

O ambiente do Azure Active Directory Premium pode ser configurado com a sincronização de diretório da ferramenta do Azure Active Directory Connect e o AD FS (Serviços de Federação do Active Directory), conforme o necessário.

Para cenários do Azure Active Directory Premium que incluem a sincronização de identidades locais com a nuvem, nós ajudaremos você adicionando os administradores de TI e os usuários à sua assinatura, configurando pré-requisitos de gerenciamento, configurando o Azure Active Directory Premium, configurando a sincronização de diretório usando a ferramenta Azure Active Directory Connect e o AD FS (Serviços de Federação do Active Directory) usando a ferramenta Azure Active Directory Connect, configurando usuários de teste e validando os principais casos de uso para o serviço.

A configuração do Azure Active Directory Premium inclui a habilitação dos seguintes recursos:

-   SSPR (Autoatendimento de Redefinição de Senha)

-   MFA (Multi-factor Authentication) do Azure

-   Aplicativo SaaS (Software como Serviço) – configure um aplicativo SaaS no [Marketplace do Azure Active Directory](https://azure.microsoft.com/marketplace/active-directory/).

-   SSGM (Autoatendimento de Gerenciamento de Grupo)

-   Relatórios administrativos

![Fase de habilitação da integração - AADP](./media/ft-7-enable-phase-aadp.png)

###Fase habilitar - Microsoft Intune

Para o Microsoft Intune, e com base em seu dispositivo móvel e nas necessidades de gerenciamento de aplicativos móveis, vamos orientá-lo sobre como preparar-se para usar o Microsoft Intune para gerenciar dispositivos. As etapas exatas dependem de seu ambiente de origem e podem incluir:

-   Licenciamento dos usuários finais. Quando necessário, também forneceremos assistência sobre como ativar licenças de volume para seu locatário de serviço de nuvem da Microsoft.

-   Configurando identidades que serão usadas pelo Microsoft Intune, aproveitando as identidades locais de nuvem ou do Active Directory.

-   Adicionando usuários à sua assinatura do Microsoft Intune, definindo funções de administrador de TI e criando grupos de usuários e dispositivos.

-   Com base em suas necessidades de gerenciamento, configurando a autoridade de Gerenciamento de Dispositivo Móvel:

    -   Configure o Microsoft Intune como sua autoridade MDM quando o Microsoft Intune for sua única solução MDM ou se estiver em conjunto com o gerenciamento de dispositivo móvel do Office 365.

    -   Se você tiver uma implementação existente do System Center Configuration Manager e quiser para expandir seus recursos de gerenciamento com o Microsoft Intune, configure o Configuration Manager como sua autoridade MDM.

        > [!NOTE]
        > Se você estiver procurando apenas aproveitar o Gerenciamento de Aplicativo Móvel nos dispositivos próprios, dispositivos compartilhados ou dispositivos de quiosque de seus usuários finais, a configuração de uma autoridade MDM não é necessária.

-   Se o Gerenciamento de Dispositivo Móvel estiver no seu escopo, forneceremos orientações com:

    -   Configuração de grupos de testes a serem usados para validar as políticas de gerenciamento do MDM.

    -   Configuração de políticas de gerenciamento do MDM e serviços, como:

        -   Implantação de aplicativo para cada plataforma com suporte por meio de links da web ou links profundos.

        -   Políticas de acesso condicional.

        -   Implantação de perfis de email.

        -   Configuração do Microsoft Intune Exchange Connector, quando aplicável.

    -   Registro de dispositivos de cada [plataforma com suporte](https://technet.microsoft.com/library/dn600287.aspx) para o Microsoft Intune ou o Gerenciador de Configurações com o serviço Microsoft Intune.

-   Se o Gerenciamento de Aplicativo Móvel (MAM) estiver no seu escopo, ou se você estiver procurando complementar seu Microsoft existente ou solução MDM de terceiros com políticas MAM, forneceremos orientações com:

    -   Configuração de políticas de MAM para cada plataforma com suporte.

    -   Configuração de políticas de acesso condicional para aplicativos gerenciados.

    -   Direcionamento dos grupos de usuários apropriado com as políticas MAM acima.

    -   Utilização de relatórios de uso de aplicativos gerenciados.

-   Se o gerenciamento de PCs estiver no seu escopo, forneceremos orientações para:

    -   Quando necessário, instalar o software cliente do Intune.

    -   Uso dos relatórios de hardware e software disponíveis no Intune.

A Microsoft também conectará você com diretrizes sobre como gerar uma adoção bem-sucedida dos serviços qualificados.

![Fase de habilitação da integração - Intune](./media/ft-8-enable-phase-intune.png)

###Fase de habilitação - Azure Right Management Premium

O ambiente do Azure Right Management Premium pode ser configurado com a sincronização de diretórios do Azure Active Directory Connect e o AD FS (Serviços de Federação do Active Directory), conforme o necessário.

Para cenários do AzRMS que incluem sincronização de identidades locais com a nuvem, nós o ajudaremos adicionando administradores de TI e usuários à sua assinatura, configurando pré-requisitos de gerenciamento, configurando o Azure Right Management Premium, configurando a sincronização de diretórios usando a ferramenta Azure Active Directory Connect e os Serviços de Federação do Active Directory usando o Azure Active Directory Connect, configurando usuários de teste e validando os principais casos de uso para o serviço.

A instalação do AzRMS inclui a habilitação dos recursos a seguir:

-   Habilitação de Serviço do AzRMS

-   Configuração do IRM para o Exchange Online e o Sharepoint Online

-   Conector do Rights Management com o Exchange local e o Sharepoint local

-   Dispositivos do aplicativo RMS sharing para dispositivos Windows e não Windows

![Fase de habilitação da integração - Azure RMS](./media/ft-7-enable-phase-aadp.png)

Leia sobre a próxima parte do processo de integração do FastTrack: [Responsabilidades da Microsoft](fasttrack-center-benefit-process-for-ems-microsoft-responsibilities.md)

### Quer saber mais?
Consulte [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).



<!--HONumber=Apr16_HO5-->


