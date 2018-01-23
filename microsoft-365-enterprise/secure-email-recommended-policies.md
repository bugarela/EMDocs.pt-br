---
title: "Políticas recomendadas para email seguro – Microsoft 365 Enterprise | Microsoft Docs"
description: "Descreve as políticas para as recomendações da Microsoft sobre como aplicar configurações e políticas de email."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 01/18/2018
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: c86f8f86d134d77e45ab7a59564b9f0d4821ed38
ms.sourcegitcommit: eb3521981c5dec164ce2a14b4d4d53830b5ba461
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2018
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendações de política para proteger o email

Este artigo descreve as políticas recomendadas para ajudar a proteger o email organizacional e os clientes de email que dão suporte à Autenticação Moderna e ao Acesso Condicional. Essas recomendações são um complemento à [identidade comum e às recomendações da política de acesso](identity-access-policies.md).

As recomendações a seguir se baseiam em três camadas de segurança e proteção diferentes para o seu email que podem ser aplicadas com base na granularidade das suas necessidades:

- **Linha de base**: a Microsoft recomenda que você estabeleça um padrão mínimo para a proteção dos dados e também das identidades e dos dispositivos que acessam os dados. A Microsoft fornece uma proteção padrão forte que atende às necessidades de diversas organizações. Algumas organizações precisam de recursos adicionais para atender aos seus requisitos de linha de base.
- **Confidencial**: alguns clientes têm um subconjunto de dados que precisam ser protegidos em níveis mais altos. Você pode aplicar uma proteção maior a conjuntos de dados específicos no ambiente do Office 365. A Microsoft recomenda proteger as identidades e os dispositivos que acessam os dados confidenciais com os mesmos níveis de segurança. 
- **Altamente regulamentada**: algumas organizações têm uma quantidade muito pequena de dados classificados como altamente confidenciais, segredos comerciais ou dados regulamentados. A Microsoft fornece recursos para ajudar as organizações a atender a esses requisitos, incluindo proteção adicional para identidades e dispositivos.

Consulte o tópico [Políticas de segurança e configurações recomendadas](microsoft-365-policies-configurations.md) para obter mais detalhes.

> [!IMPORTANT]
> Todos os grupos de segurança criados como parte dessas recomendações devem ser criados com recursos do Office habilitados. Isso é importante principalmente para a implantação da AIP (Proteção de Informações do Azure) ao proteger documentos no SharePoint Online.
>
>![Recursos do Office habilitados para grupos de segurança](./media/security-group.png)
>

## <a name="baseline"></a>Linha de base
Para criar uma nova política de acesso condicional: 

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Depois de entrar com êxito, você verá o Painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**, como mostra a captura de tela abaixo:

![Política de AC de linha de base](./media/secure-email/CA-EXO-policy-1.png)

As tabelas a seguir descrevem as configurações apropriadas necessárias para expressar as políticas necessárias para cada nível de proteção.

### <a name="medium-and-above-risk-requires-mfa"></a>O risco médio e superior requer a MFA

A tabela a seguir descreve as configurações de política de acesso condicional a serem implementadas para esta política.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Atribuições**|Usuários e grupos|Incluir|Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto.|
|||Excluir|Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)|Associação modificada de forma temporária, conforme o necessário|
||Aplicativos em nuvem|Incluir|Selecionar aplicativos – selecione Office 365 Exchange Online||
||Condições|Configurado|Sim|Configure específicos para suas necessidades e ambiente|
||Risco de entrada|Nível de risco|Alto, médio|Marque ambos|
|**Controles de acesso**|Conceder|Conceder acesso|verdadeiro|Selecionada|
|||Exigir MFA|verdadeiro|Verificar|
|||Exigir dispositivos em conformidade|Falso||
|||Exigir dispositivos ingressados no domínio|Falso||
|||Exigir todos os controles selecionados|verdadeiro|Selecionada|
|**Habilitar política**|||Ativado|Implantar política de acesso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio

Para criar uma política de acesso condicional para o Exchange Online:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Depois de entrar com êxito, você verá o Painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

5. Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.

6. Escolha **Aplicativos na nuvem**.

7. Escolha **Selecionar aplicativos**, selecione **Office 365 Exchange Online** na lista **Aplicativos na nuvem** e clique em **Selecionar**. Depois que o aplicativo **Office 365 Exchange Online** for selecionado, clique em **Concluído**.

8. Escolha **Conceder** na seção **Controles de acesso**.

9. Escolha **Conceder acesso**, selecione **Exigir que o dispositivo seja marcado como em conformidade** e **Exigir que esteja ingressado no domínio (Azure AD Híbrido)** e, em seguida, escolha **Selecionar**.

10. Clique em **Criar** para criar a política de acesso condicional do Exchange Online.

    > [!NOTE]
    > Ao começar a usar o Intune no Azure, você precisará criar todas as políticas de acesso condicional na carga de trabalho do Azure Active Directory. O Intune fornece um link para a carga de trabalho de políticas de acesso condicional do Azure AD em seu portal para facilitar o processo.

    > [!IMPORTANT]
    > Se você precisar de assistência ao migrar as políticas de acesso condicional que já foram criadas no portal clássico do Intune para o Intune no portal do Azure, consulte o tópico [Reatribuir políticas de acesso condicional no portal clássico do Intune para o Portal do Azure](https://docs.microsoft.com/intune/conditional-access-intune-reassign). 

### <a name="app-based-conditional-access-for-exchange-online"></a>Acesso condicional baseado em aplicativo para o Exchange Online

Você pode adicionar mais uma camada de segurança, configurando uma política de acesso condicional baseada em aplicativo para o Exchange Online no Intune no portal do Azure. Ao aplicar um acesso condicional baseado em aplicativo no Exchange Online, você passa a exigir que os usuários usem um aplicativo específico (por exemplo, o aplicativo Microsoft Outlook) para acessar o email corporativo.

Para adicionar uma política de acesso condicional baseada em aplicativo:

1. Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune. Depois de entrar com êxito, você verá o Painel do Azure.

2. Escolha **Mais serviços** no menu à esquerda e, em seguida, digite: "**Intune**".

3. Escolha **Proteção de Aplicativo do Intune**.

4. Na folha **Gerenciamento de aplicativo móvel do Intune**, escolha **Todas as Configurações**.

5. Escolha **Exchange Online** na seção **Acesso condicional**.

6. Selecione **Permitir aplicativos compatíveis com as políticas de aplicativo do Intune** e, em seguida, escolha o aplicativo (por exemplo, o Microsoft Outlook).

7. Escolha **Grupos de usuário com restrições**, clique em **Selecionar grupos**, selecione o usuário ou o grupo ao qual deseja aplicar a política e clique em **Selecionar**.

## <a name="sensitive"></a>Confidencial

### <a name="low-and-above-risk-requires-mfa"></a>O risco baixo e superior requer a MFA
A tabela a seguir descreve as configurações de política de acesso condicional a serem implementadas para políticas de risco baixo e superior.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Atribuições**|Usuários e grupos|Incluir|Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto|
|||Excluir|Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)|Associação modificada de forma temporária, conforme o necessário|
||Aplicativos em nuvem|Incluir|Selecionar aplicativos – selecione Office 365 Exchange Online||
||Condições|Configurado|Sim|Configure específicos para suas necessidades e ambiente|
||Risco de entrada|Configurado|Sim|Configure específicos para suas necessidades e ambiente|
|||Nível de risco|Baixo, médio, alto|Marque todos os três|
|**Controles de acesso**|Conceder|Conceder acesso|verdadeiro|Selecionada|
|||Exigir MFA|verdadeiro|Verificar|
|||Exigir dispositivos em conformidade|Falso||
|||Exigir dispositivo ingressado no domínio|Falso||
|||Exigir todos os controles selecionados|verdadeiro|Selecionada|
|**Habilitar política**|||Ativado|Implantar política de acesso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio
(Consulte as instruções de linha de base)

### <a name="app-based-conditional-access-for-exchange-online"></a>Acesso condicional baseado em aplicativo para o Exchange Online

(Consulte as instruções de linha de base)

#### <a name="apply-to"></a>Aplicar a

Depois que o projeto piloto foi concluído, essas políticas devem ser aplicadas aos usuários em sua organização que exigem acesso ao email considerado confidencial.

## <a name="highly-regulated"></a>Altamente controlada
### <a name="mfa-required"></a>MFA necessária

A tabela a seguir descreve as configurações de política de acesso condicional a serem implementadas para a política altamente controlada.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Atribuições**|Usuários e grupos|Incluir|Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto|
|||Excluir|Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)|Associação modificada de forma temporária, conforme o necessário|
||Aplicativos em nuvem|Incluir|Selecionar aplicativos – selecione Office 365 Exchange Online||
|**Controles de acesso**|Conceder|Conceder acesso|verdadeiro|Selecionada|
|||Exigir MFA|verdadeiro|Verificar|
|||Exigir dispositivos em conformidade|Falso|Verificar|
|||Exigir dispositivo ingressado no domínio|Falso||
|||Exigir todos os controles selecionados|verdadeiro|Selecionada|
|**Habilitar política**|||Ativado|Implantar política de acesso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio
(Consulte as instruções de linha de base)
### <a name="app-based-conditional-access-for-exchange-online"></a>Acesso condicional baseado em aplicativo para o Exchange Online
(Consulte as instruções de linha de base)
#### <a name="apply-to"></a>Aplicar a
Depois que o projeto piloto foi concluído, essas políticas devem ser aplicadas aos usuários em sua organização que exigem acesso ao email considerado altamente controlado.

### <a name="high-risk-users-policy"></a>Política de usuários de alto risco
Para garantir que todas as contas de usuários de alto risco comprometidas sejam forçadas a executar uma alteração de senha ao entrar, você deve aplicar a política a seguir.

Faça logon no [Portal do Microsoft Azure (http://portal.azure.com)](http://portal.azure.com/) com suas credenciais de administrador e, em seguida, navegue até **Azure AD Identity Protection > Política de Risco do Usuário**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Atribuições**|Usuários|Incluir|todos os usuários|Selecionada|
|||Excluir|Nenhum||
||Condições|Risco do usuário|Alta|Selecionada|
|**Controles**|Acessar|Permitir acesso|verdadeiro|Selecionada|
||Acessar|Requer a alteração de senha|verdadeiro|Verificar|
|**Examinar**|N/D|N/D|N/D|N/D|
|**Impor a política**|||Ativado|Inicia a imposição de política|


## <a name="additional-configurations"></a>Configurações adicionais
Além das políticas acima, você deve definir as seguintes configurações de aplicativo móvel e gerenciamento de dispositivo abordadas nesta seção.

### <a name="intune-mobile-application-management"></a>Gerenciamento de aplicativos móveis do Intune

Para garantir que o email está protegido pelas recomendações de política indicadas anteriormente para cada camada de proteção de dados e segurança, você deve criar políticas de proteção de aplicativo do Intune de dentro do Portal do Azure.

Para criar uma nova política de proteção de aplicativo, faça logon no portal do Microsoft Azure com suas credenciais de administrador e, em seguida, navegue em **Proteção de Aplicativo do Intune > Política de aplicativo**.

Adicione uma nova política (+Adicionar), conforme mostrado na captura de tela a seguir:

![Gerenciamento de aplicativos móveis do Intune](./media/secure-email/CA-EXO-policy-2.png)

>[!NOTE]
>Há pequenas diferenças nas opções de política de proteção de aplicativo entre o iOS e o Android. A política abaixo é especificamente para Android.
>

As tabelas a seguir descrevem as configurações de política de proteção de aplicativo do Intune recomendadas:

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Geral**|Email|Nome|Política de email seguro para Android|Insira um nome de política|
|||Descrição||Digite o texto que descreve a política|
|||Plataforma|Android|Há pequenas diferenças nas opções de política de proteção de aplicativo entre o iOS e o Android, essa política é especificamente para Android|
|**Apps**|Aplicativos|Aplicativos|Outlook|Selecionado (lista)|
|**Configurações**|Realocação de dados|Impedir backup do Android|Sim|No iOS isso especificamente indicará o iTunes e o iCloud|
||||Permitir que o aplicativo transfira dados para outros aplicativos|Aplicativos gerenciados por política||
|||Permitir que o aplicativo receba dados para outros aplicativos|Aplicativos gerenciados por política||
|||Impedir "Salvar como"|Sim||
|||Restringir recortar, copiar e colar com outros aplicativos|Aplicativos gerenciados por política||
|||Restringir a exibição de conteúdo da Web no Managed Browser|Não||
|||Criptografar dados do aplicativo|Sim|No iOS, selecione a opção: Quando o dispositivo está bloqueado|
|||Desabilitar a sincronização de contatos|Não||
||Acessar|Solicitar PIN para acesso|Sim||
|||Número de tentativas antes da redefinição do PIN|3||
|||Permitir PIN simples|Não||
|||Tamanho do PIN|6||
|||Permitir a impressão digital em vez do PIN|Sim||
|||Exigir credenciais corporativas para acesso|Não||
|||Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou root|Sim||
|||Verificar novamente o requisito de acesso após (minutos)|30||
|||Período de cortesia offline|720||
|||Intervalo offline (dias) antes do apagamento dos dados do aplicativo|90||
|||Bloquear captura de tela e Assistente do Android|Não|No iOS isso não é uma opção disponível|

Ao concluir, lembre-se de clicar em "Criar". Repita as etapas acima e substitua a plataforma selecionada (menu suspenso) por iOS. Isso cria duas políticas de aplicativo, portanto, após criar a política, atribua grupos à política e implante-a.

- Consulte [Como criar e atribuir as políticas de proteção de aplicativo](https://docs.microsoft.com/intune/app-protection-policies) para obter mais detalhes.

### <a name="intune-mobile-device-management"></a>Gerenciamento de dispositivo móvel do Intune
Para criar os perfis de configuração do dispositivo e as políticas de conformidade do dispositivo a seguir, você deverá fazer logon no [Intune no portal do Azure](https://portal.azure.com) com suas credenciais do Intune.

#### <a name="ios-email-profile"></a>Perfil de email do iOS
No [Intune no portal do Azure](https://portal.azure.com), você pode criar os seguintes perfis de configuração do dispositivo em **Configuração do dispositivo > Perfis > Criar Perfil > Plataforma (iOS) > Tipo de perfil (email)**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Perfil de email**|Exchange Active Sync|Host (#)|Outlook.office365.com||
|||Nome da Conta (#)|SecureEmailAccount|Escolha do administrador|
|||Nome de usuário|Nome UPN|Selecionado – lista suspensa|
|||Endereço de email|Endereço SMTP primário|Selecionado – lista suspensa|
|||Método de autenticação|Nome de usuário e senha|Selecionado – lista suspensa|
|||Usar S/MIME|Falso||
||Configurações de sincronização|Número de dias de email para sincronizar|Duas semanas|Selecionado – lista suspensa|
|||Usar SSL|verdadeiro|Verificar|
|||Permitir que as mensagens sejam movidos para outras contas de email|Falso||
|||Permitir que o email seja enviado de aplicativos de terceiros|verdadeiro||
|||Sincronizar os endereços de email usados recentemente|verdadeiro|Verificar|

#### <a name="android-email-profile"></a>Perfil de email do Android
No [Intune no portal do Azure](https://portal.azure.com), você pode criar os seguintes perfis de configuração do dispositivo em **Configuração do dispositivo > Perfis > Criar Perfil > Plataforma (Android) > Tipo de perfil (email)**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Perfil de email**|Exchange Active Sync|Host (#)| Outlook.office365.com|
|||Nome da Conta (#)|SecureEmailAccount|Escolha do administrador|
|||Nome de usuário|Nome UPN|Selecionado – lista suspensa|
|||Endereço de email|Endereço SMTP primário|Selecionado – lista suspensa|
|||Método de autenticação|Nome de usuário e senha|Selecionado – lista suspensa|
|||Usar S/MIME|Falso||
||Configurações de sincronização|Número de dias de email para sincronizar|Duas semanas|Selecionado – lista suspensa|
|||Agenda de sincronização|Não configurado|Selecionado – lista suspensa|
|||Usar SSL|verdadeiro|Verificar|
|||Tipo de conteúdo para sincronizar|||
|||Email|verdadeiro|Verificar (bloqueado)|
|||Contacts|verdadeiro|Verificar|
|||Calendário|verdadeiro|Verificar|
|||Tarefas|verdadeiro|Verificar|
|||Anotações|verdadeiro|Verificar|

#### <a name="android-for-work-email-profile"></a>Perfil de email do Android for Work
No [Intune no portal do Azure](https://portal.azure.com), você pode criar os seguintes perfis de configuração do dispositivo em **Configuração do dispositivo > Perfis > Criar Perfil > Plataforma (Android for Work) > Tipo de perfil (email)**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Perfil de email**|Exchange Active Sync|Host(#)| Outlook.office365.com|
|||Nome da Conta(#)|SecureEmailAccount|Escolha do administrador|
|||Nome de usuário|Nome UPN|Selecionado – lista suspensa|
|||Endereço de email|Endereço SMTP primário|Selecionado – lista suspensa|
|||Método de autenticação|Nome de usuário e senha|Selecionado – lista suspensa|
||Configurações de sincronização|Número de dias de email para sincronizar|Duas semanas|Selecionado – lista suspensa|
|||Usar SSL|verdadeiro|Verificar|

#### <a name="device-compliance-policy"></a>Política de conformidade do dispositivo
No [Intune no portal do Azure](https://portal.azure.com), você pode criar as seguintes políticas de conformidade do dispositivo em **Conformidade do dispositivo > Políticas > Criar Política > Plataforma (iOS, Android ou outras) > Configurações**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Segurança do sistema**|Senha|Exigir uma senha para desbloquear os dispositivos móveis (...)|Sim|Selecionado – lista suspensa|
|||Permitir senhas simples (...)|Não|Selecionado – lista suspensa|
|||Comprimento mínimo da senha (...)|6|Selecionado – lista|
||Configurações de senha avançadas|Tudo|Não configurado||
||Criptografia|Exigir criptografia no dispositivo móvel (...)|Sim|Selecionado – lista suspensa|
||Perfis de email|A conta de email deve ser gerenciada pelo Intune (iOS 8.0+)|Sim| Selecionado – lista suspensa|
|||Selecionar (#)||Necessário selecionar a política de configuração de email do iOS: política de Email do iOS (consulte as políticas de configuração acima)|
|**Integridade do dispositivo**|Atestado de integridade do dispositivo Windows|Exigir que os dispositivos sejam relatados como íntegros (Windows 10 Desktop e Mobile e posterior)|Sim||
||Configurações de segurança de dispositivo|Tudo|Não configurado||
||Proteção contra ameaças ao dispositivo|Tudo|Não configurado||
||Jailbreak|O dispositivo não pode estar com jailbreak ou com raiz (iOS 8.0+, Android 4.0+)|Sim||
|**Propriedades do dispositivo**|Versão do sistema operacional|Tudo|Não configurado|||

Para todas as políticas acima para serem consideradas implantadas, elas devem ser direcionadas para grupos de usuários. Você pode fazer isso criando a política (ao Salvar) ou posteriormente selecionando Gerenciar Implantação na seção Política (no mesmo nível de Adicionar).

## <a name="remediating-medium-or-high-risk-access-events"></a>Correção de eventos de acesso de risco médio ou alto
Se um usuário relata que agora deve executar a MFA quando isso não era exigido anteriormente, o suporte pode examinar seu status de uma perspectiva de risco.  

Os usuários dentro da organização com uma função de Administrador Global ou Administrador de Segurança podem usar o Azure AD Identity Protection para examinar os eventos de risco que contribuíram para a pontuação de risco calculada. Se eles identificarem alguns eventos que foram marcados como suspeitos, mas que foram confirmados com sendo válidos (como um logon de um local desconhecido quando um funcionário está em férias), o administrador poderá resolver o evento para que ele não contribua mais para a pontuação de risco.

## <a name="next-steps"></a>Próximas etapas

[Saiba mais sobre as recomendações de política para proteger arquivos e sites do SharePoint](sharepoint-file-access-policies.md)
