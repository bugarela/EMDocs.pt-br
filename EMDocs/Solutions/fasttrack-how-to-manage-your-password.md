---
title: Como gerenciar sua senha
description: "Como gerenciar sua própria senha"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 02/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 162e59f3-33a2-44b5-a59f-24612dc743f3
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 1bf552e92104a7872099e555df12993dd4258293
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="how-to-manage-your-own-password"></a>Como gerenciar sua própria senha

Se você for um usuário (e não um administrador) em uma organização que usa o Office 365 ou contas da Microsoft para acessar recursos de trabalho, leia as seções abaixo para saber como corrigir problemas comuns com sua senha.

## <a name="how-to-register-for-password-reset"></a>Como se registrar para redefinição de senha
A maneira mais rápida para se registrar para redefinição de senha é ir até [http://aka.ms/ssprsetup](http://aka.ms/ssprsetup).

1.  Navegue até [http://aka.ms/ssprsetup](http://aka.ms/ssprsetup).
2.  Digite seu nome de usuário e senha.
3.  Escolha uma opção na qual se registrar clicando **configurar agora**. Nesse caso, farei uma demonstração registrando meu **telefone de autenticação**.
![Captura de tela mostrando blahblah](./media/ft-mngPW-1-setup.png)
4.  Selecione o código de seu país/região na lista suspensa e insira seu número de telefone completo com código de área.
![Captura de tela mostrando como selecionar um código de país. ](./media/ft-mngPW-2-enterNumber.png)![Captura de tela mostrando onde digitar um número de telefone.](./media/ft-mngPW-3-enterNumber2.png)
5.  Selecione uma das opções **enviar texto** ou **telefonar**. Nesse caso, selecionarei **enviar texto**, que enviará um código de 6 dígitos para meu telefone. Aguarde até que o código chegue em seu telefone.
![Captura de tela mostrando um código de seis dígitos enviado a um telefone.](./media/ft-mngPW-4-textCode.png)
6.  Após o código chegar, insira-o na caixa de entrada e clique em "verificar".
7.  Quando vir **Obrigado**, você terminou! Agora, você pode usar o que registrou para redefinir sua senha a qualquer momento acessando [https://passwordreset.microsoftonline.com](https://passwordreset.microsoftonline.com).
![Captura de tela mostrando a mensagem de agradecimento recebida quando o registro é concluído.](./media/ft-mngPW-5-thanks.png)

> [!IMPORTANT]
> Se seu administrador permitir se registrar em mais de uma opção, será altamente recomendável que você também registre uma opção de backup caso perca seu telefone ou o acesso ao seu email.

## <a name="how-to-reset-your-password"></a>Como redefinir sua senha
Siga as etapas abaixo para redefinir a senha de sua conta corporativa ou de estudante em qualquer tela de logon da conta corporativa ou de estudante.

> [!IMPORTANT]
> Esse recurso só ficará disponível para você se o administrador a tiver habilitado. Se ela não estiver ativada, você verá uma mensagem indicando que sua conta não está habilitada para esse recurso. Nesse caso, você pode usar o link "entrar em contato com seu administrador" para entrar em contato com seu administrador e desbloquear sua conta.
>
Se o administrador tiver habilitado você para esse recurso, primeiro você precisará inscrever-se antes de pode usar. Você pode fazer isso aqui: [http://aka.ms/ssprsetup](http://aka.ms/ssprsetup).

1.  Em qualquer tela de logon da conta corporativa ou de estudante, clique em um dos links "não é possível acessar sua conta?" ou "esqueceu sua senha?" ou navegue diretamente até [https://passwordreset.microsoftonline.com](https://passwordreset.microsoftonline.com).
![Captura de tela mostrando a primeira mensagem recebida se a ID de usuário ou senha não forem reconhecidas.](./media/ft-mngPW-6-resetPWbegin.png)
2.  Na página "quem é você?", insira a ID da conta corporativa ou de estudante e prove que você não é um robô fornecendo o captcha.
![Captura de tela solicitando que o usuário digite a ID de usuário e o código captcha exibido.](./media/ft-mngPW-7-enterID.png)
3.  Clique em **Avançar**.
4.  Escolha uma opção para redefinir sua senha. Dependendo de como o administrador tiver configurado o sistema, você poderá ver uma ou mais das seguintes opções:
 - **Inserir o meu email alternativo** – envia um email com um código de 6 dígitos para seu email alternativo ou email de autenticação (você escolhe).
  - **Enviar SMS para meu celular** – envia um SMS para seu telefone com um código de 6 dígitos seu telefone celular ou email de autenticação (você escolhe).
  - **Ligar para meu celular** – telefona para seu telefone celular ou telefone de autenticação (você escolhe) – pressione a tecla # para verificar a chamada.
 - **Ligar para meu telefone comercial** – telefona para seu telefone comercial – pressione a tecla # para verificar a chamada.
 - **Responder às minhas perguntas de segurança** – exibe suas perguntas de segurança registradas previamente para você responder.
 ![Captura de tela solicitando que o usuário escolha o método pelo qual deseja ser contatado para verificação.](./media/ft-mngPW-8-answerQuestions.png)
5.  Vamos usar a opção **Enviar SMS para meu celular** como exemplo. Se estiver usando uma opção baseada em telefone, você precisará verificar o número de telefone antes de nós enviarmos um SMS. Insira seu número de telefone completo e clique em **Avançar** para confirmar que ele está correto e enviar um SMS.
![Captura de tela mostrando que o usuário deve inserir o número de telefone no qual receberá a mensagem de texto de verificação.](./media/ft-mngPW-9-textNumber.png)
6.  Quando receber o texto, certifique-se de usar o código de verificação no corpo da mensagem, não o número do qual o código foi enviado. Pode levar alguns minutos para você receber o SMS, então vá tomar um café!
![Captura de tela mostrando o código de verificação recebido.](./media/ft-mngPW-10-verificationCode.png)
7.  Agora, digite o código que acabou de receber em seu telefone na caixa de entrada na página.
![Captura de tela mostrando que o usuário deve digitar o código de verificação recebido.](./media/ft-mngPW-11-enterCode.png)
8.  O administrador pode exigir uma segunda etapa de verificação. Nesse caso, repita a etapa 4 com uma opção diferente selecionada.
9.  Na tela "escolher uma nova senha", selecione uma nova senha, confirme sua escolha e clique em **Concluir**.
![Captura de tela mostrando que o usuário deve digitar e confirmar uma nova senha.](./media/ft-mngPW-12-clickFinish.png)
10. Quando vir a página êxito, você estará pronto para começar! Agora, você pode entrar com sua nova senha.
![Captura de tela mostrando que o processo de redefinição de senha foi concluído.](./media/ft-mngPW-13-success.png)
Teve problemas para redefinir sua senha? Leia sobre os [problemas comuns e suas soluções](https://azure.microsoft.com/en-us/documentation/articles/active-directory-passwords-update-your-own-password/#common-problems-and-their-solutions).

### <a name="want-to-learn-more"></a>Quer saber mais?
Consulte [Enterprise Mobility + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx).
