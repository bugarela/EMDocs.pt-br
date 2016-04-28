---
# required metadata

title: Usar acesso condicional no Exchange Online e no local com o Microsoft Intune e o Configuration Manager
description:
keywords:
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 5ccd033f-bc31-4fae-b6bf-9e1c2722627f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Implantar o Exchange Online e local com o Microsoft Intune e o Configuration Manager
Agora que leu as [diretrizes de arquitetura para proteger emails e documentos da empresa](../Solutions/architecture-guidance-for-protecting-company-email-and-documents.md), você está pronto para prosseguir com a implantação de uma solução.

Um ambiente no qual ambos os Exchange local e o Exchange Online são usados para gerenciar perfis de email proporciona a capacidade de estender a experiência repleta de recursos e o controle administrativo que têm em sua organização para o Microsoft Exchange local existente na nuvem. Esse tipo de implantação "híbrida" fornece a aparência simplificada de uma única organização do Exchange entre uma organização local do Exchange Server 2013 e o Exchange Online no Microsoft Office 365. Além disso, esse tipo de implantação pode servir como uma etapa intermediária para migrar completamente para uma organização do Exchange Online.

Se já estiver usando o Configuration Manager, bem como uma coexistência entre o Exchange local e o Exchange Online, você pode incorporar o Intune para gerenciar o acesso ao email e proteger os dados de email em dispositivos móveis. Você pode implementar essa solução seguindo as instruções acima para a implementação de cada solução separadamente.

## Pré-requisitos
Para configurar um tipo de coexistência de ambiente que implementa ambos o Exchange local e o Exchange Online, sua organização do Exchange existente deve atender a certos requisitos. Se você não atender a esses requisitos, não será possível concluir as etapas necessárias para configurar uma implantação híbrida entre sua organização do Exchange local e a organização do Exchange Online no Microsoft Office 365.

Consulte os [Pré-requisitos de implantação híbrida](https://technet.microsoft.com/en-us/library/hh534377.aspx) para examinar os requisitos para criar e configurar esse tipo de ambiente.

## Etapas de Implantação
Para implantar uma solução de coexistência, siga as etapas acima para implantar as soluções do [Exchange Server local](../Solutions/conditional-access-intune-configmgr-exchange.md) e do [Exchange Online](../Solutions/conditional-access-intune-configmgr-exchange-online.md).

## Onde ir daqui
Depois que tiver implantado uma solução para proteger emails corporativos e dados de emails em dispositivos móveis, você poderá aprender mais sobre a [experiência de acesso condicional do usuário final](../Solutions/end-user-experience-conditional-access.md). Isso ajudará a preparar você para problemas que possam surgir quando os usuários finais registrarem seus dispositivos específicos.


<!--HONumber=Apr16_HO2-->


