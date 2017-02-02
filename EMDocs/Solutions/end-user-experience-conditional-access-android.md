---
title: "Experiência do usuário final para acesso condicional em dispositivos Android"
description: "A experiência do usuário final de registrar um dispositivo Android."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0b5e4330-6fa5-445c-b73e-86ce5b9c7964
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2342889a686db8a6496c97979cb222af8347241a
ms.openlocfilehash: fc06debb97cdbd3be1a241a711f36f6c530d65cf


---

# <a name="android"></a>Android

O processo de registro e as telas que o usuário vê serão um pouco diferentes dependendo da versão do sistema operacional em execução no dispositivo do usuário final. Este tópico descreve a experiência do usuário final para registrar dispositivos Android.

## <a name="enrolling"></a>Registro

1.  Ao tentar acessar o email, o usuário primeiro recebe um email de quarentena semelhante a este exemplo:

    ![Captura de tela mostrando o email em quarentena que o usuário recebe em um dispositivo Android](./media/ProtectEmail/EUX-Android-quarantine-Email.png)

    A usuário clica em **Comece agora mesmo** para começar a registrar seus dispositivos.

    > [!NOTE]
    > Se um usuário não tiver definido um navegador padrão para o seu dispositivo, será solicitado durante o registro do dispositivo e a ativação do registro sua permissão para que um link abra uma janela do navegador. Quando solicitado, eles devem selecionar o mesmo navegador todas as vezes ou o processo de registro falhará.

2.  É solicitado que o usuário instale o aplicativo do Portal da Empresa do Intune na respectiva loja de aplicativos.

    ![Captura de tela mostrando o Portal da empresa do Intune em um dispositivo Android](./media/ProtectEmail/EUX-Android-Portal.png)

    Depois de instalado, o usuário abre o aplicativo e entra usando suas credenciais da empresa.

3.  Na tela de Configuração de Acesso da Empresa, o usuário clica em **Iniciar** para começar a configurar seu dispositivo e verificar se ele é compatível.

    ![Captura de tela mostrando a tela Configuração de Acesso da Empresa em um dispositivo Android](./media/ProtectEmail/EUX-Android-company-Access-Setup.PNG)

4.  Na tela de registro do dispositivo, o usuário clica em **Registro** para registrar seu dispositivo.

    ![Captura de tela mostrando a tela Registro do Dispositivo em um dispositivo Android](./media/ProtectEmail/EUX-Android-device-Enroll.png)

5.  Os usuários deverão ativar o administrador do dispositivo clicando em **Ativar** quando solicitado ou o procedimento de registro do dispositivo será cancelado.

    ![Captura de tela mostrando que o usuário deve ativar o administrador do dispositivo em um dispositivo Android](./media/ProtectEmail/EUX-Android-activate-DeviceAdmin.PNG)

    O registro do dispositivo começa. Dependendo do dispositivo, pode aparecer um prompt de instalação do certificado ou um prompt de Política de Privacidade da Samsung KNOX durante o registro. Eles são necessários para permitir que você, o administrador de TI, gerencie remotamente o dispositivo. O dispositivo está registrado no Intune e estabelece uma identidade de dispositivo com o Active Directory do Azure.

    ![Captura de tela mostrando que o registro do dispositivo começa em um dispositivo Android](./media/ProtectEmail/EUX-Android-enrolling-Device.png)

6.  Após o registro ser concluído com êxito, o usuário clica em **Continuar** para iniciar a verificação de conformidade do dispositivo.

    ![Captura de tela mostrando que o registro do dispositivo foi bem-sucedido em um dispositivo Android](./media/ProtectEmail/EUX-Android-enroll-Success.png)

    Se houver um problema de conformidade, será solicitado que o usuário resolva o problema (como criar uma senha válida) e, em seguida, clique em **Verificar Conformidade** para continuar.

    ![Captura de tela mostrando que o usuário deve resolver problemas de conformidade em um dispositivo Android](./media/ProtectEmail/EUX-Android-resolve-Compliance-Issues.png)

7.  Depois que o dispositivo for totalmente compatível, o usuário clica em **Continuar** para iniciar a ativação do registro. Isso conectará a identidade do dispositivo AAD à ID de EAS fornecida pelo Exchange.

    > [!NOTE]
    > No Android, o navegador padrão será exibido por alguns segundos durante a ativação do registro. Se o usuário não estiver selecionado um navegador padrão, será solicitado que ele escolha um navegador. Ao concluir a Configuração de Acesso da Empresa, o mesmo navegador deve ser selecionado pelo usuário sempre que solicitado.

    ![Captura de tela mostrando que o dispositivo Android é compatível](./media/ProtectEmail/EUX-Android-compliance-Successful.PNG)

8.  A ativação do registro será concluída e o usuário clica em **Concluído** para sair do processo de verificação do registro e conformidade.

    ![Captura de tela mostrando que a configuração de acesso da empresa está concluída em um dispositivo Android](./media/ProtectEmail/EUX-Android-all-Successful2.PNG)

    Depois que o usuário estiver registrado e a conformidade for verificada, o acesso ao email deverá ficar disponível dentro de alguns minutos.

Se o usuário seguir essas etapas para registrar e ficar compatível e ainda não puder acessar seus emails no dispositivo móvel, ele poderá seguir estas etapas adicionais para tentar corrigir o problema:

1.  Primeiro, verifique se seu dispositivo está registrado. Caso contrário, o usuário deve seguir as etapas acima.

2.  Verifique se o dispositivo é compatível clicando em **Verificar conformidade**. Se um erro de conformidade for identificado, o usuário poderá seguir as instruções específicas para seu dispositivo móvel sobre como resolvê-la, tal como redefinir sua senha.

3.  Ligue para o suporte técnico.

## <a name="issues-and-solutions"></a>Problemas e soluções
Por padrão, a cada 8 horas os dispositivos são verificados para verificar se eles ainda são compatíveis. Se um dispositivo que era anteriormente compatível for considerado incompatível (por exemplo, devido a uma política de conformidade ter sido adicionada ou alterada), o usuário pode seguir estas etapas para restaurar a conformidade do dispositivo:

1.  O usuário recebe a notificação por email ou em seu dispositivo que este é incompatível. Neste momento, o dispositivo está em quarentena no Exchange.

2.  Quando o usuário tenta acessar o email, ele verá um email de quarentena informando que os problemas de conformidade devem ser corrigido para poder obter acesso. Quando o usuário clica no hiperlink no email de quarentena, este o redireciona para a tela de Configuração de Acesso da Empresa no Portal da Empresa do Intune (via navegador padrão e Google Play) em que se é mostrado que o dispositivo não é compatível.

    ![Captura de tela mostrando que o dispositivo Android se tornou não compatível](./media/ProtectEmail/EUX-Android-outOfCompliance.png)

3.  A usuário clica em **Continuar** e o problema de conformidade que está impedindo que ele acesse o email é mostrado.

    ![Captura de tela mostrando que o usuário deve resolver problemas de conformidade em um dispositivo Android](./media/ProtectEmail/EUX-Android-resolve-Compliance-Issues.png)

4.  Depois que o problema foi corrigido, eles devem clicar em **Verificar Conformidade** para verificar se o problema foi resolvido.

5.  Se o problema estiver corrigido, o usuário clica em **Continuar** para concluir o processo. O acesso ao email deverá ficar disponível novamente dentro de alguns minutos.

### <a name="where-to-go-from-here"></a>Onde ir daqui
A experiência do usuário final é um pouco diferente em outros dispositivos móveis. Saiba mais sobre a experiência do usuário final do [iOS](end-user-experience-conditional-access-ios.md) e [Windows Phone](end-user-experience-conditional-access-winphone.md).



<!--HONumber=Jan17_HO1-->


