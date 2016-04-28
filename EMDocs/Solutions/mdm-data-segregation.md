---
# required metadata

title: Diferenciação de dados
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 50bd37fe-30b5-4a45-9c36-0b907dd13cc2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Diferenciação de dados

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

A diferenciação de dados é importante, não apenas para a sua organização, mas também para manter a privacidade das informações pessoais do usuário. A diferenciação de dados ajuda a remover todos os aplicativos e dados da empresa de um dispositivo que pertence a um usuário, sem afetar os dados pessoais do usuário (veja a figura abaixo):

![Diferenciação de dados](./media/MDM_Figure_10.png)

## Os dados pessoais do usuário são isolados dos dados da empresa

Ao manter separados todos os aplicativos, dados da empresa e políticas que foram implantadas pela solução de MDM, eles podem ser removidos do dispositivo, se necessário, sem afetar o conteúdo e aplicativos pessoais do usuário usando o apagamento seletivo. 

>[!TIP]Leia [Ajudar a proteger seus dados com apagamento remoto, bloqueio remoto ou redefinição de senha com o Microsoft Intune](/intune/deployuse/help-protect-your-data-with-remote-wipe,-remote-lock,-or-passcode-reset-using-microsoft-intune) para saber mais sobre como o apagamento remoto se comportará em outras plataformas como iOS e Android. 

O apagamento seletivo para o gerenciamento de dados de dispositivos móveis está incluído no Windows Server 2012 R2 e Windows 8.1. Ele funciona por meio da vinculação de recursos que ajudam os administradores do Exchange Server e do Microsoft Intune a gerenciar dados corporativos em dispositivos e a desenvolver aplicativos que possam usar os recursos de [Apagamento Seletivo do Windows](https://technet.microsoft.com/library/dn486874.aspx).  O Windows Phone 8 e mais recentes dão suporte à separação de dados no armazenamento interno.

![Diferenciação de dados](./media/MDM_Figure_11.png)

Leia mais sobre os recursos de segurança do Windows Phone 8.1 baixando a [Visão geral de segurança do Windows Phone 8.1](http://www.microsoft.com/download/details.aspx?id=42509).

A diferenciação de dados pode ser um desafio se os usuários alternam entre contas pessoais e contas corporativas em seus dispositivos móveis. Em um cenário BYOD, é comum que os usuários usem várias credenciais para executar diferentes tarefas em seus dispositivos. 

A EDP (Proteção de Dados Empresariais) fornece a separação de dados, mas não usa contêineres nem exige uma versão especial de um aplicativo para acessar os dados corporativos, e uma segunda instância dele para acessar dados pessoais. Não há contêineres, partições ou pastas especiais para separar fisicamente os dados pessoais e corporativos. Em vez disso, o Windows 10 Mobile é o agente de controle de acesso, identificando dados empresariais, pois estão criptografados para a empresa. 

A EDP oferece a separação de dados por meio de criptografia de dados empresariais. Leia [Visão geral da EDP (Proteção de Dados Empresariais)](https://technet.microsoft.com/library/dn985838.aspx) para saber mais. As políticas de EDP do Intune gerenciarão a lista de aplicativos protegidos pela EDP, locais de rede da empresa, nível de proteção e configurações de criptografia.

Quando um usuário instala e entra em um aplicativo que dá suporte a várias identidades em um dispositivo gerenciado pelo Intune, como o Outlook, o Intune verifica se a conta que está sendo usada corresponde à conta gerenciada no dispositivo. Se a conta for gerenciada e também houver uma política para o aplicativo e o usuário, as configurações da política protegerão os dados nessa conta. Quando o usuário adiciona contas pessoais ao aplicativo, essas contas ficam fora do gerenciamento e da proteção do Intune. Isso permite o uso pessoal do aplicativo sem comprometer a proteção corporativa. Leia [Proteger dados usando políticas de gerenciamento de aplicativos móveis com o Microsoft Intune](/intune/deployuse/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) para saber mais sobre a funcionalidade de várias identidade no Intune. 

A tabela abaixo compara os recursos de apagamento seletivo disponíveis em diferentes soluções de MDM para ajudar você a escolher a solução de MDM que melhor atende aos requisitos de diferenciação de dados de sua organização.

## Intune (autônomo)

**Vantagens**

- Permite executar apagamentos seletivos para remover apenas os dados da empresa localizados nos dispositivos móveis
- Permite que você execute redefinições de fábrica e apague por completo dispositivos móveis
- Suporte para aplicativos de várias identidades

**Desvantagens**

- Não inclui a criptografia nativa para o armazenamento de dispositivo móvel
- A falta de integração com a atual plataforma de MDM local significa uma interface de gerenciamento adicional para você usar

## Office 365 com MDM

**Vantagens**

- Permite executar redefinições de fábrica e apagamento completo de dispositivos iOS, Android e Windows Phone
- Permite executar apagamentos seletivos em dispositivos com Android, Windows Phone e iOS para remover apenas os dados da empresa dos dispositivos móveis

**Desvantagens**

- A falta de integração com a atual plataforma de MDM local significa uma interface de gerenciamento adicional para você usar

## Híbrido (Intune com ConfigMgr)

**Vantagens**

- Permite executar apagamentos seletivos para remover apenas os dados da empresa dos dispositivos móveis
- Permite que você execute redefinições de fábrica e apague por completo dispositivos móveis
- Suporte para aplicativos de várias identidades
- Um único console de gerenciamento para gerenciar dispositivos móveis locais e baseados em nuvem

**Desvantagens**

- Se a organização não tiver uma infraestrutura local do ConfigMgr atual, será necessário planejar, instalar e configurar essa plataforma antes da integração

Não deixe de ler o artigo [Ajudar a proteger seus dados com apagamento remoto, bloqueio remoto ou redefinição de senha com Microsoft Intune](/intune/deployuse/help-protect-your-data-with-remote-wipe,-remote-lock,-or-passcode-reset-using-microsoft-intune) para entender como os dados são removidos e mantidos após um apagamento seletivo para cada plataforma de dispositivo móvel. Se você tiver um ambiente híbrido, confira o artigo [Como apagar dispositivos móveis remotamente usando o Configuration Manager](https://technet.microsoft.com/library/dn956981.aspx) para entender como o ConfigMgr pode ser usado para realizar essa tarefa.

<!--HONumber=Apr16_HO2-->


