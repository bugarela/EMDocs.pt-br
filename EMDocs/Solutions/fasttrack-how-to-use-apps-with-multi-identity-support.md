---
title: "Como usar aplicativos com suporte para várias identidades"
description: "Como usar aplicativos com suporte para várias identidades"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586ecd93-b097-42a0-9229-bcf3b781021c
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: dab9c133dd5a79afef07291405c2ac25218ca715
ms.openlocfilehash: 597e1e4bf5d910a3339c8239efafda29b1463652


---

# <a name="how-to-use-apps-with-multi-identity-support"></a>Como usar aplicativos com suporte para várias identidades

Neste cenário, estamos usando o Microsoft Word como exemplo. Você pode aplicar estas mesmas etapas para outros aplicativos incluídos no Office 365.
1.  Abra o aplicativo **Word** em seu dispositivo. Neste exemplo, estamos usando um dispositivo iOS.
2.  Toque em **Novo** para criar um novo documento do Word.

  ![Captura de tela mostrando que o usuário deve selecionar "Novo" para criar um documento do Word.](./media/ft-multiID-1-createDoc.png)

3.  Digite uma frase de sua escolha e toque em **Salvar**. Você verá duas opções de local em que deseja salvar o documento: o local pessoal e o local de trabalho. As políticas de aplicativo não estão ativas neste estágio, uma vez que ainda não estabelecemos se o documento é de uso pessoal ou de trabalho.

  ![Captura de tela mostrando que o usuário digitou uma frase no novo documento do Word.](./media/ft-multiID-2-saveDoc.png)

4.  Salve o documento em seu **local de trabalho**, como o OneDrive for Business. Como o OneDrive for Business é reconhecido como seu local de trabalho, o documento agora está marcado como dados da empresa e as restrições de política serão aplicadas.
5.  Agora, abra o documento que você acabou de salvar em seu local de trabalho e copie o texto. Abra sua conta pessoal do **Facebook** e tente colar o texto copiado. Você não poderá colar o conteúdo em uma nova postagem do Facebook. A opção de colar não está desativada, mas nada acontece quando você pressiona **Colar**. Isso acontece porque as restrições de política impedem que dados corporativos sejam compartilhados em aplicativos pessoais.

  ![Captura de tela mostrando que o usuário está copiando texto do documento do Word. ](./media/ft-multiID-3-copyText.png)

  ![Captura de tela mostrando que o usuário não está conseguindo colar o texto no Facebook.](./media/ft-multiID-4-pasteInFB.png)
6.  Em seguida, crie outro novo documento do Word, repetindo as etapas 2 e 3. Digite uma frase de sua escolha e, desta vez, salve-o em seu local pessoal, como **OneDrive – pessoal**. O documento está marcado como pessoal e restrições de políticas corporativas não se aplicam.

  ![Captura de tela mostrando que o usuário digitou uma frase no novo documento do Word.](./media/ft-multiID-5-createDoc.png)

7.  Abra o documento que você acabou de salvar em seu local pessoal e copie o texto. Novamente, abra o **Facebook** e cole o texto copiado. Uma vez que o documento está marcado como pessoal, você poderá colar o conteúdo em uma postagem de Facebook.

  ![Captura de tela mostrando que o usuário conseguiu colar o texto no Facebook.](./media/ft-multiID-6-copyText.png)

### <a name="want-to-learn-more"></a>Quer saber mais?
Consulte [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).



<!--HONumber=Nov16_HO3-->


