---
title: "Experiência do usuário final de MAM"
description: "Experiência do usuário final das políticas de gerenciamento de aplicativo móvel."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: bbc9f6ea-fc92-468d-bb5b-60c67949ca28
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 55a3dbe32e3b5e10e21a6d99bc101ec76fc51f5e
ms.openlocfilehash: 38a642c24e506d1528f0e79ad26fa77a50a4fed6


---

# Experiência do usuário final das políticas de gerenciamento de aplicativo móvel
As políticas de MAM são aplicadas somente quando os aplicativos são usados no contexto de trabalho. Leia os cenários de exemplo a seguir para ajudar a instruir seus usuários para que eles compreendam como os aplicativos gerenciados funcionam.

Esta seção fornece exemplos das seguintes experiências do usuário final:

- Cenário: acessando o OneDrive em um dispositivo iOS
- Cenário: acessando o OneDrive em um dispositivo Android

Para obter informações sobre outras experiências específicas do usuário final, veja os seguintes artigos:

- [Usando aplicativos com suporte a várias identidades](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#using-apps-with-multi-identity-support)
- [Gerenciar contas de usuário](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#managing-user-accounts)
- [Exibindo arquivos de mídia com o aplicativo de compartilhamento do Rights Management](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app)

## Cenário: acessando o OneDrive em um dispositivo iOS

1. O usuário inicia o aplicativo **OneDrive** para abrir a página de entrada.
> [!NOTE]
> Em um dispositivo pessoal, normalmente o usuário final deve baixar o aplicativo. Se o dispositivo for gerenciado por uma solução MDM, você pode implantar o aplicativo no dispositivo.

2. O usuário digita seu nome de usuário da conta de trabalho e é redirecionado para a página de **Autenticação do O365** para inserir as credenciais de trabalho.

  Depois que as credenciais são autenticadas com êxito pelo Azure AD, as políticas de MAM são aplicadas.
3. O usuário é solicitado a definir um **PIN** para o aplicativo (se você tiver configurado a política para isso).

4.  Quando o PIN é definido e confirmado, o usuário pode acessar os arquivos em seu **OneDrive for Business**.
> [!NOTE]
> Quando você altera uma política implantada, as alterações são aplicadas da próxima vez que você abrir o aplicativo.

## Cenário: acessando o OneDrive em um dispositivo Android
1. O usuário inicia o aplicativo **OneDrive** para abrir a página de entrada.
> [!NOTE]
> Em um dispositivo pessoal, normalmente o usuário final deve baixar o aplicativo. Se o dispositivo for gerenciado por uma solução MDM, você pode implantar o aplicativo no dispositivo.

2.  O usuário digita seu nome de usuário da conta de trabalho e é redirecionado para a página de **Autenticação do O365** para inserir as credenciais de trabalho.

  Depois que as credenciais são autenticadas com êxito pelo Azure AD, as políticas de MAM são aplicadas.

3.  O aplicativo **OneDrive** é iniciado automaticamente e o usuário é solicitado a definir um **PIN**, desde que as configurações de política tenham sido definidas para exigir um **PIN** para acessar o aplicativo **OneDrive**.

4.  Depois que o PIN for definido e confirmado, o usuário poderá continuar usando o **OneDrive**, agora gerenciado por políticas de aplicativo.

## Onde ir daqui
Há outras experiências do usuário final que você pode ler, incluindo [Usando aplicativos com suporte a várias identidades](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#using-apps-with-multi-identity-support), [Gerenciando contas de usuário](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#managing-user-accounts) e [Exibindo arquivos de mídia com o aplicativo de compartilhamento Rights Management](https://docs.microsoft.com/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app).



<!--HONumber=Aug16_HO1-->


