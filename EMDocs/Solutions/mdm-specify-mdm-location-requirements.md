---
title: "Especificar os requisitos de local do gerenciamento de dispositivos móveis"
description: "Este artigo oferece uma série de requisitos comuns sobre a localização do dispositivo em um cenário de gerenciamento de dispositivo móvel."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c8824726-082e-417a-8522-183a69328ae4
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: cf9b0a04e00ddf991e0f068144a1993f9fb88527


---

# <a name="specify-your-mobile-device-management-location-requirements"></a>Especificar os requisitos de local do gerenciamento de dispositivos móveis

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Os requisitos locais são um dos vários fatores que você deve levar em consideração ao criar sua estratégia de gerenciamento de dispositivos móveis. O local é importante da perspectiva da solução de gerenciamento de dispositivos móveis, bem como do próprio dispositivo. Responda às seguintes perguntas:

- Acompanhar usuários: para alguns tipos de controle de dispositivo móvel, talvez você precise implementar políticas que possam restringir o acesso aos recursos da empresa com base na localização de um usuário.
    - A empresa precisa implementar mecanismos para abranger o isolamento geográfico ou a capacidade de impor políticas com base na localização geográfica do dispositivo? 
    - A empresa precisa controlar a localização geográfica do usuário quando ele acessou um recurso da empresa?
- Modelo de administração: dependendo da solução de gerenciamento de dispositivos móveis que você implantar, a administração poderá ser distribuída em vários sites (locais) ou ser centralizada em um único local. Um site de administração central é adequado para implantações de grande escala e fornece um ponto central de administração e a flexibilidade para fornecer suporte para dispositivos distribuídos por uma infraestrutura de rede global. Um site primário é adequado para implantações menores, embora tenha menos opções para acomodar o crescimento futuro. Determine se o controle de MDM deve ser centralizado ou distribuído.
    - Sua empresa precisa de um modelo de administração centralizada?
    - A solução de gerenciamento de dispositivos precisa estar localizada localmente?
        - Caso contrário, ela pode estar localizada na nuvem?
        - Caso contrário, ela pode ser híbrida?
    - Sua empresa precisa de um modelo descentralizado em que diferentes locais devem ter autonomia sobre a administração do gerenciamento de dispositivos?

>[!TIP] 
> Lembre-se de fazer anotações de cada resposta e entender a lógica por trás da resposta. A próxima seção apresentará as opções disponíveis e as vantagens/desvantagens de cada uma delas.  Ao responder a essas perguntas, você poderá selecionar a solução que melhor atende às suas necessidades de negócios.




<!--HONumber=Nov16_HO4-->


