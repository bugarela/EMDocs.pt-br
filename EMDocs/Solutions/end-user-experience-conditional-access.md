---
title: "Experiência do usuário final para acesso condicional"
description: "A experiência do usuário final de registrar um dispositivo ou corrigir problemas de conformidade."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e186dd2-e17c-40d8-b160-48038b2c6593
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 1daeb790d5e01f0b59829231ce0e0401a9ff749d
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="end-user-experience-of-conditional-access"></a>Experiência do usuário final para acesso condicional
Quando o usuário tenta acessar email no dispositivo pela primeira vez ou sincronizar posteriormente, o status de conformidade e de registro do dispositivo é verificado. O processo de registrar ou corrigir problemas de conformidade é uma experiência guiada. São mostradas ao usuário final as etapas necessárias para registrar o dispositivo e torná-lo compatível sem necessidade de chamar o suporte técnico da TI:

-   **Se o dispositivo não estiver registrado**, a página de logon mostrará o acesso negado e solicitará o registro. No registro, o dispositivo é registrado automaticamente no Active Directory do Azure. O Intune verifica o dispositivo para fins de conformidade e apresenta as etapas de solução para resolver quaisquer problemas de não conformidade. Depois que o dispositivo estiver em conformidade, o Intune define o status de conformidade do dispositivo com o Active Directory do Azure.

-   **Se o dispositivo estiver registrado, mas não estiver em conformidade**, um link com etapas para corrigir os problemas é enviado ao dispositivo. Quando o usuário final corrige o problema (por exemplo, definir senha, criptografia), o Intune que gerencia as políticas de conformidade atualiza o status de conformidade do dispositivo no Azure AD.

Quando o dispositivo é avaliado como registro e em conformidade, a sincronização de email deve acontecer dentro de alguns minutos.

## <a name="android"></a>Android

[Este tópico](end-user-experience-conditional-access-android.md) descreve a experiência de registro após o acesso condicional ser habilitado, e um usuário final tentar acessar emails em seu dispositivo móvel Android.

## <a name="ios"></a>iOS

[Este tópico](end-user-experience-conditional-access-ios.md) descreve a experiência do usuário quando um usuário final tenta acessar um email em seu dispositivo móvel iOS após a habilitação do acesso condicional.

## <a name="windows-phone"></a>Windows Phone

[Este tópico](end-user-experience-conditional-access-winphone.md) descreve a experiência do usuário final após o acesso condicional ser habilitado e um usuário final tentar acessar email em seu Windows Phone.
