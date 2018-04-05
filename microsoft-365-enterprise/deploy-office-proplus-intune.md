---
title: Implantar o Office 365 ProPlus com o Microsoft Intune – Microsoft 365 Enterprise | Microsoft Docs
description: Descreve como implantar o Microsoft Office 365 ProPlus com o Microsoft Intune.
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/10/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: da8fb9ee62b458a3580abadb2a65a84110ac51a9
ms.sourcegitcommit: a322bdd365c7d648c5241cf959dcd04b3815672d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2018
---
# <a name="deploy-office-365-proplus-with-microsoft-intune"></a>Implantar Office 365 ProPlus com Microsoft Intune
O Microsoft 365 Enterprise é uma solução de local de trabalho moderna que permite que todos sejam criativos e trabalhem em conjunto de forma segura. As soluções do Microsoft 365 Enterprise são o resultado de uma estreita colaboração entre as equipes de EMS (Enterprise Mobility + Security), do Office 365 e do Windows 10. Essa colaboração leva a soluções inovadoras, como a capacidade de implantar aplicativos do Office 365 ProPlus em dispositivos Windows 10 com o Intune.

Agora é mais fácil do que nunca selecionar os aplicativos Office 365 ProPlus específicos (usando o Clique para Executar), implantá-los em dispositivos que executam o Atualização do Windows 10 para Criadores e exibir as métricas de implantação por meio do novo portal do Intune no Azure. Isso funciona bem com o Windows AutoPilot para deixar os dispositivos dos funcionários prontos para o trabalho fornecendo apenas credenciais da empresa durante a OOBE (configuração inicial pelo usuário) enquanto o Azure AD e o Intune trabalham em conjunto em segundo plano para registrar o dispositivo, implantar as configurações necessárias e agora também instalar os aplicativos do Office 365 ProPlus.

![Simplificar o gerenciamento do Windows 10 e reduzir o TCO com o EMS](./media/deploy-office-proplus-intune/windows-10-management-ems.png)

Você pode [baixar este infográfico aqui](https://gallery.technet.microsoft.com/Infographic-Simplify-37e77674).

## <a name="deploy-office-365-proplus-with-intune"></a>Implantar o Office 365 ProPlus com Intune
Vamos analisar como você pode configurar uma implantação do Office 365 ProPlus com o Intune.

Por meio do novo portal do Intune, tornamos fácil adicionar e personalizar as implantações do Office 365 ProPlus. Depois de escolher o tipo de aplicativo do **pacote do Office 365 ProPlus (Windows 10)**, você pode personalizar a implantação de aplicativos do Office em três etapas simples.

Primeiro, escolha os aplicativos que você deseja instalar em dispositivos de usuário final:

![Escolha os aplicativos para implantar](./media/deploy-office-proplus-intune/Configure-App-Suite.png)

Em seguida, configure as informações do pacote de aplicativos. Por exemplo, você pode adicionar uma descrição breve de quais aplicativos estão no pacote a ser exibido no Portal da Empresa do Intune:

![Configurar informações de pacote de aplicativos](./media/deploy-office-proplus-intune/App-Suite-Information.png)

Por fim, defina algumas configurações de instalação, como a arquitetura do sistema ou o canal de atualização:

![Definir as configurações de instalação](./media/deploy-office-proplus-intune/App-Suite-Settings.png)

Os usuários finais podem instalar aplicativos do Office por meio do Portal da Empresa do Intune se você os disponibilizou. Caso contrário, os usuários simplesmente desfrutam de uma instalação silenciosa. Depois que o Office é instalado em seus dispositivos, os usuários podem entrar, ativar o produto e experimentar os recursos mais recentes como [O Office é mantido atualizado automaticamente pelo serviço](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).

> [!NOTE]
> Atualmente, essa forma de implantação do Office 365 ProPlus tem suporte apenas para dispositivos sem uma versão existente do Office instalado. Para dispositivos com versões existentes do Office, é recomendável remover todas as versões do Office antes do registro. Estamos trabalhando com as equipes do Windows e do Office em aperfeiçoamentos futuros para dar suporte a dispositivos com as implantações existentes do Office.

## <a name="learn-more"></a>Saiba mais
Para obter instruções passo a passo, consulte [Implantar aplicativos do Office 365 para Windows 10 com o Intune](https://docs.microsoft.com/intune/apps-add-office365).
