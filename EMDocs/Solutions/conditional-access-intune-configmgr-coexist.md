---
title: Acesso condicional no Exchange com o Intune e o Configuration Manager
description: "Use uma coexistência do Exchange local e Exchange Online juntamente com o Configuration Manager e o Intune para gerenciar o acesso ao email e proteger os dados de email em dispositivos móveis."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 5ccd033f-bc31-4fae-b6bf-9e1c2722627f
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 026e6701b635a3b05753404fd064fee5bf10147e
ms.openlocfilehash: 8d1e7f6bf8d798dee570d970c30e98974f9bd5be


---

# Implantar o Exchange Online e local com o Microsoft Intune e o Configuration Manager
Agora que você leu as [diretrizes de arquitetura para proteger emails e documentos da empresa](architecture-guidance-for-protecting-company-email-and-documents.md), está pronto para prosseguir com a implantação de uma solução.

Um ambiente no qual ambos os Exchange local e o Exchange Online são usados para gerenciar perfis de email proporciona a capacidade de estender a experiência repleta de recursos e o controle administrativo que têm em sua organização para o Microsoft Exchange local existente na nuvem. Esse tipo de implantação "híbrida" fornece a aparência simplificada de uma única organização do Exchange entre uma organização local do Exchange Server 2013 e o Exchange Online no Microsoft Office 365. Além disso, esse tipo de implantação pode servir como uma etapa intermediária para migrar completamente para uma organização do Exchange Online.

Se já estiver usando o Configuration Manager, bem como uma coexistência entre o Exchange local e o Exchange Online, você pode incorporar o Intune para gerenciar o acesso ao email e proteger os dados de email em dispositivos móveis. Você pode implementar essa solução seguindo as instruções acima para a implementação de cada solução separadamente.

## Pré-requisitos
Para configurar um tipo de coexistência de ambiente que implementa ambos o Exchange local e o Exchange Online, sua organização do Exchange existente deve atender a certos requisitos. Se você não atender a esses requisitos, não será possível concluir as etapas necessárias para configurar uma implantação híbrida entre sua organização do Exchange local e a organização do Exchange Online no Microsoft Office 365.

Consulte os [Pré-requisitos de implantação híbrida](https://technet.microsoft.com/en-us/library/hh534377.aspx) para examinar os requisitos para criar e configurar esse tipo de ambiente.

## Etapas de Implantação
Para implantar uma solução de coexistência, siga as etapas acima para implantar as soluções [Exchange Server local](conditional-access-intune-configmgr-exchange.md) e [Exchange Online](conditional-access-intune-configmgr-exchange-online.md).

## Onde ir daqui
Depois de implantar uma solução para proteger email corporativo e dados de email em dispositivos móveis, você poderá aprender mais sobre a [experiência de acesso condicional do usuário final](end-user-experience-conditional-access.md). Isso ajudará a preparar você para problemas que possam surgir quando os usuários finais registrarem seus dispositivos específicos.



<!--HONumber=Aug16_HO1-->


