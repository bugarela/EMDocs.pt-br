---
title: Proteger dados da empresa usando MAM com MDM
description: "Crie e implante aplicativos com políticas de MAM (gerenciamento de aplicativos móveis) para proteger melhor os dados da empresa."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6c7088a9-ca88-4ff2-97a6-f842691fd3c7
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 88625a3bc5ac5f1a877650f73185721674e0f28d
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="protect-company-data-on-mobile-devices-through-app-management-policies"></a>Proteger os dados da empresa em dispositivos móveis por meio de políticas de gerenciamento de aplicativo
Proteger os dados da empresa é extremamente importante e é uma tarefa de cada vez mais desafiadora, conforme mais funcionários usam seus dispositivos móveis para acessar recursos da empresa, incluindo emails e anexos de email. Como administrador de TI, você deseja garantir que os dados da empresa permaneçam protegidos mesmo quando os dispositivos móveis não estiverem no local físico da empresa.

Este guia se concentra na habilitação de aplicativos gerenciados como ele se aplica às duas implantações do MDM do Intune:

- Como uma solução de gerenciamento de nuvem usando o Intune
- Como um serviço integrado com o Configuration Manager

Isso permite que você crie e implante aplicativos com políticas de MAM (gerenciamento de aplicativos móveis) para proteger melhor os dados da empresa.

Este documento se concentra na criação dessas políticas de MAM quando o dispositivo do usuário final é registrado no Intune para MDM. Veja [Proteger a linha de aplicativos de negócios e dados em dispositivos não registrados no Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune) para obter informações sobre como configurar essas políticas de MAM quando o dispositivo não estiver registrado no Intune para MDM.

> [!TIP]
> Baixe uma cópia deste tópico completo na [Galeria do TechNet](https://gallery.technet.microsoft.com/Protect-Company-Data-on-d972f4f4/file/154240/1/Protect%20Company%20Data%20on%20Mobile%20Devices%20through%20Application%20Management%20Policies.pdf).

## <a name="introduction"></a>Introdução
Aplicativos gerenciados são aplicativos que têm políticas de MAM aplicadas que os tornam compatíveis com os requisitos de segurança da sua empresa. Você tem duas opções para gerenciar aplicativos móveis:
- **A funcionalidade padrão**, como Apple Managed Open In, que protege os dados da empresa controlando os aplicativos que têm permissão para abrir certos documentos e anexos de email
- **O SDK de Aplicativo do Intune**, que permite limitar a funcionalidade e restringir o compartilhamento de dados para todos os aplicativos que têm o SDK de Aplicativo do Intune habilitado. Alguns dos principais recursos do SDK de Aplicativo do Intune é que ele permite:
  - Gerenciar a função de salvar como
  - Impedir cortar, copiar e colar
  - Exigir autenticação quando um aplicativo é acessado
  - Apagar dados da empresa de um aplicativo gerenciado pelo Intune

  Confira [Visão geral do SDK de aplicativo do Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk) para obter uma descrição de todos os recursos do SDK.

## <a name="before-you-begin"></a>Antes de começar
- **Saiba mais sobre a implantação de aplicativos usando o Microsoft Intune:**  [aprenda sobre](https://docs.microsoft.com/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) os conceitos básicos da implantação de aplicativos do Intune.

- **Avalie a implementação desejada:** com todas as opções diferentes de design e configuração para gerenciar dispositivos móveis, é difícil determinar qual combinação melhor atende às necessidades da sua empresa. O [Guia de considerações de design do Gerenciamento de dispositivo móvel](https://docs.microsoft.com/enterprise-mobility/Solutions/mdm-design-considerations-guide) ajuda você a entender os requisitos de design de gerenciamento de dispositivo móvel e detalha uma série de etapas e tarefas que você pode seguir para criar a solução mais adequada às necessidades de negócios e tecnologia da sua empresa.
- **Entenda a experiência do usuário final de alto nível:** depois que a solução é implementada, você poderá proteger dados em dispositivos caso a empresa os gerencie ou não. Basta implementar políticas de nível de aplicativo para poder restringir o acesso aos recursos da empresa e manter os dados dentro do alcance do seu departamento de TI.

   > [!NOTE]
   > A experiência do usuário final desta solução é descrita com mais detalhes no artigo [Experiência do usuário final](end-user-experience-mam.md).

- **Entenda o ciclo de vida do aplicativo:** assim como com o gerenciamento de dispositivos, os aplicativos têm um ciclo de vida que acompanha você da preparação à implantação, monitoramento, atualização e desativação. O Intune pode ajudá-lo em todos os estágios desse ciclo de vida. Para obter informações detalhadas sobre o ciclo de vida do aplicativo, confira [Visão geral do ciclo de vida do aplicativo](https://docs.microsoft.com/intune/deploy-use/overview-of-app-lifecycle-in-microsoft-intune).
- **Saiba mais sobre os aplicativos da Microsoft que você pode usar com políticas de MAM:** a página de [parceiros de aplicativos Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) contém as informações mais recentes sobre aplicativos da Microsoft e de outras empresas que você pode usar com as políticas de gerenciamento de aplicativos móveis.

  Use a Ferramenta de encapsulamento de aplicativos do Microsoft Intune para mudar o comportamento de aplicativos internamente e configurar as funcionalidades do aplicativo sem mudar seu código. Veja os tópicos a seguir para obter informações mais específicas:
 - [Preparar aplicativos iOS para o gerenciamento de aplicativo móvel com a Ferramenta de Disposição do Aplicativo do Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
 - [Preparar aplicativos Android para gerenciamento de aplicativos móveis com a Ferramenta de Encapsulamento de Aplicativos do Intune](https://docs.microsoft.com/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)

- **Entender como os conflitos da política são resolvidos:** quando houver um conflito de política de gerenciamento de aplicativo móvel na primeira implantação para o usuário ou dispositivo, o valor da configuração específica em conflito será removido da política implantada para o aplicativo e ele usará um valor de conflito interno (**mais restritivo** é o padrão).

  Quando houver um conflito de política de gerenciamento de aplicativo móvel em implantações posteriores ao aplicativo ou usuário, o valor da configuração específica em conflito não será atualizado na política de gerenciamento de aplicativos móveis implantada para o aplicativo e ele usará o valor existente para essa configuração.

  Em casos em que o dispositivo ou usuário receber duas políticas conflitantes, o comportamento a seguir se aplicará:
  - Se já tiver sido implantada uma política para o dispositivo, as configurações de política existentes não serão substituídas.
  - Se nenhuma política tiver sido implantada no dispositivo e duas configurações conflitantes forem implantadas, a configuração padrão integrada no dispositivo será usada.

## <a name="where-to-go-from-here"></a>Onde ir daqui
Agora que você está familiarizado com o processo geral de MAM, está pronto para [usar políticas de gerenciamento de aplicativos móveis no Intune](mam-intune.md) ou [usar políticas de gerenciamento de aplicativos móveis no Configuration Manager](mam-configmgr.md). Ou você pode ler sobre a [experiência do usuário final de políticas de MAM](end-user-experience-mam.md).
