---
title: Como usar aplicativos móveis que sua organização gerencia
description: Como usar aplicativos móveis gerenciados pela sua organização
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 174348f0-dbc6-4204-8626-3c6f38b7bbde
ms.reviewer: ''
ms.suite: ems
ms.openlocfilehash: 30b9009b0321de26d3c78bf8876b3456eec350c6
ms.sourcegitcommit: 4401a878f88cc60b3cfd90a915747fe37e333014
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2018
ms.locfileid: "30848148"
---
# <a name="how-to-use-mobile-apps-managed-by-your-organization"></a>Como usar aplicativos móveis gerenciados pela sua organização

## <a name="accessing-onedrive-on-an-ios-device"></a>Acessando o OneDrive em um dispositivo iOS

Esta seção usa o OneDrive for Business como exemplo para demonstrar como a experiência do usuário pode mudar ligeiramente em um aplicativo gerenciado pelo Intune.

1. Inicie o aplicativo **OneDrive for Business** para abrir a página de logon.

   ![Captura de tela mostrando a página de logon do OneDrive for Business para o iOS.](./media/ft-useMngdApps-1-launchOnedrive.png)
   > [!NOTE]
   > Em um dispositivo pessoal, normalmente o usuário final deve baixar o aplicativo. Se o dispositivo for gerenciado por uma solução MDM, você pode implantar o aplicativo no dispositivo.

2. Digite seu nome de usuário da conta corporativa. Você será redirecionado para a página de **autenticação do O365** para inserir suas credenciais de trabalho.

   ![Captura de tela mostrando um usuário do iOS digitando suas credenciais na página de entrada do Office 365.](./media/ft-useMngdApps-2-enterName.png)
3. Depois que as credenciais forem autenticadas com êxito pelo Azure AD, as políticas de MAM serão aplicadas e você deverá será solicitado a reiniciar o aplicativo **OneDrive for Business**.

   ![Captura de tela mostrando que o OneDrive deve ser reiniciado.](./media/ft-useMngdApps-3-restart.png)
   > [!NOTE]
   > A caixa de diálogo de reinício necessário é exibida somente em dispositivos que não estão registrados no Intune.

4. Inicie novamente o aplicativo **OneDrive for Business**. O aplicativo é iniciado com as políticas de MAM ativadas. Agora você deverá definir um **PIN** para o aplicativo. (se você tiver configurado a política para isso).

   ![Captura de tela solicitando que usuário do iOS defina um PIN para o aplicativo.](./media/ft-useMngdApps-4-enterPIN.png)
5. Depois de definir e confirmar o PIN, você poderá acessar os arquivos no seu **OneDrive for Business**.

   ![Captura de tela mostrando vários arquivos acessíveis no OneDrive for Business no iOS.](./media/ft-useMngdApps-5-accessFiles.png)
   > [!NOTE]
   > Quando você altera uma política implantada, as alterações serão aplicadas da próxima vez que abrir o aplicativo.

## <a name="accessing-onedrive-on-an-android-device"></a>Acessando o OneDrive em um dispositivo Android
Esta seção usa o OneDrive for Business como exemplo para demonstrar como a experiência do usuário pode mudar ligeiramente em um aplicativo gerenciado pelo Intune.
1. Inicie o aplicativo **OneDrive for Business** para abrir a página de logon.
   > [!NOTE]
   > Em um dispositivo pessoal, normalmente o usuário final deve baixar o aplicativo. Se o dispositivo for gerenciado por uma solução MDM, você pode implantar o aplicativo no dispositivo.

2. Digite seu nome de usuário da conta corporativa. Você será redirecionado para a página de autenticação do O365 para inserir suas credenciais de trabalho.

   ![Captura de tela mostrando um usuário do Android digitando suas credenciais na página de entrada do Office 365.](./media/ft-useMngdApps-6-enterCreds.png)
3. Depois que as credenciais forem autenticadas com êxito pelo Azure AD, você verá uma mensagem com instruções para instalar o aplicativo do portal da empresa, se ele já não estiver instalado no dispositivo. Toque em **Obter o aplicativo** para continuar.
   > [!NOTE]
   > O aplicativo Portal da Empresa é necessário para todos os aplicativos associados a políticas de MAM em dispositivos Android. Para dispositivos não registrados no Intune, o aplicativo deve ser instalado no dispositivo, mas não precisa inicialização ou autenticação no aplicativo.

4. Agora você estará na loja do **Google Play** , em que poderá baixar e instalar o aplicativo do **Portal da Empresa** .

   ![Captura de tela solicitando que o usuário do Android acesse a Google Play Store para obter o Portal da Empresa do Intune.](./media/ft-useMngdApps-7-installPortal.png)

   O aplicativo de Portal da Empresa ajuda a manter os dados seguros e protegidos.
   ![Captura de tela solicitando que o usuário do Android instale o Portal da Empresa do Intune.](./media/ft-useMngdApps-8-intunePortal.png)
5. Depois de concluir a instalação, escolha **Aceitar** para aceitar os termos.
6. O aplicativo **OneDrive for Business** é iniciado automaticamente.
7. Na próxima vez que abrir o OneDrive for Business, você verá o prompt para definir um **PIN**, desde que as configurações de política tenham sido definidas para exigir um PIN para acessar o aplicativo **OneDrive for Business**.

   ![Captura de tela solicitando que o usuário do Android defina um PIN para o aplicativo](./media/ft-useMngdApps-9-setNewPIN.png)
8. Depois que o PIN for definido e confirmado, você poderá continuar usando o **OneDrive for Business**, agora gerenciado por políticas de aplicativo.

### <a name="want-to-learn-more"></a>Quer saber mais?
Consulte [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).
