---
title: Especificar seus requisitos de acesso
description: "Este artigo fornece uma série de requisitos comuns de acesso que devem ser usados em um cenário de gerenciamento de dispositivo móvel."
keywords: 
author: YuriDio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1cdc3cdf-cb71-46d5-99fd-05ec96771b81
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 0eaf680de8a6ad90cc20edd42e8662cde1f928df
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="specify-your-access-requirements"></a>Especificar seus requisitos de acesso

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Um dispositivo móvel que não pode usar aplicativos ou acessar dados da empresa que são necessários para executar o trabalho não é útil para seus funcionários. Portanto, é fundamental entender como os dados serão transmitidos do local de origem (local ou nuvem) para o dispositivo móvel.

Os dados serão transmitidos de e para os dispositivos móveis, e as considerações que devem estar em vigor para cada caminho. Muitas empresas que têm políticas de segurança em vigor ainda não consideraram como os dispositivos móveis podem aumentar a probabilidade de vazamento dos dados corporativos. Portanto, examine as políticas atuais de sua empresa para garantir que os requisitos que você desenvolver para autenticação, autorização e controle de acesso estejam alinhados aos seus requisitos de negócios.

Responda às seguintes perguntas para ajudar a determinar os requisitos de acesso para dispositivos móveis:

- Autenticação e autorização: como parte da estratégia para permitir que os usuários acessem os dados da empresa em dispositivos móveis, você deve identificar quais usuários estão qualificados para o acesso. Algumas empresas decidem inicialmente permitir o acesso a dados apenas para uma parte de seus usuários e, em seguida, conceder acesso a outros funcionários conforme eles solicitarem, com base na necessidade de negócios. Para restringir o acesso, sua solução deve autenticar (identificar se o usuário é quem ele alega ser) e autorizar (avaliar se o usuário deve ter acesso aos dados que está solicitando) de acordo com a política de sua empresa.

Ao projetar sua solução de MDM, considere o seguinte:

- Sua organização tem um serviço de diretório atual que é usado para a autenticação e autorização?
    - Em caso afirmativo, a solução de MDM é integrada ao serviço de diretório para autenticar e autorizar o acesso aos recursos?
    - Sua organização precisa ter a autenticação centralizada ou ela pode ser híbrida?
    - Sua organização pretende ter a autenticação multifator para usuários móveis?
    - Sua organização usa uma PKI (infraestrutura de chave pública) local para emitir certificados?
        - Em caso afirmativo, a solução de MDM tem a capacidade de executar a autenticação usando certificados digitais?
            - Em caso afirmativo, a solução de MDM tem a capacidade de ser integrada a um PKI local existente?
- Sua organização precisa usar os serviços de diretório atuais para autenticar os usuários que acessam aplicativos de terceiros?
    - Em caso afirmativo, a solução de MDM permite que os usuários usem o SSO (logon único) para se autenticarem em aplicativos de terceiros?


**Controle de Acesso**: quando um usuário é autenticado e autorizado, as solicitações de acesso a um recurso devem ser validadas com o nível de acesso do usuário. O recurso solicitado pode ser um aplicativo ou dados. Ao projetar sua solução, considere o seguinte:

- Sua empresa precisa ter um nível diferente de controle para que você gerencie os dispositivos móveis e a solução de MDM?
    - Em caso afirmativo, a solução de MDM dá suporte ao RBAC (Controle de Acesso Baseado em Função)?
- Sua empresa precisa ter diferentes níveis de acesso de acordo com a localização do usuário?
    - Em caso afirmativo, a solução de MDM permite criar restrições de controle de acesso de acordo com a localização do usuário?
- Sua empresa precisa controlar o acesso aos aplicativos?
    - Em caso afirmativo, a solução de MDM permite controlar o acesso aos aplicativos instalados no dispositivo móvel?
- Sua empresa precisa controlar o acesso de acordo com um conjunto de condições?
    - Em caso afirmativo, a solução de MDM permite ter o controle de acesso condicional?
    - Em caso afirmativo, a solução de MDM permite habilitar/desabilitar o recurso do aplicativo de acordo com a identidade do usuário?
    - Em caso afirmativo, a solução de MDM permite que você gerencie o atestado do dispositivo?

Leia [Proteger o acesso aos recursos da empresa de qualquer local, em qualquer dispositivo](https://technet.microsoft.com/library/dn550982) para entender melhor como aproveitar os recursos internos do Windows Server 2012 R2 em conjunto com o ConfigMgr para fornecer acesso aos recursos de sua empresa.
