---
title: Expectativas para o ambiente de origem
description: "Requisitos de ambiente de origem para usar o Benefício do FastTrack Center"
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/07/2016
ms.topic: article
ms.prod: 
ms.service: ems
ms.technology: 
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 999947648cdf98b94312dfd2e700cc8d74011a99
ms.openlocfilehash: ac5783c0343f1e92dbf6d5f0352ae22591fb7def


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

**Quer saber mais?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)



<!--HONumber=Nov16_HO4-->


