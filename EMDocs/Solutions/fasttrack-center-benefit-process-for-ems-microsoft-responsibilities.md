---
title: Responsabilidades da Microsoft
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 10/02/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 323bdb56b3d81eb6a63e266899427672abf79da4
ms.openlocfilehash: 777236784c06eeea2e62bcb77b2ceabc5d31b14a


---

# Responsabilidades da Microsoft

A Microsoft tem as responsabilidades a seguir durante a integração.

## Geral

-   Fornecer assistência via suporte remoto a você para as atividades de configuração necessárias conforme listado nas descrições detalhadas de fase.

-   Fornece ferramentas de software e de documentação, consoles de administração e scripts disponíveis para ajudá-lo a reduzir ou eliminar tarefas de configuração.

## Fase Iniciar

-   Entrar em contato com você dentro de 30 dias após a compra de licenças qualificadas para um novo locatário.

-   Trabalhar com você para começar a integração.

-   Defina quais serviços você deseja integrar.

## Fase Avaliar

-   Fornecimento de uma visão geral administrativa.

-   Fornecimento de orientação sobre:

    -   Necessidades de DNS, rede e infraestrutura.

    -   Necessidades do cliente (navegador de Internet, sistema operacional do cliente e necessidades dos serviços).

    -   Identidade do usuário e provisionamento.

    -   Habilitação de serviços elegíveis que foram adquiridos e definidos como parte da integração.

-   Estabelecimento da linha do tempo para atividades de correção.

-   Fornecimento de uma lista de verificação de correção.

## Fase Corrigir

-   Realização de teleconferências com você de acordo com a agenda definida para analisar o progresso das atividades de correção.

-   Ajudá-lo com a execução de ferramentas para identificar e corrigir problemas, além de ajudá-lo com a interpretação dos resultados.

## Fase Habilitar
Fornecimento de orientação sobre:

-   Ativação de seu locatário do Serviço Online da Microsoft.

-   Configuração de protocolos TCP/IP e portas de firewall.

-   Configuração do DNS para serviços qualificados.

-   Validação de conectividade para serviços online da Microsoft.

-   Para um ambiente de floresta única:

    -   Instalação de um servidor de sincronização de diretórios entre seus Serviços de Domínio do Active Directory (AD DS) e do(s) serviço(s) online da Microsoft qualificado(s), se necessário.

    -   Configuração da sincronização de senha (hash de senha) para o Microsoft Intune (Active Directory do Azure) com a ferramenta Azure Active Directory Connect.

        > [!NOTE]
        > Desenvolvimento e implementação de extensões de regras personalizadas estão fora do escopo.

-   Para uma única floresta quando o destino são identidades federadas: Instalação e configuração dos Serviços de Federação do Active Directory (AD FS) para autenticação de domínio local com o Microsoft Intune em uma configuração de site único e tolerante a falhas, se necessário.

    > [!NOTE]
    > Para todas as configurações de várias florestas, as implantações do AD FS estão fora do escopo.

-   Teste da funcionalidade de SSO (logon único) se implantada.

### Fase de habilitação - Azure Active Directory Premium

Fornecimento de orientação sobre:

-   Ativação do seu locatário do Microsoft Azure Active Directory Premium.

-   Configuração das portas do firewall.

-   Configuração do DNS para serviços qualificados.

-   Validação de conectividade para serviços do Microsoft Azure Active Directory Premium.

-   Para um ambiente de floresta única:

    -   Instalação de uma sincronização de diretórios entre o AD DS (Serviços de Domínio do Active Directory) e o Azure Active Directory Connect, se necessário.

    -   Configuração da sincronização de senha com a ferramenta Azure Active Directory Connect.

-   Para um ambiente de várias florestas:

    -   Instale a sincronização do Azure Active Directory Connect, configure para cenários com várias florestas. Observe que a sincronização de hash de senha e write-back de senha dão suporte a várias florestas.  No entanto, não há suporte para outros cenários de write-back.

    -   Configure a sincronização entre florestas do Active Directory local e o diretório do Microsoft Azure Active Directory Premium (Azure Active Directory).

        > [!NOTE]
        > Desenvolvimento e implementação de extensões de regras personalizadas estão fora do escopo.

-   Para uma única floresta quando destinar-se a identidades federadas: instalação e configuração dos Serviços de Federação do Active Directory (AD FS) para autenticação de domínio local com o Microsoft Azure Active Directory Premium em uma configuração de site único e tolerante a falhas, se necessário.

    > [!NOTE]
    > Para todas as configurações de várias florestas, as implantações do AD FS estão fora do escopo.

-   Teste da funcionalidade de SSO (logon único), se implantada.

### Fase de habilitação - Azure Active Directory Premium – com os AD FS (Serviços de Federação do Active Directory) e o Azure Active Directory Connect

Fornecimento de orientação sobre a configuração de:

-   Provisionamento do usuário, incluindo licenciamento.

-   Sincronização de diretório do Azure Active Directory Connect (com write-back de senha e sincronização de hash de senha).

  - SSPR (Autoatendimento de Redefinição de Senha).

  - MFA (Autenticação Multifator do Azure).

  - Uma integração de Aplicativo SaaS (software como serviço) com SSO (logon único) do [Marketplace do Azure Active Directory](https://azure.microsoft.com/marketplace/active-directory/).

  - Tela de logon personalizada, incluindo logotipo, texto e imagens.

  - Grupos de autoatendimento e dinâmico (grupos).

  - Proxy de Aplicativo do Azure Active Directory.

  - Azure Active Directory Connect Health.

  - Identity Protection.

  - Privileged Identity Management.

  - Relatórios de uso e segurança para administradores.

  - Notificações e alertas administrativos.

### Fase habilitar - Microsoft Intune
Fornecimento de orientação sobre:

-   Licenciamento dos usuários finais. Quando necessário, também forneceremos assistência sobre como ativar licenças de volume para seu locatário de serviço de nuvem da Microsoft.

-   Configuração de identidades a serem usadas pelo Microsoft Intune, aproveitando suas identidades de nuvem ou do Active Directory local.

-   Adicionar usuários à sua assinatura do Microsoft Intune, definição de funções de administrador de TI e criação de grupos de usuários e dispositivos.

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

        -   Implantação de perfis de email.

        -   Configuração do Microsoft Intune Exchange Connector, quando aplicável.

    -   Registro de dispositivos de cada plataforma com suporte para o Microsoft Intune ou o Configuration Manager com o serviço Microsoft Intune.

    -   Uso de relatórios de inventário de hardware e software.

-   Se o MAM (Gerenciamento de Aplicativo Móvel) estiver no seu escopo ou se você estiver procurando complementar a solução de MDM de terceiros existente com as políticas de MAM, forneceremos diretrizes para:

    -   Configuração de políticas de MAM para cada plataforma com suporte.

    -   Configuração de políticas de acesso condicional para aplicativos gerenciados.

    -   Direcionamento dos grupos de usuários apropriado com as políticas MAM acima.

    -   Utilização de relatórios de uso de aplicativos gerenciados.

-   Se o gerenciamento de PCs estiver no seu escopo, forneceremos orientações para:

    -   Quando necessário, instalar o software cliente do Intune.

    -   Uso dos relatórios de hardware e software disponíveis no Intune.

**Quer saber mais?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)


<!--HONumber=Oct16_HO1-->


