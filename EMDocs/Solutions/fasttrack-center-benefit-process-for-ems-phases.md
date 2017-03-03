---
title: "Fases de migração e integração"
description: "Fases do Benefício do FastTrack Center"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e51f030b-8b08-4fea-96c9-d4ded435a264
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 61241368440bea9a12bbac136466250da91da997
ms.openlocfilehash: 50389fcdfc8f8dd9d2c565b60990449b442d90aa


---

# <a name="onboarding-and-migration-phases"></a>Fases de Migração e Integração
Quando você usa os [Planos e Serviços Qualificados do Benefício do FastTrack Center](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) para deixar o Microsoft Azure Active Directory Premium e o Microsoft Intune prontos para uso, há várias fases envolvidas no processo. As seções a seguir descrevem cada fase do processo de integração.

A integração tem quatro fases principais:

![As quatro fases do processo de integração do FastTrack](./media/ft-onboarding-benefit.png)


## <a name="initiate-phase"></a>Fase Iniciar

Após ter comprado o número de licenças apropriado, siga as diretrizes no email de confirmação de compra para associar as licenças ao seu locatário existente ou novo locatário. A Microsoft verificará sua qualificação para o Benefício do FastTrack Center e tentará entrar em contato com você para oferecer assistência com a integração. Você também pode solicitar assistência do [FastTrack Center](http://fasttrack.microsoft.com/) se estiver pronto para implantar esses serviços em sua organização.

Para solicitar assistência, entre no [FastTrack Center](http://fasttrack.microsoft.com/) com sua conta corporativa ou de estudante, vá até o painel, expanda **Precisa de ajuda?** à esquerda da tela e siga os prompts para concluir a solicitação. Uma vez iniciado o suporte de integração, nós definimos uma agenda de reuniões online.

Durante essa fase, discutimos o processo de integração, verificamos os dados e programamos uma reunião inicial.

![Fase inicial da integração](./media/ft-initiate-phase.png)

## <a name="assess-phase"></a>Fase Avaliar

Quando o processo de integração é iniciado, a Microsoft trabalha com você para avaliar seu ambiente de origem e os requisitos. Serão executadas ferramentas para avaliar seu ambiente e a Microsoft o orientará ao longo da avaliação de seus navegadores da Internet, Active Directory local, sistemas operacionais de dispositivos cliente, DNS (Sistema de Nomes de Domínio), rede, infraestrutura e sistema de identidade para determinar se são necessárias alterações para a integração.

A Microsoft também fornece a você diretrizes de como chegar a uma adoção bem-sucedida dos serviços qualificados.

Com base em sua configuração atual, forneceremos um plano de correção que levará seu ambiente de origem para os requisitos mínimos necessários para uma integração bem-sucedida com o EMS ou seus serviços de nuvem individuais. Também configuraremos chamadas de ponto de verificação apropriadas para a fase de correção.

![Fase de avaliação da integração](./media/ft-assess-phase.png)

## <a name="remediate-phase"></a>Fase Corrigir
Você realizará as tarefas no plano de correção no ambiente de origem, para que atenda aos requisitos de integração e adoção de cada serviço (conforme necessário).

![Fase de correção da integração](./media/ft-remediate-phase.png)

Antes de iniciar a fase Habilitar, verificaremos em conjunto os resultados das atividades de correção para garantir que você esteja pronto para continuar.

## <a name="enable-phase"></a>Fase Habilitar
Quando todas as atividades de correção estiverem concluídas, o projeto mudará para a configuração da infraestrutura básica para consumo do serviço e para o provisionamento de cada serviço de nuvem do EMS.

**Habilitar fase – Principais recursos**

A integração de núcleo envolve o provisionamento de serviços e a integração de locatário e identidade. Também inclui etapas para fornecer uma base para a integração de serviços online, como o Azure AD Premium e o Intune.

![Fase de habilitação da integração - Principais funcionalidades](./media/ft-enable-phase-core-01.png)

![Fase de habilitação da integração - Principais funcionalidades](./media/ft-enable-phase-core-02.png)

### <a name="enable-phase---azure-ad-premium"></a>Fase Habilitar – Azure AD Premium

O ambiente do Azure AD Premium pode ser configurado usando a sincronização de diretório da ferramenta do Azure Active Directory Connect e o AD FS (Serviços de Federação do Active Directory), conforme necessário.

Para cenários do Azure AD Premium que incluem a sincronização de identidades locais com a nuvem, nós o ajudaremos adicionando os administradores de TI e usuários à sua assinatura, configurando pré-requisitos de gerenciamento, configurando o Azure AD Premium, configurando a sincronização de diretório e o AD FS usando a ferramenta do Azure AD Connect, configurando usuários de teste e validando os principais casos de uso para o serviço.

A instalação do Azure AD Premium inclui a habilitação dos recursos a seguir:

-   SSPR (Autoatendimento de Redefinição de Senha).

-   Azure MFA (Autenticação Multifator do Azure).

-   Uma integração de aplicativo SaaS (software como serviço) com SSO (logon único) do [Marketplace do Azure Active Directory](https://azure.microsoft.com/marketplace/active-directory/).

-   Tela de logon personalizada, incluindo logotipo, texto e imagens.

-   Grupos de autoatendimento e dinâmico (Grupos).

-   Proxy de Aplicativo do Azure Active Directory.

-   Azure Active Directory Connect Health.

-   Identity Protection.

-   Privileged Identity Management.

-   Relatórios de uso e segurança para administradores.

-   Notificações e alertas administrativos.

![Fase de habilitação da integração – Azure AD Premium](./media/ft-enable-phase_aad-premium_adconnect_adfed.png)

### <a name="enable-phase---intune"></a>Fase Habilitar – Intune

Para o Intune, vamos orientá-lo sobre como se preparar para usar o Microsoft Intune para gerenciar dispositivos. As etapas exatas dependem de seu ambiente de origem e são baseadas em suas necessidades de gerenciamento de dispositivo móvel e aplicativo móvel. As etapas podem incluir:

-   Licenciamento dos usuários finais. Nós também forneceremos assistência sobre como ativar licenças de volume para seu locatário de serviço de nuvem da Microsoft (conforme necessário).

-   Configurar identidades que serão usadas pelo Intune usando as identidades de nuvem ou do Active Directory local.

-   Adicionar usuários à sua assinatura do Intune, definir funções de administrador de TI e criar grupos de usuários e dispositivos.

-   Configurar sua autoridade de MDM (gerenciamento de dispositivo móvel), com base em suas necessidades de gerenciamento, incluindo:

    -   Configurar o Intune como sua autoridade de MDM quando o Intune for sua única solução de MDM ou estiver em conjunto com o gerenciamento de dispositivo móvel do Office 365.

    -   Configurar o System Center Configuration Manager como sua autoridade de MDM se você tiver uma implementação existente do Configuration Manager e quiser expandir seus recursos de gerenciamento com o Intune.

        > [!NOTE]
        > Se você quiser apenas aproveitar o MDM nos dispositivos de propriedade dos usuários finais, dispositivos compartilhados ou dispositivos do tipo quiosque, a configuração de uma autoridade de MDM não será necessária.

-   Fornecer diretrizes de MDM para:

    -   Configuração de grupos de testes a serem usados para validar as políticas de gerenciamento do MDM.

    -   Configuração de políticas e serviços de gerenciamento de MDM, como:

        -   Implantação de aplicativo para cada plataforma com suporte por meio de links da web ou links profundos.

        -   Políticas de acesso condicional.

        -   Implantação de email, redes sem fio e perfis VPN (Rede Virtual Privada) se você tiver uma autoridade de certificação existente, infraestrutura de Wi-Fi ou VPN na sua organização.

        -   Configuração do Microsoft Intune Exchange Connector (quando aplicável).

    -   Registro de dispositivos de cada [plataforma com suporte](https://technet.microsoft.com/library/dn600287.aspx) no Intune ou o no Configuration Manager com o serviço do Intune.

-   Fornecimento de diretrizes de MAM (gerenciamento de aplicativo móvel) sobre:

    -   Configuração de políticas de MAM para cada plataforma com suporte.

    -   Configuração de políticas de acesso condicional para aplicativos gerenciados.

    -   Direcionamento dos grupos de usuários apropriado com as políticas MAM acima.

    -   Utilização de relatórios de uso de aplicativos gerenciados.

-   Fornecimento de diretrizes para gerenciamento de PCs sobre:

    -   Instalação do software cliente do Intune (quando necessário).

    -   Uso dos relatórios de hardware e software disponíveis no Intune.

A Microsoft também fornece a você diretrizes de como chegar a uma adoção bem-sucedida dos serviços qualificados.

![Fase de habilitação da integração - Intune](./media/ft-enable-phase_intune_mam.png)

![Fase de habilitação da integração - Intune](./media/ft-enable-phase_intune_mdm-mam_cloudonly.png)

![Fase de habilitação da integração - Intune](./media/ft-enable-phase-intune-mdm-mam-sccm.png)

**Quer saber mais?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)



<!--HONumber=Nov16_HO4-->


