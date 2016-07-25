---
title: Usar o acesso condicional com o Microsoft Intune
description: "Use o acesso condicional no Intune para ajudar a proteger emails e outros serviços."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 28662db2-faea-425f-ada9-04cf1d976fc2
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7c389de59d0ca6b33fbd4d872cb77236930d55bf
ms.openlocfilehash: 4cdcef9c5c38cf4b4294dde581a0c2864b5ba043


---

# Usar o acesso condicional com o Microsoft Intune
Essa solução permite usar o acesso condicional no Intune para ajudar a proteger emails e outros serviços de acordo com as condições especificadas.

Confira [Restringir o acesso a email e serviços do O365 com o Microsoft Intune](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) para saber mais sobre como usar o recurso de acesso condicional com o Intune.

> [!TIP]
> Obtenha uma cópia baixável deste tópico completo na [Galeria do TechNet](https://gallery.technet.microsoft.com/protect-company-data-and-8c5e08b4).

## Antes de começar
Você pode controlar o acesso ao Exchange Online e ao Exchange local nos seguintes aplicativos de email:

-   O aplicativo interno para Android 4.0 e posterior, Samsung Knox 4.0 Standard e posterior

-   O aplicativo interno para iOS 7.1 e posterior

-   O aplicativo interno para Windows Phone 8.1 e posterior

-   O aplicativo de email do Windows 8.1 e posterior

-   O aplicativo Microsoft Outlook para Android e iOS (para o Exchange Online somente)

Antes de começar a usar o acesso condicional, certifique-se de que você tenha os requisitos corretos definidos:

## Para o Exchange Online
O Acesso condicional ao Exchange Online dá suporte a dispositivos que executam:

-   Windows 8.1 e posterior (quando registrado no Intune)

-   Windows 7.0 ou posterior (quando ingressado no domínio)

-   Windows Phone 8.1 e posterior

-   iOS 7.1 e posterior

-   Android 4.0 e posterior, Samsung Knox Standard 4.0 e posterior

Além disso, os dispositivos devem ser registrados no AAD DRS (Serviço de Registro de Dispositivo do Azure Active Directory).

O AAD DRS será ativado automaticamente para clientes do Intune e do Office 365. Clientes que já tiverem implantado o Serviço de Registro de Dispositivos do ADFS não verão dispositivos registrados no seu Active Directory local.

-   Você deve usar uma assinatura do Office 365 que inclui o Exchange Online (como E3) e os usuários devem ser licenciados para o Exchange Online.

-   O **Microsoft Intune Service to Service Connector** conecta o Intune ao Microsoft Exchange Online e ajuda a gerenciar informações de dispositivos por meio do console do Intune (confira [Mobile device management with Exchange ActiveSync and Microsoft Intune (Gerenciamento de dispositivo móvel usando o Exchange ActiveSync no Microsoft Intune)](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)). O conector não é necessário para usar políticas de conformidade ou políticas de acesso condicional, mas é necessário para executar relatórios que ajudam a avaliar o impacto de acesso condicional.

    Se você configurar o conector, algumas políticas do Exchange ActiveSync do Intune podem ficar visíveis no console do Office, mas não serão definidas como políticas padrão e, portanto, não afetarão os dispositivos.

    > [!IMPORTANT]
    > Não configure o conector de serviço a serviço se você pretende usar o acesso condicional para o Exchange Online e o Exchange local.

    Agora você está pronto para aprender a [implantar o Exchange Online com o Intune](conditional-access-intune-exchange-online.md).

## Para o Exchange Server local
O acesso condicional ao Exchange local é compatível com:

-   Windows 8 e posterior (quando registrado no Intune)

-   Windows Phone 8 e posterior

-   Qualquer dispositivo iOS que usa um cliente de email do Exchange ActiveSync (EAS)

-   Android 4 e posterior

Além disso:

-   A versão do Exchange deve ser Exchange 2010 ou posterior. Há suporte para a configuração de CAS (Servidor de Acesso para Cliente) do servidor Exchange.

    > [!TIP]
    > Se o ambiente do Exchange estiver em uma configuração de servidor CAS, você deverá configurar o Exchange Connector local para apontar para qualquer um dos servidores CAS.

-   O Exchange ActiveSync pode ser configurado com autenticação baseada em certificado ou em entrada de credenciais de usuário.

-   É preciso usar o **Exchange Connector local**, que conecta o Intune ao Microsoft Exchange Server local. Isso permite que você gerencie dispositivos por meio do console do Intune (confira [Mobile device management with Exchange ActiveSync and Microsoft Intune (Gerenciamento de dispositivo móvel usando o Exchange ActiveSync no Microsoft Intune)](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)).

  > [!IMPORTANT]
> Use a versão mais recente do Exchange Connector local. O Exchange Connector local disponível no console do Intune é específico para seu locatário do Intune e não pode ser usado com nenhum outro locatário. Você também deve garantir que o Exchange Connector para seu locatário esteja instalado em exatamente um computador, e não em várias máquinas.

  Agora você está pronto para aprender a [implantar o Exchange Server local com o Intune](conditional-access-intune-exchange.md).



<!--HONumber=Jul16_HO3-->


