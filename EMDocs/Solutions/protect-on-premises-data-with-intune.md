---
title: Proteger dados locais com o Microsoft Intune | Microsoft Docs
description: "Com o Enterprise Mobility + Security (EMS), será possível manter os funcionários produtivos com seus aplicativos e dispositivos favoritos e os dados locais da empresa em segurança."
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 02/03/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebf7be63-4ac2-4158-9772-58f15416ccb7
ms.reviewer: vlpetros
ms.suite: ems
ms.custom: active-directory
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea7cc0c6c7b8286077c0bbc4251a22d138ed8e2
ms.openlocfilehash: 98acda761b353eacb2ce861dcef2f39385691021
ms.contentlocale: pt-br
ms.lasthandoff: 05/29/2017


---
# <a name="protect-on-premises-company-data-with-intune"></a>Proteger dados locais da empresa com o Intune
Sozinhos, os firewalls não podem fornecer um limite de segurança corporativa adequado. Hoje, os limites de segurança devem incluir o usuário final e como ele acessa, usa e compartilha os dados da empresa. Seja no trabalho com smartphones, tablets ou laptops, os operadores de informação esperam acesso irrestrito aos recursos, em qualquer lugar, em qualquer dispositivo e sempre que necessário. Habilitar recursos de proteção e acesso para usuários pode ser um desafio para os administradores de TI, que também precisam assegurar a proteção dos dados da empresa. Com o Enterprise Mobility + Security (EMS), será possível manter os funcionários produtivos com seus aplicativos e dispositivos favoritos e os dados locais da empresa em segurança. Continue lendo para saber como.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>Como o EMS (Enterprise Mobility + Security) pode ajudar você?
O EMS (Enterprise Mobility + Security) é a única solução de nuvem abrangente que protege nativamente dados corporativos no próprio dispositivo e além dele, com quatro camadas de proteção de identidades, dispositivos, aplicativos e dados. Com o EMS, os funcionários terão acesso seguro e contínuo ao email corporativo e a documentos, ao passo que o TI estará confiante de que os dados da empresa estão protegidos.

## <a name="recommended-solution"></a>Solução recomendada
Com o Microsoft Intune, é possível configurar remotamente recursos de políticas de acesso de perfil para provisionar automaticamente contas de email, acessar perfis com configurações de Wi-Fi ou VPN e fornecer perfis de certificado, o que assegura que os dispositivos aceitarão e instalarão somente as configurações confiáveis.

Além de fornecer permissão, o acesso condicional do Intune aos servidores do Microsoft Exchange 2010 local, ou posterior, garante que apenas dispositivos gerenciados e compatíveis acessem o email da empresa. Ao expandir o gerenciamento para além dos próprios dispositivos, também é possível usar o Mecanismo de Serviços de Identidade (ISE) da Cisco no Intune e, em breve, outros parceiros, para restringir o acesso à rede da empresa somente a dispositivos registrados para gerenciamento com o Intune e compatíveis com as políticas da empresa. Você pode até mesmo fornecer acesso seguro aos aplicativos locais sem VPNs, DMZs ou proxies reversos locais, aproveitando o Proxy de Aplicativo do Azure Active Directory. O melhor de tudo é que isso pode ser feito sem instalar ou manter infraestruturas locais adicionais ou abrir o firewall da empresa para rotear tráfego por meio dele.

Este é um breve vídeo que lhe dará uma introdução rápida de como o acesso condicional com o EMS fornece uma experiência fácil para os funcionários acessarem dados da empresa com segurança usando dispositivos iOS, Android e Windows:

<iframe width="675" height="480" src="https://youtube.com/embed/fvCT7Y3nlAY" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>Como implementar esta solução
O restante dessa solução está dividido nas seções a seguir, que mostram como proteger os dados de empresa do Office 365 com o Intune:
- **Registrar dispositivos móveis e computadores Windows no gerenciamento**. Esta seção descreve como registrar dispositivos (iOS, Android, Android for Work e computadores Windows) para gerenciamento a fim de configurar o acesso seguro a recursos locais com o Intune.
- **Acessar e proteger os emails da empresa**. Esta seção mostra como o Intune pode configurar automaticamente as configurações de email do aplicativo nativo para os usuários e como fornecer acesso condicional ao Exchange Server local.
- **Fornecer acesso a outros recursos locais da empresa**. Esta seção descreve como fornecer aos funcionários acesso seguro aos recursos da rede local usando Wi-Fi, VPN ou o Proxy de Aplicativo do Azure Active Directory.
- **Usar certificados para proteger o acesso aos recursos da empresa**. Esta seção ajuda a criar e implantar um certificado PKCS #12 (.PFX) ou um Protocolo SCEP para proteger o acesso do usuário aos recursos da empresa.

## <a name="enroll-mobile-devices-and-windows-pcs-into-management"></a>Registrar dispositivos móveis e computadores Windows no gerenciamento
Registrar dispositivos e computadores para gerenciamento com o Intune garante que todas as políticas e perfis de acesso que configurados para os dispositivos gerenciados sejam aplicadas. Antes que possa registrar dispositivos, primeiro você precisará [preparar o serviço do Intune](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) atribuindo licenças a usuários, definindo a autoridade de gerenciamento de dispositivo móvel e atendendo os vários requisitos de registro para os diferentes tipos de dispositivo que deseja gerenciar. Enquanto estiver fazendo isso, você provavelmente também deveria [personalizar o portal da empresa](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal) com informações de suporte e a identidade visual específica da empresa para fornecer uma experiência confiável de registro e suporte para seus usuários.

Depois de preparar o serviço do Intune, o processo de registrar os dispositivos para gerenciamento é bastante simples, mas ligeiramente diferente para os diferentes tipos de dispositivo:

-   **Dispositivos iOS e Mac**. Você precisará obter um certificado do APNs (Apple Push Notification Service) para registrar dispositivos Mac OS X, iPhones ou iPads. Após ter [carregado o certificado do APNs no Intune](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune), os usuários podem [registrar dispositivos iOS](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios) usando o aplicativo do Portal da Empresa e usar o site do Portal da Empresa para [registrar dispositivos Mac OS X](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x).
-   **Dispositivos Android**. Não há nada que você precisa fazer para deixar o serviço do Intune pronto para registrar dispositivos Android. Os usuários podem simplesmente [registrar seus dispositivos Android](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune) para gerenciamento usando o aplicativo de Portal da Empresa no Google Play.
-   **Android for Work**. Para [configurar o Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work) para o Android 5.0 Lollipop e dispositivos posteriores que dão suporte aos perfis de trabalho a serem gerenciados pelo Intune, é necessário que a organização se inscreva no Android for Work com o Google e, em seguida, configure as definições do Android for Work no nó ADMIN do console de administração do Intune.
-   **Telefones e computadores Windows**. Você deve [definir um alias DNS para o servidor de registro](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) para facilitar o registro de dispositivos Windows. Caso contrário, você pode [registrar dispositivos Windows](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows) adicionando uma conta corporativa ou de estudante.

> [!TIP]
> É possível tornar o registro em dispositivos Windows ainda mais fácil para os usuários [habilitando o recurso de registro automático](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment) no Azure AD (Premium). Ao habilitar esse recurso, os dispositivos serão registrados automaticamente para gerenciamento com o Intune quando um usuário adicionar uma conta corporativa ou de estudante para registrar um dispositivo pessoal ou corporativo no Azure AD da organização.

## <a name="access-and-protect-company-email"></a>Acessar e proteger os emails da empresa
A primeira coisa que a maioria dos funcionários quer em seus dispositivos móveis é acesso a documentos e email da empresa. E esperam configurá-lo sem passar por etapas complexas ou chamar o suporte técnico. O Microsoft Intune facilita a criação e implantação de configurações de email para aplicativos nativos de email pré-instalados em dispositivos móveis usados pela organização.

Ao usar as políticas de Acesso Condicional do Intune para o Exchange local, você tem a garantia de que apenas os dispositivos gerenciados, em conformidade com a política e registrados no Azure Active Directory poderão acessar as informações contidas no Exchange Server local da empresa.

### <a name="configure-exchange-email-settings-for-native-email-apps-on-managed-devices"></a>Definir as configurações de email do Exchange para aplicativos de email nativos em dispositivos gerenciados
É possível [definir as configurações de aplicativos de email nativos](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) facilmente nos dispositivos a seguir criando políticas de configuração para perfis de email e as implantando para os usuários:

-   Windows Phone (8 e posterior).
-   Windows 10 Desktop e Mobile
-   iOS (8.0 e posterior)
-   Android (Samsung Knox Standard 4.0 e posterior ou Android for Work)

> [!NOTE]
> O Intune dá suporte à configuração de perfis de email do Android for Work para os aplicativos do Gmail e do Nine Work encontrados na loja do Google Play.

### <a name="protect-access-to-your-on-premises-exchange-server"></a>Proteger o acesso ao Exchange Server local
Além de utilizar o Intune para fornecer configurações de email para se conectar aos servidores Exchange locais, também é possível usá-lo para [controlar o acesso por email a um Exchange Server local](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune) (2010 ou posterior) por meio do [conector do Exchange local](https://docs.microsoft.com/intune/deploy-use/intune-on-premises-exchange-connector) do Intune.

Se um dispositivo não estiver registrado ou em conformidade com as políticas da empresa, o usuário receberá informações sobre como registrá-lo para gerenciamento ou corrigir os problemas de conformidade que estão bloqueando o acesso ao email.

> [!TIP]
> Dê uma olhada nestes [cenários de exemplo](https://docs.microsoft.com/intune/deploy-use/restrict-email-access-example-scenarios#all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune) para obter mais ideias sobre como usar o acesso condicional do Intune para proteger o email do Exchange da empresa.

É possível [configurar uma política de acesso condicional para o Exchange local](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune#configure-a-conditional-access-policy) para os seguintes tipos de dispositivo usados pela organização:

-   Windows Phone (8.1 e posterior)
-   iOS (8.0 e posterior)
-   Android (4.0 ou posterior e Samsung Knox Standard 4.0)
-   Android for Work (no momento, há suporte somente para perfis de aplicativo email Gmail e Nine Work)
-   O aplicativo de email em computadores Windows gerenciados

> [!NOTE]
> As políticas de acesso condicional do Intune funcionam nos dispositivos apenas com os aplicativos de email nativos, com exceção do Gmail e do Nine Work no perfil de trabalho do Android for Work. Não há suporte para o aplicativo do Microsoft Outlook para Android e iOS atualmente, mas existem planos para oferecer suporte no futuro.

## <a name="provide-access-to-other-on-premises-company-resources"></a>Fornecer acesso a outros recursos locais da empresa
Além do email, o EMS também ajuda a controlar o acesso e proteger os dados locais da empresa acessados fora dos limites de segurança corporativa tradicionais. Os perfis de Wi-Fi, VPN e email do Microsoft Intune funcionam em conjunto para ajudar os usuários a obter acesso aos arquivos e recursos necessários para realizar seu trabalho, independentemente de onde estiverem. Os aplicativos Web e serviços da empresa hospedados localmente também podem ser acessados com segurança e protegidos usando o Proxy de Aplicativo do Azure Active Directory e o acesso condicional.

### <a name="deploy-wi-fi-settings-to-managed-devices"></a>Implantar configurações de Wi-Fi para dispositivos gerenciados
As políticas de configuração de Wi-Fi do Intune facilitam a [implantação de configurações de rede sem fio para os usuários](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune). Essas configurações facilitam para os usuários a conexão à rede corporativa, sem a necessidade de configurar manualmente as configurações de Wi-Fi em qualquer um dos seguintes dispositivos com suporte:

-   Android (4.0 e posterior, Samsung Knox Standard e Android for Work)<sup>1</sup>
-   iOS (8.0 e posterior)<sup>1</sup>
-   Mac OS X (10.9 e posterior)<sup>1</sup>
-   Dispositivos do Windows (computadores Windows 8.1 e posterior, Windows Phone 8.1 ou Windows 10 Mobile e posterior)<sup>2</sup>

> <sup>1</sup>É possível usar uma política de configuração interna de Wi-Fi no Intune.

> <sup>2</sup>É possível [importar um perfil de configuração .xml de configurações de Wi-Fi previamente exportado](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune#export-or-import-a-wi-fi-configuration-profile-for-windows-devices).

### <a name="deploy-vpn-settings-to-managed-devices"></a>Implantar configurações VPN para dispositivos gerenciados
Conexões VPN são usadas quando os usuários precisam se conectar remotamente aos recursos da empresa em seus dispositivos móveis. Com o Intune, é possível [criar e implantar perfis de configuração VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) que permitem que os usuários acessem facilmente e com segurança os recursos da rede corporativa sem configurar manualmente o servidor VPN ou as informações de método de autenticação.

É possível definir configurações VPN para os vários [tipos de conexão VPN com suporte do Intune](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#vpn-connection-types) nos seguintes tipos de dispositivos:

-   Android (4.0 e posterior, Samsung Knox Standard e Android for Work)
-   iOS (8.0 e posterior)
-   Mac OS X (10.9 e posterior)
-   Dispositivos do Windows (computadores Windows 8.1 e posterior, Windows Phone 8.1 e Windows 10 Mobile e posterior)

### <a name="protect-network-access"></a>Proteger o acesso à rede
Além de permitir acesso às informações do Exchange apenas para dispositivos gerenciados e compatíveis, também é possível usar as políticas de rede do [Mecanismo de Serviços de Identidade da Cisco (ISE)](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_00.html) para proteger o acesso ao ambiente de rede. O ISE da Cisco é um controle de acesso à rede baseado em políticas que podem ser implantadas em infraestruturas corporativas com suporte para 802.1X com fio, sem fio e VPNs.

Em vez de definir as configurações no console de administração do Intune, o acesso do dispositivo às redes gerenciadas pelo ISE da Cisco é configurado no servidor do ISE da Cisco. Tudo o que você precisa fazer é [conceder permissões ao servidor do ISE da Cisco para acessar o seu locatário do Intune](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-networks) e, em seguida, usar as políticas do ISE da Cisco para permitir acesso ao ambiente de rede somente para os dispositivos gerenciados e compatíveis.

> [!IMPORTANT]
> [Licenças do ISE da Cisco](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_0110.html), não incluídas no EMS, são necessárias para aproveitar essa proteção.

Também é possível habilitar o logon único (SSO) e o acesso condicional para proteger o acesso remoto seguro a aplicativos Web hospedados localmente usando o Proxy de Aplicativo do Azure AD. O Proxy de Aplicativo do Azure AD facilita para os usuários o acesso a aplicativos Web hospedados localmente, como sites do SharePoint, Outlook Web Access ou outros aplicativos LOB da Web, sem a necessidade de um VPN. Conexões às APIs da Web para dar suporte a diferentes dispositivos e aplicativos hospedados por trás de um Gateway de Área de Trabalho Remota também podem ser protegidas.

[Configurar o Proxy de Aplicativo do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-enable) é fácil. Basta habilitar o recurso no Azure AD (Basic ou Premium), instalar um pequeno serviço chamado conector do Windows Server na rede e, em seguida, publicar aplicativos. Não é necessário abrir portas de entrada de firewall ou colocar algo em um DMZ. Após a configuração, o acesso a aplicativos Web locais é fornecido por um logon único no Azure AD. [Regras de acesso condicional](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-conditional-access), como exigir autenticação multifator ou bloquear o acesso quando os funcionários não estiverem no trabalho, fornecem proteções adicionais

## <a name="use-certificates-to-secure-company-resource-access"></a>Usar certificados para proteger o acesso aos recursos da empresa
Ao conceder aos usuários acesso a recursos corporativos por meio de VPN, Wi-Fi ou perfis de email, é possível [proteger o acesso usando um certificado](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles) instalado em cada dispositivo de usuário, em vez de depender de um nome de usuário e senha para autenticação.

É possível criar e implantar um perfil de certificado **PKCS #12 (.PFX)** ou **Protocolo SCEP** para ser usado pelos dispositivos que solicitam certificados de autenticação nestas plataformas de dispositivo:

-   iOS (8.0 e posterior)
-   Mac OS X (10.9 e posterior)
-   Android (4.0 e posterior e Android for Work)
-   Windows 8.1 (e posterior)
-   Windows Phone (8.1 e posterior)
-   Windows 10 (Desktop e Mobile) e posterior

Embora seja necessária uma Autoridade de Certificação Corporativa (AC) para realizar qualquer autenticação baseada em certificado para a empresa, há outros pré-requisitos que devem ser atendidos antes de usar certificados SCEP ou .PFX para proteger o acesso aos recursos da empresa.

-   Antes de poder usar o Intune para criar e implantar perfis de certificado SCEP, primeiro você deve [configurar a infraestrutura de certificado para o SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep). Esta etapa requer a configuração de vários servidores locais, incluindo uma Autoridade de Certificação Corporativa (AC), um Servidor de Registro de Dispositivo de Rede (NDES) e os servidores do Microsoft Intune Certificate Connector.
-   Para [usar perfis de certificado .PFX](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx) (certificados de dispositivo móvel confiável), além da Autoridade de Certificação Corporativa, é necessário o Microsoft Intune Certificate Connector (pode ser instalado na AC). O NDES não é obrigatório.

> [!NOTE]
> O uso de um servidor de proxy de aplicativo Web (WAP) é opcional, tanto com certificado SCEP quanto .PFX, para habilitar os dispositivos a receber e renovar certificados usando uma conexão à Internet.

Ao [implantar perfis de certificado](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles) para usuários, o Certificado de Autoridade de Certificação confiável é instalado no dispositivo. O dispositivo, então, usa o protocolo SCEP ou o perfil de certificado .PFX para criar uma solicitação de certificado. Após a conclusão da solicitação de certificado, é possível usar certificados para autenticar políticas de configuração de Wi-Fi, VPN e perfis de email selecionando a opção do método de autenticação de políticas de certificados (em vez de nome de usuário e senha).

### <a name="learn-more"></a>Saiba mais

[Começar a usar o Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)

