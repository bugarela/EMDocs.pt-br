---
title: "Habilitar uma solução de dispositivo compartilhado de uso limitado| Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: angrobe
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d78e2b94-8ad3-4703-b7f0-db070288a20b
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: 66586ce378ab3faff29286bd032ac4099647494b
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="enable-a-limited-use-shared-device-solution-with-intune"></a>Habilitar uma solução de dispositivo compartilhado de uso limitado com o Intune
Às vezes, os funcionários precisam compartilhar dispositivos a fim de acessar aplicativos e dados da empresa para concluir uma tarefa básica a qual exige apenas configurações e aplicativos específicos. Isso ocorre normalmente em lojas de varejo, fábricas e setores de transporte. Outras vezes, não são os funcionários, mas os clientes que precisam acessar interativamente os recursos usando dispositivos acessíveis publicamente em locais como conferências, saguões de hotéis, escolas ou bibliotecas. Em alguns casos, talvez seja necessário apenas exibir uma apresentação automática ou fornecer informações estáticas para os transeuntes.

É possível executar o aplicativo em tela inteira, sem outras opções, a fim de fornecer uma experiência de usuário de quiosque segura e interativa, além de proteger os ativos de sua empresa das atividades suspeitas dos usuários. Essa capacidade permite que a TI forneça mais segurança junto com uma experiência personalizável que mantém os funcionários produtivos e atende às necessidades do cliente.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?
O EMS permite que você forneça funcionalidades e experiências que criam um local de trabalho produtivo e atenda às necessidades do cliente, em qualquer lugar. Se você estiver usando dispositivos iOS, Mac OS, Android ou Windows de propriedade da empresa, o Microsoft Intune poderá ajudar sua equipe a ser mais produtiva, dar informações aos seus clientes e manter a segurança dos dados da empresa.

### <a name="recommended-solution"></a>Solução recomendada
Com o Intune, você pode aproveitar as definições da política de configuração no modo de quiosque para dispositivos móveis com Android ou iOS e o acesso atribuído para telefones com Windows Mobile a fim de bloquear um dispositivo para que somente certos aplicativos ou recursos funcionem. As políticas de configuração do Intune são grupos de configurações que controlam os recursos nos dispositivos móveis e em computadores. Políticas são criadas usando modelos que contêm configurações recomendadas ou personalizadas e depois são implantadas em grupos de dispositivos ou de usuários. Por exemplo, você pode implantar políticas de configuração no modo de quiosque em dispositivos que permitem a execução apenas de um aplicativo gerenciado especificado por você, ou pode desabilitar os botões de volume em um dispositivo. Essas configurações podem ser usadas para um modelo de demonstração de um dispositivo ou um dispositivo que é dedicado a apenas uma função, como um dispositivo de ponto de venda.

### <a name="how-to-implement-this-solution"></a>Como implementar esta solução
O restante dessa solução está dividido nas seções a seguir, que mostram como configurar:
- **Modo de quiosque para iOS**. Esta seção mostra como bloquear dispositivos iOS usando as definições de política de configuração do Intune no modo de quiosque.
- **Modo de quiosque para Android**. Esta seção mostra como bloquear dispositivos Android usando as definições da política de configuração do Intune no modo de quiosque para dispositivos Samsung KNOX.
- **Políticas de acesso atribuídas ao Windows**. Esta seção descreve como o CSP (Provedor de serviços de configuração) EnterpriseAssignedAccess é usado para bloquear os dispositivos com Windows Mobile 10 a fim de fornecer uma experiência de Acesso Atribuído.

## <a name="kiosk-mode-for-ios"></a>Modo de quiosque para iOS
O Intune fornece várias configurações gerais internas que podem ser configuradas em dispositivos iOS, incluindo definições de configuração do modo de quiosque que permitem o bloqueio de dispositivos iOS gerenciados.  

Antes de configurar um dispositivo iOS (8.0 e posterior) para o modo de quiosque, você deve usar a [ferramenta Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) em um dispositivo Mac ou implantar um perfil de registro para [registrar dispositivos iOS que foram comprados por meio do programa DEP (Programa de Registro de Dispositivos) da Apple](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) a fim de colocar o dispositivo no modo supervisionado. Depois que fizer isso, implante as definições de configuração do modo de quiosque para controlar as configurações de aplicativo e do dispositivo usando uma política de configuração do Intune.

No console do administrador do Intune, basta navegar até o nó POLÍTICA do console de administração do Intune, depois acesse iOS, crie uma nova política **Configuração Geral de iOS (iOS 8.0 e posterior)** e defina as configurações do modo de quiosque. O mais importante dessas configurações é definir o aplicativo gerenciado que poderá ser executado quando o dispositivo for colocado no modo de quiosque.

![Configurações da política do modo de quiosque para iOS](..\Solutions\media\limited-use-devices\kiosk-mode-policy.png)

Você pode especificar um aplicativo gerenciado ou um aplicativo da Apple App Store, mas nenhum outro aplicativo poderá ser executado no dispositivo após a aplicação da política do modo de quiosque. Além disso, lembre-se de que, após a implantação, a política só terá efeito em dispositivos iOS no modo supervisionado.

> [!NOTE]
> Se o aplicativo que você especificar for instalado depois de implantar a política de configuração, ele não entrará no modo de quiosque até depois de ser reiniciado.

## <a name="kiosk-mode-for-android"></a>Modo de quiosque para Android
O bloqueio de dispositivos Android KNOX Standard (4.0 e posteriores) é realizado de uma forma parecida com a colocação dos dispositivos iOS no modo de quiosque. No console do administrador do Intune, navegue até o nó POLÍTICA, depois acesse Android, crie uma nova política **Configuração Geral (Android 4 e posterior, Samsung KNOX Standard 4.0 e posterior)** e defina as configurações do modo de quiosque.

Há menos configurações disponíveis em dispositivos Android KNOX, ainda assim, a mais importante é do aplicativo gerenciado que poderá ser executado no modo de quiosque. Não há suporte para aplicativos de armazenamento nesses dispositivos, e a política que você implantar será executada em qualquer dispositivo Samsung KNOX que a receba, incluindo dispositivos pessoais BYOD se você não tiver cuidado. Por esse motivo, implante as configurações do modo de quiosque em dispositivos Android somente para a pessoa que gerencia o registro em massa dos dispositivos de propriedade de sua empresa que precisam ser gerenciados como dispositivos de quiosque.

> [!NOTE]
> Se o aplicativo que você especificar for instalado depois de implantar a política de configuração, ele não entrará no modo de quiosque até depois de ser reiniciado.

## <a name="assigned-access-policies-for-windows"></a>Políticas de acesso atribuídas ao Windows
Os dispositivos com Windows Mobile 10 (versão 1511 e posterior) também podem ser configurados como dispositivos de quiosque, mas em vez de usar uma política de configuração geral, uma política de configuração personalizada do Windows é usada. Esses tipos de políticas permitem que você aproveite as [configurações de OMA-URI do Windows 10](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) para gerenciar as definições de configuração de dispositivo com o Intune.

> [!TIP]
> [CSPs (Provedores de serviço de configuração)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) expõem as definições de configuração de dispositivo OMR URI no Windows 10.

O [CSP EnterpriseAssignedAccess](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/enterpriseassignedaccess-csp) é usado para bloquear os dispositivos com Windows 10 para fornecer uma experiência de Acesso Atribuído. Também é possível usar esse CSP para definir outras configurações como linguagem, temas ou configurar layouts personalizados em um dispositivo.

Para criar a política para dispositivos com Windows, acesse o nó POLÍTICA do console de administração do Intune, depois acesse Windows, crie uma nova política **Configuração personalizada (Windows 10 Desktop e Mobile e posterior)**. A partir daí, você precisa fornecer as informações de CSP e importar um arquivo XML válido que define as configurações a serem aplicadas a dispositivos com Windows direcionados pela implantação dessa política.  

![Configurações de OMA-URI](..\Solutions\media\limited-use-devices\settings.png)

Para criar uma política de acesso atribuído simples, forneça os metadados básicos de nome, descrição, defina o tipo de dados como **String (XML)** e insira **./Vendor/MSFT/EnterpriseAssignedAccess/AssignedAccess/AssignedAccessXml** para o valor de OMA-URI que *diferencia maiúsculas e minúsculas*. No exemplo de .XML a seguir, o dispositivo será bloqueado para que somente os aplicativos especificados em uma Lista de permissões (Microsoft Edge, neste caso) estejam disponíveis para uso no dispositivo. Aplicativos não identificados por suas [IDs de produto de aplicativo do Windows 10 Mobile](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/customize/mdm/enterpriseassignedaccess-csp#productid) na lista de permissões permanecem instalados no dispositivo, mas ficam ocultos e não podem iniciar. Para inserir os dados .XML necessários, basta importar um novo arquivo .XML contendo as seguintes informações de exemplo, ou copiar e colá-lo como um XML formatado em uma linha para a área de texto **Valor**:


> [!IMPORTANT]
> Ao colar o exemplo de XML formatado fornecido na caixa de valores, certifique-se de que todo o XML esteja formatado em uma única linha.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<HandheldLockdown version="1.0">
   <Default>
      <ActionCenter enabled="false" />
      <Apps>
         <!-- Microsoft Edge -->
         <Application productId="{395589FB-5884-4709-B9DF-F7D558663FFD}" autoRun="true">
            <PinToStart>
               <Size>Medium</Size>
               <Location>
                  <LocationX>0</LocationX>
                  <LocationY>0</LocationY>
               </Location>
            </PinToStart>
         </Application>
      </Apps>
      <Buttons>
         <ButtonLockdownList>
            <!-- Lockdown all buttons -->
            <Button name="Search">
               <ButtonEvent name="Press" />
               <ButtonEvent name="PressAndHold" />
            </Button>
            <Button name="Camera">
               <ButtonEvent name="Press" />
               <ButtonEvent name="PressAndHold" />
            </Button>
         </ButtonLockdownList>
         <ButtonRemapList />
      </Buttons>
      <MenuItems>
         <DisableMenuItems />
      </MenuItems>
      <Settings>
         <System name="Microsoft.WiFi" />
         <System name="Microsoft.About" />
         <System name="Microsoft.Feedback" />
         <System name="Microsoft.CompanyAccount" />
         <System name="Microsoft.VPN" />
      </Settings>
      <StartScreenSize>Small</StartScreenSize>
   </Default>
</HandheldLockdown>

```
Após a criação da política, implante-a em um grupo de dispositivos com Windows que você deseja configurar como dispositivos de quiosque.

> [!IMPORTANT]
> Certifique-se de que a política de acesso atribuído seja implantada no grupo correto. Não é possível reverter uma política de acesso atribuído senão redefinindo o dispositivo para suas configurações de fábrica.

### <a name="learn-more"></a>Saiba mais
[Começar a usar o Enterprise Mobility + Security](https://docs.microsoft.com/enterprise-mobility/solutions/ems-get-started)

[Microsoft Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility)
