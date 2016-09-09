---
title: Usar o acesso condicional com o Intune e Configuration Manager
description: "Implante o Intune com a solução do Configuration Manager."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e65a0662-33ff-4e8c-9305-a21e80ea0f69
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: faa30f461ff9a1a14d150bd85d86d37cd298570c
ms.openlocfilehash: 4d7d429b4c6ede6197501f4035903f23cbe2ade3


---

# Usar o acesso condicional com o Intune e Configuration Manager
Este tópico supõe que você já esteja usando o System Center Configuration Manager e o Microsoft Exchange Server (com implantação local, no Exchange Online ou uma implantação híbrida de ambos) em sua empresa para gerenciar o acesso ao email. Esta solução combina seu ambiente existente do Configuration Manager com o Intune para gerenciar com segurança o acesso ao email em todos os tipos de dispositivos, independentemente da localização.

> [!TIP]
> Obtenha uma cópia baixável deste tópico completo na [Galeria do TechNet](https://gallery.technet.microsoft.com/Deploying-Enterprise-16499404).

## Antes de começar
Antes de começar a usar o acesso condicional, certifique-se de que você tenha os requisitos corretos no lugar:

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

Se seu ambiente incluir o Exchange Online e o Exchange local, você poderá ler sobre [como implantar o Exchange Online e o Exchange local com o Microsoft Intune e o Configuration Manager](conditional-access-intune-configmgr-coexist.md).



<!--HONumber=Sep16_HO1-->


