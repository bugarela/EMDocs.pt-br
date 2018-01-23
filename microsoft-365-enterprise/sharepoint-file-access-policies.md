---
title: "Políticas de documento seguro recomendadas – Microsoft 365 Enterprise | Microsoft Docs"
description: "Descreve as políticas para as recomendações da Microsoft sobre como proteger o acesso a arquivos do SharePoint."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 01/18/2018
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 3eabab5a19c99fe97d56ed3d802c026c0b0bc6ef
ms.sourcegitcommit: eb3521981c5dec164ce2a14b4d4d53830b5ba461
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2018
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendações de política para proteger arquivos e sites do SharePoint
As recomendações a seguir são fornecidas *adicionalmente* às [recomendações de política de acesso e identidade comum](identity-access-policies.md) e [recomendações de política para proteger o email](secure-email-recommended-policies.md). Para proteger os arquivos do SharePoint Online, as novas políticas devem ser criadas e as existentes devem ser alteradas, conforme descrito aqui.

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

### <a name="medium-and-above-risk-requires-mfa"></a>O risco médio e superior requer a MFA
Faça as seguintes alterações para a política de AC existente criada ao aplicar as [recomendações de política para proteger email](secure-email-recommended-policies.md):

| Category|Tipo|Propriedades|Valores|Anotações|
|:-----|:-----|:-----|:-----|:-----|
|Atribuições|Aplicativos em nuvem|Incluir|Selecionar aplicativos:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|Selecione as duas opções|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio

Para criar uma política de acesso condicional para o Exchange Online:

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais. Depois de entrar com êxito, você verá o Painel do Azure.

2. Escolha **Azure Active Directory** no menu à esquerda.

3. Na seção **Segurança**, escolha **Acesso condicional**.

4. Escolha **Nova política**.

5. Insira um nome para a política e escolha os **Usuários e grupos** aos quais deseja aplicar a política.

6. Escolha **Aplicativos na nuvem**.

7. Escolha **Selecionar aplicativos**, selecione **Office 365 SharePoint Online** na lista **Aplicativos na nuvem** e clique em **Selecionar**. Depois que o aplicativo **Office 365 SharePoint Online** for selecionado, clique em **Concluído**.

8. Escolha **Conceder** na seção **Controles de acesso**.

9. Escolha **Conceder acesso**, selecione **Exigir que o dispositivo seja marcado como em conformidade** e **Exigir que esteja ingressado no domínio (Azure AD Híbrido)** e, em seguida, escolha **Selecionar**.

10. Clique em **Criar** para criar a política de acesso condicional do Exchange Online.

    > [!NOTE]
    > Ao começar a usar o Intune no Azure, você precisará criar todas as políticas de acesso condicional na carga de trabalho do Azure Active Directory. O Intune fornece um link para a carga de trabalho de políticas de acesso condicional do Azure AD em seu portal para facilitar o processo.

    > [!IMPORTANT]
    > Se você precisar de assistência ao migrar as políticas de acesso condicional que já foram criadas no portal clássico do Intune para o Intune no portal do Azure, consulte o tópico [Reatribuir políticas de acesso condicional no portal clássico do Intune para o Portal do Azure](https://docs.microsoft.com/intune/conditional-access-intune-reassign). 

### <a name="app-based-conditional-access-for-sharepoint-online"></a>Acesso condicional baseado em aplicativo para o SharePoint Online

Você pode adicionar mais uma camada de segurança, configurando uma política de acesso condicional baseada em aplicativo para o SharePoint Online no Intune no portal do Azure. Ao aplicar um acesso condicional baseado em aplicativo no SharePoint Online, você passa a exigir que os usuários usem apenas esse aplicativo para acessar recursos corporativos.

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

Faça as seguintes alterações para a política de AC existente criada ao aplicar as [recomendações de política para proteger email](secure-email-recommended-policies.md):

| Category|Tipo|Propriedades|Valores|Anotações|
|:-----|:-----|:-----|:-----|:-----|
|Atribuições|Aplicativos em nuvem|Incluir|Selecionar aplicativos:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|Selecione as duas opções|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio

(Consulte as instruções de linha de base)

### <a name="app-based-conditional-access-for-sharepoint-online"></a>Acesso condicional baseado em aplicativo para o SharePoint Online

(Consulte as instruções de linha de base)

## <a name="highly-regulated"></a>Altamente controlada

### <a name="mfa-required"></a>MFA necessária

Faça as seguintes alterações para a política de AC existente criada ao aplicar as [recomendações de política para proteger email](secure-email-recommended-policies.md):

| Category|Tipo|Propriedades|Valores|Anotações|
|:-----|:-----|:-----|:-----|:-----|
|Atribuições|Aplicativos em nuvem|Incluir|Selecionar aplicativos:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|Selecione as duas opções|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio
(Consulte as instruções de linha de base)

### <a name="app-based-conditional-access-for-sharepoint-online"></a>Acesso condicional baseado em aplicativo para o SharePoint Online
(Consulte as instruções de linha de base)

## <a name="additional-configurations"></a>Configurações adicionais
Além das políticas acima, você também deve bloquear protocolos herdados que não dão suporte à autenticação moderna.

### <a name="lock-down-legacy-protocols"></a>Bloquear protocolos herdados
As políticas de acesso condicional protegem o acesso por meio de fluxos de navegador e aplicativos que usam autenticação moderna, como o Office 2016 e os aplicativos na lista de plataformas com suporte. Para aplicativos da área de trabalho mais antigos do Office, como o Office 2010, a política de acesso condicional não é aplicada.

Aplicativos mais antigos que não usam autenticação moderna podem ser bloqueados [usando o portal de administração do OneDrive](https://support.office.com/article/Control-access-based-on-network-location-or-app-59b83701-cefd-4bf8-b4d1-d4659b60da08). O cmdlet do PowerShell de administração do SharePoint também pode ser usado para desabilitar os protocolos herdados do SharePoint. Para usar o PowerShell, basta executar o [cmdlet Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) e definir **-LegacyAuthProtocolsEnabled** como **$false**.  Depois de definido, o suporte a protocolos herdados é desabilitado e todo o acesso ao SharePoint usando aplicativos cliente mais antigos é bloqueado.

## <a name="next-steps"></a>Próximas etapas
[Saiba mais sobre os serviços do Microsoft 365](index.md)
