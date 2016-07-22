---
title: "Processo do Benefício do FastTrack Center para o Enterprise Mobility Suite - responsabilidades da Microsoft"
description: 
keywords: 
author: staciebarker
manager: jeffgilb
ms.date: 07/07/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c8fd871e-f1bc-43ec-a5f3-ad025df9b026
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1e23cdad577738a72b6dc8423a5ba6cf7af29bfb
ms.openlocfilehash: 5aa145639d7f38beb0a9b684cd70227edccccf42


---

# Processo do Benefício do FastTrack Center para o Enterprise Mobility Suite - responsabilidades da Microsoft
As seções a seguir descrevem o que você pode esperar da Microsoft quando sua organização estiver usando o [Benefício do FastTrack Center para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) para preparar o Azure Active Directory Premium, o Microsoft Intune e/ou o Azure Rights Management para uso.

Para ler sobre as outras partes do processo de integração do FastTrack, confira [Processo do Benefício do FastTrack Center para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-process-for-enterprise-mobility-suite-ems.md).


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

-   Para uma única floresta quando o destino for identidades federadas: instalação e configuração dos Serviços de Federação do Active Directory (AD FS) para autenticação de domínio local com o Microsoft Azure AD Premium em uma configuração de site único e tolerante a falhas, se necessário.

    > [!NOTE] 
    > Para todas as configurações de várias florestas, as implantações do AD FS estão fora do escopo.

-   Teste da funcionalidade de SSO (logon único), se implantada.

### Fase de habilitação - Azure Active Directory Premium – com os AD FS (Serviços de Federação do Active Directory) e o Azure Active Directory Connect

Fornecimento de orientação sobre a configuração de:

-   Provisionamento do usuário, incluindo licenciamento.

-   Sincronização de diretório do Azure Active Directory Connect (com write-back de senha e sincronização de hash de senha).

-   AD FS (Serviços de Federação do Active Directory).

- SSPR (Autoatendimento de Redefinição de Senha).

- MFA (Multi-factor Authentication do Azure).

- Um aplicativo integrado, que pode incluir Logon Único para aplicativos SaaS.

- Relatórios de uso e segurança para administradores.

- SSGM (Autoatendimento de Gerenciamento de Grupo).

- Proxy de aplicativo.

- Notificações do administrador.

- Tela de logon personalizada, incluindo logotipo, texto e imagens.
 
### Fase habilitar - Microsoft Intune
Fornecimento de orientação sobre:

-   Licenciamento dos usuários finais. Quando necessário, também forneceremos assistência sobre como ativar licenças de volume para seu locatário de serviço de nuvem da Microsoft.

-   Configuração de identidades a serem usadas pelo Microsoft Intune, aproveitando suas identidades de nuvem ou do Active Directory local.

-   Adicionar usuários à sua assinatura do Microsoft Intune, definição de funções de administrador de TI e criação de grupos de usuários e dispositivos.

-   Com base em suas necessidades de gerenciamento, configurando a autoridade de Gerenciamento de Dispositivo Móvel:

    -   Configure o Microsoft Intune como sua autoridade MDM quando o Microsoft Intune for sua única solução MDM ou se estiver em conjunto com o gerenciamento de dispositivo móvel do Office 365.

    -   Se você tiver uma implementação existente do System Center Configuration Manager e quiser para expandir seus recursos de gerenciamento com o Microsoft Intune, configure o Configuration Manager como sua autoridade MDM.

        > [!NOTE] 
        > Se você estiver apenas procurando aproveitar o Gerenciamento de Aplicativo Móvel nos dispositivos compartilhados, de quiosque ou compartilhados dos seus usuários finais, a configuração de uma autoridade MDM não é necessária.

-   Se o Gerenciamento de Dispositivo Móvel estiver no seu escopo, forneceremos orientações com:

    -   Configuração de grupos de testes a serem usados para validar as políticas de gerenciamento do MDM.

    -   Configuração de políticas de gerenciamento do MDM e serviços, como:

        -   Implantação de aplicativo para cada plataforma com suporte por meio de links da web ou links profundos.

        -   Políticas de acesso condicional.

        -   Implantação de perfis de email.

        -   Configuração do Microsoft Intune Exchange Connector, quando aplicável.

    -   Registro de até dois dispositivos de teste de cada plataforma com suporte para o Microsoft Intune ou Configuration Manager com o serviço Microsoft Intune.

    -   Uso de relatórios de inventário de hardware e software.

-   Se o Gerenciamento de Aplicativo Móvel (MAM) estiver no seu escopo, ou se você estiver procurando complementar a solução MDM de terceiros existente com as políticas de MAM, forneceremos orientações para:

    -   Configuração de políticas de MAM para cada plataforma com suporte.

    -   Configuração de políticas de acesso condicional para aplicativos gerenciados.

    -   Direcionamento dos grupos de usuários apropriado com as políticas MAM acima.

    -   Utilização de relatórios de uso de aplicativos gerenciados.

-   Se o gerenciamento de PCs estiver no seu escopo, forneceremos orientações para:

    -   Quando necessário, instalar o software cliente do Intune.

    -   Uso dos relatórios de hardware e software disponíveis no Intune.

### Fase de habilitação - Azure Right Management Premium

Fornecimento de orientação sobre:

-   Ativando o locatário do Azure RMS.

-   Adicionando administradores de segurança de informações adicionais para gerenciar modelos.

-   Atribuir uma conta de superusuário para o Azure RMS.

-   Licenciando dois usuários piloto para o Azure RMS.

-   Configurando dois grupos de distribuição de teste para validar as políticas.

-   Configurando um modelo personalizado do Azure RMS para seu diretório.

-   Fornecendo diretrizes ao configurar a integração do SharePoint Online e o Exchange Online com o Azure RMS, incluindo:

    -   Configurando e validando a integração do Exchange Online com o Azure RMS.

    -   Configurando um regra de fluxo de email de teste para criptografar mensagens confidenciais enviadas a destinatários externos à sua organização.

    -   Configurando e validando a proteção do SharePoint Online de uma biblioteca de teste a ser protegida com o Azure RMS.

-   Configurar um servidor local com o conector RMS, quando aplicável:

    -   Configurando e validando a integração local do Exchange 2013/2010 com o Azure RMS.

    -   Instalando uma regra de fluxo de email de teste para criptografar mensagens confidenciais enviadas a destinatários externos à sua organização usando o conector.

    -   Configurando e validando a proteção local do SharePoint 2013/2010 de uma biblioteca de teste a ser protegida com o Azure RMS.

-   Instalando o aplicativo RMS sharing para dispositivos Windows e não Windows.

Leia sobre a próxima parte do processo de integração do FastTrack: [Responsabilidades do cliente](fasttrack-center-benefit-process-for-ems-your-responsibilities.md)

### Quer saber mais?
Confira [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).




<!--HONumber=Jul16_HO3-->


