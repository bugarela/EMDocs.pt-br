---
title: Expectativas para o ambiente de origem
description: "Requisitos de ambiente de origem para usar o Benefício do FastTrack Center"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 07aeaee067dbd6c827992b9d613d7716b5d57954
ms.openlocfilehash: 6c871d792424f5066328d26892c27c3883605a06
ms.contentlocale: pt-br
ms.lasthandoff: 07/07/2017


---


# <a name="source-environment-expectations"></a>Expectativas para o Ambiente de Origem
Quando você usa o [Benefício do FastTrack Center para EMS (Enterprise Mobility + Security)](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) para tornar o Microsoft Azure Active Directory Premium e o Microsoft Intune prontos para uso, seu ambiente precisa atender às expectativas descritas nas seções a seguir.

Talvez você já tenha o Microsoft Active Directory local em seu ambiente atual e queira integrá-lo com o EMS ou com qualquer um de seus serviços individuais a fim de aproveitar o gerenciamento avançado de identidade em um único console. O Benefício do FastTrack Center ajuda você a integrar o Azure AD com a implementação local existente. Se a integração for necessária, seu ambiente de origem precisará atender ao nível mínimo desse aplicativo.

A tabela a seguir mostra o que é esperado do seu ambiente de origem existente para integração.

|Atividade|Expectativa para o ambiente de origem|
|------------|----------------------------------|
|Integração de núcleo|Florestas do Active Directory com o nível funcional de floresta definido como Windows Server 2008 ou superior, com a seguinte configuração de floresta:<br /><br />-   Floresta única do Active Directory<br />-   Várias florestas do Active Directory </br></br>**Observação**: para todas as configurações com várias florestas, a implantação do AD FS (Serviços de Federação do Active Directory) está fora do escopo do Benefício do FastTrack Center.|
|Integração do Azure AD Premium|O Active Directory local e seu ambiente foram preparados para o Azure AD Premium, que inclui a correção dos problemas identificados que poderiam impedir a integração com o Azure AD e os recursos do Azure AD Premium.|
|Intune, somente em nuvem ou integrado ao System Center Configuration Manager, integração|Para gerenciamento de dispositivos com o Configuration Manager 2012 R2 ou posterior, conectado ao Intune, os administradores de TI precisam seguir a [Lista de verificação do administrador: configurando o Configuration Manager para gerenciar dispositivos móveis usando o Microsoft Intune](https://technet.microsoft.com/library/jj943763.aspx).</br></br> **Observação**: o benefício de serviço não inclui assistência para configurar ou atualizar o Configuration Manager para os requisitos mínimos necessários para a integração do Microsoft Intune com o Configuration Manager.</br></br>Para implantação de perfil de Wi-Fi e VPN, os administradores de TI precisam ter autoridade de certificação existente, infraestruturas de Wi-Fi e VPN já em funcionamento nos ambientes de produção.</br></br> **Observação**: o benefício do serviço não inclui assistência para instalação ou configuração de autoridades de certificação, infraestruturas de Wi-Fi ou VPN. |
|Experiência de administração do Intune no Azure | Em dezembro de 2016, Microsoft Intune [anunciou](https://blogs.technet.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) a visualização pública da sua nova experiência de admin do Intune no Portal do Azure (portal.azure.com), conhecida como Intune no Azure.<br><br>Durante o período de visualização pública, será fornecido suporte de integração para o Intune no Azure apenas como um melhor esforço. O suporte à integração total continuará para o console administrativo existente (manage.microsoft.com).<br><br>O FastTrack dará suporte total ao Intune na experiência do Azure quando ele for disponibilizado mais tarde, ainda este ano.


**Quer saber mais?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)

