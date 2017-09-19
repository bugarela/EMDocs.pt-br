---
title: "Políticas de documento seguro recomendadas – Microsoft 365 Enterprise | Microsoft Docs"
description: "Descreve as políticas para as recomendações da Microsoft sobre como proteger o acesso a arquivos do SharePoint."
author: jeffgilb
manager: femila
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 8d38b1f9f899bcf61b1d35c8962a6829ce3d9a56
ms.sourcegitcommit: 0e0a15476e3bbd2d4ac6101c2cedd02e082ee25d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2017
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Recomendações de política para proteger arquivos e sites do SharePoint
As recomendações a seguir são fornecidas *adicionalmente* às [recomendações de política de acesso e identidade comum](identity-access-policies.md) e [recomendações de política para proteger o email](secure-email-recommended-policies.md). Para proteger os arquivos do SharePoint Online, as novas políticas devem ser criadas e as existentes devem ser alteradas, conforme descrito aqui. 

As seguintes recomendações se baseiam em três diferentes camadas de segurança e proteção para os arquivos do SharePoint que podem ser aplicadas com base na granularidade de suas necessidades: **linha de base**, **confidencial** e **altamente controlada**. Você pode aprender mais sobre esses níveis de segurança e os sistemas operacionais de cliente recomendada, referenciados por essas recomendações na [introdução de configurações e políticas de segurança recomendadas](microsoft-365-policies-configurations.md).

>[!NOTE]
>Todos os grupos de segurança criados como parte dessas recomendações devem ser criados com recursos do Office habilitados. Isso é especificamente importante para a implantação do AIP ao proteger documentos no SharePoint. 
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
Para criar uma nova Política de Acesso Condicional do Intune para SharePoint Online, faça logon no [Portal de Gerenciamento da Microsoft](http://manage.microsoft.com) com suas credenciais de administrador e navegue até **Política** > **Acesso Condicional** > **Política do SharePoint Online**.

![Política do SharePoint Online](./media/secure-docs/sharepoint-online-policy.png)

Você deve definir uma política de acesso condicional especificamente para o SharePoint Online no Portal de Gerenciamento do Intune para exigir um dispositivo em conformidade ou ingressado no domínio.
| Category|Tipo|Propriedades|Valores|Anotações|
|:-----|:-----|:-----|:-----|:-----|
|**Acesso ao aplicativo**|OneDrive for Business e outros aplicativos que usam autenticação moderna|Todas as plataformas|verdadeiro|Selecionada|
|     |     |O Windows deve atender aos seguintes requisitos|O dispositivo deve estar ingressado no domínio ou estar em conformidade|Selecionado (Lista)|
|     |     |Plataformas específicas|Falso||
|     |Acesso do navegador ao SharePoint e OneDrive for Business |Bloquear dispositivos sem conformidade nas mesmas plataformas que o OneDrive for Business|verdadeiro|Verificar|
|**Implantação de política**|Grupos de destino|Selecione os grupos do Active Directory a serem atingidos por essa política|     |     |
|     |     |todos os usuários|Falso|     |
|     |     |Grupos de segurança selecionados|verdadeiro|Selecionada|
|     |     |Modificar|Selecione grupos de segurança específicos que contém os usuários de destino.|     |
|     |Grupos isentos|Selecione os grupos do Active Directory a serem isentados desta política (substitui membros da lista de Grupos de Destino).|     |     |    
|     |     |Nenhum usuário isento|verdadeiro|Selecionada|
|     |     |Grupos de segurança selecionados|Falso|     |

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>Acesso condicional para gerenciamento de aplicativos móveis para o SharePoint Online

Você deve definir uma política de acesso condicional especificamente para o SharePoint Online no Portal de Gerenciamento do Intune para gerenciar aplicativos móveis.

Para gerenciar aplicativos móveis, faça logon no Portal do Microsoft Azure com suas credenciais de administrador e, em seguida, navegue até **Proteção de Aplicativo do Intune** > **Configurações** > **Acesso Condicional** > **SharePoint Online**.

| Category|Tipo|Propriedades|Valores|Anotações|
|:-----|:-----|:-----|:-----|:-----|
|**Acesso ao aplicativo**|Aplicativos permitidos|Habilitar acesso ao aplicativo|Permitir os aplicativos que dão suporte a políticas de aplicativo do Intune|Selecionado (lista) – isso resulta em uma lista de combinações de aplicativos/plataforma com suporte pelas políticas de aplicativo do Intune.|
|**Acesso do usuário**|     |Grupos de usuários com restrições|Adicionar grupos de usuários – selecione grupos de segurança específicos que contém os usuários de destino.|Inicie com o grupo de segurança, incluindo usuários piloto.|
|     |     |Grupos de usuários isentos|Grupos de segurança de exceção|     |

### <a name="apply-to"></a>Aplicar a

Depois que o projeto foi concluído, essas políticas devem aplicadas a todos os usuários em sua organização.

## <a name="sensitive"></a>Confidencial 

### <a name="low-and-above-risk-requires-mfa"></a>O risco baixo e superior requer a MFA

Faça as seguintes alterações para a política de AC existente criada ao aplicar as [recomendações de política para proteger email](secure-email-recommended-policies.md):

| Category|Tipo|Propriedades|Valores|Anotações|
|:-----|:-----|:-----|:-----|:-----|
|Atribuições|Aplicativos em nuvem|Incluir|Selecionar aplicativos:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|Selecione as duas opções|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio

(Consulte as instruções de linha de base)

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>Acesso condicional para gerenciamento de aplicativos móveis para o SharePoint Online

(Consulte as instruções de linha de base)

## <a name="highly-regulated"></a>Altamente controlada 

### <a name="mfa-required"></a>MFA necessária

Faça as seguintes alterações para a política de AC existente criada ao aplicar as [recomendações de política para proteger email](secure-email-recommended-policies.md):

| Category|Tipo|Propriedades|Valores|Anotações|
|:-----|:-----|:-----|:-----|:-----|
|Atribuições|Aplicativos em nuvem|Incluir|Selecionar aplicativos:<br></br>  Office 365 Exchange Online<br></br>  Office 365 SharePoint Online|Selecione as duas opções|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio
(Consulte as instruções de linha de base)

### <a name="mobile-application-management-conditional-access-for-sharepoint-online"></a>Acesso condicional para gerenciamento de aplicativos móveis para o SharePoint Online
(Consulte as instruções de linha de base)

## <a name="additional-configurations"></a>Configurações adicionais
Além das políticas acima, você também deve bloquear protocolos herdados que não dão suporte à autenticação moderna.

### <a name="lock-down-legacy-protocols"></a>Bloquear protocolos herdados
As políticas de acesso condicional protegem o acesso por meio de fluxos de navegador e aplicativos que usam autenticação moderna, como o Office 2016 e os aplicativos na lista de plataformas com suporte. Para aplicativos da área de trabalho mais antigos do Office, como o Office 2010, a política de acesso condicional não é aplicada. 

Aplicativos mais antigos que não usam autenticação moderna podem ser bloqueados [usando o portal de administração do OneDrive](https://support.office.com/article/Control-access-based-on-network-location-or-app-59b83701-cefd-4bf8-b4d1-d4659b60da08). O cmdlet do PowerShell de administração do SharePoint também pode ser usado para desabilitar os protocolos herdados do SharePoint. Para usar o PowerShell, basta executar o [cmdlet Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) e definir **-LegacyAuthProtocolsEnabled** como **$false**.  Depois de definido, o suporte a protocolos herdados é desabilitado e todo o acesso ao SharePoint usando aplicativos cliente mais antigos é bloqueado.
                                                     
## <a name="next-steps"></a>Próximas etapas
[Saiba mais sobre os serviços do Microsoft 365](index.md)
