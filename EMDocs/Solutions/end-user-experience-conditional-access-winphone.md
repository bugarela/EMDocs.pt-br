---
title: "Experiência do usuário final para acesso condicional em dispositivos Windows Phone"
description: "A experiência do usuário final de registrar um Windows Phone."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 906566e0-f05e-4af5-b4d5-0efb083dca76
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 2342889a686db8a6496c97979cb222af8347241a
ms.openlocfilehash: e498fd2a1efea2ef6416185c5ce63223004805c6
ms.contentlocale: pt-br
ms.lasthandoff: 01/05/2017


---

# <a name="windows-phone"></a>Windows Phone

O processo de registro e as telas que o usuário vê serão um pouco diferentes dependendo da versão do sistema operacional em execução no dispositivo do usuário final.  Este tópico descreve a experiência do usuário final para registrar dispositivos Windows Phone.

## <a name="enrolling"></a>Registro

1.  Se um usuário já estiver registrado no Intune e for compatível, ele não verá nenhuma diferença em dispositivos do Windows: o acesso aos emails continuará normalmente. Os usuários ainda não registrados no Intune receberão um email de quarentena semelhante a este exemplo:

    ![Captura de tela mostrando email em quarentena que o usuário recebe em um Windows Phone](./media/ProtectEmail/EUX-Windows-quarantineEmail.png)

    A usuário clica em **Comece agora mesmo** para começar a registrar seus dispositivos.

2.  Na tela de Configuração de Acesso da Empresa, o usuário clica em **Iniciar** para começar a configurar seu dispositivo e verificar se ele é compatível.

    ![Captura de tela mostrando a tela Configuração de Acesso da Empresa em um Windows Phone](./media/ProtectEmail/EUX-Windows1-company-Access-Setup.png)

3.  Na tela Registre Seu Dispositivo, o usuário clica em **Confirmar Registro** para registrar seu dispositivo.

    ![Captura de tela mostrando a tela Registro do Dispositivo em um Windows Phone](./media/ProtectEmail/EUX-Windows3-enroll-Device.png)

    Durante o registro, o perfil de Gerenciamento de Dispositivo Móvel é instalado para permitir que você, o administrador de TI, gerencie remotamente o dispositivo. O usuário pode ser solicitado a aceitar um certificado de autorização de Ingresso do Local de Trabalho.

    ![Captura de tela mostrando Ingresso no local de trabalho em um Windows Phone](./media/ProtectEmail/EUX-Windows4-workplaceJoin1.png)

4.  O usuário faz logon usando seu endereço de email usado com o Office. Depois de conectados, talvez seja necessário clicar em **Confirmar Registro** mais uma vez para continuar a registrar seu dispositivo.

    ![Captura de tela mostrando Ingresso no local de trabalho em andamento em um Windows Phone](./media/ProtectEmail/EUX-Windows5-workplaceJoin2.png)

    O dispositivo é verificado para ver se ele está registrado.

    ![Captura de tela mostrando que o registro do dispositivo começa em um Windows Phone](./media/ProtectEmail/EUX-Windows6-checking-Enrollment.png)

5.  O usuário conclui então o processo de registro selecionando seu dispositivo e clicando em **Selecionar**. Se seu dispositivo não for exibido, é possível selecionar **Meu dispositivo não está listado** para tentar novamente.

    ![Captura de tela mostrando que o usuário deve confirmar seu dispositivo para um Windows Phone](./media/ProtectEmail/EUX-Windows7-confirm-Device.png)

    O dispositivo é verificado para confirmar se ele é compatível com as políticas da empresa.

    ![Captura de tela mostrando que um Windows Phone está sendo verificado quanto à conformidade](./media/ProtectEmail/EUX-Windows9-checking-Compliance.png)

6.  Se houver um problema de conformidade, será solicitado que o usuário resolva o problema (como criar uma senha válida) e, em seguida, clique em **Verificar Conformidade** para continuar.

    ![Captura de tela mostrando que o usuário deve resolver problemas de conformidade em um Windows Phone](./media/ProtectEmail/EUX-Windows13-resolve-Compliance.png)

    Depois que a conformidade for verificada, o usuário verá que o registro está sendo ativado.

    ![Captura de tela mostrando que a ativação do registro começa em um Windows Phone](./media/ProtectEmail/EUX-Windows10-activating-Enrollment.png)

7.  O registro é ativado e o usuário clica em **Continuar** para concluir o processo. O usuário clica em **Concluído** para sair da configuração.

    ![Captura de tela mostrando que a configuração de acesso está concluída em um Windows Phone](./media/ProtectEmail/EUX-Windows11-COMPLETE.png)

    Depois que o usuário estiver registrado e a conformidade for verificada, o acesso ao email deverá ficar disponível dentro de alguns minutos.

Se o usuário seguir essas etapas para registrar e ficar compatível e ainda não puder acessar seus emails no dispositivo móvel, ele poderá seguir estas etapas adicionais para tentar corrigir o problema:

-   Primeiro, verifique se seu dispositivo está registrado. Caso contrário, o usuário deve seguir as etapas acima.

-   Verifique se o dispositivo é compatível clicando em **Verificar conformidade**. Se um erro de conformidade for identificado, o usuário poderá seguir as instruções específicas para seu dispositivo móvel sobre como resolvê-la, tal como redefinir sua senha.

-   Ligue para o suporte técnico.

## <a name="issues-and-solutions"></a>Problemas e soluções
Por padrão, a cada 8 horas os dispositivos são verificados para verificar se eles ainda são compatíveis. Se um dispositivo que era anteriormente compatível for considerado incompatível (por exemplo, devido a uma política de conformidade ter sido adicionada ou alterada), o usuário pode seguir estas etapas para restaurar a conformidade do dispositivo:

1.  O usuário recebe a notificação por email ou em seu dispositivo que este é incompatível. Neste momento, o dispositivo está em quarentena no Exchange.

2.  Se o usuário tentar acessar o email, ele será redirecionado para a tela de Configuração de Acesso da Empresa do Portal da Empresa do Intune em que se é mostrado se eles estão fora de conformidade.

    ![Captura de tela mostrando que um Windows Phone se tornou não compatível](./media/ProtectEmail/EUX-Windows14-OutOfCompliance.png)

3.  A usuário clica em **Continuar** e o problema de conformidade que está impedindo que ele acesse o email é mostrado.

4.  Depois que o problema foi corrigido, eles devem clicar em **Verificar Conformidade** para verificar se o problema foi resolvido.

5.  Se o problema estiver corrigido, o usuário clica em **Continuar** para concluir o processo. O acesso ao email deverá ficar disponível novamente dentro de alguns minutos.

### <a name="where-to-go-from-here"></a>Onde ir daqui
A experiência do usuário final é um pouco diferente em outros dispositivos móveis. Saiba mais sobre a experiência do usuário final para [Android](end-user-experience-conditional-access-android.md) e [iOS](end-user-experience-conditional-access-ios.md).

