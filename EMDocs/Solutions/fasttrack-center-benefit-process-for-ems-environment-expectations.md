---
title: "Processo do Benefício do FastTrack Center para o Enterprise Mobility Suite - expectativas do ambiente de origem"
description: 
keywords: 
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 9048f3e5-cc28-4744-bb5e-36f974abb261
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a92fcc56cea75adb6c3db4eeb197dba77d2b63b7
ms.openlocfilehash: 5f1ab589594ccd846686e51612fe54f4ffd226b6


---


# Processo do Benefício do FastTrack Center para o Enterprise Mobility Suite - expectativas do ambiente de origem
Quando você usa o [Benefício do FastTrack Center para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-for-enterprise-mobility-suite-ems.md) para preparar o Azure Active Directory Premium, o Microsoft Intune e/ou o Azure Rights Management para uso, seu ambiente precisa atender às expectativas descritas nas seções a seguir.

Para ler sobre as outras partes do processo de integração do FastTrack, confira [Processo do Benefício do FastTrack Center para Enterprise Mobility Suite (EMS)](fasttrack-center-benefit-process-for-enterprise-mobility-suite-ems.md).

Talvez você já tenha o Microsoft Active Directory local em seu ambiente atual e você queira integrá-lo com o EMS ou com qualquer um de seus serviços individuais a fim de aproveitar o gerenciamento avançado de identidade de um único console. O benefício do FastTrack Center inclui ajudar você com a integração do Microsoft Azure Active Directory Premium com sua implementação local existente. Se a integração for necessária, seu ambiente de origem deve estar em um nível mínimo para esse aplicativo.

A tabela a seguir mostra o que é esperado no seu ambiente de origem existente para integração.

|Atividade|Expectativa para o ambiente de origem|
|------------|----------------------------------|
|Integração de núcleo|Florestas do Active Directory com o nível funcional de floresta definido como Windows Server 2008 ou superior, com a seguinte configuração de floresta:<br /><br />-   Floresta única do Active Directory<br />-   Várias florestas do Active Directory </br></br>**Observação**: para todas as configurações com várias florestas, a implantação do AD FS está fora do escopo para o Benefício do FastTrack Center.|
|Integração do Microsoft Azure Active Directory Premium|O Active Directory e o ambiente local foram preparados para o Azure Active Directory Premium, que inclui a correção dos problemas identificados que poderiam impedir a integração com o Azure Active Directory e os recursos do Azure Active Directory Premium.|
|Microsoft Intune, somente nuvem ou integrado ao System Center Configuration Manager, integração|Gerenciamento de dispositivos com o System Center Configuration Manager 2012 R2 ou posterior conectado ao Microsoft Intune, os administradores de TI precisarão seguir a [Lista de verificação do administrador: configuração do Configuration Manager para gerenciar dispositivos móveis usando o Microsoft Intune](https://technet.microsoft.com/library/jj943763.aspx).</br></br> **Observação**: o benefício do serviço não inclui assistência para configurar ou atualizar o System Center Configuration Manager aos requisitos mínimos necessários para o Microsoft Intune integrado com o System Center Configuration Manager.|

Leia sobre a próxima parte do processo de integração do FastTrack: [Fases do processo de integração](fasttrack-center-benefit-process-for-ems-phases.md)

### Quer saber mais?
Confira [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).




<!--HONumber=Jul16_HO3-->


