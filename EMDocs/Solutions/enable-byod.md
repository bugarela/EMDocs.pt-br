---
title: "Habilitar BYOD (Traga seu próprio dispositivo) com o Intune | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 2/10/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d31eebe-81d2-4c6b-bfec-fbd536096dda
ms.reviewer: vlpetros
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4edb16e4ef00b7376af800ab542f42c0e530197
ms.openlocfilehash: 9defe28a74bc3e53f6ae5dc33b33396e47247265


---
# <a name="enable-byod-with-intune"></a>Habilitar BYOD (Traga seu próprio dispositivo) com o Intune
O suporte para transformação digital implica em novos desafios para os profissionais de TI, à medida que eles se esforçam para proteger os dados da empresa para que os funcionários possam se manter produtivos no cenário móvel atual, cada vez mais complexo. Como as organizações continuam migrando para a nuvem, os funcionários esperam ser produtivos fora do trabalho com uma experiência semelhante às experiências de cliente deles em vários dispositivos.

![Opções em um cenário complexo de dispositivo](..\Solutions\media\enable-byod\management-choices-with-intune.png)

> <sup>Você pode baixar esse infográfico em https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup>

Alguns desses dispositivos são gerenciados pela empresa e podem ser exclusivos para um usuário específico ou é possível compartilhar um único dispositivo entre vários funcionários. Haverá também dispositivos gerenciados pelos funcionários. Esses dispositivos pessoais podem ser um iPhone ou um computador que eles usam para trabalhar diariamente ou um dispositivo complementar que usam para se conectar de vez em quando, como um computador familiar ou um iPad dos filhos.

Além dos dispositivos, o local em que as pessoas realizam o trabalho também está mudando. Elas deixaram de trabalhar exclusivamente em escritórios ou locais de trabalho tradicionais. A força de trabalho moderna passou a trabalhar em casa, em lanchonetes, no local do cliente, fora do escritório e até mesmo durante os voos. Por isso, os programas BYOD (traga seu próprio dispositivo) se tornaram comuns no local de trabalho moderno. Cabe aos profissionais de TI se beneficiarem de alguma forma das vantagens e oportunidades a fim de aumentar a satisfação dos funcionários e reduzir os custos, além de manter o controle dos dados da empresa.

Os programas BYOD bem-sucedidos permitem aumentar a segurança e manter um controle mais rigoroso, sem precisar impor processos complexos ou alterar a maneira de trabalhar das pessoas. Uma experiência ideal para os usuários finais significa que eles estão mais propensos a usar as soluções de segurança que você fornece e menos propensos a criar soluções alternativas que estejam totalmente fora do seu controle para realizar o trabalho.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>Como o EMS (Enterprise Mobility + Security) pode ajudar você?

Com o EMS, você pode fornecer recursos e experiências a fim de criar um local de trabalho produtivo que inclua vários estilos de trabalho, em praticamente qualquer lugar. Se os funcionários estiverem usando dispositivos MacOS, Android, iOS ou Windows, o Microsoft Intune, que integra o EMS, pode ajudá-lo a fornecer produtividade à sua equipe em vários dispositivos, além de manter a segurança dos dados da empresa. O Intune fornece recursos de MAM e MDM que permitem proteger os dados corporativos, com ou sem gerenciamento de dispositivos. Além do gerenciamento abrangente do ciclo de vida de aplicativos e dispositivos móveis, o Intune se integra diretamente aos aplicativos móveis do Office e do Office 365.

### <a name="recommended-solution"></a>Solução recomendada

Usando o Intune você pode, de maneira fácil, fornecer aos funcionários acesso a aplicativos, dados e recursos da empresa de praticamente qualquer lugar em qualquer dispositivo, enquanto ajuda a manter as informações corporativas em segurança. A integração direta com o Office 365 possibilita experiências incríveis para o usuário final e fornece recursos abrangentes de prevenção contra perda de dados para aplicativos móveis do Office e controle de acesso para o Office 365. Quando um dispositivo é perdido, roubado ou quando simplesmente não é mais necessário para o trabalho, o Intune permite que você apague, seletivamente, apenas os dados da empresa dos dispositivos BYOD.

Assista a um breve vídeo para conhecer as necessidades e os desafios de usuários finais e profissionais de TI, que envolvem manter o equilíbrio entre a produtividade e a segurança em um mundo móvel e em nuvem:
<iframe width="675" height="480" src="https://www.youtube.com/embed/pgAmKnluwVw" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>Como implementar esta solução

O restante dessa solução está dividido nas seções a seguir, que mostram como:

-   **Registrar dispositivos e verificar a conformidade**. Esta seção descreve como habilitar os usuários a registrar os dispositivos (iOS, MacOS, Android, Android for Work e Windows) no gerenciamento por meio do Intune e como implantar políticas a fim de garantir que eles estejam em conformidade com os requisitos básicos de segurança.

-   **Fornecer acesso aos recursos da empresa**. Esta seção mostra como os profissionais de TI podem habilitar os usuários a acessar os recursos da empresa facilmente e de forma segura, implantando perfis de acesso para dispositivos gerenciados, e como gerenciar implantações de aplicativos comprados com base no volume com o Intune.  

-   **Proteger os dados da empresa**. Nesta seção, você vai saber mais sobre como fornecer acesso condicional aos recursos da empresa, como evitar a perda de dados e como remover aplicativos e dados empresariais de dispositivos, quando eles não são mais necessários ou forem perdidos ou roubados.

## <a name="enroll-devices-and-check-for-compliance"></a>**Registrar dispositivos e verificar a conformidade**

Esta seção descreve como habilitar os usuários a registrar os dispositivos no gerenciamento por meio do Intune e garantir que os dispositivos deles estejam em conformidade com os requisitos básicos de segurança.

### <a name="enable-users-to-enroll-their-personal-devices-into-management"></a>Habilitar os usuários a registrar os dispositivos pessoais no gerenciamento

Registrar dispositivos e computadores para gerenciamento com o Intune garante que todas as políticas e perfis de acesso que configurados para os dispositivos gerenciados sejam aplicadas. Antes que possa registrar dispositivos, primeiro você precisará [preparar o serviço do Intune](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) atribuindo licenças a usuários, definindo a autoridade de gerenciamento de dispositivo móvel e atendendo os vários requisitos de registro para os diferentes tipos de dispositivo que deseja gerenciar. Enquanto estiver fazendo isso, você provavelmente também deveria [personalizar o portal da empresa](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal) com informações de suporte e a identidade visual específica da empresa para fornecer uma experiência confiável de registro e suporte para seus usuários.

Depois de preparar o serviço do Intune, o processo de registrar os dispositivos para gerenciamento é bastante simples, mas ligeiramente diferente para os diferentes tipos de dispositivo:

-   **Dispositivos iOS e Mac**. Você deve obter um certificado APNs (Apple Push Notification Service) para registrar iPads, iPhones ou dispositivos MacOS. Após [carregar o certificado APNs no Intune](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune), os usuários podem [registrar dispositivos iOS](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios) usando o aplicativo do portal da empresa e usar o site do portal da empresa para [registrar dispositivos MacOS](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x).

-   **Dispositivos Android**. Não há nada que você precisa fazer para deixar o serviço do Intune pronto para registrar dispositivos Android. Os usuários podem simplesmente [registrar seus dispositivos Android](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune) para gerenciamento usando o aplicativo de Portal da Empresa no Google Play.

-   **Android for Work**. Para [configurar o Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work) para o Android 5.0 Lollipop e dispositivos posteriores que dão suporte aos perfis de trabalho a serem gerenciados pelo Intune, é necessário que a organização se inscreva no Android for Work com o Google e, em seguida, configure as definições do Android for Work no nó ADMIN do console de administração do Intune.

-   **Telefones e computadores Windows**. Você deve [definir um alias DNS para o servidor de registro](https://docs.microsoft.com/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) para facilitar o registro de dispositivos Windows. Caso contrário, você pode [registrar dispositivos Windows](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows) adicionando uma conta corporativa ou de estudante.

> [!TIP]
> É possível tornar o registro em dispositivos Windows ainda mais fácil para os usuários [habilitando o recurso de registro automático](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment) no Azure AD (Premium). Ao habilitar esse recurso, os dispositivos serão registrados automaticamente para gerenciamento com o Intune quando um usuário adicionar uma conta corporativa ou de estudante para registrar um dispositivo pessoal ou corporativo no Azure AD da organização.

### <a name="make-sure-that-managed-devices-comply-with-basic-security-requirements"></a>Verificar se os dispositivos gerenciados estão em conformidade com os requisitos básicos de segurança

Depois que os usuários registrarem os dispositivos no gerenciamento, o departamento de TI deverá verificar se esses dispositivos usados para acessar aplicativos e dados da empresa estão em conformidade com os requisitos básicos de segurança. Essas regras podem incluir o uso de um PIN para acessar os dispositivos e criptografar dados armazenados em dispositivos. Chamamos um conjunto dessas regras de [política de conformidade](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

Quando você [cria e implanta uma política de conformidade](https://docs.microsoft.com/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) para os usuários, todos os dispositivos gerenciados pelo Intune serão verificados a fim de confirmar se estão de acordo com os requisitos básicos de segurança, definidos como parte da sua política de BYOD. Depois de avaliar se um dispositivo está em conformidade com a política, ele relatará o respectivo status ao serviço Intune. Em alguns casos, os usuários podem ser solicitados a corrigir configurações não compatíveis, como o uso de um PIN ou criptografia de dispositivo, mas outras vezes, o aplicativo do portal da empresa notificará o usuário apenas sobre os problemas de conformidade encontrados.

## <a name="provide-access-to-company-resources"></a>Fornecer acesso aos recursos da empresa

Esta seção mostra como o departamento de TI pode habilitar os usuários a acessar os recursos da empresa facilmente e de forma segura, implantando perfis de acesso para dispositivos gerenciados, e como gerenciar aplicativos comprados com base no volume.

### <a name="provide-access-to-company-data"></a>Fornecer acesso aos dados da empresa
A primeira coisa que a maioria dos funcionários quer em seus dispositivos móveis é acesso a documentos e email da empresa. E esperam configurá-lo sem passar por etapas complexas ou chamar o suporte técnico. O Microsoft Intune facilita a [criação e a implantação de configurações de email](https://docs.microsoft.com/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) para aplicativos nativos de email, pré-instalados em dispositivos móveis usados pela organização.

> [!NOTE]
> O Intune dá suporte à configuração de perfis de email do Android for Work para os aplicativos do Gmail e do Nine Work encontrados na loja do Google Play.

Além do email, o EMS também ajuda a controlar o acesso e proteger os dados locais da empresa acessados fora dos limites de segurança corporativa tradicionais. Os perfis de [Wi-Fi](https://docs.microsoft.com/intune/deploy-use/wi-fi-connections-in-microsoft-intune), [VPN](https://docs.microsoft.com/intune/deploy-use/vpn-connections-in-microsoft-intune#create-a-vpn-profile) e email do Microsoft Intune funcionam em conjunto para ajudar os usuários a obter acesso aos arquivos e recursos necessários para realizar o trabalho, em praticamente qualquer lugar. Os aplicativos Web e serviços da empresa hospedados localmente também podem ser acessados com segurança e protegidos usando o Proxy de Aplicativo do Azure Active Directory e o acesso condicional.

### <a name="manage-volume-purchased-apps"></a>Gerenciar aplicativos adquiridos por volume
Você pode facilmente [fornecer uma loja de aplicativos para dispositivos gerenciados](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune) e direcionar aplicativos para dispositivos não gerenciados usando o site do portal da empresa. No entanto, o Intune também permite gerenciar e implantar aplicativos comprados com base no volume, na loja de aplicativos iOS e na Windows Store para Empresas. Isso ajuda a reduzir a sobrecarga administrativa no acompanhamento de aplicativos comprados com base no volume.

> [!TIP]
> Você pode facilmente [configurar SSO (logon único) com o Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para que os usuários possam entrar em aplicativos com o nome de usuário do domínio e a senha que eles usam no local. Além disso, você pode [fornecer acesso baseado na Internet para aplicativos Web hospedados no local](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) usando o Proxy de Aplicativo do Azure Active Directory.

Com o Intune, é fácil importar as informações de licença de volume de todas as lojas de aplicativos, controlar a quantidade de licenças que você usou e impedir que os usuários instalem mais cópias do aplicativo do que o permitido.

-   [Gerenciar aplicativos comprados com base no volume para dispositivos iOS](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune). Você compra várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/). Isso envolve a configuração de uma conta do Apple VPP no site da Apple e upload do token do Apple VPP no Intune. Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

-   [Windows Store para Empresas](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune). O [Windows Store para a Empresa](https://www.microsoft.com/business-store) fornece um local para encontrar e comprar aplicativos para sua organização, individualmente ou em um volume. Se conectar a loja ao Microsoft Intune, você pode gerenciar os aplicativos comprados com base no volume no portal do Intune.

## <a name="protect-company-data"></a>Proteger os dados da empresa

O Intune protege os dados da empresa por meio de várias camadas de tecnologia. Na camada de identidade, o acesso condicional protege o acesso aos serviços, permitindo o acesso somente de dispositivos gerenciados e compatíveis. Na camada de aplicativo do cliente, o MAM (Gerenciamento de aplicativos Móveis) protege contra a perda de dados impedindo que os dados sejam movidos para aplicativos ou locais de armazenamento não protegidos e apagando os dados quando um dispositivo é perdido ou roubado.

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



<!--HONumber=Feb17_HO2-->


