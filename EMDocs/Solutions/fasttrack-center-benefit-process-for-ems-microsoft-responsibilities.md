---
title: Responsabilidades da Microsoft
description: "Responsabilidades da Microsoft quando os clientes estão usando o Benefício do FastTrack Center"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 77e668d5f638ee2e4b9a9e81a1f9181252fde8b9
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="microsoft-responsibilities"></a>Responsabilidades da Microsoft

A Microsoft tem as responsabilidades a seguir durante a integração.

## <a name="general"></a>Geral

-   Fornecer assistência via suporte remoto a você para as atividades de configuração necessárias conforme listado nas descrições detalhadas de fase.

-   Fornece ferramentas de software e de documentação, consoles de administração e scripts disponíveis para ajudá-lo a reduzir ou eliminar tarefas de configuração.

## <a name="initiate-phase"></a>Fase Iniciar

-   Entrar em contato com você dentro de 30 dias após a compra de licenças qualificadas para um novo locatário.

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

-   Fornecimento de uma lista de verificação de correção.

## <a name="remediate-phase"></a>Fase Corrigir

-   Realização de teleconferências com você de acordo com a agenda definida para analisar o progresso das atividades de correção.

-   Ajudá-lo com a execução de ferramentas para identificar e corrigir problemas, além de ajudá-lo com a interpretação dos resultados.

## <a name="enable-phase"></a>Fase Habilitar
Fornecimento de orientação sobre:

-   Ativação de seu locatário do Serviço Online da Microsoft.

-   Configuração de protocolos TCP/IP e portas de firewall.

-   Configuração do DNS para serviços qualificados.

-   Validação de conectividade para serviços online da Microsoft.

-   Para um ambiente de floresta única:

    -   Instalação de um servidor de sincronização de diretórios entre o AD DS (Active Directory Domain Services) e os serviços online da Microsoft qualificados (se necessário).

    -   Configuração da sincronização de senha (hash de senha) para o Microsoft Intune (Active Directory do Azure) com a ferramenta Azure Active Directory Connect.

        > [!NOTE]
        > Desenvolvimento e implementação de extensões de regras personalizadas estão fora do escopo.

-   Para uma única floresta quando o destino são identidades federadas: instalação e configuração do AD FS (Serviços de Federação do Active Directory) para autenticação de domínio local com o Intune em uma configuração de site único e tolerante a falhas, se necessário.

    > [!NOTE]
    > Para todas as configurações de várias florestas, as implantações do AD FS estão fora do escopo.

-   Teste da funcionalidade de SSO (logon único), se implantada.

### <a name="enable-phase---microsoft-azure-active-directory-premium"></a>Fase Habilitar – Microsoft Azure Active Directory Premium

Fornecimento de orientação sobre:

-   Ativação do seu locatário do Azure AD Premium.

-   Configuração das portas do firewall.

-   Configuração do DNS para serviços qualificados.

-   Validação de conectividade com serviços do Azure AD Premium.

-   Para um ambiente de floresta única:

    -   Instalação de uma sincronização de diretórios entre o AD DS (Serviços de Domínio do Active Directory) e o Azure AD Connect, se necessário.

    -   Configuração da sincronização de senha com a ferramenta Azure AD Connect.

-   Para um ambiente de várias florestas:

    -   Ao instalar a sincronização do Azure AD Connect, configure para vários cenários de floresta.

        > [!NOTE]
        > A sincronização de hash de senha e write-back de senha dão suporte a várias florestas. No entanto, não há suporte para outros cenários de write-back.

    -   Configure a sincronização entre florestas do Active Directory local e o diretório do Microsoft Azure Active Directory Premium (Azure Active Directory).

        > [!NOTE]
        > Desenvolvimento e implementação de extensões de regras personalizadas estão fora do escopo.

-   Para uma única floresta quando o destino são identidades federadas:

    -   Instalação e configuração do AD FS para autenticação de domínio local com o Azure AD Premium em uma configuração de site único e tolerante a falhas (se necessário).

    > [!NOTE]
    > Para todas as configurações de várias florestas, as implantações do AD FS estão fora do escopo.

-   Teste da funcionalidade de SSO (se implantada).

### <a name="enable-phase---azure-ad-premium--with-azure-ad-connect-and-ad-fs"></a>Fase Habilitar - Azure AD Premium – com o Azure AD Connect e AD FS

Fornecimento de orientação sobre a configuração de:

-   Provisionamento do usuário, incluindo licenciamento.

-   Sincronização de diretório do Azure AD Connect (com write-back de senha e sincronização de hash de senha).

  - SSPR (Autoatendimento de Redefinição de Senha).

  - Autenticação Multifator do Azure.

  - Uma integração de aplicativo SaaS (software como serviço) com SSO do [Marketplace do Azure Active Directory](https://azure.microsoft.com/marketplace/active-directory/).

  - Tela de logon personalizada, incluindo logotipo, texto e imagens.

  - Grupos de autoatendimento e dinâmico (Grupos).

  - Proxy de Aplicativo do Azure Active Directory.

  - Azure AD Connect Health.

  - Identity Protection.

  - Privileged Identity Management.

  - Relatórios de uso e segurança para administradores.

  - Notificações e alertas administrativos.

### <a name="enable-phase---intune"></a>Fase Habilitar – Intune
Fornecimento de orientação sobre:

-   Licenciamento dos usuários finais.

-   Configurar identidades que serão usadas pelo Intune usando as identidades de nuvem ou do Active Directory local.

-   Adicionar usuários à sua assinatura do Intune, definir funções de administrador de TI e criar grupos de usuários e dispositivos.

-   Configurar sua autoridade de MDM (gerenciamento de dispositivo móvel), com base em suas necessidades de gerenciamento, incluindo:

    -   Configurar o Intune como sua autoridade de MDM quando o Intune for sua única solução de MDM ou estiver em conjunto com o gerenciamento de dispositivo móvel do Office 365.

    -   Configurar o System Center Configuration Manager como sua autoridade de MDM se você tiver uma implementação existente do Configuration Manager e quiser expandir seus recursos de gerenciamento com o Intune.

        > [!NOTE]
        > Se você quiser apenas aproveitar o MDM nos dispositivos de propriedade dos usuários finais, dispositivos compartilhados ou dispositivos do tipo quiosque, a configuração de uma autoridade de MDM não será necessária.

    -   Configuração de grupos de testes a serem usados para validar as políticas de gerenciamento do MDM.

    -   Configuração de políticas e serviços de gerenciamento de MDM, como:

        -   Implantação de aplicativo para cada plataforma com suporte por meio de links da web ou links profundos.

        -   Políticas de acesso condicional.

        -   Implantação de email, redes sem fio e perfis VPN se você tiver uma autoridade de certificação existente, infraestrutura de Wi-Fi ou VPN na sua organização.

        -   Configuração do Microsoft Intune Exchange Connector (quando aplicável).

    -   Registro de dispositivos de cada plataforma com suporte para o Intune ou o Configuration Manager com o serviço Microsoft Intune.

    -   Uso de relatórios de inventário de hardware e software.

    -   Configuração de políticas de MAM para cada plataforma com suporte.

    -   Configuração de políticas de acesso condicional para aplicativos gerenciados.

    -   Direcionamento dos grupos de usuários apropriado com as políticas MAM acima.

    -   Utilização de relatórios de uso de aplicativos gerenciados.

    -   Instalação do software cliente do Intune (quando necessário).

    -   Uso dos relatórios de hardware e software disponíveis no Intune.

**Quer saber mais?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
