---
title: "Visão geral das políticas de acesso do dispositivo e identidade – Microsoft 365 Enterprise | Microsoft Docs"
description: "Descreve as políticas para as recomendações da Microsoft sobre como aplicar as configurações e políticas de dispositivo e identidade."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 12/10/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: a25903de35ad349a09056ab24da5e00cd1a07695
ms.sourcegitcommit: 3cc06a29762d99a3649fb3cc80f9534dc6396d80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2017
---
# <a name="general-identity-and-device-access-policy-recommendations"></a>Recomendações gerais de política de acesso de dispositivo e identidade
Este artigo descreve as políticas recomendadas comuns para ajudá-lo a proteger o Microsoft 365 Enterprise. Também são abordadas as configurações padrão do cliente da plataforma que recomendamos para oferecer a melhor experiência SSO para seus usuários, bem como os pré-requisitos técnicos para acesso condicional.

Estas diretrizes descrevem como implantar as políticas recomendadas em um ambiente recém-provisionado. Configurar essas políticas em um ambiente de laboratório separado permite compreender e avaliar as políticas recomendadas antes de preparar a distribuição para seus ambientes de produção e pré-produção. Seu ambiente recém-provisionado pode estar somente em nuvem ou ser híbrido.  

Para implantar as políticas recomendadas com êxito, você precisa executar ações no Portal do Azure para atender aos pré-requisitos mencionados anteriormente. Especificamente, você precisa:
* Configurar redes nomeadas, para garantir que o Azure Identity Protection possa gerar corretamente a pontuação de risco
* Exigir que todos os usuários se registrem para a MFA (autenticação multifator)
* Configurar a sincronização de hash de senha e a redefinição de senha de autoatendimento para permitir que os próprios usuários possam redefinir as senhas

Você pode direcionar políticas do Azure AD e do Intune para grupos ou usuários específicos. Sugerimos que você implante as políticas definidas anteriormente em etapas. Dessa forma, que você pode validar o desempenho das políticas e das suas equipes de suporte em relação à política incrementalmente.


## <a name="prerequisites"></a>Pré-requisitos

Antes de implementar as políticas descritas no restante deste documento, existem vários pré-requisitos que sua organização deve atender:
* [Configurar sincronização de hash de senha](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Isso deve ser habilitado para detectar credenciais perdidas e atuar sobre elas para Acesso Condicional com base no risco. **Observação:** isso é necessário, independentemente de a sua organização usar autenticação gerenciada, como PTA (Autenticação de passagem), ou autenticação federada.
* [Configurar redes nomeadas](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). O Azure AD Identity Protection coleta e analisa todos os dados de sessão disponíveis para gerar uma pontuação de risco. É recomendável que você especifique os intervalos de IP públicos da sua organização para sua rede na configuração de redes nomeadas do Azure AD. O tráfego proveniente desses intervalos recebe uma pontuação de risco reduzida, para que o tráfego de fora do ambiente corporativo seja tratado como uma pontuação de risco mais alta.
* [Registrar todos os usuários com a MFA (autenticação multifator)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-manage-users-and-devices). O Azure AD Identity Protection utiliza o MFA do Azure para executar a verificação de segurança adicional. É recomendável que você exija que todos os usuários se registrem para o MFA do Azure antecipadamente.
* [Habilitar o registro automático de dispositivo de computadores Windows ingressados no domínio](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). O acesso condicional pode garantir que o dispositivo se conectando ao serviço é um dispositivo em conformidade ou ingressado no domínio. Para dar suporte a isso em computadores Windows, o dispositivo deve ser registrado com o Azure AD.  Este artigo discute como configurar o registro de dispositivo automático.
* **Preparar sua equipe de suporte**. Tenha um plano em vigor para os usuários que não podem concluir a MFA. Isso pode ser adicioná-los a um grupo de exclusão de política ou registrar novas informações de MFA para eles. Antes de fazer qualquer uma dessas alterações importantes de segurança, você precisa garantir que o usuário atual está fazendo a solicitação. Exigir que os gerentes dos usuários ajudem na aprovação é uma etapa eficaz.
* [Configurar o write-back de senha para o AD local](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). O write-back de senha permite que o Azure AD exija que os usuários alterem suas senhas locais quando um alto risco de comprometimento de contas tiver sido detectado. Você pode habilitar esse recurso usando o Azure AD Connect de uma das duas maneiras. Você pode habilitar o write-back de senha na tela de recursos opcionais do assistente de configuração do Azure AD Connect ou pode habilitá-lo por meio do Windows PowerShell.  
* [Habilitar a autenticação moderna](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) e [proteger pontos de extremidade herdados](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-supported-apps).  O acesso condicional funciona com aplicativos móveis e de área de trabalho que usam autenticação moderna. Se o aplicativo usa protocolos de autenticação herdados, ele pode obter acesso apesar das condições sendo aplicadas. É importante saber quais aplicativos podem usar as regras de acesso condicional e as etapas que você precisa realizar para proteger outros pontos de entrada do aplicativo.
* [Habilitar a Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/get-started/infoprotect-tutorial-step1) ativando o Rights Management. Use a Proteção de Informações do Azure com o email para começar a trabalhar com a classificação de emails. Siga o tutorial de início rápido para personalizar e publicar a política.  

### <a name="recommended-email-clients"></a>Clientes de email recomendados
Os clientes de email a seguir dão suporte ao acesso condicional e à autenticação moderna. A Proteção de Informações do Azure ainda não está disponível para todos os clientes.

|Plataforma|Cliente|Versão/Notas|Azure Information Protection|
|:-------|:-----|:------------|:--------------------|
|**Windows**|Outlook|2016, 2013 [Habilitar autenticação moderna](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910)|Sim|
|**iOS**|Outlook|[Mais recente](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|Não|
|**Android**|Outlook|[Mais recente](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|Não|
|**macOS**|Visualização pública||Não|
|**Linux**|Sem suporte||Não|

Para acessar os documentos protegidos pela Proteção de Informações do Azure, pode ser necessário ter software adicional. Certifique-se de que você esteja usando os [formatos de documento e software com suporte](https://docs.microsoft.com/information-protection/get-started/requirements-applications) para criar e exibir documentos protegidos com a Proteção de Informações do Azure.


### <a name="recommended-client-platforms-when-securing-documents"></a>Plataformas de cliente recomendadas ao proteger documentos
Os seguintes clientes são recomendados quando uma política de documentos seguros é aplicada.

|Plataforma|Word/Excel/PowerPoint|OneNote|Aplicativo OneDrive|Aplicativo do SharePoint|Cliente de sincronização do OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Com suporte|Com suporte|N/D|N/D|Versão prévia<sup>*</sup>|
|Windows 8.1|Com suporte|Com suporte|N/D|N/D|Versão prévia<sup>*</sup>|
|Windows 10|Com suporte|Com suporte|N/D|N/D|Versão prévia<sup>*</sup>|
|Windows Phone 10|Sem suporte|Sem suporte|Com suporte|Com suporte|N/D|
|Android|Com suporte|Com suporte|Com suporte|Com suporte|N/D|
|iOS|Com suporte|Com suporte|Com suporte|Com suporte|N/D|
|macOS|Visualização Pública|Visualização Pública|N/D|N/D|Sem suporte|
|Linux|Sem suporte|Sem suporte|Sem suporte|Sem suporte|Sem suporte|

<sup>*</sup> Saiba mais sobre a [Versão prévia do cliente de sincronização do OneDrive](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

> [!NOTE]
> As seguintes recomendações se baseiam em três diferentes camadas de segurança e proteção para seu email que podem ser aplicadas com base na granularidade de suas necessidades: **linha de base**, **confidencial** e **altamente controlada**. Você pode aprender mais sobre esses níveis de segurança e os sistemas operacionais de cliente recomendada, referenciados por essas recomendações na [introdução de configurações e políticas de segurança recomendadas](microsoft-365-policies-configurations.md).


## <a name="baseline"></a>Linha de base
Esta seção descreve as recomendações para a camada de linha de base de dados, identidade e proteção do dispositivo. Essas recomendações devem atender às necessidades de proteção padrão de muitas organizações.

>[!NOTE]
>As políticas abaixo são aditivas e se complementam. Cada seção descreve somente as adições aplicadas a cada camada.
>

### <a name="conditional-access-policy-settings"></a>Configurações de política de acesso condicional

#### <a name="identity-protection"></a>Proteção de identidade
Você pode fornecer a experiência de SSO (logon único) dos usuários conforme descrito nas seções anteriores. Você só precisará intervir quando necessário com base em [eventos de risco](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).  

* MFA necessária com base no risco de entrada **médio ou acima**
* Requer a alteração de senha segura para usuários de **alto** risco

>[!IMPORTANT]
>A [sincronização de senha](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) e a [redefinição de senha de autoatendimento](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) são necessárias para esta recomendação de política.
>

#### <a name="data-loss-prevention"></a>Prevenção de perda de dados
A meta de suas políticas de gerenciamento de aplicativo e dispositivo é proteger contra a perda de dados no caso de um dispositivo perdido ou roubado. Você pode fazer isso garantindo que o acesso aos dados está protegido por um PIN, que os dados estão criptografados no dispositivo e que o dispositivo não está comprometido.

|Recomendação de política|Descrição|
|:--------------------|:----------|
|**Requer gerenciamento do computador do usuário**|Exija que os usuários ingressem seus computadores Windows em um Domínio do Active Directory ou registrem seus computadores no gerenciamento com o Microsoft Intune ou System Center Configuration Manager.|
|**Aplicar configurações de segurança por meio de GPOs (objetos de política de grupo) ou políticas do Configuration Manager para computadores ingressados no domínio**|Implante as políticas que configuram computadores gerenciados para habilitar o BitLocker, o antivírus e o firewall.|
|**Exigir o gerenciamento de dispositivo móvel do usuário**|Exija que os dispositivos do usuário usados para acessar emails sejam gerenciados pelo Intune **ou** que o email da empresa seja acessado apenas por aplicativos móveis de email protegidos pelas políticas da Proteção de Aplicativo do Intune como o Outlook Mobile.|
|**Aplicar uma política de conformidade do dispositivo do Intune em dispositivos gerenciados**|Aplique uma política de conformidade de dispositivo do Intune para dispositivos móveis corporativos gerenciados e computadores gerenciados pelo Intune que exigem: um PIN com no mínimo seis caracteres, criptografia de dispositivo, um dispositivo íntegro (que não esteja com jailbreak ou com raiz, que passe o atestado de integridade) e, se disponível, exija dispositivos que são de **baixo** risco conforme determinado por um MTP de terceiros como o Lookout ou SkyCure.|
|**Aplicar uma Política de Proteção de Aplicativo do Intune para aplicativos gerenciados em execução em dispositivos não gerenciados**|Aplique uma Política de Proteção de Aplicativo do Intune para aplicativos gerenciados em execução em dispositivos móveis pessoais não gerenciados para exigir: um PIN com no mínimo 6 caracteres, criptografia de dados e que o dispositivo esteja íntegro (que não esteja com jailbreak ou com raiz, que passe o atestado de integridade).|

### <a name="user-impact"></a>Impacto do usuário

Para a maioria das organizações, é importante poder definir as expectativas dos usuários em relação a quando e para quais condições eles deverão se conectar no Office 365 para acessar seu email.  

Os usuários normalmente se beneficiam do SSO (logo único), exceto durante as seguintes situações:
* Ao solicitar tokens de autenticação para o Exchange Online:
  * Os usuários podem ser solicitados a utilizar a MFA sempre que um risco de entrada **médio ou acima** é detectado e os usuários ainda não executaram a MFA em suas sessões atuais.  
  * Os usuários precisarão usar aplicativos de email que dão suporte ao SDK de Proteção de Aplicativo do Intune ou acessar os emails de dispositivos ingressados no domínio do AD ou em conformidade com o Intune.
* Quando usuários em risco entram e concluem com sucesso a MFA, é solicitado que eles alterem a senha.

## <a name="sensitive"></a>Confidencial
Esta seção descreve as recomendações para a camada confidencial de dados, identidade e proteção do dispositivo. Essas recomendações são para clientes que têm um subconjunto de dados que devem ser protegidos em níveis mais altos ou exigem que todos os dados sejam protegidos nesses níveis mais altos.

Você pode aplicar mais proteção a todos ou conjuntos de dados específicos em seu ambiente do Office 365. Por exemplo, você pode aplicar políticas para garantir que os dados confidenciais serão compartilhados apenas entre aplicativos protegidos para evitar a perda de dados. É recomendável proteger identidades e dispositivos que acessam dados confidenciais com níveis compatíveis de segurança.

### <a name="conditional-access-policy-settings"></a>Configurações de política de acesso condicional
#### <a name="identity-protection"></a>Proteção de identidade

Você pode fornecer a experiência de SSO (logon único) dos usuários conforme descrito nas seções anteriores. Você só precisará intervir quando necessário com base em [eventos de risco](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Exigir a MFA em sessões de risco **baixo ou acima**
* Requer a alteração de senha segura para usuários de alto risco

>[!IMPORTANT]
>A [sincronização de senha](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) e a [redefinição de senha de autoatendimento](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) são necessárias para esta recomendação de política.
>

#### <a name="data-loss-prevention"></a>Prevenção de perda de dados

A meta dessas políticas de gerenciamento de aplicativo e dispositivo é proteger contra a perda de dados no caso de um dispositivo perdido ou roubado. Você pode fazer isso garantindo que o acesso aos dados está protegido por um PIN, que os dados estão criptografados no dispositivo e que o dispositivo não está comprometido.

|Recomendação de política|Descrição|
|:--------------------|:----------|
|**Requer gerenciamento do computador do usuário**|Exija que os usuários ingressem seus computadores em um Domínio do Active Directory ou registrem seus computadores no gerenciamento com o Intune ou Configuration Manager e garantam que esses dispositivos estejam em conformidade com as políticas antes de permitir o acesso ao email.|
|**Aplicar configurações de segurança por meio de GPOs (objetos de política de grupo) ou políticas do Configuration Manager para computadores ingressados no domínio**|Implante as políticas que configuram computadores gerenciados para habilitar o BitLocker, o antivírus e o firewall.|
|**Exigir o gerenciamento de dispositivo móvel do usuário**|Exija que os dispositivos do usuário usados para acessar emails sejam gerenciados pelo Intune **ou** que o email da empresa seja acessado apenas por aplicativos móveis de email protegidos pelas políticas da Proteção de Aplicativo do Intune como o Outlook Mobile.|
|**Aplicar uma política de conformidade do dispositivo do Intune em dispositivos gerenciados**|Aplique uma política de conformidade de dispositivo do Intune para dispositivos móveis corporativos gerenciados e computadores gerenciados pelo Intune que exigem: um PIN com no mínimo seis caracteres, criptografia de dispositivo, um dispositivo íntegro (que não esteja com jailbreak ou com raiz, que passe o atestado de integridade) e, se disponível, exija dispositivos que são de **baixo** risco conforme determinado por um MTP de terceiros como o Lookout ou SkyCure.|
|**Aplicar uma Política de Proteção de Aplicativo do Intune para aplicativos gerenciados em execução em dispositivos não gerenciados**|Aplique uma Política de Proteção de Aplicativo do Intune para aplicativos gerenciados em execução em dispositivos móveis pessoais não gerenciados para exigir: um PIN com no mínimo 6 caracteres, criptografia de dados e que o dispositivo esteja íntegro (que não esteja com jailbreak ou com raiz, que passe o atestado de integridade).|

### <a name="user-impact"></a>Impacto do usuário
Para a maioria das organizações, é importante poder definir as expectativas dos usuários específicas para quando e sob quais condições é esperado que eles entrem no email do Office 365.

Os usuários normalmente se beneficiam do SSO (logo único), exceto nas seguintes situações:
* Ao solicitar tokens de autenticação para o Exchange Online:
  * Os usuários serão solicitados a utilizar a MFA sempre que um risco de entrada **baixo ou acima** é detectado e os usuários ainda não executaram a MFA em suas sessões atuais.  
  * Os usuários precisarão usar aplicativos de email que dão suporte ao SDK de Proteção de Aplicativo do Intune ou acessar os emails de dispositivos ingressados no domínio do AD ou em conformidade com o Intune.
* Quando usuários em risco entram e concluem com sucesso a MFA, é solicitado que eles alterem a senha.

## <a name="highly-regulated"></a>Altamente controlada
Esta seção descreve as recomendações para a camada altamente controlada de dados, identidade e proteção do dispositivo. Essas recomendações são para clientes que podem ter uma quantidade muito pequena de dados altamente confidenciais, segredos comerciais ou dados controlados. A Microsoft fornece recursos para ajudar as organizações a atender a esses requisitos, incluindo proteção adicional para identidades e dispositivos.

### <a name="conditional-access-policy-settings"></a>Configurações de política de acesso condicional
#### <a name="identity-protection"></a>Proteção de identidade

Para a camada altamente controlada, a Microsoft recomenda a aplicação da MFA para todas as sessões.
* Exigir a MFA para todas as novas sessões
* Requer a alteração de senha segura para usuários de **alto** risco

>[!IMPORTANT]
>A [sincronização de senha](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) e a [redefinição de senha de autoatendimento](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) são necessárias para esta recomendação de política.
>

#### <a name="data-loss-prevention"></a>Prevenção de perda de dados
A meta dessas políticas de gerenciamento de aplicativo e dispositivo é evitar a perda de dados no caso de um dispositivo perdido ou roubado. Isso é feito garantindo que o acesso aos dados está protegido por um PIN, que os dados estão criptografados no dispositivo e que o dispositivo não está comprometido.

Para a camada altamente controlada, recomendamos exigir aplicativos que dão suporte à execução de política de Proteção de Aplicativo do Intune apenas em dispositivos ingressados no domínio ou em conformidade com o Intune.

|Recomendação de política|Descrição|
|:--------------------|:----------|
|**Requer gerenciamento do computador do usuário**|Exija que os usuários ingressem seus computadores Windows em um Domínio do Active Directory **ou** registrem seus computadores no gerenciamento com o Intune ou Configuration Manager e garantam que esses dispositivos estejam em conformidade com as políticas antes de permitir o acesso ao email.|
|**Aplicar configurações de segurança por meio de GPOs (objetos de política de grupo) ou políticas do Configuration Manager para computadores ingressados no domínio**|Implante as políticas que configuram computadores gerenciados para habilitar o BitLocker, o antivírus e o firewall.|
|**Exigir o gerenciamento de dispositivo móvel do usuário**|Exija que os dispositivos usados para acessar arquivos e o email do Office 365 sejam gerenciados pelo Intune ou que o email da empresa seja acessado apenas por aplicativos móveis de email protegidos pelas políticas da Proteção de Aplicativo do Intune como o Outlook Mobile.|
|**Aplicar uma política de conformidade do dispositivo do Intune em dispositivos gerenciados**|Aplique uma política de conformidade de dispositivo do Intune para dispositivos móveis corporativos gerenciados e computadores gerenciados pelo Intune que exigem: um PIN com no mínimo seis caracteres, criptografia de dispositivo, um dispositivo íntegro (que não esteja com jailbreak ou com raiz, que passe o atestado de integridade) e, se disponível, exija dispositivos que são de Baixo risco conforme determinado por um MTP de terceiros como o Lookout ou SkyCure.|

### <a name="user-impact"></a>Impacto do usuário
Para a maioria das organizações, é importante poder definir as expectativas dos usuários específicas para quando e sob quais condições é esperado que eles entrem nos arquivos do Office 365.

* Os usuários configurados como altamente regulamentados deverão se autenticar novamente com o MFA depois que a sessão expirar.
* Quando usuários em risco entrarem, será solicitado que eles alterem sua senha após concluir a MFA.
* Ao solicitar tokens de autenticação para o Exchange Online:
  * Será solicitado que os usuários realizem a MFA sempre que iniciarem uma nova sessão.  
  * Será exigido que os usuários usem aplicativos de email que dão suporte ao SDK de Proteção de Aplicativo do Intune
  * Será exigido que os usuários acessem emails de dispositivos ingressados em domínio de AD ou em conformidade do Intune.

## <a name="next-steps"></a>Próximas etapas

[Saiba mais sobre recomendações de política para proteger o email](secure-email-recommended-policies.md)
