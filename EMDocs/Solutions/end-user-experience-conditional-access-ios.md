---
title: "Experiência do usuário final para acesso condicional em dispositivos iOS"
description: 
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 3c641ea8-2c0e-490e-b1de-831336f46d19
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5f1c98cc916bee9bb83249a16a52a5fdd3810142
ms.openlocfilehash: 6ff6f8c66e5b4ed838c72dd06f200118c6461cb0


---

# iOS

O processo de registro e as telas que o usuário vê serão um pouco diferentes dependendo da versão do sistema operacional em execução no dispositivo do usuário final. Este tópico descreve a experiência do usuário final para dispositivos iOS.

## Registro

1.  Se um usuário já estiver registrado no Intune e for compatível, ele não verá nenhuma diferença em dispositivos do iOS: o acesso aos emails continuará normalmente. Se o usuário ainda não estiver registrado, ele verá uma mensagem de quarentena semelhante a este quando iniciar seu aplicativo de email:

    ![Captura de tela mostrando o email em quarentena que o usuário recebe em um dispositivo iOS](./media/ProtectEmail/EUX-iOS-Get-Started.PNG)

    A usuário clica em **Comece agora mesmo** para começar a registrar seus dispositivos.

2.  É solicitado que o usuário instale o aplicativo do Portal da Empresa do Intune na respectiva loja de aplicativos.

    ![Captura de tela mostrando o Portal da empresa do Intune em um dispositivo iOS](./media/ProtectEmail/EUX-iOS-intune-Company-Portal.png)

    Depois de instalado, o usuário abre o aplicativo e entra usando suas credenciais da empresa.

3.  Na tela de Configuração de Acesso da Empresa, o usuário clica em **Iniciar** para começar a configurar seu dispositivo e verificar se ele é compatível.

    ![Captura de tela mostrando a tela Configuração de Acesso da Empresa em um dispositivo iOS](./media/ProtectEmail/EUX-iOS-company-AccessSetup.png)

4.  Na tela de registro do dispositivo, o usuário clica em **Registro** para registrar seu dispositivo.

    ![Captura de tela mostrando a tela Registro do Dispositivo em um dispositivo iOS](./media/ProtectEmail/EUX-iOS-device-Enrollment.png)

    Durante o registro, o perfil de Gerenciamento de Dispositivo Móvel é instalado para permitir que você, o administrador de TI, gerencie remotamente o dispositivo. O usuário insere sua senha se solicitada.

5.  Na tela de Configuração de Acesso da Empresa, o usuário clica em **Continuar** para iniciar a verificação de conformidade do dispositivo.

    ![Captura de tela mostrando que o registro de dispositivo foi bem-sucedido em um dispositivo iOS e o usuário precisa verificar a conformidade](./media/ProtectEmail/EUX-iOS-device-Compliance-Check.png)

    Se houver um problema de conformidade, será solicitado que o usuário resolva o problema (como criar uma senha válida) e, em seguida, clique em **Verificar Conformidade** para continuar.

    ![Captura de tela mostrando que o usuário deve resolver problemas de conformidade em um dispositivo iOS](./media/ProtectEmail/EUX-iOS-check-Compliance.png)

6.  Depois que o dispositivo estiver totalmente compatível, o usuário clica em **Continuar** para continuar.

    ![Captura de tela mostrando que o dispositivo iOS é compatível e a instalação foi concluída](./media/ProtectEmail/EUX-iOS-compliance-Check-Completed.png)

    Depois que o usuário estiver registrado e a conformidade for verificada, o acesso ao email deverá ficar disponível dentro de alguns minutos.

Se o usuário seguir essas etapas para registrar e ficar compatível e ainda não puder acessar seus emails no dispositivo móvel, ele poderá seguir estas etapas adicionais para tentar corrigir o problema:

-   Primeiro, verifique se seu dispositivo está registrado. Caso contrário, o usuário deve seguir as etapas acima.

-   Verifique se o dispositivo é compatível clicando em **Verificar conformidade**. Se um erro de conformidade for identificado, o usuário poderá seguir as instruções específicas para seu dispositivo móvel sobre como resolvê-la, tal como redefinir sua senha.

-   Ligue para o suporte técnico.

## Problemas e soluções
Por padrão, a cada 8 horas os dispositivos são verificados para verificar se eles ainda são compatíveis. Se um dispositivo que era anteriormente compatível for considerado incompatível (por exemplo, devido a uma política de conformidade ter sido adicionada ou alterada), o usuário pode seguir estas etapas para restaurar a conformidade do dispositivo:

1.  O usuário recebe a notificação por email ou em seu dispositivo que este é incompatível. Neste momento, o dispositivo está em quarentena no Exchange.

2.  Se o usuário tentar acessar o email, ele será redirecionado para a tela de Configuração de Acesso da Empresa do Portal da Empresa do Intune em que se é mostrado se eles estão fora de conformidade.

    ![Captura de tela mostrando que o dispositivo iOS se tornou não compatível](./media/ProtectEmail/EUX-iOS-fallOut-Compliance.png)

3.  A usuário clica em **Continuar** e o problema de conformidade que está impedindo que ele acesse o email é mostrado.

    ![Captura de tela mostrando que o usuário deve resolver problemas de conformidade em um dispositivo iOS](./media/ProtectEmail/EUX-iOS-check-Compliance.png)

4.  Depois que o problema foi corrigido, eles devem clicar em **Verificar Conformidade** para verificar se o problema foi resolvido.

5.  Se o problema estiver corrigido, o usuário clica em **Continuar** para concluir o processo.

    ![Captura de tela mostrando que o dispositivo iOS é compatível e a instalação foi concluída](./media/ProtectEmail/EUX-iOS-compliance-Check-Completed.png)

    O acesso ao email deverá ficar disponível novamente dentro de alguns minutos.

### Onde ir daqui
A experiência do usuário final é um pouco diferente em outros dispositivos móveis. Saiba mais sobre a experiência do usuário final para [Android](end-user-experience-conditional-access-android.md) e [Windows Phone](end-user-experience-conditional-access-winphone.md).



<!--HONumber=Jun16_HO4-->


