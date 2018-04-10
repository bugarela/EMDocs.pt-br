---
title: Milhares de aplicativos, uma identidade
description: Este artigo descreve como o Enterprise Mobility + Security pode ser usado para fornecer uma única identidade que funcione em aplicativos baseados na Web do setor aproveitando as ferramentas do Azure Active Directory.
keywords: ''
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: ''
ms.service: active-directory
ms.technology: ''
ms.assetid: dd879a14-919e-431b-89b9-c035c83a6899
ROBOTS: ''
ms.reviewer: atkladak, jsnow
ms.suite: ems
ms.openlocfilehash: 7710b1465256e99b9a0f7fa05af780af079731ae
ms.sourcegitcommit: 4401a878f88cc60b3cfd90a915747fe37e333014
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2018
---
# <a name="thousands-of-apps-one-identity"></a>Milhares de aplicativos, uma identidade
O Azure AD (Active Directory) torna os usuários mais produtivos fornecendo a eles uma identidade comum para acessar recursos na nuvem e no local de aplicativos SaaS (software como serviço).

O Azure AD integra-se a muitos aplicativos SaaS populares de hoje, como Box, Twitter, ServiceNow, DocuSign, Workday, entre muitos outros. Ele dá suporte à autenticação SSO (logon único) e à identidade, além de proteger o gerenciamento de acesso a aplicativos de qualquer dispositivo de maneira segura e confiável.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?
O EMS (Enterprise Mobility + Security) é a única solução de nuvem abrangente que protege nativamente dados corporativos no próprio dispositivo e além dele, com quatro camadas de proteção de identidades, dispositivos, aplicativos e dados. O EMS ajuda a enfrentar um dos principais desafios do mundo dos dispositivos móveis, do mundo da nuvem – fornecer uma única identidade que funcione em todos os aplicativos baseados na Web do setor:
- Experiência de autenticação contínua conectada à nuvem
- Logon único para 1000 aplicativos pré-integrados ou seus próprios aplicativos
- Acesso remoto seguro aos aplicativos no local
- Suporte de mudança para a nuvem


## <a name="recommended-solution"></a>Solução recomendada
O Azure AD é uma solução de identidade de nuvem e gerenciamento de acesso que pode fornecer às organizações acesso a tudo que elas precisam de qualquer lugar — de maneira segura e produtiva — em colaboração com investimentos já feitos em ferramentas tradicionais.
### <a name="access-to-single-sign-on-applications"></a>Acesso a aplicativos de logon único

Antes do logon único, os administradores de TI tinham que gerenciar diferentes usuários e senhas para todos os diferentes aplicativos para os quais as organizações tinham que dar suporte:

- Os usuários inserem um nome de usuário e uma senha em cada aplicativo que usam
- Os usuários gerenciam muitas senhas
- A reutilização de senha é comum
- A revogação de acesso é muito difícil

De acordo com uma pesquisa recente, 63% das violações de dados confirmadas envolveram senhas fracas, padrão ou roubadas.

O logon único permite que os usuários acessem todos os aplicativos e recursos de que precisam para fechar negócios bastando efetuar logon uma única vez usando uma única conta de usuário. Depois de conectados, os usuários podem acessar todos os aplicativos de que precisam sem precisar se autenticar (por exemplo, digitar uma senha) pela segunda vez.

O Azure AD dá suporte a três tipos de autenticação de logon único:

- **Logon Único do Microsoft Azure AD:** essa opção usa logon federado para permitir que os usuários entrem automaticamente em aplicativos de terceiros, como o Salesforce, usando as informações da conta de usuário do Azure AD.
- **Logon Único com Senha:** essa opção permite aos usuários entrar automaticamente no aplicativo SaaS de terceiros pelo Azure AD usando as informações da conta de usuário de terceiros.
- **Logon Único Existente:** essa opção dá suporte ao logon único em empresas SaaS de terceiros usando o ADFS (Serviços de Federação do Active Directory) ou outro provedor de logon único de terceiros.

### <a name="how-single-sign-on-works"></a>Como o logon único funciona
O Azure AD dá suporte ao logon único em aplicativos que são compatíveis com qualquer um destes protocolos padrão:
- SAML 2.0
- OAuth 2.0 / OpenID Connect
- WS-Federation

Um aplicativo é configurado para usar o Azure AD como seu provedor de identidade. Uma vez configurado, o aplicativo não requer entrada direta de nome de usuário/senha e, em vez disso, redireciona para o provedor de identidade para autenticação:

![Gráfico mostrando as relações de confiança configuradas entre o Azure AD e os diferentes aplicativos.](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig1.png)


### <a name="do-i-still-need-azure-active-directory-federation-services-adfs"></a>Ainda preciso do ADFS (Serviços de Federação do Azure Active Directory)?
Sim. Uma conexão do ADFS com o Azure AD permite logon único direto de computadores que ingressaram no domínio:
- Os usuários não veem a página de entrada baseada na Web
- As relações de confiança individuais do aplicativo são gerenciadas no Azure AD

![Gráfico mostrando como os Serviços de Federação do Azure Active Directory se conecta ao Azure AD para fornecer logon único direto a muitos aplicativos.](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig2.png)

### <a name="what-if-an-app-doesnt-support-federated-single-sign-on"></a>E se um aplicativo não oferecer suporte ao logon único federado?
O SSO baseado em senha é a melhor solução para aplicativos que não oferecem suporte aos protocolos SAML/OpenID e dão suporte apenas a inserção de nomes de usuário e senhas em um formulário da Web.
- Permite que conjuntos de credenciais específicos do aplicativos sejam definidos e armazenados do Azure AD
- As credenciais podem ser atribuídas a usuários ou grupos para acesso compartilhado

### <a name="user-account-provisioning"></a>Provisionamento de conta de usuário
O provisionamento de conta de usuário é o ato de criar, atualizar e/ou desabilitar registros de conta de usuário no repositório local de perfis de usuário de um aplicativo. A maioria dos aplicativos SaaS armazena a função e as permissões do usuário em seu próprio repositório local de perfis de usuário.

O serviço de provisionamento do Azure AD conecta-se a uma API de gerenciamento de usuários soap/rest fornecida por aplicativo, que adiciona, atualiza e desabilita contas de usuário. Ele dá suporte à sincronização de grupos, e perfis/funções também podem ser importados do aplicativo no Azure AD.

![Gráfico mostrando como o serviço de provisionamento do Azure AD se conecta à API de gerenciamento de usuários soap/rest.](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig3.png)

### <a name="the-end-user-experience"></a>A experiência do usuário final
O Painel de Acesso de Aplicativos é um portal entre dispositivos e navegadores que pode ser acessado usando iOS, Android, Mac e Windows. Para acessar o Painel de Acesso, os usuários se autenticam no Azure AD uma vez, veem a lista de Aplicativos aos quais eles têm acesso e podem iniciar o aplicativo com apenas um clique no painel. Se o aplicativo foi configurado para SSO pelo administrador, os usuários não precisarão se autenticar novamente para acessar o aplicativo: o logon único cuidará da autenticação automaticamente.

### <a name="bring-your-own-apps"></a>Traga seus próprios aplicativos
A galeria de aplicativos do Azure AD conta com milhares de aplicativos que você pode adicionar à sua organização. Porém, se não for possível encontrar um aplicativo de terceiro, ainda assim você poderá adicioná-lo como um aplicativo personalizado para uso da organização.

É possível integrar quase todos os aplicativos baseados na Web que tenham um mecanismo de autenticação baseado em nome de usuário e senha, estejam eles listados ou não na galeria de aplicativos do Azure.

![Captura de tela mostrando como usar a galeria de aplicativos do Azure AD para adicionar um aplicativo para sua organização.](./media/thousands-apps-one-identity/thousands-apps-one-identity-fig4.png)

### <a name="secure-remote-access-to-on-premises-apps"></a>Acesso remoto seguro aos aplicativos no local
O [Proxy de Aplicativo do Azure AD](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-enable/) fornece SSO (logon único) e acesso remoto seguro para aplicativos Web hospedados no local. Isso pode incluir sites do SharePoint, Outlook Web Access ou qualquer outro aplicativo Web LOB que você tenha. Esses aplicativos Web no local são integrados ao Azure AD, a mesma plataforma de identidade e controle que é usada pelo O365.

Os usuários finais podem acessar seus aplicativos no local da mesma forma que acessam o O365 e outros aplicativos SaaS integrados ao Azure AD, sem a necessidade de uma VPN ou de alterar a infraestrutura da rede.

## <a name="how-to-implement-this-solution"></a>Como implementar esta solução
As etapas a seguir descrevem como implementar cada recurso do Azure AD anteriormente discutido. Cada link representa um conjunto diferente de artigos com um conjunto diferente de instruções/etapas a serem implementadas na sua organização:
1. [Habilite o logon único com proxy de aplicativo.](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-sso-using-kcd/)
2. [Forneça acesso remoto seguro a aplicativos locais.](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-get-started/)
   - [Trabalhe com domínios personalizados no proxy de aplicativo do Azure AD.](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-custom-domains/)
   - [Trabalhe com aplicativos com reconhecimento de declarações no proxy de aplicativo.](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-claims-aware-apps/)
   - [Trabalhe com acesso condicional para aplicativos publicados usando o proxy de aplicativo.](https://azure.microsoft.com/en-us/documentation/articles/active-directory-application-proxy-conditional-access/)
3. [Coloque seus próprios aplicativos no Azure AD.](https://blogs.technet.microsoft.com/enterprisemobility/2015/06/17/bring-your-own-app-with-azure-ad-self-service-saml-configuration-now-in-preview/)

## <a name="additional-resources"></a>Recursos adicionais
- **Galeria de aplicativos em Azure.com**
  - https://azure.microsoft.com/marketplace/active-directory/
- **Lista de aplicativos SaaS** (com recursos de integração)
  - https://aadappgallery.azurewebsites.net/Default.aspx?Microsoft_Integrated_Synchronization=on
- **Tutoriais de aplicativos SaaS**
  - https://azure.microsoft.com/documentation/articles/active-directory-saas-tutorial-list/
