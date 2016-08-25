---
title: "Usando Políticas de Gerenciamento de Aplicativos Móveis no Intune"
description: "Crie e implante um aplicativo no Intune com uma política de gerenciamento de aplicativos móveis."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 05/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 6d7c4104-b85f-407e-8832-0e6bbac934f5
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 55a3dbe32e3b5e10e21a6d99bc101ec76fc51f5e
ms.openlocfilehash: 9f97f1090792064ee909ff27f81e01957fb07964


---

# Usar Políticas de Gerenciamento de Aplicativos Móveis no Intune
Um dos motivos principais pelos quais muitas empresas usam o Microsoft Intune é implantar aplicativos que os usuários precisam para realizar seu trabalho. Antes de implantar aplicativos, você precisará [tornar seus dispositivos gerenciados](https://docs.microsoft.com/intune/deploy-use/enroll-devices-in-microsoft-intune).

Por exemplo, se sua empresa usa o Microsoft Word, há versões disponíveis para Windows, iOS, Android e outros. O desafio que você como um administrador de TI enfrenta é gerenciar a variedade de aplicativos disponíveis, em muitas plataformas diferentes de computador e de dispositivo com o objetivo de permitir que os usuários façam seu trabalho e, simultaneamente, garantir a segurança dos seus dados corporativos.

Se estiver usando o Intune com o Configuration Manager, consulte [How to Control Apps Using Mobile Application Management Policies in Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396) (Como controlar aplicativos usando políticas de gerenciamento de aplicativos móveis no Configuration Manager).

As políticas de MAM (gerenciamento de aplicativos móveis) dão suporte a:
- Dispositivos que executam o Android 4 e posterior.
- Dispositivos que executam o iOS 7 e posterior.

> [!NOTE]
> As políticas de MAM dão suporte a dispositivos registrados com o Intune. Para saber mais sobre como criar políticas de gerenciamento de aplicativos para dispositivos que não são gerenciados pelo Intune, veja [Proteger os dados do aplicativo usando políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).

Diferente de outras políticas do Intune, você não implanta uma política de MAM diretamente. Em vez disso, você associa a política ao aplicativo que deseja restringir. Quando o aplicativo é implantado e instalado em dispositivos, as configurações especificadas entrarão em vigor.

Para aplicar restrições a um aplicativo, o aplicativo deve incorporar o SDK (Software Development Kit) do aplicativo Microsoft Intune. Há dois métodos de obter esse tipo de aplicativo:

- **Usar um aplicativo gerenciado por política** – tem o SDK interno do aplicativo. Para adicionar este tipo de aplicativo, especifique um link para o aplicativo de uma loja de aplicativos, como a iTunes Store ou o Google Play. Nenhum processamento adicional é necessário para este tipo de aplicativo. Para ver a lista completa de aplicativos da Microsoft com suporte, vá para a galeria de aplicativos móveis do Microsoft Intune na página de [parceiros de aplicativos do Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners). Clique no aplicativo para ver os cenários e plataformas com suporte e se o aplicativo dá suporte a várias identidades ou não.
- **Usar um aplicativo "encapsulado"** – aplicativos que são empacotados novamente para incluir o SDK do aplicativo usando a Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune. Normalmente, essa ferramenta é usada para processar aplicativos da empresa criados internamente. Ele não pode ser usado para processar aplicativos que foram baixados da loja de aplicativos. Consulte:
  - [Preparar aplicativos iOS para o gerenciamento de aplicativos móveis com a Ferramenta de disposição de aplicativos do Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
  - [Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

Alguns aplicativos gerenciados, como o aplicativo do Outlook para iOS e Android, dão suporte a **multi-identidade**. Isso significa que Intune aplica as configurações de gerenciamento somente a dados ou contas corporativas no aplicativo.

Por exemplo, usando o aplicativo do Outlook:
- Se o usuário configurar uma conta de email pessoal e uma corporativa, o Intune aplicará as configurações de gerenciamento apenas à conta corporativa e não gerencia a conta pessoal.
- Se o dispositivo for desativado ou seu registrado cancelado, somente os dados corporativos do Outlook serão removidos do dispositivo.
- A conta corporativa usada deve ser a mesma conta que foi usada para registrar o dispositivo no Intune.

Word, Excel e PowerPoint também dão suporte a várias identidades, exceto as restrições de política que se aplicam somente ao gerenciar e editar dados de identificação empresarial de um serviço, como OneDrive ou SharePoint.

## Criar e implantar um aplicativo no Intune com uma política de gerenciamento de aplicativos móveis

- Etapa 1: obter o link para um aplicativo gerenciado por política ou criar um aplicativo encapsulado.
- Etapa 2: publicar o aplicativo em seu espaço de armazenamento de nuvem.
- Etapa 3: criar uma política de gerenciamento de aplicativos móveis.
- Etapa 4: implantar o aplicativo, selecionando a opção para associar o aplicativo a uma política de gerenciamento de aplicativos móveis.
- Etapa 5: monitorar a implantação do aplicativo.

### Etapa 1: obter o link para um aplicativo gerenciado por política ou criar um aplicativo encapsulado
- **Para obter um link para um aplicativo gerenciado por política** - na Windows Store, encontre e anote a URL do aplicativo gerenciado por política que você deseja implantar.
Por exemplo, a URL do aplicativo do Microsoft Word para iPad é [https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8](https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8)
- **Para criar um aplicativo encapsulado**: use as informações nos tópicos [Preparar aplicativos iOS para o gerenciamento de aplicativos móveis com a Ferramenta de Disposição do Aplicativo do Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) e [Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de Disposição do Aplicativo do Intune](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) para criar um aplicativo encapsulado. A ferramenta cria um aplicativo processado que será usado quando você publica o aplicativo no espaço de armazenamento de nuvem.

### Etapa 2: Carregar o aplicativo em seu espaço de armazenamento de nuvem
Quando você publica um aplicativo gerenciado, os procedimentos diferem se você estiver publicando um aplicativo gerenciado por política ou um aplicativo que foi processado usando a ferramenta de disposição de aplicativos do Microsoft Intune para iOS.

Veja [Adicionar aplicativos para dispositivos móveis no Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune#add-the-app) para obter as etapas completas necessárias para carregar um aplicativo em seu espaço de armazenamento de nuvem.

### Etapa 3: criar uma política de gerenciamento de aplicativos móveis
O portal do Azure é o console de administração recomendado para criar políticas de MAM. O portal do Azure dá suporte aos seguintes cenários MAM:
- Dispositivos registrados no Intune
- Dispositivos gerenciados por uma solução MDM terceirizada
- Dispositivos que não são gerenciados por uma solução MDM (BYOD).

Veja [Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) para saber mais sobre o uso do portal do Azure para criar uma política de MAM.

Se no momento você estiver usando o console de administração do Intune para gerenciar seus dispositivos, poderá criar uma política MAM que dê suporte a aplicativos para dispositivos registrados no Intune usando o [Console de administração do Intune](https://docs.microsoft.com/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console#-step-3-create-a-mobile-application-management-policy).


### Etapa 4: implantar o aplicativo, selecionando a opção para associar o aplicativo a uma política de gerenciamento de aplicativos móveis
Se você estiver usando o portal do Azure, [implante a política de MAM para usuários](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune#deploy-a-policy-to-users).

Se você estiver usando o portal do Intune, [implante o aplicativo](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune#deploy-an-app), garantindo que você selecione a política de gerenciamento de aplicativo móvel na página de Gerenciamento de Aplicativo Móvel para associar a política ao aplicativo.

Se o dispositivo tiver o registro no Intune desfeito, as políticas não serão removidas dos aplicativos. Quaisquer aplicativos que tiverem políticas aplicadas manterão as configurações de política, mesmo depois de ser desinstalado e reinstalado.

#### O que fazer quando um aplicativo já está implantado em dispositivos

Pode haver situações em que você implantar um aplicativo e um dos usuários ou dispositivos de destino já tem uma versão não gerenciada do aplicativo instalada, por exemplo, o usuário instalou o Microsoft Word da loja de aplicativos.

Nesse caso, você deve pedir ao usuário para desinstalar manualmente a versão não gerenciada para que possa ser instalada a versão gerenciada que você configurou.

No entanto, para dispositivos que executam o iOS 9 e versões posteriores, o Intune automaticamente solicitará ao usuário permissão para assumir o gerenciamento do aplicativo existente. Se eles concordarem, o aplicativo será gerenciado pelo Intune e qualquer política de MAM associada ao aplicativo também será aplicada.


### Etapa 5: monitorar a implantação do aplicativo com a política de MAM
Use os procedimentos a seguir para monitorar a implantação do aplicativo por meio do console do Intune e resolver conflitos de política.

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Grupos**.
2. Execute uma das seguintes etapas:
  -  Clique em **Todos os Usuários** e clique duas vezes no usuário cujos dispositivos você deseja examinar. Na página Propriedades do Usuário, clique em **Dispositivos** e clique duas vezes no dispositivo que você deseja examinar.
  -  Clique em **Todos os Dispositivos > Todos os Dispositivos Móveis**. Na página Propriedades do Grupo de Dispositivos, clique em **Dispositivos** e clique duas vezes no dispositivo que você deseja examinar.
3. Na página Propriedades do Dispositivo Móvel, clique em **Política** para ver uma lista das políticas de MAM que foram implantados no dispositivo.
4. Selecione a política de MAM cujo status você deseja exibir. Você pode ver detalhes da política no painel inferior e expandir o nó para exibir as configurações.
5.  Na coluna Status de cada uma das políticas de MAM, Compatível, Compatível (Pendente)ou Erro será exibido. Se a política selecionada tiver uma ou mais configurações conflitantes, Erro será exibido nesse campo.
6.  Após ter identificado um conflito, você pode revisar as configurações de política conflitantes para usar a mesma configuração ou implantar apenas uma política para o aplicativo e o usuário.

> [!NOTE]
> Você pode saber mais informações gerais sobre monitoramento de aplicativos por meio do [portal do Azure](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune) ou usando o [console do Intune](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).

## Onde ir daqui

Depois de criar e implantar um aplicativo associado a uma política de MAM, você pode saber mais sobre o [experiência do usuário final de MAM](end-user-experience-mam.md). Isso ajudará a se preparar para problemas que possam surgir.



<!--HONumber=Aug16_HO1-->


