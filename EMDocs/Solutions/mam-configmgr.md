---
title: "Usando políticas de gerenciamento de aplicativos móveis no Configuration Manager"
description: "Crie e implante um aplicativo no Configuration Manager com uma política de MAM (gerenciamento do aplicativo móvel)."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74288276-84d3-4d24-8307-7875491be9c9
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: d0bc5fb61b481256d816df7c898ade798379aa19


---

# <a name="use-mobile-app-management-policies-in-configuration-manager"></a>Usar políticas de gerenciamento de aplicativos móveis no Configuration Manager
Começando com o System Center 2012 Configuration Manager SP2, as políticas de gerenciamento de aplicativos permitem mudar a funcionalidade dos aplicativos implantados para ajudar a alinhá-los com as políticas de conformidade e segurança de sua empresa. Por exemplo, você pode restringir as operações de recortar, copiar e colar em um aplicativo restrito, ou configurar um aplicativo para abrir todos os links da web dentro do navegador gerenciado. As políticas de gerenciamento de aplicativos dão suporte a:

- Dispositivos que executam o Android 4 e posterior.
- Dispositivos que executam o iOS 7 e posterior.

> [!TIP]
> Além dos dispositivos gerenciados, políticas de MAM (gerenciamento de aplicativo móvel) podem ser usadas para proteger aplicativos em dispositivos que não são gerenciados pelo Intune. Usando essa nova funcionalidade, você pode aplicar políticas de gerenciamento de aplicativo móvel para aplicativos conectados aos serviços do Office 365. Isso não tem suporte em aplicativos que se conectam ao Exchange ou SharePoint local.
Para usar essa nova funcionalidade, você deve usar o portal do Azure. Os seguintes tópicos podem ajudá-lo a começar:
- [Preparar-se para configurar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)
- [Criar e implantar políticas de gerenciamento de aplicativo móvel com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

Ao contrário dos itens de configuração e das linhas de base no Configuration Manager, uma política de gerenciamento de aplicativos não é implantada diretamente. Em vez disso, associe a política ao DT (tipo de implantação) do aplicativo que deseja restringir. Quando o DT do aplicativo for implantado e instalado nos dispositivos, as configurações especificadas terão efeito.

Para aplicar restrições a um aplicativo, o aplicativo deve incorporar o SDK (Software Development Kit) do aplicativo Microsoft Intune. Há dois métodos de obter esse tipo de aplicativo:

- **Usar um aplicativo gerenciado por política** (Android e iOS): tem o SDK do aplicativo inserido. Para adicionar este tipo de aplicativo, especifique um link para o aplicativo de uma loja de aplicativos, como a iTunes Store ou o Google Play. Nenhum processamento adicional é necessário para este tipo de aplicativo. Para obter uma lista dos aplicativos gerenciados pela política que estão disponíveis para dispositivos iOS e Android, veja [Galeria de aplicativos móveis do Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
- **Usar um aplicativo "encapsulado"** (Android e iOS): aplicativos que são empacotados novamente para incluir o SDK do aplicativo usando a Ferramenta de disposição de aplicativos do Microsoft Intune. Normalmente, essa ferramenta é usada para processar aplicativos da empresa criados internamente. Ele não pode ser usado para processar aplicativos que foram baixados da loja de aplicativos. Consulte [Preparar aplicativos iOS para o gerenciamento de aplicativos móveis com a Ferramenta de Disposição de Aplicativo do Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) e [Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de Disposição do Aplicativo do Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool).

## <a name="create-and-deploy-an-app-in-configuration-manager-with-a-mobile-app-management-policy"></a>Criar e implantar um aplicativo no Configuration Manager com uma política de gerenciamento do aplicativo móvel

- Etapa 1: obter o link para um aplicativo gerenciado por política ou criar um aplicativo encapsulado.
- Etapa 2: criar um aplicativo do Configuration Manager contendo um aplicativo.
- Etapa 3: criar uma política de gerenciamento de aplicativos móveis.
- Etapa 4: associar a política de gerenciamento de aplicativo a um tipo de implantação.
- Etapa 5: monitorar a implantação do aplicativo.

### <a name="step-1-obtain-the-link-to-a-policy-managed-app-or-create-a-wrapped-app"></a>Etapa 1: obter o link para um aplicativo gerenciado por política ou criar um aplicativo encapsulado.
- **Para obter um link para um aplicativo gerenciado por política** - na Windows Store, encontre e anote a URL do aplicativo gerenciado por política que você deseja implantar.
Por exemplo, a URL do aplicativo do Microsoft Word para iPad é [https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8](https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8)
- **Para criar um aplicativo encapsulado**: use as informações nos tópicos [Preparar aplicativos iOS para o gerenciamento de aplicativos móveis com a Ferramenta de Disposição do Aplicativo do Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) e [Preparar aplicativos Android para o gerenciamento de aplicativos móveis com a Ferramenta de Disposição do Aplicativo do Intune](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool) para criar um aplicativo encapsulado. A ferramenta cria um aplicativo processado e um arquivo de manifesto associado. Você usará esses arquivos ao criar um aplicativo do Configuration Manager que contém o aplicativo.

### <a name="step-2-create-a-configuration-manager-application-that-contains-an-app"></a>Etapa 2: criar um aplicativo do Configuration Manager contendo um aplicativo.
O procedimento para criar o aplicativo do Configuration Manager é diferente, dependendo se você estiver usando um aplicativo gerenciado por política (link externo) ou um aplicativo que foi criado com a Ferramenta de Encapsulamento de Aplicativos do Microsoft App para iOS (pacote do aplicativo para iOS).

Veja [Como controlar aplicativos usando políticas de gerenciamento de aplicativos móveis no Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396#BKMK_Step2) para obter as etapas completas necessárias para criar um aplicativo do Configuration Manager que contém um aplicativo.

Depois que você criar o aplicativo, ele é exibido no nó **Aplicativos** do espaço de trabalho **Biblioteca de Software**.

### <a name="step-3-create-a-mobile-application-management-policy"></a>Etapa 3: criar uma política de gerenciamento de aplicativos móveis.
Em seguida, [crie uma política de gerenciamento de aplicativos](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396#bkmk_step3) que você associará ao aplicativo. É possível criar uma política geral ou de navegador gerenciado.

Depois que você criar a nova política, ela é exibida no nó **Políticas de Gerenciamento de Aplicativos** no espaço de trabalho **Biblioteca de Software**.

### <a name="step-4-associate-the-app-management-policy-with-a-deployment-type"></a>Etapa 4: associar a política de gerenciamento de aplicativo a um tipo de implantação.
Quando um tipo de implantação é criado para um aplicativo que exige uma política de gerenciamento de aplicativos, o Configuration Manager reconhecerá que uma política de gerenciamento de aplicativos deve ser vinculada a este tipo de implantação quando o aplicativo associado é implantado e solicitará que você associe uma política de gerenciamento de aplicativos. Para o Managed Browser, você precisará associar uma política Geral e uma política do Managed Browser. Para saber mais, veja [Como criar e implantar aplicativos para dispositivos móveis no Configuration Manager](https://technet.microsoft.com/library/dn469410.aspx).

> [!TIP]
> Para dispositivos que executam sistemas operacionais anteriores ao iOS 7.1, as políticas associadas não serão removidas quando o aplicativo for desinstalado.

> Se o dispositivo tiver seu registro no Configuration Manager cancelado, as políticas não serão removidas dos aplicativos. Os aplicativos que tinham políticas aplicadas manterão as configurações de política, mesmo depois que o aplicativo é desinstalado e reinstalado.


### <a name="step-5-monitor-the-app-deployment"></a>Etapa 5: monitorar a implantação do aplicativo.
Depois de criar e implantar um aplicativo associado a uma política de MAM, é possível [monitorar o aplicativo e resolver conflitos de política](https://technet.microsoft.com/library/mt131414.aspx?f=255&MSPPError=-2147217396#BKMK_Step5).

Para obter informações gerais sobre como monitorar aplicativos, veja [Como monitorar aplicativos no Configuration Manager](https://technet.microsoft.com/library/gg682201.aspx).

## <a name="where-to-go-from-here"></a>Onde ir daqui

Depois de criar e implantar um aplicativo associado a uma política de MAM, você pode saber mais sobre o [experiência do usuário final de MAM](end-user-experience-mam.md). Isso ajudará a se preparar para problemas que possam surgir.



<!--HONumber=Jan17_HO2-->


