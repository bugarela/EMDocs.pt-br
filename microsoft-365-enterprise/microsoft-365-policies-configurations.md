---
title: "Políticas de segurança e configurações recomendadas – Microsoft 365 Enterprise | Microsoft Docs"
description: "Descreve as recomendações da Microsoft e os conceitos principais para implantar configurações e políticas de email seguro, documentos e aplicativos."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 869fd439cfd1dc1fa74bf108341fec18929d92a3
ms.sourcegitcommit: d8588b191a4f9daea73698426dd632e7997140dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2017
---
# <a name="recommended-security-policies-and-configurations"></a>Políticas de segurança e configurações recomendadas

## <a name="introduction"></a>Introdução
Embora não haja uma melhor recomendação única para todos os ambientes de cliente, as melhores práticas e recomendações neste documento descrevem as recomendações gerais da Microsoft sobre como aplicar a política e a configuração dentro da nuvem da Microsoft para garantir que seus funcionários estejam protegidos e sejam produtivos.  

**Público-alvo** Essas recomendações destinam-se aos arquitetos de infraestrutura corporativa e profissionais de TI familiarizados com o [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) e o [Microsoft Enterprise Mobility + Security](http://microsoft.com/ems) que inclui, entre outros, o Azure Active Directory (identidade), o Microsoft Intune (gerenciamento de dispositivo) e a Proteção de Informações do Azure (proteção de dados).

**Ambiente do cliente** As políticas recomendadas são aplicáveis a empresas que operam totalmente dentro da nuvem da Microsoft e para clientes com a infraestrutura implantada entre a nuvem da Microsoft e local.

**Suposições** Muitas das recomendações fornecidas dependem de serviços disponíveis apenas com assinaturas do EMS (Enterprise Mobility + Security) E5. As recomendações apresentadas consideram os recursos completos de assinatura do EMS E5.

**Advertências** Sua organização pode estar sujeita aos requisitos regulatórios ou outros requisitos de conformidade, incluindo recomendações específicas que podem exigir que você aplique políticas que divergem das configurações recomendadas.  Essas configurações recomendam controles de uso que historicamente não estavam disponíveis.  Recomendamos esses controles porque acreditamos que eles representam um equilíbrio entre produtividade e segurança.  

Embora tenhamos feito o melhor para levar em conta uma ampla variedade de requisitos de proteção organizacional, não conseguimos considerar todos os requisitos possíveis ou todos os aspectos exclusivos da sua organização. Use essas recomendações como um guia para como a Microsoft e a equipe de Secure Productive Enterprise estão pensando sobre como aplicar a política corretamente.  

>[!NOTE]
>Para obter uma visão geral dos principais conceitos necessários para compreender os recursos de proteção descritos nessas recomendações, consulte a [home page da documentação do Microsoft 365 Enterprise](index.md).
>

## <a name="core-concepts"></a>Conceitos básicos
Todas as medidas de segurança do mundo não importam quando os usuários, que experimentam fricção desnecessária ao tentar realizar seu trabalho, ignoram as políticas de segurança organizacional. O SSO (logon único) do Azure AD tenta minimizar a carga nos usuários. Dessa forma, os usuários podem continuar produtivos enquanto ainda estão em conformidade com as políticas de controle de acesso da organização.

### <a name="single-sign-on-authentication"></a>Autenticação de logon único

O diagrama a seguir ilustra um fluxo típico de autenticação de SSO:

![Experiência de logon único do usuário final](./media/policies-configurations/authentication-flow.png)

Para começar a autenticação, o cliente envia as credenciais (como nome de usuário e a senha) e/ou quaisquer artefatos de SSO obtidos no passado para o Azure AD. Um artefato de SSO pode ser um token de sessão para um navegador ou um token de atualização para aplicativos avançados.

Depois que o artefato de SSO e/ou as credenciais tiverem sido verificadas no Azure AD e todas as políticas aplicáveis tiverem sido avaliadas, um token de acesso para o provedor de recursos (Office 365 no diagrama acima) será emitido. O Azure AD também emite um artefato de SSO como parte da resposta para permitir que os clientes atinjam o SSO em solicitações subsequentes. O cliente armazena o artefato de SSO e envia o token de acesso como uma prova de identidade para o provedor de recursos. Depois que o Office 365 verifica o token de acesso e executa as verificações necessárias, ele concede ao cliente o acesso aos documentos.

#### <a name="single-sign-on-sso-refresh-tokens"></a>Tokens de atualização de SSO (logon único)

O SSO pode ser obtido de várias maneiras. Por exemplo, os cookies de um provedor de identidade podem ser usados como o artefato de SSO para armazenar o estado de entrada para um usuário em um navegador. Futuras tentativas de entrar no modo silencioso (sem nenhum prompt de credenciais) para aplicativos que usam o mesmo provedor de identidade são possíveis então.

Quando um usuário se autentica com o Azure AD, uma sessão de SSO é estabelecida com o navegador do usuário e o Azure AD. O token do SSO, na forma de um cookie, representa essa sessão. O Azure AD usa dois tipos de tokens de sessão de SSO: persistentes e não persistentes. Os tokens de sessão persistentes são armazenados como cookies persistentes por navegadores quando a caixa de seleção **Manter-me conectado** é selecionada durante a entrada. Os tokens de sessão não persistentes são armazenados como cookies de sessão e são destruídos quando o navegador é fechado.

Para aplicativos robustos capazes de usar protocolos de autenticação modernos, como [OpenId Connect](http://openid.net/specs/openid-connect-core-1_0.html) e [OAuth 2.0](https://tools.ietf.org/html/rfc6749), o SSO é habilitado usando tokens de atualização como os artefatos de SSO (além de cookies de SSO anteriormente descritos). Os tokens de atualização são apresentados para um servidor de autorização quando um aplicativo solicita um novo token de acesso. O token de atualização contém declarações e atributos sobre o tipo de métodos de autenticação usado ao autenticar usuários. Por exemplo, se um usuário tiver sido autenticado com êxito usando vários métodos (nome de usuário e senha e autenticação baseada em telefone), uma declaração de MFA (autenticação multifator) estará presente no token de atualização. Além disso, pode haver declarações adicionais que contêm dados, como a duração da validade do MFA.

Os tokens de atualização permitem que o cliente obtenha um novo token de acesso, sem a necessidade de fazer outra autenticação interativa. Os tokens de atualização têm um tempo de vida muito maior do que os tokens de acesso e podem ser resgatados para obter um novo acesso e atualizar o par de tokens. Os tokens de atualização recém-obtidos podem ser usados continuamente para buscar outro conjunto de tokens de acesso e de atualização. O cliente continua esse processo de SSO até que a configuração de tempo de inatividade máximo do token de atualização expire, a idade máxima do token de atualização expire ou os requisitos de política de autorização e autenticação mudem. Essa alteração ocorre durante o tempo em que o token de atualização original foi emitido. Alterações de atributo de usuário significativas, por exemplo, uma redefinição de senha, também exigem que um novo token de autenticação seja gerado. O cliente deve fazer uma nova autenticação interativa para continuar. Essencialmente, isso significa um intervalo no processo de SSO que o cliente não vivenciou até agora.

#### <a name="conditional-access"></a>Acesso condicional
O Azure AD, atuando como um serviço de autorização para seus aplicativos, determina se deve emitir tokens de acesso com base em uma avaliação de todas as políticas de acesso condicional aplicadas ao recurso que você está tentando acessar. Se os requisitos de política forem atendidos, um token de acesso e um token de atualização atualizado serão emitidos. Se a política não for atendida, o usuário receberá instruções sobre como atender à política e/ou deverá realizar etapas adicionais, incluindo a MFA (autenticação multifator). Depois de a MFA ser concluída, a declaração de MFA será adicionada ao token de atualização resultante.  

Declarações no token de atualização são acumuladas ao longo do tempo. Algumas das declarações têm linhas do tempo de expiração, após as quais elas não são consideradas durante as verificações de autorização. Às vezes, isso pode causar resultados inesperados. Por exemplo, se uma política de acesso condicional estiver configurada de forma que a MFA seja necessária para as tentativas de autenticação vindo de locais de extranet. Nesse caso, os usuários podem às vezes não receber o prompt de MFA esperado ao acessar um recurso da extranet. Um motivo possível para isso é que o usuário realizou a MFA anteriormente logo antes de sair da intranet. Portanto, ele tem uma declaração de MFA válida no seu token de acesso. Esta declaração de MFA satisfaz o requisito de política e, portanto, o Azure AD não realiza uma solicitação de MFA adicional para o usuário.

#### <a name="token-lifetime-policy"></a>Política do tempo de vida do token
Além da expiração de declarações individuais em um token, os próprios tokens têm tempos de expiração. Conforme observado anteriormente, os tokens expirados são um motivo pelo qual a experiência de SSO pode ser interrompida. Você pode definir o tempo de vida de um token emitido pelo Azure AD usando [políticas de tempo de vida do token](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes). Como pode ser deduzido acima, a definição do contorno de uma sessão de SSO é mais difícil capturar. Por exemplo, quando aplicativos avançados como vários fatores que aparentemente estão desconectados podem afetar o tempo de vida de uma sessão de SSO.

>[!NOTE]
>Os Administradores Globais do Azure AD podem controlar os períodos de validade e inatividade dos tokens de atualização. Informações sobre o token de acesso e as declarações usando as configurações descritas no artigo [Tempos de vida de token configuráveis no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes).
>

#### <a name="primary-refresh-tokens"></a>Tokens de atualização principais
Até agora, este artigo discutiu como o SSO funciona dentro do contexto de um único cliente, mas isso não é suficiente para a experiência de SSO em um único aplicativo. Atualmente, os usuários experimentam fluxos de trabalho interativos em vários aplicativos dentro do mesmo pacote de aplicativos, como o Microsoft Office. Os usuários também precisam de acesso entre aplicativos não relacionados, incluindo aplicativos de LOB (Linha de Negócios) desenvolvidos internamente.

Tradicionalmente, os dispositivos Windows ingressados no domínio, usando a Autenticação Integrada do Windows (Kerberos), alcançam um alto grau de experiência de SSO em vários aplicativos e recursos. Esses aplicativos incluem os navegadores com suporte, como o Internet Explorer ou o Edge. Há um analógico para o realm do Azure AD, na forma de um PRT (token de atualização principal). Esse token com privilégios está disponível apenas para um conjunto selecionado de entidades de cliente (como componentes de sistema de plataforma). As entidades podem então permitir o acesso de autenticação orientadas a outros aplicativos de cliente para que eles também possam oferecer uma experiência contínua de SSO. Para usuários do Office 365 em dispositivos [iOS](https://docs.microsoft.com/azure/active-directory/develop/active-directory-sso-ios) e [Android](https://docs.microsoft.com/azure/active-directory/develop/active-directory-sso-android), o trabalho adicional foi feito para reduzir o número de autenticações necessárias aplicando a funcionalidade de agente de autenticação. Essa funcionalidade é criada nos aplicativos de Portal da Empresa do Intune e do Microsoft Authenticator.

>[!NOTE]
>As recomendações descritas neste documento pressupõem que um desses aplicativos (Microsoft Authenticator ou Portal da Empresa do Intune) foi implantado para os dispositivos Android ou iOS dos seus usuários.

### <a name="multi-factor-authentication"></a>Autenticação Multifator
A MFA (Autenticação Multifator) fornece um alto nível de confiança sobre o assunto de autenticação porque o assunto fornece várias provas ou partes de evidências sobre sua identidade. As provas podem ser segredos pré-estabelecidos que apenas o assunto e a autoridade estão cientes ou uma entidade física que apenas o assunto deve ter. A MFA normalmente é executada em estágios. Primeiro ela estabelece a identidade usando senhas e, em seguida, ela exige um método de autenticação (menos propenso a ataques mal-intencionados) diferente como o segundo fator ou vice-versa.

Autoridades diferentes podem ter uma interpretação ligeiramente diferente de MFA ou de autenticação forte. Por exemplo, algumas autoridades (ou mais especificamente os administradores configurando a política nessas autoridades) podem optar por interpretar a autenticação baseada em cartão inteligente físico como MFA. Isso pode ocorrer mesmo que estritamente falando a autenticação de cartão inteligente seja uma autenticação de estágio único.

A combinação de exigir um cartão inteligente físico e a necessidade de inserir um PIN (segredo) para usar o cartão inteligente pode ser interpretada como MFA. No entanto, as organizações podem optar por ser mais brandas em termos da frequência com que os métodos de autenticação mais onerosos devem ser executados. Nesses casos, as autenticações normais, que ocorrem entre as autenticações mais fortes, podem ser consideradas válidas para recursos que normalmente exigem autenticação forte. Por exemplo, em algumas organizações pode ser aceitável exigir que um usuário faça a MFA a cada intervalo de poucas horas ou dias. O tempo depende da confidencialidade dos recursos sendo protegidos e desde que a localização física do usuário tentando acessar o recurso não mude.

Azure AD e o AD FS usam a declaração de MFA para indicar se a autenticação é executada com MFA. Por padrão, o Azure AD emite tokens com declaração de MFA quando a autenticação é feita com [MFA do Azure](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud) ou [Windows Hello para Empresas](https://docs.microsoft.com/windows/access-protection/hello-for-business/hello-identity-verification). Em cenários de federação, o Azure AD segue a declaração de MFA de provedores de identidade federada como o AD FS e traz a declaração de MFA nos tokens.

## <a name="recommended-client-configurations"></a>Configurações de cliente recomendadas
Esta seção descreve as configurações de cliente de plataforma padrão que recomendamos para oferecer a melhor experiência SSO para seus usuários, bem como os pré-requisitos técnicos para acesso condicional.

### <a name="windows-devices"></a>Dispositivos Windows
Recomendamos que o Windows 10 (versão 1703 ou posterior), como Azure foi desenvolvido para fornecer a melhor experiência de SSO possível para o Azure AD e local. Dispositivos emitidos pelo trabalho ou pela escola devem ser configurados para ingressar no Azure AD diretamente ou, se a organização usar o ingresso no domínio do AD local, esses dispositivos deverão ser [configurados para se registrar com o Azure AD de forma automática e silenciosa](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

Para dispositivos Windows BYOD, os usuários podem usar "Adicionar conta corporativa ou de estudante". Para dispositivos Windows BYOD, os usuários podem usar "Adicionar conta corporativa ou de estudante". Observe que os usuários do navegador Chrome no Windows 10 precisam [instalar uma extensão](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) para esses usuários poderem obter a mesma experiência de entrada sem problemas que o Edge/IE. Além disso, se sua organização tiver dispositivos Windows 7 ingressados no domínio, você poderá instalar o Microsoft Workplace Join para computadores sem Windows 10 [empacotarem para registrar](https://www.microsoft.com/download/details.aspx?id=53554) os dispositivos com o Azure AD.

### <a name="ios-devices"></a>Dispositivos iOS
É recomendável instalar o [aplicativo Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) em dispositivos de usuário antes de implantar o acesso condicional ou políticas de MFA. No mínimo, o aplicativo deve ser instalado quando os usuários forem [solicitados a registrar seu dispositivo](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/multi-factor-authentication-end-user-first-time) com o Azure AD adicionando uma conta corporativa ou de estudante ou ao instalar o aplicativo do Portal da Empresa do Intune para registrar seus dispositivos no gerenciamento. Isso depende da política de acesso condicional configurada.

### <a name="android-devices"></a>Dispositivos Android
É recomendável que os usuários instalem o [aplicativo de Portal da Empresa do Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en
) e o [aplicativo Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) antes de políticas de acesso condicional serem implantadas ou quando necessário durante determinadas tentativas de autenticação. Após a instalação do aplicativo, os usuários podem ser solicitados a se registrarem com o Azure AD ou registrar seus dispositivos com o Intune. Isso depende da política de acesso condicional configurada.

Também recomendamos que os CODs (dispositivos corporativos) sejam padronizados em OEMs e versões que dão suporte ao Android for Work ou Samsung Knox para permitir que as contas de email sejam gerenciadas e protegidas pela política de MDM do Intune.

## <a name="security-guidelines"></a>Diretrizes de segurança
Esta seção contém diretrizes gerais de segurança que devem ser seguidas durante a implementação das recomendações fornecidas nas seções posteriores.

### <a name="security-and-productivity-trade-offs"></a>Vantagens e desvantagens de produtividade e segurança
Há uma compensação entre a segurança e a produtividade. Para ajudar a entender essas compensações, a tríade de segurança SFU (Segurança-Funcionalidade-Usabilidade/Facilidade de Uso) é amplamente usada:

![Vantagens e desvantagens de produtividade e segurança](./media/policies-configurations/security-triad.png)

As recomendações são fornecidas com base nos seguintes princípios da tríade de segurança de SFU:

* Conhecer o público-alvo – Ser flexível por barra de segurança/função de trabalho
* Aplicar a política de segurança no momento e certificar-se de que é significativa

### <a name="administrators-versus-users"></a>Administradores versus usuários
É recomendável criar grupos de segurança que contêm todos os usuários que têm contas administrativas ou que estão qualificados para receber privilégios de conta de administrador em caráter temporário. Esses grupos de segurança devem então ser usados para definir políticas de acesso condicional específicas ao Azure AD e administradores do Office 365.  

As recomendações de política fornecidas consideram os privilégios associados a uma conta. As funções de [administrador do Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) têm substancialmente mais privilégios para os serviços do Office 365. Assim, nossas recomendações de política para essas contas são mais rígidas do que para contas de usuário comuns. Todas as políticas que se referem aos administradores indicam a política recomendada para contas administrativas do Office 365.

### <a name="reduce-the-number-of-accounts-with-persistent-admin-access"></a>Reduza o número de contas com acesso de administrador persistente
Use o Azure AD Privileged Identity Management para reduzir o número de contas administrativas persistentes. Além disso, é recomendável que os administradores do Office 365 tenham uma conta de usuário separada para uso comum não administrativo e usem a conta de administrador somente quando necessário para realizar uma tarefa relacionada à sua função de trabalho.

## <a name="tiers-of-security-and-protection"></a>Camadas de segurança e proteção
A maioria das organizações tem requisitos específicos sobre segurança e proteção de dados. Esses requisitos variam por segmento do setor e por funções de trabalho dentro das organizações. Por exemplo, seu departamento jurídico e os administradores do Office 365 podem exigir controles de proteção de informações e segurança adicionais em sua correspondência de email que não são necessários para outros usuários da unidade de negócios.

Cada setor também tem seu próprio conjunto de normas especializadas. Em vez de fornecer uma lista de todas as opções de segurança possíveis ou uma recomendação por função de trabalho ou segmento do setor, as recomendações foram fornecidas para três diferentes camadas de segurança e proteção que podem ser aplicadas com base na granularidade de suas necessidades: [linha de base, confidencial e altamente controlada](https://go.microsoft.com/fwlink/p/?linkid=841656).  

**Linha de base**. É recomendável que você estabeleça um padrão mínimo para a proteção de dados, bem como as identidades e dispositivos que acessam os dados. As recomendações de linha de base podem ser seguidas para fornecer proteção forte padrão que atende às necessidades de muitas organizações.

**Confidencial**. Alguns clientes têm um subconjunto de dados que devem ser protegidos em níveis mais altos ou exigem que todos os dados sejam protegidos nesses níveis mais altos. Você pode aplicar mais proteção a todos ou conjuntos de dados específicos em seu ambiente do Office 365. É recomendável proteger identidades e dispositivos que acessam dados confidenciais com níveis compatíveis de segurança.

**Altamente controlada**. Algumas organizações podem ter uma quantidade muito pequena de dados altamente confidenciais, segredos comerciais ou dados controlados. A Microsoft fornece recursos para ajudar as organizações a atender a esses requisitos, incluindo proteção adicional para identidades e dispositivos.

### <a name="default-protection-mechanism-recommendations"></a>Recomendações de mecanismo de proteção padrão
A tabela a seguir contém recomendações do mecanismo de proteção padrão para cada uma das camadas de proteção e segurança definidas anteriormente:

|Mecanismo de proteção|Linha de base|Confidencial|Altamente controlada|
|:-------------------|:-------|:--------|:---------------|
|**Impor a MFA**|No risco de entrada médio ou acima|No risco de entrada baixo ou acima|Em todas as novas sessões|
|**Impor a alteração de senha**|Para usuários de alto risco|Para usuários de alto risco|Para usuários de alto risco|
|**Impor a proteção de aplicativos do Intune**|Sim|Sim|Sim|
|**Impor o registro do Intune (COD)**|Exigir um dispositivo em conformidade ou ingressado no domínio|Exigir um dispositivo em conformidade ou ingressado no domínio|Exigir um dispositivo em conformidade ou ingressado no domínio|

### <a name="device-ownership"></a>Propriedade do dispositivo
A tabela acima reflete a tendência para muitas organizações darem suporte a uma mistura de CODs (dispositivos corporativos), bem como dispositivos pessoais ou BYOD (traga seu próprio dispositivo) para permitir a produtividade móvel entre as forças de trabalho. As Políticas de Proteção de Aplicativo do Intune garantem que o email seja protegido contra a filtragem excessiva do aplicativo móvel do Outlook e outros aplicativos móveis do Office, no COD e no BYOD.  

Os dispositivos corporativos devem ser gerenciados pelo Intune ou ingressados no domínio para fornecer controle e proteções adicionais.  Dependendo da confidencialidade de dados, sua organização pode optar por não permitir BYOD para grupos de usuários específicos ou aplicativos específicos.

## <a name="next-steps"></a>Próximas etapas

 [Implantar identidade comum e políticas de acesso ao dispositivo](identity-access-policies.md)
