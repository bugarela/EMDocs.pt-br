---
title: Proteger dados da empresa no Office 365 | Microsoft Docs
description: "Juntos, o EMS e o Office 365 oferecem uma solução gerenciada completa de produtividade móvel que proporciona aos seus usuários o padrão de ouro de produtividade e à sua equipe de TI controles de dados profundamente integrados."
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cc0d2e1f-9c34-4dcb-ac1f-2f355e9ebb7e
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: c57332d427eec2d591fdaf527a783f5e58d457d9
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="protect-office-365-company-data-with-intune"></a>Proteger dados da empresa no Office 365 com o Intune
A primeira coisa que a maioria dos funcionários quer em seus dispositivos móveis é acesso a documentos e email da empresa. E esperam configurá-lo sem passar por etapas complexas ou chamar o suporte técnico. A IT, por outro lado, quer manter os dados da empresa em segurança onde quer que estejam, sem a dor de cabeça de manter uma grande infraestrutura local. Com o EMS (Enterprise Mobility + Security), você poderá manter seus funcionários produtivos com seus aplicativos e dispositivos favoritos — e os dados da empresa em segurança. Continue lendo para saber como.

## <a name="how-can-enterprise-mobility--security-ems-help-you"></a>Como o EMS (Enterprise Mobility + Security) pode ajudar você?
O EMS é a única solução que foi criada para proteger nativamente arquivos, aplicativos e email do Microsoft Office em todos os dispositivos que os usuários levam para o trabalho. Nos bastidores, o EMS facilita o fornecimento de email seguro aos funcionários, em qualquer lugar, trabalhando para fornecer quatro camadas de proteção em identidades, dispositivos, aplicativos e dados. Com o EMS, seus funcionários terão acesso seguro e direto ao email e a documentos corporativos, bem como experiências familiares de produtividade e email com aplicativos do Office Mobile, como Outlook, Word, Excel, PowerPoint e OneDrive.

O Office 365 foi projetado para funcionários que desejam a flexibilidade de levar o trabalho consigo, aonde quer que forem, sem sacrificar a experiência do usuário. Juntos, o EMS e o Office 365 oferecem uma solução gerenciada completa de produtividade móvel que proporciona aos seus usuários o padrão de ouro de produtividade e à sua equipe de TI controles de dados profundamente integrados.

### <a name="recommended-solution"></a>Solução recomendada
Usando o Intune você pode, de maneira fácil, fornecer aos funcionários acesso a aplicativos, dados e recursos da empresa de praticamente qualquer lugar em qualquer dispositivo, enquanto ajuda a manter as informações corporativas em segurança. Além de ser mais fácil, o Intune também protege os dados da empresa de forma mais moderna e econômica do que a maioria das soluções locais tradicionais. Com o Intune protegendo os dados do Office 365, não é necessário instalar e manter uma infraestrutura local ou abrir o firewall da empresa para encaminhar o tráfego através dele.

Este é um breve vídeo que lhe dará uma introdução rápida de como o Intune e o Office 365 funcionam juntos para fornecer uma experiência simples para os funcionários acessarem dados da empresa com segurança usando dispositivos iOS, Android e Windows:

<iframe width="675" height="480" src="https://www.youtube.com/embed/To9zfl6-Z6Y" frameborder="0" allowfullscreen></iframe>

### <a name="how-to-implement-this-solution"></a>Como implementar esta solução
O restante dessa solução está dividido nas seções a seguir, que mostram como proteger os dados de empresa do Office 365 com o Intune:
- **Registrar dispositivos móveis e computadores Windows no gerenciamento**. Esta seção descreve como registrar dispositivos (iOS, Android, Android for Work e computadores Windows) no gerenciamento com o Intune a fim de implantar políticas que protegem os dados de empresa do Office 365.
- **Acesso seguro a serviços do Office 365**. Nesta seção, é possível saber mais sobre as políticas de conformidade do Intune e como gerenciar o acesso condicional aos serviços do Office 365 do Exchange Online e do SharePoint Online.
- **Proteger os dados da empresa**. Esta seção mostra como usar as políticas de proteção do aplicativo para dispositivos Android e iOS, e também como aproveitar as políticas de Proteção de Informações do Windows para proteger os dados de aplicativo da empresa em computadores Windows 10 gerenciados como dispositivos pelo Intune.
- **Apagar seletivamente dados da empresa**. Esta seção ensinará como remover aplicativos da empresa e dados de dispositivos quando eles não são mais necessários ou foram perdidos ou roubados.


## <a name="enroll-mobile-devices-and-windows-pcs-into-management"></a>Registrar dispositivos móveis e computadores Windows no gerenciamento
Inscrever dispositivos e computadores para gerenciamento com o Intune garante que todas as políticas e perfis de acesso que você configurou para os dispositivos gerenciados sejam aplicadas. Antes que possa registrar dispositivos, primeiro você precisará [preparar o serviço do Intune](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) atribuindo licenças a usuários, definindo a autoridade de gerenciamento de dispositivo móvel e atendendo os vários requisitos de registro para os diferentes tipos de dispositivo que deseja gerenciar. Enquanto estiver fazendo isso, você provavelmente também deveria [personalizar o portal da empresa](https://docs.microsoft.com/intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune#configure-the-intune-company-portal) com informações de suporte e a identidade visual específica da empresa para fornecer uma experiência confiável de registro e suporte para seus usuários.

Depois de preparar o serviço do Intune, o processo de registrar os dispositivos para gerenciamento é bastante direto, mas ligeiramente diferente para os diferentes tipos de dispositivo:
- **Dispositivos iOS e Mac**. Você precisará obter um certificado do APNs (Apple Push Notification Service) para registrar dispositivos Mac OS X, iPhones ou iPads. Após ter [carregado seu certificado do APNs no Intune](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune), você pode [registrar dispositivos iOS](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-ios) usando o aplicativo de Portal da Empresa e usar o site do Portal da Empresa para [registrar dispositivos Mac OS X](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-mac-os-x).
- **Dispositivos Android**. Não há nada que você precisa fazer para deixar o serviço do Intune pronto para registrar dispositivos Android. Os usuários podem simplesmente [registrar seus dispositivos Android](https://docs.microsoft.com/intune/deploy-use/set-up-android-management-with-microsoft-intune) para gerenciamento usando o aplicativo de Portal da Empresa no Google Play.
-   **Android for Work**. Para [configurar o Android for Work](https://docs.microsoft.com/intune/deploy-use/set-up-android-for-work) para o Android 5.0 Lollipop e dispositivos posteriores que dão suporte aos perfis de trabalho a serem gerenciados pelo Intune, é necessário que a organização se inscreva no Android for Work com o Google e, em seguida, configure as definições do Android for Work no nó ADMIN do console de administração do Intune.
- **Telefones e computadores Windows**. Você deve [definir um alias DNS para o servidor de registro](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) para facilitar o registro de dispositivos Windows. Caso contrário, você pode [registrar dispositivos Windows](https://docs.microsoft.com/intune/enduser/enroll-your-w10-phone-or-w10-pc-windows) adicionando uma conta corporativa ou de estudante.

> [!TIP]
> É possível tornar o registro em dispositivos Windows ainda mais fácil para os usuários [habilitando o recurso de registro automático](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment) no Azure AD (Premium). Ao habilitar esse recurso, os dispositivos serão registrados automaticamente para gerenciamento com o Intune quando um usuário adicionar uma conta corporativa ou de estudante para registrar um dispositivo pessoal ou corporativo no Azure AD da organização.

## <a name="secure-access-to-office-365-services"></a>Acesso seguro a serviços do Office 365
Seus usuários esperam obter acesso a todos os seus arquivos e emails da empresa quando usam aplicativos móveis do Office 365, mas você também precisa garantir que somente dispositivos confiáveis se conectem aos recursos da empresa. Para ajudar a fazer isso, você pode usar políticas de acesso condicional do Intune para garantir que os funcionários acessem os serviços de nuvem do Office 365 usando somente dispositivos gerenciados e compatíveis com as políticas.

Para que as políticas de acesso condicional funcionem, primeiro você precisa definir uma [política de conformidade de dispositivo do Intune](https://docs.microsoft.com/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune). Esses tipos de políticas do Intune verificam os dispositivos, no momento do registro e depois periodicamente, para garantir que as configurações dos dispositivos estejam definidas da maneira como você deseja. Assim, é mais fácil você ter certeza de que apenas dispositivos que atendam aos seus requisitos de segurança possam acessar recursos da empresa. Basta definir o que torna um dispositivo compatível (por exemplo, exigir senha para desbloquear, permitir ou negar senhas simples, comprimento mínimo da senha, sem jailbreak etc.) criando uma política de conformidade do dispositivo do Intune e implantando-a para os usuários.

> [!IMPORTANT]
> Políticas de acesso condicional não funcionarão se não houver nenhuma política de conformidade em vigor para validar a conformidade.

[Políticas de acesso condicional](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) podem ser usadas para proteger o acesso aos serviços do Office 365, como o Dynamics CRM Online<sup>1</sup>, o Exchange Online<sup>2</sup>, o SharePoint Online<sup>2</sup> e o Skype for Business Online<sup>1</sup>. Políticas de acesso condicional serão configuradas para o Exchange Online e o SharePoint Online nos exemplos a seguir.  

> <sup>1</sup> Apenas para iOS e Android.

> <sup>2</sup> Dispositivos iOS, Android e Windows.

### <a name="secure-access-to-exchange-online"></a>Proteger o acesso ao Exchange Online
Com o Intune, o email do Exchange Online de sua empresa é protegido de acordo com as políticas de conformidade e acesso condicionais que você definir. Por exemplo, você pode [restringir o acesso ao email do Exchange Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) para dispositivos que não usam uma senha forte, não têm jailbreak e não são criptografados.

Veja o que acontece quando um usuário tenta acessar seu email usando um dispositivo que não é gerenciado pelo Intune quando você configurou políticas de acesso condicional para acessar o Exchange Online:
1. O usuário tenta ler seus emails da empresa no Exchange Online usando o aplicativo de email nativo em seu dispositivo Android não gerenciado. O acesso ao email é negado porque o dispositivo não está sendo gerenciado pelo Intune e, portanto, não é compatível com sua política de conformidade.
2. O único email que o usuário vê é do serviço do Intune, informando que o dispositivo não é compatível com as políticas da empresa e que o usuário precisa registrá-lo antes de obter acesso a seus emails.
3. Após o dispositivo ser registrado e avaliado como compatível com as políticas da empresa, o acesso completo ao email da empresa é restaurado.

![Imagens mostrando como o acesso condicional funciona para o Exchange Online](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig1.png)

### <a name="secure-access-to-sharepoint-online"></a>Proteger o acesso ao SharePoint Online
O Intune também pode, facilmente, [proteger o acesso ao SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) usando o acesso condicional. Assim como para proteger o acesso ao email, você precisará configurar duas políticas que devem ser cumpridas para habilitar o acesso: uma política de conformidade do dispositivo para garantir que as políticas da empresa estejam sendo seguidas no dispositivo e uma política de acesso condicional que define as condições que devem ser atendidas para acessar o serviço.

Quando um usuário tenta usar um dispositivo não gerenciado para se conectar ao serviço do SharePoint Online protegido pelas políticas de acesso condicional do Intune, o seguinte acontece:
1.  O usuário tem o acesso negado para recursos do SharePoint Online e recebe uma mensagem para fortalecer a segurança, bem como links para registrar seus dispositivos no gerenciamento do Intune.
2.  Seguindo os links fornecidos pela mensagem de acesso negado, o usuário registra seu dispositivo.
3.  Após o dispositivo ser registrado e avaliado como compatível com as políticas da empresa, o acesso completo aos dados do SharePoint Online é restaurado.

![Imagens mostrando como o acesso condicional funciona para o SharePoint Online](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig2.png)

## <a name="protect-company-data"></a>Proteger os dados da empresa
Você provavelmente já sabe que a maioria dos funcionários usam seus dispositivos móveis para fins pessoais e de trabalho. Especialmente agora, com o aumento de dispositivos dos funcionários sendo usados para fins de trabalho, também há um risco crescente de vazamentos de dados acidentais por meio de aplicativos e serviços, como email, mídia social e nuvem pública, que estão fora do seu controle. Por exemplo, quando um funcionário envia as imagens mais recentes de engenharia da sua conta de email pessoal, copia e cola informações do produto em um tweet ou salva um relatório de vendas em andamento para o armazenamento de nuvem pública. Portanto, o seu desafio é que, enquanto precisa manter os funcionários produtivos, você também precisa fazer o possível para impedir vazamentos de dados da empresa, sejam eles intencionais ou acidentais.

Enquanto as políticas de acesso condicional permitem garantir que apenas usuários e dispositivos compatíveis possam acessar emails, ainda há a questão de proteger os emails em si, bem como os arquivos anexados. Como impedir que o conteúdo seja copiado, movido, salvo em um local diferente ou compartilhado com outras pessoas? O Intune resolve esse problema usando políticas de MAM (gerenciamento de aplicativo móvel) para dispositivos iOS e Android e políticas de WIP (Proteção de Informações do Windows) para computadores Windows 10 e dispositivos móveis.  

### <a name="mam-for-managed-ios-and-android-mobile-devices"></a>MAM para dispositivos móveis Android e iOS gerenciados
Você pode usar políticas de MAM (gerenciamento de aplicativo móvel) do Intune para ajudar a proteger dados da empresa que são acessados pelos dispositivos iOS e Android dos usuários. Implementando essas políticas no nível do aplicativo, é possível controlar como os dados da empresa são usados e compartilhados por funcionários.

> [!TIP]
> As políticas de MAM do Intune podem ser usadas de forma independente de qualquer solução de MDM (gerenciamento de dispositivo móvel), desde que uma licença do Intune tenha sido atribuída ao usuário. Isso significa que você pode proteger os dados da empresa registrando ou não os dispositivos no gerenciamento do Intune ou mesmo se um serviço que não é o MDM da Microsoft gerenciar o dispositivo.

Como administrador, você define [configurações de política de aplicativo de MAM do Intune no portal de administração do Azure](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune). Os dois tipos de configurações incluídos nas políticas de MAM são configurações de *realocação de dados* e *acesso*. Políticas de realocação de dados definem como os dados de um aplicativo protegido podem ser usados. Por exemplo, você pode impedir as funções "Salvar como" ou recortar, copiar e colar. Configurações de política de acesso determinam o nível de segurança de dispositivo que você considera necessário para os funcionários usarem o aplicativo. Com essas configurações, você pode exigir um PIN de aplicativo adicional ou até mesmo impedir que o aplicativo seja executado em dispositivos com jailbreak ou raiz.

As capturas de tela a seguir mostram algumas maneiras de proteger um aplicativo usando políticas de MAM do Intune. Neste exemplo, um PIN é necessário para acessar o aplicativo (uma configuração de acesso) e os dados da empresa são protegidos impedindo que informações da empresa sejam colados em aplicativos não gerenciados (configuração de realocação de dados):

1.  Na primeira vez em que o aplicativo gerenciado (Yammer para iOS, neste exemplo) for iniciado, o usuário será solicitado a criar um PIN para acessar o aplicativo. Em seguida, ele precisará inserir o PIN sempre que o aplicativo for iniciado.
2.  O usuário pode copiar dados da empresa, como conversas do Yammer e colá-lo em outros aplicativos gerenciados.
3.  No entanto, quando o usuário tentar colar esse conteúdo em uma mensagem de texto (ou em qualquer outro aplicativo não gerenciado), a função de colar não estará disponível.  

![Imagens mostrando como as políticas de MAM funcionam](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig3.png)

### <a name="windows-information-protection-wip-for-managed-windows-10-pcs-and-mobile-devices"></a>WIP (Proteção de Informações do Windows) para computadores Windows 10 e dispositivos móveis gerenciados
As políticas de WIP do Intune ajudam a proteger contra possíveis vazamentos de dados de dispositivos Windows 10 gerenciados. E o melhor de tudo: essas políticas funcionam sem interferir na experiência do funcionário ou exigir mudanças em seu ambiente de rede ou outros aplicativos.

Funciona da seguinte forma: os dados da empresa são criptografados automaticamente após serem carregados em um dispositivo Windows gerenciado de uma fonte corporativa ou se um funcionário marcar os dados como trabalho (em vez de pessoais). Quando dados da empresa são gravados no disco, o WIP usa o EFS (Encrypting File System) fornecido pelo Windows para protegê-los e associá-los à sua identidade corporativa. Quando cria uma política de WIP do Intune, você pode definir uma lista de aplicativos confiáveis que têm permissão para acessar e modificar dados da empresa. Em seguida, a funcionalidade AppLocker funciona em segundo plano com o sistema operacional para controlar quais aplicativos podem ser executados e como os dados da empresa podem ser acessados e compartilhados. Aplicativos permitidos não precisam ser modificados para abrir os dados da empresa, porque estão na lista que permite que o Windows lhes conceda acesso aos dados da empresa.

> [!TIP]
> Quando políticas de WIP estiverem protegendo aplicativos e dados da empresa, os usuários finais verão "Gerenciado" além dos nomes dos aplicativos permitidos no Menu Iniciar em seus dispositivos. Atalhos de aplicativos e arquivos salvos também exibirão o ícone de pasta do WIP além dos ícones padrão dos aplicativos.
<img src="..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig4.png" alt="Image showing how WIP policies affect the Start Menu and files" style="width:376px;height:112x;">

[As definições de política de configuração de WIP](https://docs.microsoft.com/intune/deploy-use/microsoft-intune-policy-reference#windows-configuration-policies) permitem que você defina níveis diferentes de controle e auditoria no console do administrador do Intune. Os níveis de proteção de dados variam de **Silencioso** (atividade de log de WIP somente) a **Bloquear**, que impede completamente que os usuários compartilhem qualquer conteúdo de aplicativos protegidos. **Substituir** é uma configuração intermediária que permite que os usuários compartilhem dados da empresa com aplicativos não protegidos com um aviso, mas também registra todas as ações para análise posterior.

É assim que as políticas de WIP do Intune podem ajudar a proteger dados da empresa em dispositivos Windows 10 gerenciados:
1.  Uma nova política de WIP é criada e implantada para os usuários do console do administrador do Intune.
2.  Neste exemplo, as informações do AppLocker para o Microsoft Word são usadas para adicionar o Word 2016 à lista de aplicativos permitidos, o nível de restrição de política está definido como Substituir e a política é implantada para usuários.
3.  Um usuário tenta colar dados da empresa copiados de um documento do Word 2016 protegido para uma nova instância desprotegida do Bloco de Notas. Imediatamente, ele será solicitado a confirmar que essa mudança de configuração de trabalho para pessoal é planejada e que a ação será monitorada.

![Imagens mostrando como as políticas de WIP funcionam](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig5.png)

## <a name="selectively-wipe-company-data"></a>Apagar seletivamente dados da empresa
Quando um dispositivo deixa de ser necessário para o trabalho, tem sua função redefinida ou talvez tenha acabado de desaparecer, você precisa ser capaz de remover dados e aplicativos da empresa dele. Para isso, você pode usar as funcionalidades de apagamento completo e apagamento seletivo do Intune. Os usuários também podem apagar remotamente seus dispositivos de propriedade pessoal que registraram para gerenciamento no Portal da Empresa do Intune.

Em vez de fazer um [apagamento completo](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#full-wipe) que restaura um dispositivo para as configurações padrão de fábrica e remove dados e configurações do usuário, você pode usar a funcionalidade de [apagamento seletivo](https://docs.microsoft.com/intune/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune#selective-wipe) para remover somente os dados da empresa do dispositivo, deixando os dados pessoais do usuário intactos.

Executar um apagamento seletivo em um dispositivo é muito fácil, basta clicar com o botão direito do mouse no nome do dispositivo, selecionar **Desativar/Apagar** e **Apagar seletivamente o dispositivo**:

![Imagem das opções de apagamento seletivo no console do Intune](..\Solutions\media\protect-office365-data-with-intune\protect-office365-data-with-intune-fig6.png)

Depois de iniciado, o dispositivo iniciará imediatamente o processo de apagamento seletivo para ser removido do gerenciamento. Quando o processo for concluído, todos os dados da empresa serão excluídos e o nome do dispositivo será removido do console do administrador do Intune, concluindo o ciclo de vida de gerenciamento do dispositivo.

### <a name="learn-more"></a>Saiba mais
[Começar a usar o Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
