---
title: "Instruções de registro do usuário final no Intune para administradores de TI"
description: "Instruções de registro do usuário final no Intune para administradores de TI"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c13446e-aa31-47df-ad9d-373be7660197
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2342889a686db8a6496c97979cb222af8347241a
ms.openlocfilehash: 698af6701d756beac696648addbef11d709764fa


---

# <a name="end-user-intune-enrollment-instructions-for-it-administrators"></a>Instruções de registro do usuário final no Intune para administradores de TI

Este documento contém instruções de registro que você pode personalizar e fornecer aos usuários para ajudá-los a registrar seus dispositivos iOS e Android no Microsoft Intune™ (para dispositivos Windows, consulte Usando seu dispositivo Windows com o Intune). Recomendamos que você copie as partes deste documento que considerar mais adequadas para seus usuários. Por exemplo, você pode querer produzir um único documento para cada plataforma de dispositivo ou adicionar mais capturas de tela.

Além dessas instruções escritas, você também pode incluir hiperlinks para qualquer um dos vídeos para o usuário final do Intune, encontrados em [http://aka.ms/IntuneUserVideos](http://aka.ms/IntuneUserVideos).

> [!NOTE]
> Microsoft, Intune e Office 365 são marcas registadas da Microsoft Corporation. iPhone, Mac e Apple são marcas registradas da Apple, Inc. Android é uma marca registrada da Google Inc. Samsung KNOX é uma marca registrada da Samsung Electronics co., Ltd.

## <a name="why-enroll-in-intune"></a>Por que se registrar no Intune
Quando se registra, você pode usar seu dispositivo móvel para acessar arquivos e dados de trabalho ou de estudante. O registro dos dispositivos também permite que o departamento de TI gerencie recursos corporativos ou de estudante e os mantenha seguros, dando-lhe a liberdade de usar seu dispositivo preferido para trabalhar.

Para usar seu dispositivo no trabalho, registre-o no Intune usando o Portal da Empresa. Você poderá, então, encontrar facilmente aplicativos da empresa para instalar, consultar outros dispositivos adicionados e encontrar informações de contato do seu administrador de TI. Você também dará a seu administrador de TI para gerenciar seu dispositivo a fim de ajudar a proteger as informações da empresa contidas nele. Antes de iniciar o registro, confirme se você tem uma boa conexão Wi-Fi ou celular com a Internet.

## <a name="enroll-your-android-device-in-intune-using-the-intune-company-portal-app"></a>Registre seu dispositivo Android no Intune usando o aplicativo Portal da Empresa do Intune

Essas etapas de registro são para dispositivos Samsung Knox Android e dispositivos Android "nativos" (que não são Samsung Knox). Para determinar se você tem um dispositivo Samsung Knox, vá até **Configurações > Sobre o telefone**. Se você não vir a palavra "Knox" listada, terá um dispositivo Android nativo. As telas mostradas em seu dispositivo podem parecer um pouco diferentes das apresentadas nesta seção.

Se receber um erro ao tentar registrar seu dispositivo no Intune, consulte [Enviar erros de registro ao administrador de TI](https://technet.microsoft.com/en-US/library/mt502762(TechNet.10).aspx#BKMK_andr_send_enroll_errors).

Antes ou após o registro, você poderá ser solicitado a escolher uma categoria que melhor descreva como você usa o dispositivo. O administrador de TI usa essa categoria para ajudar a determinar quais aplicativos você terá acesso.
1.  Instale o aplicativo gratuito Portal da Empresa do Microsoft Intune em seu dispositivo na [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Abra o aplicativo Portal da Empresa do Microsoft Intune.
3.  Na tela de **Boas-vindas** do Portal da Empresa, toque em **Entrar** e entre com sua conta corporativa ou de estudante.

  ![Captura de tela mostrando a tela de entrada do Portal da Empresa do Intune em um dispositivo Android](./media/ft-userEnrollAndroid-1-signUp.png)

4.  Se o seu administrador de TI tiver configurado os termos e condições da empresa, toque em **ACEITAR** para aceitar os termos.

  ![Captura de tela pedindo que o usuário aceite os termos e condições em um dispositivo Android](./media/ft-userEnrollAndroid-2-accept.png)
5.  Se estiver usando um dispositivo Android 6.0 ou posterior, siga esta etapa. Caso contrário, vá para a próxima etapa.

  Se o administrador de TI tiver configurado algumas políticas, você poderá ver uma ou as duas mensagens a seguir:

  - Se vir a mensagem **Permitir que o Portal da Empresa acesse seus contatos?**, toque em **PERMITIR**. É seguro tocar em PERMITIR, porque a Microsoft nunca acessa seus contatos! O Google controla o texto da mensagem, então a Microsoft não pode alterá-lo. Quando você permite o acesso, ele só permite que o aplicativo Portal da Empresa acesse logs de dados para ajudar a solucionar problemas no dispositivo.

        ![Captura de tela pedindo ao usuário que permita que o portal acesse os contatos em um dispositivo Android](./media/ft-userEnrollAndroid-3-accessContacts.png)
  - Se ver a mensagem **Permitir que o Portal da Empresa faça e gerencie chamadas?**, toque em **PERMITIR**. É seguro tocar em PERMITIR, porque a Microsoft nunca faz nem gerencia suas chamadas telefônicas! O Google controla o texto da mensagem, então a Microsoft não pode alterá-lo. Ao permitir o acesso, o que você faz é permitir que o aplicativo Portal da Empresa veja seu número de telefone e uma ID chamada IMEI.

        ![Captura de tela pedindo ao usuário que permita que o portal gerencie as chamadas telefônicas em um dispositivo Android](./media/ft-userEnrollAndroid-4-manageCalls.png)

  Se você tocar em **RECUSAR**, as mensagens serão exibidas novamente na próxima vez que você entrar no aplicativo do Portal da Empresa, mas você pode desativar mensagens futuras tocando na caixa de seleção **Nunca Perguntar Novamente**. Se você decidir posteriormente permitir o acesso, acesse **Configurações > Aplicativos > Portal da Empresa > Permissões > Telefone** e ative a permissão.
6.  Conecte-se no aplicativo Portal da Empresa, usando sua conta e senha corporativa ou de estudante e, em seguida, toque em **Entrar**.

  ![Captura de tela pedindo que o usuário entre no portal da empresa em um dispositivo Android](./media/ft-userEnrollAndroid-5-signIn.png)
7.  Na tela Configuração de Acesso da Empresa, toque em **INICIAR**.

  ![Captura de tela mostrando a página Configuração de Acesso da Empresa em um dispositivo Android](./media/ft-userEnrollAndroid-6-beginSetup.png)
8.  Leia sobre o que você pode fazer quando registra seu dispositivo e, em seguida, toque em **CONTINUAR**.

  ![Captura de tela mostrando informações sobre por que você deve registrar um dispositivo Android](./media/ft-userEnrollAndroid-7-whyEnroll.png)
9.  Consulte a lista do que o administrador de TI pode ou não ver em seu dispositivo registrado e toque em **CONTINUAR**.

  ![Captura de tela mostrando a política de privacidade em um dispositivo Android](./media/ft-userEnrollAndroid-8-privacy.png)
10. Examine algumas das coisas que você pode ver depois que tocar em Registrar. Quando terminar a leitura, toque em **REGISTRAR**.

  ![Captura de tela mostrando as próximas etapas de registro em um dispositivo Android](./media/ft-userEnrollAndroid-9-whatNext.png)
11. Na tela Ativar administrador do dispositivo, clique em **ATIVAR**.

  ![Captura de tela solicitando que o usuário ative o administrador do dispositivo em um dispositivo Android](./media/ft-userEnrollAndroid-10-activateAdmin.png)
12. Siga os prompts para inserir um PIN ou senha. Se já tiver configurado um PIN ou senha neste dispositivo, você não verá esta tela ou será solicitado a inserir um novo PIN ou senha.

  ![Captura de tela solicitando que o usuário insira seu PIN em um dispositivo Android](./media/ft-userEnrollAndroid-11-enterPIN.png)
13. Siga as instruções abaixo que corresponde ao tipo de dispositivo que você está usando (Android nativo ou Samsung Knox). Se não tiver um dispositivo Samsung Knox, siga as instruções para o Android nativo. Para determinar se você tem um dispositivo Samsung Knox, vá até **Configurações > Sobre o telefone**. Se você não vir a palavra "Knox" listada, terá um dispositivo Android nativo.
 - Dispositivo nativo (que não é Samsung Knox): na tela **Nome do certificado**, toque em **OK** para aceitar o certificado padrão.

        ![Screenshot prompting the user to accept the default certificate on a native Android device](./media/ft-userEnrollAndroid-12-android.png)
 - Dispositivo Samsung Knox: toque em **CONFIRMAR**

        ![Screenshot prompting the user to confirm the privacy policy for a Samsung Knox device](./media/ft-userEnrollAndroid-13-knox.png)

 Você verá a seguinte mensagem na tela enquanto o Intune registra seu dispositivo.

  ![Captura de tela mostrando que um dispositivo Android está sendo registrado](./media/ft-userEnrollAndroid-14-enrollingDevice.png)
14.  Na tela **Configuração de Acesso da Empresa**, toque em **CONTINUAR**. Se o administrador de TI configurar requisitos de segurança adicionais, como a necessidade de definir uma senha, siga as instruções na tela e toque em **CONTINUAR** quando retornar à tela Configuração de Acesso da Empresa.

  ![Captura de tela mostrando que o dispositivo Android é compatível e solicitando que o usuário continue](./media/ft-userEnrollAndroid-15-coAccessSetup.png)
15. Toque em **CONCLUÍDO**.

  ![Captura de tela mostrando que a configuração de acesso da empresa está concluída em um dispositivo Android](./media/ft-userEnrollAndroid-16-SetupComplete.png)
16. O dispositivo agora está registrado no Intune, e você é levado de volta ao aplicativo Portal da Empresa.
17. Antes de instalar aplicativos corporativos, acesse **Configurações > Segurança** e ative **Fontes Desconhecidas**. Se não ativar essa opção antes de tentar instalar os aplicativos, você verá a mensagem "Instalação bloqueada". Por motivos de segurança, seu telefone está definido para bloquear as instalações de aplicativos obtidos de fontes desconhecidas." Você pode tocar em **Configurações** na caixa de diálogo de erro para ir para a opção **Fontes Desconhecidas**.

## <a name="enroll-your-ios-device-in-intune"></a>Registrar seu dispositivo iOS no Intune
Use estas instruções para registrar seu dispositivo iOS no Intune. Para obter mais informações sobre o registro, consulte [O que acontece quando instalo o aplicativo Portal da Empresa e registro meu dispositivo no Intune?](https://technet.microsoft.com/library/mt598622(TechNet.10).aspx#BKMK_ios_what_happ_enroll). Se receber um erro ao tentar registrar seu dispositivo no Intune, consulte [Enviar erros de registro ao administrador de TI](https://technet.microsoft.com/library/mt598622(TechNet.10).aspx#BKMK_ios_error_enrolling_tbl).

Antes ou após o registro, você poderá ser solicitado a escolher uma categoria que melhor descreva como você usa o dispositivo. O administrador de TI usa essa categoria para ajudar a determinar quais aplicativos você terá acesso.
1.  Instale o aplicativo gratuito Portal da Empresa do Microsoft Intune em seu dispositivo na App Store.
2.  Abra o aplicativo Portal da Empresa do Microsoft Intune.
3.  Na tela de **Boas-vindas** do Portal da Empresa, toque em **Entrar** e entre com sua conta corporativa ou de estudante.

  ![Captura de tela mostrando a tela de entrada do Portal da Empresa do Intune em um dispositivo iOS](./media/ft-userEnrollIOS-1-signUp.png)
4.  Se o seu administrador de TI tiver configurado os termos e condições da empresa, toque em **Aceitar** para aceitar os termos.
5.  Na tela Configuração de Acesso da Empresa, toque em **Iniciar**.

  ![Captura de tela solicitando que o usuário inicie o processo de registro em um dispositivo iOS](./media/ft-userEnrollIOS-2-coAccessSetup.png)
6.  Leia sobre o que você pode fazer quando registra seu dispositivo e, em seguida, toque em **Continuar**.

  ![Captura de tela mostrando informações sobre por que você deve registrar um dispositivo iOS](./media/ft-userEnrollIOS-3-whyEnroll.png)
7.  Consulte a lista do que o administrador de TI pode ou não ver em seu dispositivo registrado e toque em **Continuar**.

  ![Captura de tela mostrando a política de privacidade em um dispositivo iOS](./media/ft-userEnrollIOS-4-privacy.png)
8.  Examine algumas das coisas que você pode ver depois que tocar em Registrar. Quando terminar a leitura, toque em **Registrar**.

  ![Captura de tela mostrando as próximas etapas de registro em um dispositivo iOS](./media/ft-userEnrollIOS-5-whatNext.png)
9.  Na tela Instalar Perfil, toque em **Instalar** e insira sua senha, se solicitado.

  ![Captura de tela solicitando que o usuário instale o perfil de gerenciamento para um dispositivo iOS](./media/ft-userEnrollIOS-6-installProfile.png)
10. Toque em **Instalar**.

  ![Captura de tela pedindo que o usuário toque no botão Instalar para instalar o perfil em um dispositivo iOS](./media/ft-userEnrollIOS-7-tapInstall.png)
11. Toque em **Instalar** para indicar que você leu o aviso.

  ![Captura de tela pedindo que o usuário indique que leu o aviso de gerenciamento de perfil em um dispositivo iOS](./media/ft-userEnrollIOS-8-readWarning.png)
12. Toque em **Confiar**.

  ![Captura de tela pedindo que o usuário confirme a origem do perfil em um dispositivo iOS](./media/ft-userEnrollIOS-9-tapTrust.png)
13. Quando a tela for alterada para mostrar que o perfil terminou de instalar, toque em **Concluído**. Uma mensagem "Registrando dispositivo" é exibida na tela.

  ![Captura de tela mostrando que o perfil está instalado em um dispositivo iOS](./media/ft-userEnrollIOS-10-profileInstalled.png)
14. Quando uma mensagem for exibida perguntando se você deseja abrir a página no Portal da Empresa, toque em **Abrir**.

  ![Captura de tela pedindo que o usuário abra a página no Portal da Empresa em um dispositivo iOS](./media/ft-userEnrollIOS-11-openPage.png)
- Na tela Configuração de Acesso da Empresa, toque em **Continuar**. Se o administrador de TI configurar requisitos de segurança adicionais, como a necessidade de definir uma senha, siga as instruções na tela até atender a todos os requisitos de conformidade e toque em **Continuar** quando retornar à tela Configuração de Acesso da Empresa.

  ![Captura de tela mostrando que o dispositivo iOS é compatível e solicitando que o usuário continue](./media/ft-userEnrollIOS-12-coAccessSetup.png)
15. Toque em **Concluído**.

  ![Captura de tela mostrando que a configuração de acesso da empresa está concluída em um dispositivo iOS](./media/ft-userEnrollIOS-13-setupComplete.png)

O dispositivo agora está registrado no Intune, e você é levado de volta ao aplicativo Portal da Empresa.

## <a name="enroll-your-mac-os-x-device-in-intune"></a>Registrar seu dispositivo Mac OS X no Intune
1.  Usando um navegador Safari, abra o [site do Portal da Empresa](https://portal.manage.microsoft.com/), e toque na barra de notificação.
2.  Toque em **Este dispositivo não está registrado ou o Portal da Empresa não pode identificá-lo**.

  ![Captura de tela mostrando que o Portal da Empresa não pode identificar um dispositivo Mac OS X](./media/ft-userEnrollMacOSx-1-enrollBegin.png)
3.  Toque **Instalar** para registrar seu dispositivo.

  ![Captura de tela solicitando que o usuário registre o dispositivo Mac OS X](./media/ft-userEnrollMacOSx-2-enrollDevice.png)
4.  Na caixa de diálogo Instalar o Perfil de Gerenciamento, toque em **Instalar**. Se uma caixa de diálogo for exibida solicitando que você insira suas credenciais, digite seu nome de usuário e senha e, em seguida, toque em **Continuar > Instalar**.

  ![Captura de tela solicitando que o usuário instale o perfil de gerenciamento em um dispositivo Mac OS X](./media/ft-userEnrollMacOSx-3-installProfile.png)

Ao concluir o registro, você verá uma página de Perfil de Gerenciamento mostrando que o perfil foi verificado.

  ![Captura de tela mostrando que o perfil de gerenciamento foi verificado em um dispositivo Mac OS X](./media/ft-userEnrollMacOSx-4-profileVerified.png)

### <a name="want-to-learn-more"></a>Quer saber mais?
Consulte [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).



<!--HONumber=Jan17_HO1-->


