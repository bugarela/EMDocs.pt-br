---
title: O processo do FastTrack
description: Visão geral do processo de integração do Benefício do FastTrack Center
keywords: ''
author: andredm7
ms.author: andredm
manager: ''
ms.date: 03/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dd221c87-6bf7-4af8-845a-dc4c3a4f2334
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: e26aa24ea38c9ec2fa0dabe9044256fa5bfd9b4a
ms.sourcegitcommit: f045537a12763cd6164c4ae42f7b4a45c4ca040b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2018
---
# <a name="fasttrack-center-benefit-process-for-enterprise-mobility--security-ems"></a>Processo do Benefício do FastTrack Center para o EMS (Enterprise Mobility + Security)
Se sua organização estiver qualificada para o Benefício do FastTrack Center para EMS, você poderá trabalhar remotamente com especialistas do FastTrack para deixar o Microsoft Azure Active Directory Premium e o Microsoft Intune prontos para uso. Você também pode solicitar ajuda por meio do [site do FastTrack](http://fasttrack.microsoft.com/ems) para Proteção de Informações do Azure, Microsoft Cloud App Security e Microsoft Advanced Threat Analytics. Para saber se a sua organização está qualificada, veja [Planos e Serviços Qualificados do Benefício do FastTrack Center](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md).


Aqui está o que abordamos sobre o processo de integração:

-   [Visão geral do processo de integração](fasttrack-center-benefit-process-for-ems-overview.md)

-   [Expectativas para o ambiente de origem](fasttrack-center-benefit-process-for-ems-environment-expectations.md)

-   [Fases do processo de integração](fasttrack-center-benefit-process-for-ems-phases.md)

-   [Responsabilidades do FastTrack](fasttrack-center-benefit-process-for-ems-fasttrack-responsibilities.md) para cada fase

-   [Responsabilidades do cliente](fasttrack-center-benefit-process-for-ems-your-responsibilities.md) para cada fase

Eis o que você pode esperar quando a integração for concluída:

-   Seus locatários do EMS para os serviços selecionados foram criados.

-   Os usuários licenciados podem acessar os serviços do EMS usando uma das seguintes opções de identidade:

    -   Identidades de nuvem (contas exclusivas de EMS).

    -   Identidades sincronizadas: contas do EMS sincronizadas do Active Directory local usando a ferramenta do Azure Active Directory Connect (Sincronização de Hash de Senha ou Autenticação de Passagem). Essa opção é voltada para clientes com uma única floresta ou com várias florestas do Active Directory.

    -   Identidades Federadas — com contas do EMS da Microsoft que são:

        -   sincronizadas do Active Directory com a ferramenta Azure AD Connect. Essa opção é voltada para clientes com a configuração de uma única floresta do Active Directory.

        -   Federadas com o AD FS (Serviços de Federação do Active Directory) 2.0 do Windows Server 2012 R2 ou posterior do seu Active Directory local.
