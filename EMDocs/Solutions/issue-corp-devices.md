---
title: Gerenciar dispositivos da empresa com o Intune | Microsoft Docs
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9e695ec-5608-43bb-bbfb-808b869b1567
ms.reviewer: vlpetros
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: b5be7105266a7f455e1482a814929f65a130db82
ms.openlocfilehash: 6b220f4992651b5f3c107b5b958c47900515b77f
ms.contentlocale: pt-br
ms.lasthandoff: 03/08/2017


---

# <a name="manage-company-owned-devices-with-intune"></a>Gerenciar dispositivos da empresa com o Intune

Há muitas opções disponíveis para atender às expectativas de experiência de mobilidade de funcionários no local de trabalho moderno, incluindo programas BYOD (traga seu próprio dispositivo). No entanto, muitas organizações desejam ter mais controle sobre quais dispositivos são usados para acessar dados da empresa. Nesses cenários, as empresas podem implementar estratégias CYOD (escolha seu próprio dispositivo) em que o departamento de TI fornece dispositivos móveis gerenciados para funcionários.

Para que as estratégias de CYOD sejam bem-sucedidas, as empresas devem ser capazes de oferecer uma variedade de dispositivos entre os quais os usuários possam escolher. Isso é especialmente verdadeiro se a organização está implementando CYOD como uma alternativa para BYOD porque se os usuários não gostarem do dispositivo que você atribuir a eles, eles encontrarão uma maneira de usar seus próprios dispositivos não gerenciados. Com CYOD, o departamento de TI pode registrar apenas tipos específicos de dispositivos no gerenciamento, reduzir os custos de suporte e ajudar a proteger os dados da empresa a partir do minuto em que um dispositivo é atribuído a um funcionário.  Funcionários obtêm as opções de dispositivo móvel com as quais eles já estão acostumados a em suas vidas pessoais sem precisar realizar nenhuma etapa adicional nem chamar o suporte técnico para que seus dispositivos sejam gerenciados e seu acesso a dados da empresa seja configurado.  

## <a name="how-can-enterprise-mobility--security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?

Registre dispositivos corporativos ou da organização para registrá-los com o Microsoft Intune de diversas formas, dependendo do tipo do dispositivo, de como ele foi adquirido e das necessidades da organização. Você também pode instalar o aplicativo Portal da Empresa para registrar e gerenciar dispositivos corporativos, assim como em um [cenário de BYOD](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod). Dispositivos iOS corporativos podem ser registrados diretamente no gerenciamento pelo Intune por meio das ferramentas de configuração fornecidas pela Apple. Todos os tipos de dispositivo podem ser registrados por um administrador ou gerente usando o gerenciador de registro do dispositivo. Dispositivos com um número IMEI também podem ser identificados e marcados como propriedade da empresa para habilitar cenários de COD.

Com o EMS, você pode fornecer recursos e experiências a fim de criar um local de trabalho produtivo que inclua vários estilos de trabalho, em praticamente qualquer lugar. Independentemente de seus funcionários estarem usando dispositivos MacOS, Android, iOS ou Windows, o Intune poderá lhe ajudar a fornecer produtividade à sua equipe em vários dispositivos, além de manter a segurança dos dados da empresa. Além do gerenciamento abrangente do ciclo de vida de aplicativos e dispositivos móveis, o Intune se integra diretamente aos aplicativos móveis do Office e do Office 365 para permitir que você proteja dados corporativos com facilidade.

### <a name="recommended-solution"></a>Solução recomendada

Usando o Intune você pode, de maneira fácil, fornecer aos funcionários acesso a aplicativos, dados e recursos da empresa de praticamente qualquer lugar em qualquer dispositivo, enquanto ajuda a manter as informações corporativas em segurança. A integração direta com o Office 365 possibilita experiências incríveis para o usuário final e fornece recursos abrangentes de prevenção contra perda de dados para aplicativos móveis do Office e controle de acesso para o Office 365. Quando um dispositivo é perdido, roubado ou simplesmente não é mais necessário para o trabalho, o Intune permite apagar seletivamente apenas os dados da empresa dos dispositivos gerenciados.

>[!Note]
>O Intune reconhece dispositivos como *corporativos* quando qualquer um dos métodos descritos nesta solução são usados para registrar um dispositivo. Quando um dispositivo for reconhecido como corporativo pelo serviço Intune, você verá **Corporativo** na coluna Propriedade para esse registro de dispositivo no console do administrador.

![Opções em um cenário complexo de dispositivo](..\Solutions\media\enable-byod\management-choices-with-intune.png)

> <sup>Você pode baixar esse infográfico em https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup>

### <a name="how-to-implement-this-solution"></a>Como implementar esta solução
O restante dessa solução está dividido nas seções a seguir, que mostram como:
- **Registrar dispositivos iOS corporativos**. Esta seção descreve como usar o Apple Configurator (em um dispositivo Mac) e a integração do DEP (programa de registro de dispositivos) da Apple para registrar dispositivos corporativos.
- **Registrar dispositivos Windows 10 corporativos**. Nesta seção, é descrito como registrar automaticamente os dispositivos Windows 10 ao gerenciamento quando eles são adicionados ao Azure Active Directory de sua empresa.
- **Registrar dispositivos usando uma conta do DEM (gerenciador de Registro de Dispositivo)**. Saiba como contas do DEM permitem que uma pessoa do departamento de TI registre mais dispositivos no gerenciamento do que o número padrão.
- **Marcar dispositivos corporativos com números IMEI (Identidade de Equipamentos Móveis Internacional)**. Esta seção descreve a outra opção para começar a gerenciar dispositivos corporativos no ato do registro, importando os números IMEI identificam dispositivos corporativos.
- **Certificar-se de que os dispositivos gerenciados estão em conformidade com os requisitos básicos de segurança**. Esta seção descreve como certificar-se de que os dispositivos usados para acessar aplicativos e dados da empresa estejam em conformidade com os requisitos básicos de segurança.
- **Fornecer acesso aos recursos da empresa**. Esta seção mostra como os profissionais de TI podem habilitar os usuários a acessar os recursos da empresa facilmente e de forma segura, implantando perfis de acesso para dispositivos gerenciados, e como gerenciar implantações de aplicativos comprados com base no volume com o Intune.
- **Proteger os dados da empresa**. Nesta seção, você vai saber mais sobre como fornecer acesso condicional aos recursos da empresa, como evitar a perda de dados e como remover aplicativos e dados empresariais de dispositivos, quando eles não são mais necessários ou forem perdidos ou roubados.

## <a name="enroll-corporate-owned-ios-devices"></a>Registrar dispositivos iOS corporativos
Se o usuário tiver dispositivos iOS entre os quais escolher como parte de sua estratégia de CYOD, você poderá pré-configurar o registro para que o dispositivo seja gerenciado com o Intune desde a primeira vez que for ativado pelo usuário. O Intune dá suporte ao registro por meio do [DEP (Programa de Registro de Dispositivo) da Apple](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) ou usando a ferramenta Apple Configurator em um computador Mac para registro pelo [Assistente de Configuração](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) ou [registro direto](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune). Você também pode implantar um perfil de registro *pelo ar* em dispositivos iOS adquiridos por meio do DEP.

### <a name="setup-assistant-enrollment"></a>Registro pelo Assistente de Configuração
Quando você usa a [opção de registro pelo Assistente de configuração para dispositivos iOS](https://docs.microsoft.com/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune), o dispositivo é redefinido para os padrões de fábrica e preparado para a configuração final pelo novo usuário do dispositivo. Esse método requer que o administrador conecte o dispositivo iOS a um computador Mac via USB executando o [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) para pré-configurar o registro. Em seguida, os dispositivos são entregues aos usuários, que executam o processo do Assistente de Configuração. Esse processo configura o dispositivo com suas credenciais corporativas ou de estudante e conclui o processo de registro.

### <a name="direct-enrollment"></a>Registro direto
[Registro direto para dispositivos iOS](https://docs.microsoft.com/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune): cria um arquivo em conformidade com Apple Configurator para uso durante a preparação do dispositivo. O dispositivo registrado não é redefinido para os padrões de fábrica, mas não fica associado a qualquer usuário. Esse método requer que o administrador de USB conecte via USB o dispositivo iOS a um computador Mac que esteja executando o [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) para registrar o dispositivo.

### <a name="dep-enrollment"></a>Registro de DEP
O Microsoft Intune pode implantar um perfil de registro que registra os dispositivos iOS comprados por meio do [DEP (Programa de Registro de Dispositivo)](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) *pelo ar*. O pacote de registro pode incluir opções do assistente de configuração para o dispositivo de modo que quando um usuário execute o Assistente de Configuração no dispositivo, o dispositivo seja registrado no Intune para fornecer gerenciamento *desde o início*.

>[!Important]

>O registro de [dispositivos registrados pelo DEP](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) não pode ser cancelado por usuários.

## <a name="enroll-corporate-owned-windows-10-devices"></a>Registrar dispositivos Windows 10 corporativos
É possível transformar o registro de dispositivos Windows no gerenciamento em um processo integrado para os usuários habilitando o recurso de registro automático no Azure AD (Premium). Ao habilitar esse recurso, os dispositivos serão registrados automaticamente para gerenciamento com o Intune quando um usuário adicionar uma conta corporativa ou de estudante para registrar um dispositivo corporativo quando este ingressar no Azure AD da organização.

[O Ingresso do Azure Active Directory (Ingresso do Azure AD) no Windows 10](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-overview) torna mais fácil para os usuários se conectarem à sua nuvem de empresa por meio do Azure AD. A partir desse momento, eles terão acesso a aplicativos organizacionais e recursos de seus dispositivos Windows. A integração do registro de dispositivo automático significa que esses dispositivos são gerenciados automaticamente pelo Microsoft Intune.

>[!Tip]

>Para habilitar o registro automático no MDM no diretório do Azure AD Premium do [Portal do Microsoft Azure](https://portal.azure.com), vá para **Azure Active Directory** > **Mobilidade (MDM e MAM)** > **Microsoft Intune**.

O Ingresso do Azure AD destina-se a empresas que são prioritariamente na nuvem/somente na nuvem. Essas organizações normalmente são pequenas e médias empresas que não têm uma infraestrutura de Active Directory Domain Services (AD DS) do Windows Server local. Dito isso, o Ingresso do Azure AD também poderá ser usado por organizações de grandes porte em dispositivos incapazes de realizar um ingresso no domínio tradicional (dispositivos móveis, por exemplo) ou para usuários que precisam principalmente acessar o Office 365 ou outros aplicativos SaaS do Azure AD. Quando o gerenciamento de dispositivos é feito com o Intune, os administradores de TI podem gerenciar dispositivos ingressados no Azure AD junto com dispositivos ingressados no domínio do AD DS no console de gerenciamento do Configuration Manager por meio de [MDM híbrido](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management#what-is-hybrid-mdm-with-configuration-manager).
Quando um usuário adiciona uma conta corporativa ou de estudante a um dispositivo Windows 10, o dispositivo é marcado automaticamente como "corporativo".

## <a name="enroll-devices-with-a-device-enrollment-manager-dem-account"></a>Registrar dispositivos com uma conta do DEM (gerenciador de Registro de Dispositivo)
Uma única conta do [DEM (gerenciador de registro de dispositivo)](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) do Intune pode ser usada para registrar grandes números de dispositivos móveis em sua organização. Depois de criar uma conta do DEM, ele pode ser usado para registrar até 1.000 dispositivos.

Você pode usar uma conta de DEM para registrar apenas dispositivos que não são usados por um usuário único específico. Esses tipos de dispositivos são bons para aplicativos de ponto de venda ou utilitários, por exemplo, mas não para usuários que precisam acessar os recursos da empresa ou o email.
- Os usuários não podem usar aplicativos VPP (Apple Volume Purchase Program) devido aos requisitos de ID da Apple por usuário para o gerenciamento de aplicativo.
- Se você usar o DEM para registrar dispositivos iOS, não poderá usar o Apple Configurator nem o DEP (Programa de Registro de Dispositivo) da Apple para registrar dispositivos.

## <a name="tag-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Marcar dispositivos corporativos com números IMEI (Identidade de Equipamentos Móveis Internacional)
O Microsoft Intune permite aos administradores [importar números IMEI (identidade de equipamentos móveis internacionais)](https://docs.microsoft.com/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) para plataformas de dispositivos móveis usando números IMEI para ajudar a identificar dispositivos móveis corporativos.

Você pode importar até 5.000 números IMEI usando um arquivo .CSV especialmente formatado ou inserir manualmente até 15 números IMEI do dispositivo simultaneamente no console de administração do Intune. Quando o dispositivo com esse número IMEI é registrado no Intune, que geralmente é quando um usuário instala o aplicativo Portal da Empresa e conclui o processo de registro, o dispositivo é marcado como corporativo e aparece como registrado no grupo Dispositivos IMEI.

## <a name="make-sure-that-managed-devices-comply-with-basic-security-requirements"></a>Verificar se os dispositivos gerenciados estão em conformidade com os requisitos básicos de segurança
Independentemente de estar registrando um dispositivo iOS, Android ou Windows 10, o departamento de TI deverá verificar se esses dispositivos usados para acessar aplicativos e dados da empresa estão em conformidade com os requisitos básicos de segurança. Essas regras podem incluir o uso de um PIN para acessar os dispositivos e criptografar dados armazenados em dispositivos. Chamamos um conjunto dessas regras de [política de conformidade](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

Quando você [cria e implanta uma política de conformidade](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) para os usuários, todos os dispositivos gerenciados pelo Intune serão verificados a fim de confirmar se estão de acordo com os requisitos básicos de segurança, definidos como parte da sua política de CYOD ou BYOD. Depois de avaliar se um dispositivo está em conformidade com a política, ele relatará o respectivo status ao serviço Intune. Em alguns casos, os usuários podem ser solicitados a corrigir configurações não compatíveis, como o uso de um PIN ou criptografia de dispositivo, mas outras vezes, o aplicativo do portal da empresa notificará o usuário apenas sobre os problemas de conformidade encontrados.

## <a name="provide-access-to-company-resources"></a>Fornecer acesso aos recursos da empresa

Esta seção mostra como o departamento de TI pode habilitar os usuários a acessar os recursos da empresa facilmente e de forma segura, implantando perfis de acesso para dispositivos gerenciados, e como gerenciar aplicativos comprados com base no volume.

### <a name="provide-access-to-company-data"></a>Fornecer acesso aos dados da empresa
A primeira coisa que a maioria dos funcionários quer em seus dispositivos móveis é acesso a documentos e email da empresa. E esperam configurá-lo sem passar por etapas complexas ou chamar o suporte técnico. O Microsoft Intune facilita a [criação e a implantação de configurações de email](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) para aplicativos nativos de email, pré-instalados em dispositivos móveis usados pela organização.

> [!NOTE]
> O Intune dá suporte à configuração de perfis de email do Android for Work para os aplicativos do Gmail e do Nine Work encontrados na loja do Google Play.

Além do email, o EMS também ajuda a controlar o acesso e proteger os dados locais da empresa acessados fora dos limites de segurança corporativa tradicionais. Os perfis de [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune), [VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) e email do Microsoft Intune funcionam em conjunto para ajudar os usuários a obter acesso aos arquivos e recursos necessários para realizar o trabalho, em praticamente qualquer lugar. Os aplicativos Web e serviços da empresa hospedados localmente também podem ser acessados com segurança e protegidos usando o Proxy de Aplicativo do Azure Active Directory e o acesso condicional.

### <a name="add-apps-for-enrolled-devices"></a>Adicionar aplicativos para dispositivos registrados
É fácil adicionar aplicativos para dispositivos registrados com o Intune, mas antes de implantar ou gerenciar um aplicativo, você deve [adicioná-lo ao Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) usando o Intune Software Publisher. Você usa o Intune Software Publisher para configurar as propriedades do aplicativo e, onde aplicável, carregá-lo no seu espaço de armazenamento em nuvem.

Com o Intune, você pode [implantar ou gerenciar os seguintes tipos de aplicativos](https://docs.microsoft.com/intune/deploy-use/add-apps) para dispositivos registrados:
- **Instalador de Software**. Esses tipos de aplicativos incluem o instalador de software do Windows (.exe ou .msi), o pacote do aplicativo Android (.apk), o pacote do aplicativo iOS (.ipa), o pacote do aplicativo Windows Phone (.xap, .appx e .appxbundle), o pacote do aplicativo Windows (.appx, .appxbundle) e o Windows Installer por meio de arquivos (.msi) do MDM. Todos os tipos de aplicativo do instalador de software são atualizados para seu [espaço de armazenamento de nuvem](https://docs.microsoft.com/intune/deploy-use/add-apps#cloud-storage-space).
- **Link externo**. Esse tipo de implantação de aplicativo fornece um link externo (URL) que permite aos usuários baixar um aplicativo de uma loja de aplicativos ou um link para um aplicativo baseado na Web executado no navegador da Web. Aplicativos com base em links externos não são armazenados em seu espaço de armazenamento em nuvem do Intune.
- **Aplicativo iOS gerenciado da loja de aplicativos**. Você pode usar aplicativos iOS gerenciados para gerenciar e implantar aplicativos iOS gratuitos da loja de aplicativos. Você também pode usar aplicativos iOS gerenciados para associar políticas de gerenciamento de aplicativos móveis a aplicativos compatíveis e examinar seu status no console do administrador. Aplicativos iOS gerenciados não são armazenados no seu espaço de armazenamento em nuvem do Intune.

### <a name="manage-volume-purchased-apps"></a>Gerenciar aplicativos adquiridos por volume
Você pode facilmente [fornecer uma loja de aplicativos para dispositivos gerenciados](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune) e direcionar aplicativos para dispositivos não gerenciados usando o site do portal da empresa. No entanto, o Intune também permite gerenciar e implantar aplicativos comprados com base no volume, na loja de aplicativos iOS e na Windows Store para Empresas. Isso ajuda a reduzir a sobrecarga administrativa no acompanhamento de aplicativos comprados com base no volume.

> [!TIP]
> Você pode facilmente [configurar SSO (logon único) com o Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para que os usuários possam entrar em aplicativos com o nome de usuário do domínio e a senha que eles usam no local. Além disso, você pode [fornecer acesso baseado na Internet para aplicativos Web hospedados no local](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) usando o Proxy de Aplicativo do Azure Active Directory.

Com o Intune, é fácil importar as informações de licença de volume de todas as lojas de aplicativos, controlar a quantidade de licenças que você usou e impedir que os usuários instalem mais cópias do aplicativo do que o permitido.

-   [Gerenciar aplicativos comprados com base no volume para dispositivos iOS](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune). Você compra várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/). Isso envolve a configuração de uma conta do Apple VPP no site da Apple e upload do token do Apple VPP no Intune. Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

-   [Windows Store para Empresas](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune). O [Windows Store para a Empresa](https://www.microsoft.com/business-store) fornece um local para encontrar e comprar aplicativos para sua organização, individualmente ou em um volume. Se conectar a loja ao Microsoft Intune, você pode gerenciar os aplicativos comprados com base no volume no portal do Intune.

## <a name="protect-company-data"></a>Proteger os dados da empresa

O Intune protege os dados da empresa por meio de várias camadas de tecnologia. Na camada de identidade, o acesso condicional protege o acesso aos serviços, permitindo o acesso somente de dispositivos gerenciados e compatíveis. Na camada de aplicativo do cliente, as políticas de proteção do aplicativo protegem contra a perda de dados impedindo que os dados sejam movidos para aplicativos ou locais de armazenamento não protegidos e apagando os dados quando um dispositivo é perdido ou roubado.

### <a name="enforce-conditional-access-to-company-resources"></a>Impor acesso condicional aos recursos da empresa

Você pode usar políticas de conformidade em combinação com [políticas de acesso condicional](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) para verificar se os dispositivos estão em conformidade com os requisitos básicos de segurança da sua política de BYOD. Quando um dispositivo não está em conformidade com a política, as regras de acesso condicional são impostas e o acesso é negado, até que o dispositivo esteja configurado para atender aos requisitos da política. Isso garante que apenas os dispositivos gerenciados e em conformidade possam acessar dados empresarias em serviços como Exchange ([Exchange no Local](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune) ou [Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)), SharePoint Online, Skype for Business Online e muito mais.

> [!IMPORTANT]
> Políticas de acesso condicional não funcionarão se não houver nenhuma política de conformidade em vigor para validar a conformidade.

### <a name="prevent-data-loss-of-company-data-with-application-protection-policies"></a>Evitar a perda de dados empresariais com políticas de proteção de aplicativos

As políticas de proteção de aplicativos do Intune proporcionam flexibilidade para gerenciar a forma de acesso aos dados, independentemente do registro de dispositivos. Com a capacidade de proteger os dados da empresa, com ou sem o registro de dispositivos, você pode habilitar cenários de proteção de dados de modo que os dados da empresa possam ser acessados de forma segura, mesmo se o usuário não quiser registrar o dispositivo no gerenciamento.

Você pode usar as [políticas de proteção de aplicativo do Intune](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) para ajudar a proteger os dados da empresa, que são acessados por dispositivos Android e iOS dos usuários. Implementando essas políticas em nível de aplicativo, você pode controlar como os funcionários usam e compartilham os dados da empresa, mesmo que os dispositivos em si não sejam gerenciados pelo Intune.

Use as [políticas de WIP (Proteção de Informações do Windows)](https://docs.microsoft.com/intune/deploy-use/microsoft-intune-policy-reference#windows-configuration-policies) para fazer o mesmo com dispositivos Windows 10 gerenciados. Essas políticas funcionam sem afetar a experiência dos funcionários ou sem exigir alterações no ambiente de rede ou em outros aplicativos.

### <a name="wipe-company-data-while-leaving-personal-data-intact"></a>Apagar os dados da empresa deixando os dados pessoais intactos

Quando um dispositivo deixa de ser necessário para o trabalho, tem sua função redefinida ou talvez tenha acabado de desaparecer, você precisa ser capaz de remover dados e aplicativos da empresa dele. Para isso, você pode usar as funcionalidades de apagamento completo e apagamento seletivo do Intune. Os usuários também podem apagar remotamente seus dispositivos de propriedade pessoal que registraram para gerenciamento no Portal da Empresa do Intune.

Em vez de fazer um [apagamento completo](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#full-wipe) que restaura um dispositivo para as configurações padrão de fábrica e remove dados e configurações do usuário, você pode usar a funcionalidade de [apagamento seletivo](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#selective-wipe) para remover somente os dados da empresa do dispositivo, deixando os dados pessoais do usuário intactos.

Depois de iniciado, o dispositivo iniciará imediatamente o processo de apagamento seletivo para ser removido do gerenciamento. Quando o processo for concluído, todos os dados da empresa serão excluídos e o nome do dispositivo será removido do console do administrador do Intune, concluindo o ciclo de vida de gerenciamento do dispositivo.

### <a name="learn-more"></a>Saiba mais
[Começar a usar o Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)

