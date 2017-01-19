---
title: "Como registrar-se na autenticação multifator"
description: "Como configurar o método preferencial de verificação de segurança adicional"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 09/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 06e21ca9-ed6a-4f6e-a7e2-5445aaeb3552
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2342889a686db8a6496c97979cb222af8347241a
ms.openlocfilehash: b7164b33bf9d4bdb7584de9cbb78711e922a10c4


---

# <a name="how-to-set-up-your-preferred-method-for-additional-security-verification"></a>Como configurar seu método preferencial de verificação de segurança adicional



Configurações adicionais de verificação de segurança foram usadas quando um administrador configurou sua conta para exigir que sua senha e uma resposta de seu telefone devem ser usadas para verificar sua identidade. Se um administrador tiver configurado sua conta para exigir verificação de segurança adicional, você não conseguirá entrar até que o processo de registro automático seja concluído.

Na primeira vez que você entrar depois que sua conta tiver sido configurada, você será solicitado a iniciar o processo de registro automático. É possível começar esse processo ao clicar em Configurar agora.

![Captura de tela solicitando que o usuário se registre na verificação de segurança adicional para sua conta](./media/ft-enrollMFA-1-beginProcess.png)

Ao utilizar o processo de registro, você será capaz de especificar seu método preferencial de verificação de identidade. Isso pode ser qualquer uma das seguintes opções listadas na tabela a seguir. Para obter informações adicionais, incluindo um passo a passo, basta clicar em um dos métodos.


|Método|Descrição|
|------------|----------------------------------|
|[Chamada de Telefone Celular](#mobile-phone-(text-or-call))|Faz uma chamada de voz automática para o número de telefone de autenticação. O usuário atende a chamada e pressiona # no teclado numérico do telefone para autenticar. Este número de telefone não será sincronizado ao Active Directory local.|
|[Mensagem de Texto de Celular](#mobile-phone-(text-or-call))|Envia uma mensagem de texto que contém um código de verificação para o usuário. É solicitado que o usuário responda à mensagem de texto com o código de verificação ou que insira o código de verificação na interface de entrada.|
|[Chamada de Telefone Comercial](#office-phone-call)|faz uma chamada de voz automática para o usuário. O usuário atende a chamada e pressiona # no teclado numérico do telefone para autenticar.|
|[Aplicativo Móvel](#mobile-application)|Envia uma notificação para o aplicativo móvel Microsoft Authenticator no smartphone ou tablet do usuário. O usuário toca em Verificar no aplicativo para autenticar. Como alternativa, o aplicativo também pode ser usado como um token OTP para autenticação offline. O usuário insere o token na tela de entrada para autenticar.|

_O aplicativo Microsoft Authenticator pode operar em dois modos diferentes para fornecer a segurança adicional que um serviço de autenticação multifator pode proporcionar. Eles são os seguintes:_

- **Notificação** – Neste modo, o aplicativo Microsoft Authenticator impede o acesso não autorizado a contas e interrompe transações fraudulentas. Isso é feito usando uma notificação por push para seu telefone ou dispositivo registrado. Basta exibir a notificação e, se for legítima, selecionar **Autenticar**. Caso contrário, você poderá escolher **Negar** ou optar por negar e relatar a notificação fraudulenta. Para obter mais informações sobre notificações fraudulentas, consulte Como usar o recurso Negar e Relatar Fraude do Multi-Factor Authentication.
- **Senha de Uso Único** – Nesse modo, o aplicativo Microsoft Authenticator pode ser usado como um token de software para gerar um código de verificação OATH. Esse código de verificação pode ser inserido junto com o nome de usuário e a senha para fornecer a segunda forma de autenticação.

O aplicativo Microsoft Authenticator está disponível para [Windows Phone](http://www.windowsphone.com/en-us/store/app/azure-authenticator/03a5b2bf-6066-418f-b569-e8aecbc06e50), [Android](https://play.google.com/store/apps/details?id=com.azure.authenticator) e [IOS](https://itunes.apple.com/us/app/azure-authenticator/id983156458).

## <a name="mobile-phone-text-or-call"></a>Telefone Celular (Texto ou Chamada)
Se quiser usar seu telefone celular como método de contato primário, será possível usar as etapas a seguir. Será fornecido um passo a passo de como configurar a autenticação multifator para usar o telefone celular para uma chamada ou texto como método de contato.

1. Em **Etapa 1: como devemos contatá-lo?**, selecione **Telefone de autenticação**.

  ![Capturas de tela mostrando que o usuário deseja ser contatado por telefone](./media/ft-enrollMFA-2-securityVerification.png)
2.  No **país ou região**, selecione um valor na lista suspensa. Um valor padrão já pode ser exibido.
3.  Na caixa ao lado do **país ou região**, digite o número de telefone celular. Inclua o código de área.
São permitidos espaços, mas não caracteres de pontuação. Por exemplo, 5554445555 e 555 444 5555 são permitidos, mas 555-444-5555 e (555) 444 5555 não são permitidos.
4.  Selecione o modo que preferir utilizar com seu celular: Texto ou Chamada.
5.  Clique em **Avançar**.
6.  Clique no botão **Verificar Agora**. Isso iniciará uma chamada ou um texto para seu celular. Certifique-se de que seu telefone esteja com você. Dependendo do modo selecionado, Texto ou Chamada, sua resposta será diferente.
 - Caso tenha selecionado o modo de texto, você receberá um código de seis dígitos por mensagem de texto. Digite esse código na caixa exibida no navegador.

        ![Screenshot asking user to enter the code that was texted to them](./media/ft-enrollMFA-3-textCode.png)
 - Se você tiver selecionado o modo de chamada, receberá um telefonema. Responda à chamada usando o sinal # no seu telefone.

        ![Screenshot prompting user to answer their phone to continue enrollment process](./media/ft-enrollMFA-4-phoneCode.png)
7. Clique em **Avançar**.
8.  Neste ponto, você configurou seu método de contato e agora é o momento de configurar senhas de aplicativo para aplicativos que não são navegador, como o Outlook 2010 ou posterior. Caso não use esses aplicativos, clique em **Concluído**. Caso contrário, **prossiga** para a próxima etapa.
9. Se você estiver usando esses aplicativos, **copie** a senha de aplicativo fornecida.

  ![Captura de tela solicitando que o usuário insira a senha de aplicativo](./media/ft-enrollMFA-5-copyPW.png)
10. Cole a senha que foi copiada para a área de transferência no seu aplicativo que não é navegador.
11. Clique em **Concluído**.

## <a name="office-phone-call"></a>Chamada de Telefone Comercial
Esta seção deste documento o orientará durante a configuração da Autenticação Multifator do Azure para usar seu Telefone Comercial como método de contato primário.
1. Selecione Telefone Comercial na lista suspensa.

  ![Capturas de tela mostrando que o usuário deseja ser contatado pelo telefone comercial](./media/ft-enrollMFA-6-officePhone.png)
2.  Especifique seu país na lista suspensa e insira seu número de telefone comercial.
3.  Clique em **Entrar em contato comigo**. Isso iniciará uma chamada para o seu telefone comercial. Verifique se está próximo ao seu telefone.
4.  Clique em **Avançar**.
5.  Neste ponto, você configurou seu método de contato e agora é o momento de configurar senhas de aplicativo para aplicativos que não são navegador, como o Outlook 2010 ou posterior. Caso não use esses aplicativos, clique em **Concluído**. Caso contrário, **prossiga** para a próxima etapa.
7.  Se você estiver usando esses aplicativos, copie a senha de aplicativo fornecida.
8.  Cole a senha que foi copiada para a área de transferência no seu aplicativo que não é navegador.

  ![Captura de tela solicitando que o usuário insira a senha de aplicativo](./media/ft-enrollMFA-7-pastePW.png)
9.  Clique em **Concluído**.

## <a name="mobile-application"></a>Aplicativo Móvel
Esta seção deste artigo o orientará durante a configuração da Autenticação Multifator do Azure para usar seu aplicativo móvel como método de contato primário.

O aplicativo Microsoft Authenticator está disponível para Windows Phone, Android e iOS.

1. Selecione **Aplicativo Móvel** na lista suspensa.

  ![Capturas de tela mostrando que o usuário deseja ser contatado pelo aplicativo móvel](./media/ft-enrollMFA-8-mobileApp.png)
2.  Selecione Notificação ou senha de Uso único e clique em **Configurar**.
3.  No telefone que tem o aplicativo Microsoft Authenticator instalado, inicie o aplicativo e clique em **digitalizar código de barras**.

  ![Captura de tela solicitando que o usuário selecione a opção de digitalização de código de barras](./media/ft-enrollMFA-9-scanBarcode.png)
4.  Digitalize a imagem do código de barras que acompanha a tela configurar aplicativo móvel. Clique em **Concluído** para fechar a tela de código de barras. Se não for possível digitalizar o código de barras, você poderá inserir as informações manualmente.

  ![Captura de tela solicitando ao usuário que digitalize o código de barras que aparece no aplicativo móvel](./media/ft-enrollMFA-9-scanBarcode2.png)
5.  No telefone, ele começará a ativação. Depois de concluída, clique em **Entrar em contato comigo**. Isso enviará uma notificação ou um código de verificação para seu telefone. Clique em **Verificar**.

  ![Captura de tela solicitando ao usuário que verifique o código enviado para seu telefone](./media/ft-enrollMFA-10-verifyActivation.png)
6.  Clique em **Fechar**. Neste ponto, sua verificação deve ser bem-sucedida.
7.  Agora, é recomendável que você insira seu número de telefone celular caso você perca o acesso ao seu aplicativo móvel.
8.  Especifique seu país na lista suspensa e insira o número de telefone celular na caixa ao lado do país. Clique em **Avançar**.
9.  Neste ponto, você configurou seu método de contato e agora é o momento de configurar senhas de aplicativo para aplicativos que não são navegador, como o Outlook 2010 ou posterior. Caso não use esses aplicativos, clique em **Concluído**. Caso contrário, **prossiga** para a próxima etapa.
10. Se você estiver usando esses aplicativos, copie a senha de aplicativo fornecida.
11. Cole a senha que foi copiada para a área de transferência no seu aplicativo que não é navegador.

  ![Captura de tela solicitando que o usuário insira a senha de aplicativo](./media/ft-enrollMFA-11-securityVerification.png)
12. Clique em **Concluído**.

### <a name="want-to-learn-more"></a>Quer saber mais?
Consulte [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).



<!--HONumber=Jan17_HO1-->


