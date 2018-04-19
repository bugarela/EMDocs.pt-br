---
title: Responsabilidades do FastTrack
description: Responsabilidades do FastTrack quando os clientes estão usando os Benefícios do Centro FastTrack para EMS
keywords: ''
author: andredm7
ms.author: andredm
manager: ''
ms.date: 03/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: a5fce16f550e3b0e620e2cc6eb1f3d9e9cf7dc32
ms.sourcegitcommit: 5ce9b7a0ebac0c5f626b0273fa93fd02589a7452
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="fasttrack-responsibilities"></a>Responsabilidades do FastTrack

O FastTrack tem as responsabilidades a seguir durante a integração.

## <a name="general"></a>Geral

-   Fornecer assistência via suporte remoto a você para as atividades de configuração necessárias conforme listado nas descrições detalhadas de fase.

-   Fornecer ferramentas de software e de documentação e consoles de administração disponíveis para ajudá-lo a reduzir ou eliminar tarefas de configuração.

## <a name="initiate-phase"></a>Fase Iniciar

-   Trabalhar com você para começar a integração.

-   Defina quais serviços você deseja integrar.

## <a name="assess-phase"></a>Fase Avaliar

-   Fornecimento de uma visão geral administrativa.

-   Fornecimento de orientação sobre:

    -   Necessidades de DNS, rede e infraestrutura.

    -   Necessidades do cliente (navegador de Internet, sistema operacional do cliente e necessidades dos serviços).

    -   Identidade do usuário e provisionamento.

    -   Habilitação de serviços elegíveis que foram adquiridos e definidos como parte da integração.

-   Estabelecimento da linha do tempo para atividades de correção.

-   Fornecimento de uma lista de verificação das correções para o Intune e para o Azure AD Premium.

## <a name="remediate-phase"></a>Fase Corrigir

-   Realização de chamadas em conferência com você de acordo com o agendamento estabelecido para a análise do progresso das atividades de correção. Por exemplo, para orientá-lo quanto aos pré-requisitos de instalação antes da integração com um serviço de nuvem da Microsoft.

## <a name="enable-phase"></a>Fase Habilitar
Fornecimento de orientação sobre:

-   Ativação de seu locatário do serviço online ou da sua assinatura da Microsoft.

-   Configuração de protocolos TCP/IP e portas de firewall.

-   Configuração do DNS para serviços qualificados.

-   Validação de conectividade para serviços online da Microsoft.

-   Para um ambiente de floresta única:

    -   Instalação de um servidor de sincronização de diretório entre o AD DS (Active Directory Domain Services) e os serviços online da Microsoft qualificados (apenas diretrizes, se necessário).

    -   Configuração da autenticação gerenciada (Sincronização de hash de senha ou Autenticação de passagem) com a ferramenta Azure Active Directory Connect. (apenas diretrizes, se necessário).

        > [!NOTE]
        > Desenvolvimento e implementação de extensões de regras personalizadas estão fora do escopo.

-   Para uma única floresta quando o destino são identidades federadas: instalação e configuração do AD FS (Serviços de Federação do Active Directory) para autenticação de domínio local com o Intune em uma configuração de site único e tolerante a falhas, se necessário.

    > [!NOTE]
    > Para todas as configurações de várias florestas, as implantações do AD FS estão fora do escopo.

-   Teste da funcionalidade de SSO (logon único), se implantada.

### <a name="enable-phase---microsoft-azure-active-directory-premium"></a>Fase Habilitar – Microsoft Azure Active Directory Premium

Fornecimento de orientação sobre:

- Ativação do seu locatário do Azure AD Premium.

- Configuração das portas do firewall.

- Configuração do DNS para serviços qualificados.

- Validação de conectividade com serviços do Azure AD Premium.

- Para um ambiente de floresta única:

  -   Instalação de uma sincronização de diretórios entre o AD DS (Serviços de Domínio do Active Directory) e o Azure AD Connect, se necessário.

  -   Configuração de um método de autenticação (Sincronização de Hash de Senha ou Autenticação de Passagem) com a ferramenta do Azure AD Connect.

- Para um ambiente de várias florestas:

  -   Ao instalar a sincronização do Azure AD Connect, configure para vários cenários de floresta.
- Para ambientes de uma ou várias florestas:
  - Configuração da autenticação de passagem do Azure Active Directory, se necessário.
  - Configuração do logon único (SSO) contínuo do Azure Active Directory, se necessário.
    > [!NOTE]
    > A autenticação de passagem do Azure Active Directory para ambientes de várias florestas é compatível quando há relações de confiança de floresta entre as florestas do Active Directory e quando o roteamento do sufixo do nome está configurado corretamente. Agentes adicionais podem ser instalados em vários servidores locais para fornecer alta disponibilidade para solicitações de conexão.

  - Saiba mais em [Autenticação de passagem do Azure Active Directory: Início Rápido](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication-quick-start#step-1-check-prerequisites) e [Logon único contínuo do Azure Active Directory: Início Rápido](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start#step-1-check-prerequisites).
  - Saiba mais sobre as limitações da autenticação de passagem em [Autenticação de passagem do Azure Active Directory: limitações atuais](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication-current-limitations).
  - Saiba mais sobre o logon único contínuo em [Solucionar problemas de logon único contínuo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-troubleshoot-sso).

      > [!NOTE]
      > A sincronização de hash de senha e write-back de senha dão suporte a várias florestas. No entanto, não há suporte para outros cenários de write-back.

  - Configure a sincronização entre florestas do Active Directory local e o diretório do Microsoft Azure Active Directory Premium (Azure Active Directory).

    > [!NOTE]
    > Desenvolvimento e implementação de extensões de regras personalizadas estão fora do escopo.

- Para uma única floresta quando o destino são identidades federadas:

  -   Instalação e configuração do AD FS para autenticação de domínio local com o Azure AD Premium em uma configuração de site único e tolerante a falhas (se necessário).

  > [!NOTE]
  > Para todas as configurações de várias florestas, as implantações do AD FS estão fora do escopo.

- Teste da funcionalidade de SSO (se implantada).

### <a name="enable-phase---azure-ad-premium--with-azure-ad-connect-and-ad-fs"></a>Fase Habilitar - Azure AD Premium – com o Azure AD Connect e AD FS

Fornecimento de orientação sobre a configuração de:

- Provisionamento do usuário, incluindo licenciamento.

- Sincronização de diretório do Azure AD Connect (com write-back de senha e sincronização de hash de senha).

  - SSPR (Autoatendimento de Redefinição de Senha).

  - Autenticação Multifator do Azure.

  - Até três (3) ou mais integrações de aplicativo SaaS (software como serviço) com SSO do [Marketplace do Azure Active Directory](https://azure.microsoft.com/marketplace/active-directory/).

  - Tela de logon personalizada, incluindo logotipo, texto e imagens.

  - Grupos de autoatendimento e dinâmico (Grupos).

  - Proxy de Aplicativo do Azure Active Directory.

  - Azure AD Connect Health.

  - Identity Protection.

  - Privileged Identity Management.

  - Acesso condicional ao Azure Active Directory.
  
  - Ingresso híbrido no Azure AD

### <a name="enable-phase---intune"></a>Fase Habilitar – Intune

> [!IMPORTANT]
> O FastTrack não é compatível com o gerenciamento clássico em PCs Windows 10 com o Intune. O FastTrack só é compatível com o gerenciamento do Windows 10 por meio do MDM (gerenciamento de dispositivo móvel) do Intune.

Fornecimento de orientação sobre:

-   Configuração de identidades a serem utilizadas pelo Intune por meio do Active Directory local ou das identidades de nuvem (Azure Active Directory).

-   Licenciamento dos usuários finais.

-   Adicionar usuários à sua assinatura do Intune, definir funções de administrador de TI e criar grupos de usuários e dispositivos.

-   Configurar sua autoridade de MDM (gerenciamento de dispositivo móvel), com base em suas necessidades de gerenciamento, incluindo:

    -   Configurar o Intune como sua autoridade de MDM quando o Intune for a única solução de MDM.

    -   Configurar o System Center Configuration Manager como sua autoridade de MDM se você tiver uma implementação existente do Configuration Manager e quiser expandir seus recursos de gerenciamento com o Intune.

    -   Configuração de grupos de testes a serem usados para validar as políticas de gerenciamento do MDM.

    -   Navegação no portal do administrador do Intune para localizar informações sobre usuários e dispositivos.

    -   Configuração de funções no Intune (operador de suporte técnico, administradores etc.)

    -   Configuração de políticas e serviços de gerenciamento de MDM, como:

        -   Implantação de aplicativo para cada plataforma compatível por meio de links da Web, MSI e/ou links profundos.

        -   Implantação do Office ProPlus em dispositivos Windows 10.

        -   Programas de compra de volume para implantação de aplicativos, incluindo o VPP da Apple, a Microsoft Store para Empresas e a Play for Work Store do Google.

        -   Implantação de email, redes sem fio e perfis VPN se você tiver uma autoridade de certificação existente, infraestrutura de Wi-Fi ou VPN na sua organização.

        -   Configuração do Microsoft Intune Exchange Connector (quando aplicável).

        -   Perfis de configuração de dispositivo para plataformas de dispositivos compatíveis.

    -   Configuração de políticas de acesso condicional.

    -   Configuração e implantação de políticas de proteção de aplicativo do Intune para cada plataforma compatível.

    -   Preparação de aplicativos de linha de negócios para políticas de proteção de aplicativo do Intune, com diretrizes sobre as opções disponíveis.

    -   Registro de dispositivos de cada plataforma com suporte para o Intune ou o Configuration Manager com o serviço Microsoft Intune.

    -   Conexão com o Intune Data Warehouse.

    -   Integração do Intune com o Team Viewer para assistência remota, parceiros do Mobile Threat Defense e do Telecom Expense (licenciamento de produto de terceiros não incluído na assinatura do Intune).

    -   Configuração de atualizações de software para as plataformas compatíveis aplicáveis.

    -   Recursos de planejamento de adoção do usuário.

> [!NOTE]
> **Quer saber mais?** Consulte [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility).

## <a name="next-steps"></a>Próximas etapas

[Benefícios do FastTrack para o EMS – suas responsabilidades](fasttrack-center-benefit-process-for-ems-your-responsibilities.md)
