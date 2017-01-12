---
title: Proteger dados da empresa sem gerenciar dispositivos com o Intune | Microsoft Docs
description: "O EMS oferece funcionalidades inovadoras de proteção contra perda de dados com o Microsoft Intune. Com ele, é possível proteger dados da empresa e manter a experiência excelente do usuário com os aplicativos do Office 365 com os quais os funcionários já estão acostumados, sem a necessidade de gerenciar seus dispositivos."
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 12/15/2016
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b46877f3-cf32-4919-ba63-4df55cd2af32
ms.reviewer: vlpetros
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 83e901c3f5d9e6e35aea989de146e59ddc3354ef
ms.openlocfilehash: 19d2c610417667aec3346ac7d25d2bac95c7d8ba


---

# <a name="protect-company-data-without-managing-devices-with-intune"></a>Proteger dados da empresa sem gerenciar dispositivos com o Intune
No mundo da tecnologia móvel de hoje, os funcionários precisam acessar os dados corporativos e as ferramentas de produtividade em seus próprios dispositivos móveis, onde quer que estejam. Devido à sua popularidade e importância, muitas organizações buscam proteção adicional para os dados do Office 365 para evitar a perda de dados dos aplicativos móveis do Office, sem prejudicar a experiência excelente dos usuários finais. A TI precisa proteger o acesso ao Office 365 e evitar a perda de dados corporativos dos aplicativos e dos dispositivos móveis não pertencentes nem gerenciados pela organização. O problema é que, embora a TI precise manter os dados corporativos seguros, muitos funcionários precisam manter a privacidade quando a TI assume o controle dos seus dispositivos pessoais.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>Como o EMS (Enterprise Mobility + Security) pode ajudar você?

O EMS oferece funcionalidades inovadoras de proteção contra perda de dados com o Microsoft Intune. Com ele, é possível proteger dados da empresa e manter a experiência excelente do usuário com os aplicativos do Office 365 com os quais os funcionários já estão acostumados. E você pode fazer isso sem exigir que os usuários registrem os dispositivos para gerenciamento, o que pode aumentar de maneira significativa as chances de sucesso do seu programa BYOD e a conformidade do usuário final com as políticas de TI. Você obtém o controle do que precisa e os usuários desfrutam de uma experiência moderna já conhecida por eles.  Uma vez que o Microsoft Intune funciona diretamente com o Azure Active Directory e com o Office 365 para gerenciar o acesso e proteger os dados da empresa, não há a necessidade de instalar e manter uma infraestrutura local nem de encaminhar todo o tráfego por meio dela.

### <a name="recommended-solution"></a>Solução recomendada

Com o Microsoft Intune, as organizações podem fornecer acesso a aplicativos móveis e proteção contra vazamentos de dados do Office 365 sem exigir que os funcionários se registrem no gerenciamento de dispositivo. Se necessário, o MDM (gerenciamento de dispositivo móvel) ainda pode ser feito, mas agora ele é opcional. As funcionalidades avançadas de proteção de aplicativo do Intune ajudam a IT na proteção dos dados da empresa no nível do aplicativo sem a necessidade de gerenciar dispositivos reais. Para dados altamente confidenciais, a proteção pode estender-se ainda mais até o nível do arquivo com a Proteção de Informações do Azure. Funcionários, fornecedores e parceiros podem usar seus dispositivos móveis favoritos para acessar os dados corporativos e as ferramentas de produtividade com as quais estão familiarizados, sem o risco de sofrerem intrusão de privacidade. E se a TI já tiver uma solução MDM em funcionamento, o Intune poderá adicionar proteção avançada contra perda de dados do controle de acesso do Office 365, sem a necessidade de cancelar o registro dos dispositivos na solução MDM atual e, depois, registrá-los novamente no MDM do Intune.

Assista a esta demonstração para ver como você pode evitar a perda de dados de aplicativos móveis (incluindo do O365 e dos aplicativos LOB (linha de negócios) internos) usando as funcionalidades inovadoras de proteção de aplicativo do Intune que não exigem o registro dos dispositivos dos usuários no MDM do Intune:

<iframe width="675" height="480"  src="https://www.youtube.com/embed/BcwgKmsAy18?list=TLGGQ9qBhVYxOZIxMzEyMjAxNg" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>Como implementar esta solução

O restante dessa solução está dividido nas seções a seguir, que mostram como proteger os dados de empresa do Office 365 com o Intune:

- **Proteger dados de aplicativo com políticas de proteção de aplicativo móvel do Intune**. Esta seção descreve como criar e implantar políticas de proteção de aplicativo do Microsoft Intune para fornecer funcionalidades de prevenção contra perda de dados (como copiar/colar/salvar como/PIN/criptografia/apagamento seletivo, etc.) para usuários de dispositivos móveis não gerenciados.

- **Permitir que apenas aplicativos móveis que dão suporte às políticas de proteção de aplicativo acessem os serviços do Office 365**. Nesta seção, você aprenderá a criar uma política que permita aos aplicativos móveis que dão suporte às políticas de MAM do Intune acessar serviços do O365, como o Exchange Online.

## <a name="protect-app-data-with-intune-mobile-app-protection-policies"></a>Proteger dados de aplicativo com políticas de proteção de aplicativo móvel do Intune

Para proteger dados de aplicativos em dispositivos não gerenciados, você deixa de implantar aplicativos como faria com os dispositivos gerenciados. Em vez disso, os usuários baixam os aplicativos do Office 365 da loja de aplicativos pública em seus dispositivos pessoais iOS ou Android e fazem logon com suas contas de trabalho como de costume.

As políticas de proteção desses aplicativos para dispositivos iOS e Android são facilmente criadas no Portal do Azure. Esses tipos de políticas permitem que você restrinja ações do usuário, como recortar, copiar, colar e salvar como, ou imponha um PIN, exija criptografia e apague de maneira seletiva os dados da empresa contidos nos aplicativos móveis. Ao serem atribuídas aos usuários, as políticas de proteção de aplicativo são automaticamente aplicadas pelo Intune e impostas entre os aplicativos e as contas pessoais e corporativas. Como o Intune é perfeitamente integrado ao Azure AD e ao Office 365, os dados de trabalho são protegidos sem que os dados pessoais nos aplicativos do Office sejam usados.

>[!NOTE]
>Políticas de proteção de aplicativo como essas estão disponíveis para computadores Windows 10 gerenciados pelo Intune como dispositivos móveis usando as [políticas de WIP (Proteção de Informações do Windows)](https://technet.microsoft.com/itpro/windows/keep-secure/create-wip-policy-using-intune).

Veja como é fácil selecionar os aplicativos a serem protegidos, definir as configurações de política de proteção de aplicativo e implantar as políticas em grupos de usuários finais depois de fazer logon no Portal do Azure:

>[!TIP]
>Para encontrar as configurações de política de proteção de aplicativo do Intune, faça logon no [Portal do Azure](https://portal.azure.com) com suas credenciais de administrador do Intune e pesquise **Proteção de Aplicativo do Intune** na caixa *Pesquisar recursos* na parte superior do portal. Todas as etapas seguintes são concluídas lá.

-   **Crie uma política de proteção de aplicativo móvel.** Além de nomear (e, como alternativa, fornecer uma descrição) a política, tudo o que você precisa fazer para [criar uma política de proteção de aplicativo](https://docs.microsoft.com/intune-azure/manage-apps/app-protection-policies#create-an-app-protection-policy) é definir a plataforma, selecionar os aplicativos que você deseja proteger e definir as configurações de política a serem impostas:

> **Defina a plataforma**: ao criar uma nova política, você poderá selecionar as plataformas iOS ou Android, mas não poderá criar políticas de proteção de aplicativo para os dispositivos Windows aqui. Em vez disso, você pode [usar as políticas de WIP (Proteção de Informações do Windows)](https://technet.microsoft.com/itpro/windows/keep-secure/create-wip-policy-using-intune).

> **Selecione um ou mais aplicativos** como destino na lista de aplicativos disponíveis que podem ser protegidos em dispositivos não gerenciados. À medida que mais aplicativos tiverem suporte, eles serão adicionados automaticamente à lista de aplicativos disponíveis. Por padrão, nenhum aplicativo estará selecionado, mas você poderá clicar e manter pressionado a tecla CTRL para selecionar quantos aplicativos você deseja proteger com a política. Como alternativa, você pode [adicionar o nosso próprio aplicativo LOB (linha de negócios)](https://docs.microsoft.com/intune/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune) para iOS ou Android.

> **Defina as configurações necessárias da política** [para iOS ou Android](https://docs.microsoft.com/en-us/intune-azure/manage-apps/app-protection-policies#policy-settings) em relação à realocação de dados (recortar, copiar, colar, salvar como, criptografia, etc.) e ao acesso (exigir PIN, intervalo offline, etc.).

- **Implante a política de proteção de aplicativo a grupos de usuários** [selecionando os grupos de usuários](https://docs.microsoft.com/intune-azure/manage-apps/app-protection-policies#deploy-a-policy-to-users) aos quais as políticas serão aplicadas. Podem ser os mesmos grupos que você já gerencia no Office 365 ou qualquer grupo disponível no Azure Active Directory.

Ao abrir pela primeira vez um aplicativo protegido por uma política de proteção de aplicativo, o usuário final receberá uma mensagem informando que o departamento de TI começou a proteger os dados da empresa no aplicativo. Se as configurações de acesso da política tiverem sido configuradas para exigir PIN ou senha, o usuário também precisará criar um ou uma antes de obter acesso ao aplicativo protegido, conforme mostrado no dispositivo Android abaixo:

![Exigência de PIN da política de proteção de aplicativo](..\Solutions\media\protect-company-data-without-managing-devices\protect-company-data-without-managing-devices-fig1.png)

Uma vez que as políticas de proteção de aplicativo funcionam no nível do aplicativo e não do dispositivo, o Intune facilita para TI a proteção de dados da empresa restringindo o compartilhamento de dados da empresa entre os aplicativos gerenciados e pessoais, entre as contas corporativas e pessoais no mesmo aplicativo e permitindo que os dados corporativos sejam salvos apenas em localizações aprovadas. Os funcionários móveis não precisam mais ceder o controle de seus dispositivos para obter acesso a dados e a ferramentas corporativas essenciais onde quer que estejam.

>[!TIP]
>Para dados altamente confidenciais, a proteção pode estender-se ainda mais até o nível do arquivo com a tecnologia de proteção usada pela Proteção de Informações do Azure: [Azure RMS (Rights Management Service).](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

## <a name="allow-only-mobile-apps-that-support-app-protection-policies-to-access-office-365-services"></a>Permitir que apenas aplicativos móveis que dão suporte às políticas de proteção de aplicativo acessem os serviços do Office 365
Por padrão, todos os usuários e todos os aplicativos têm acesso às informações da empresa hospedadas pelo Exchange Online. Com o Intune, você pode controlar facilmente quem e quais aplicativos têm acesso configurando políticas de acesso condicional de aplicativo que restringem o acesso aos serviços do Office 365 somente aos aplicativos que dão suporte às políticas de proteção de aplicativo do Intune. Por exemplo, no [Portal do Azure](https://portal.azure.com) você pode criar uma política que restrinja o acesso ao Exchange Online a somente determinados grupos e aplicativos no Android e iOS, independentemente se o dispositivo é gerenciado ou não.

- **Crie uma política de acesso condicional de proteção de aplicativo para o Exchange Online.** [Essas políticas são criadas](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-exchange-online) no mesmo local que você cria as políticas de proteção de aplicativo mencionadas anteriormente. Além de definir quais aplicativos poderão acessar o Exchange Online, você também precisará definir os grupos de acesso de usuários para gerenciar as conexões ao Exchange Online.

- Os usuários precisarão **configurar um aplicativo agente** na primeira vez que tentarem usar um aplicativo com suporte à política para acessar o Exchange Online. Para os dispositivos iOS, o aplicativo agente é o Microsoft Authenticator, enquanto que, para os dispositivos Android, o aplicativo Portal da Empresa do Intune precisará ser instalado. Embora [esses aplicativos agente](https://docs.microsoft.com/intune/deploy-use/use-apps-with-mam-ca) registrarão o dispositivo no Azure AD para fornecer a verificação de identidade do dispositivo, eles não registrarão o dispositivo no gerenciamento.

Com a política de acesso condicional para o Exchange Online em vigor, os usuários receberão um email semelhante ao encontrado abaixo ao tentarem acessar seus emails corporativos usando o cliente de email nativo, conforme mostrado em um dispositivo Android:

![Exigência do aplicativo Outlook em relação à política de proteção de aplicativo](..\Solutions\media\protect-company-data-without-managing-devices\protect-company-data-without-managing-devices-fig2.png)

Quando o usuário final toca no link *Comece agora mesmo* no email, o navegador da Web padrão do dispositivo é aberto e exibe https://portal.manage.microsoft.com/OutlookRedirect.aspx. De lá, o usuário deve instalar o aplicativo Microsoft Outlook gratuito da loja de aplicativos usada pelo dispositivo.

### <a name="learn-more"></a>Saiba mais

[Começar a usar o Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)



<!--HONumber=Jan17_HO1-->


