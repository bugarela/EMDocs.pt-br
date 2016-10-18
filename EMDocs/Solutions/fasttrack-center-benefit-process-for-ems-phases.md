---
title: "Fases de Migração e Integração"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 10/02/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fd3cdf64ae84d45f285302fd8557dfdfadc60c8f
ms.openlocfilehash: 9f0a69a7bd9bc1910281c44ec818efbf9c87370a


---

# Fases de Migração e Integração
Quando você usa os [Planos e Serviços Qualificados do Benefício do FastTrack Center](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) para deixar o Azure Active Directory Premium e/ou o Microsoft Intune prontos para uso, há várias fases envolvidas no processo. As seções a seguir descrevem cada fase do processo de integração.

A integração tem as seguintes fases principais:

![As quatro fases do processo de integração do FastTrack](./media/ft-onboarding-benefit.png)


## Fase Iniciar

Depois que você tiver comprado o número de licenças apropriado, siga as diretrizes do email de confirmação de compra para associar as licenças ao seu locatário existente ou novo locatário. A Microsoft verificará sua qualificação para o Benefício do FastTrack Center, e tentará entrar em contato com você para oferecer assistência com a integração. Você também pode solicitar assistência do [Centro FastTrack](http://fasttrack.microsoft.com/) se estiver pronto para implantar esses serviços em sua organização.

Para solicitar assistência, entre no [FastTrack Center](http://fasttrack.microsoft.com/) (http://fasttrack.microsoft.com) com sua conta corporativa ou de estudante, clique em sua empresa (ou adicione-a se necessário), clique na guia Serviços e depois em “Solicitar Assistência para o Microsoft Intune ou o Azure Active Directory Premium”. Uma vez iniciado o suporte de integração, vamos definir uma agenda de reuniões online.

Durante essa fase, podemos discutir o processo de integração, verificar os dados e programar uma reunião inicial.

![Fase inicial da integração](./media/ft-initiate-phase.png)

## Fase Avaliar

Quando começar o processo de integração, a Microsoft trabalhará com você para avaliar seu ambiente de origem e os requisitos. Ferramentas serão executadas para avaliar seu ambiente e a Microsoft vai guiá-lo pela avaliação de seus navegadores de Internet, Active Directory local, sistemas operacionais de dispositivos do cliente, DNS, rede, infraestrutura e sistema de identidade para determinar se são necessárias quaisquer alterações para integração.

A Microsoft também conectará você com diretrizes sobre como gerar uma adoção bem-sucedida dos serviços qualificados.

Com base em sua configuração atual, forneceremos um plano de correção que atualizará o seu ambiente de origem para os requisitos mínimos necessários para uma integração bem-sucedida com o EMS ou seus serviços de nuvem individuais. Também configuraremos chamadas de ponto de verificação apropriadas para a fase de correção.

![Fase de avaliação da integração](./media/ft-assess-phase.png)

## Fase Corrigir
Se for necessário, você realizará as tarefas no plano de correção no ambiente de origem, para que você atenda aos requisitos de integração e adoção de cada serviço.

![Fase de correção da integração](./media/ft-remediate-phase.png)

Antes de iniciar a fase Habilitar, verificaremos em conjunto os resultados das atividades de correção para garantir que você esteja pronto para continuar.

## Fase Habilitar
Quando todas as atividades de correção estiverem concluídas, o projeto mudará para a configuração da infraestrutura básica para consumo do serviço e para o provisionamento de cada serviço de nuvem do EMS.

**Habilitar fase - principais recursos**

A integração de núcleo envolve o provisionamento de serviços e a integração de locatário e identidade. Também inclui etapas para fornecer uma base para a integração de serviços online, assim como o Azure Active Directory Premium e o Microsoft Intune.

![Fase de habilitação da integração - Principais funcionalidades](./media/ft-enable-phase-core-01.png)

![Fase de habilitação da integração - Principais funcionalidades](./media/ft-enable-phase-core-02.png)

### Fase de habilitação - Azure Active Directory Premium

O ambiente do Azure Active Directory Premium pode ser configurado com a sincronização de diretório da ferramenta do Azure Active Directory Connect e o AD FS (Serviços de Federação do Active Directory), conforme o necessário.

Para cenários do Azure Active Directory Premium que incluem a sincronização de identidades locais com a nuvem, nós lhe ajudaremos adicionando os administradores de TI e os usuários à sua assinatura, configurando pré-requisitos de gerenciamento, configurando o Azure Active Directory Premium, configurando a sincronização de diretório e o AD FS (Serviços de Federação do Active Directory) usando a ferramenta Azure Active Directory Connect, configurando usuários de teste e validando os principais casos de uso para o serviço.

A configuração do Azure Active Directory Premium inclui a habilitação dos seguintes recursos:

-   SSPR (Autoatendimento de Redefinição de Senha).

-   Azure MFA (Autenticação Multifator do Azure).

-   Uma integração de Aplicativo SaaS (software como serviço) com SSO (logon único) do [Marketplace do Azure Active Directory](https://azure.microsoft.com/marketplace/active-directory/).

-   Tela de logon personalizada, incluindo logotipo, texto e imagens.

-   Grupo de autoatendimento e dinâmico (grupos).

-   Proxy de Aplicativo do Azure Active Directory.

-   Azure Active Directory Connect Health.

-   Identity Protection.

-   Privileged Identity Management.

-   Relatórios de uso e segurança para administradores.

-   Notificações e alertas administrativos.

![Fase de habilitação da integração - AADP](./media/ft-enable-phase_aad-premium_adconnect_adfed.png)

### Fase habilitar - Microsoft Intune

Para o Microsoft Intune, e com base em seu dispositivo móvel e nas necessidades de gerenciamento de aplicativos móveis, vamos orientá-lo sobre como preparar-se para usar o Microsoft Intune para gerenciar dispositivos. As etapas exatas dependem de seu ambiente de origem e podem incluir:

-   Licenciamento dos usuários finais. Quando necessário, também forneceremos assistência sobre como ativar licenças de volume para seu locatário de serviço de nuvem da Microsoft.

-   Configurando identidades que serão usadas pelo Microsoft Intune, aproveitando as identidades locais de nuvem ou do Active Directory.

-   Adicionando usuários à sua assinatura do Microsoft Intune, definindo funções de administrador de TI e criando grupos de usuários e dispositivos.

-   Com base em suas necessidades de gerenciamento, configurando a autoridade de Gerenciamento de Dispositivo Móvel:

    -   Configure o Microsoft Intune como sua autoridade MDM quando o Microsoft Intune for sua única solução MDM ou se estiver em conjunto com o gerenciamento de dispositivo móvel do Office 365.

    -   Se você tiver uma implementação existente do System Center Configuration Manager e quiser expandir seus recursos de gerenciamento com o Microsoft Intune, você deverá configurar o Configuration Manager como sua autoridade do MDM.

        > [!NOTE]
        > Se você desejar apenas aproveitar o Gerenciamento de Aplicativo Móvel nos dispositivos compartilhados, dispositivos de quiosque ou dispositivos de propriedade de seus usuários finais, a configuração de uma autoridade do MDM não será necessária.

-   Se o Gerenciamento de Dispositivo Móvel estiver no seu escopo, forneceremos orientações com:

    -   Configuração de grupos de testes a serem usados para validar as políticas de gerenciamento do MDM.

    -   Configuração de políticas de gerenciamento do MDM e serviços, como:

        -   Implantação de aplicativo para cada plataforma com suporte por meio de links da web ou links profundos.

        -   Políticas de acesso condicional.

        -   Implantação de email, Wi-Fi e perfis VPN.

        -   Configuração do Microsoft Intune Exchange Connector, quando aplicável.

    -   Registro de dispositivos de cada [plataforma com suporte](https://technet.microsoft.com/library/dn600287.aspx) para o Microsoft Intune ou o Gerenciador de Configurações com o serviço Microsoft Intune.

-   Se o Gerenciamento de Aplicativo Móvel (MAM) estiver no seu escopo ou se você estiver procurando complementar seu Microsoft existente ou solução de MDM de terceiros com políticas MAM, forneceremos diretrizes para:

    -   Configuração de políticas de MAM para cada plataforma com suporte.

    -   Configuração de políticas de acesso condicional para aplicativos gerenciados.

    -   Direcionamento dos grupos de usuários apropriado com as políticas MAM acima.

    -   Utilização de relatórios de uso de aplicativos gerenciados.

-   Se o gerenciamento de PCs estiver no seu escopo, forneceremos orientações para:

    -   Quando necessário, instalar o software cliente do Intune.

    -   Uso dos relatórios de hardware e software disponíveis no Intune.

A Microsoft também conectará você com diretrizes sobre como gerar uma adoção bem-sucedida dos serviços qualificados.

![Fase de habilitação da integração - Intune](./media/ft-enable-phase_intune_mam.png)

![Fase de habilitação da integração - Intune](./media/ft-enable-phase_intune_mdm-mam_cloudonly.png)

![Fase de habilitação da integração - Intune](./media/ft-enable-phase-intune-mdm-mam-sccm.png)

**Quer saber mais?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)


<!--HONumber=Oct16_HO2-->


