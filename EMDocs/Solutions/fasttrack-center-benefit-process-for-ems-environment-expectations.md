---
title: Expectativas para o Ambiente de Origem
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 10/02/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 323bdb56b3d81eb6a63e266899427672abf79da4
ms.openlocfilehash: cd295135195fe96a53a49d47b9e982fe3ba8600c


---


# Expectativas para o Ambiente de Origem
Quando você usa o [Benefício do FastTrack Center para EMS (Enterprise Mobility + Security)](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) para tornar o Azure Active Directory Premium e/ou o Microsoft Intune prontos para uso, seu ambiente precisa atender às expectativas descritas nas seções a seguir.

Talvez você já tenha o Microsoft Active Directory local em seu ambiente atual e você queira integrá-lo com o EMS ou com qualquer um de seus serviços individuais a fim de aproveitar o gerenciamento avançado de identidade de um único console. O benefício do FastTrack Center inclui ajudá-lo a integrar o Microsoft Azure Active Directory com a implementação local existente. Se a integração for necessária, seu ambiente de origem deve estar em um nível mínimo para esse aplicativo.

A tabela a seguir mostra o que é esperado do seu ambiente de origem existente para integração.

|Atividade|Expectativa para o ambiente de origem|
|------------|----------------------------------|
|Integração de núcleo|Florestas do Active Directory com o nível funcional de floresta definido como Windows Server 2008 ou superior, com a seguinte configuração de floresta:<br /><br />-   Floresta única do Active Directory<br />-   Várias florestas do Active Directory </br></br>**Observação**: para todas as configurações com várias florestas, a implantação do AD FS está fora do escopo para o Benefício do FastTrack Center.|
|Integração do Microsoft Azure Active Directory Premium|O Active Directory e o ambiente local foram preparados para o Azure Active Directory Premium, que inclui a correção dos problemas identificados que poderiam impedir a integração com o Azure Active Directory e os recursos do Azure Active Directory Premium.|
|Microsoft Intune, somente nuvem ou integrado ao System Center Configuration Manager, integração|Para gerenciamento de dispositivos com o System Center Configuration Manager 2012 R2 ou posterior conectado ao Microsoft Intune, os administradores de TI precisam seguir a [Lista de verificação do administrador: configurando o Configuration Manager para gerenciar dispositivos móveis usando o Microsoft Intune](https://technet.microsoft.com/library/jj943763.aspx).</br></br> **Observação**: o benefício do serviço não inclui assistência para configurar ou atualizar o System Center Configuration Manager aos requisitos mínimos necessários para o Microsoft Intune integrado com o System Center Configuration Manager.|

**Quer saber mais?**

[Enterprise Mobility + Security](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)


<!--HONumber=Oct16_HO1-->


