---
title: "Proteção de dispositivos móveis"
description: "Este artigo fornece um conjunto de considerações de design para proteger dispositivos móveis em um cenário de gerenciamento de dispositivo móvel."
keywords: 
author: YuriDio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ade57c73-a8a2-497f-ad8d-5dfc3cba9e70
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 050d92824ad2616440d9d4b972a812be0ab5a14a
ms.contentlocale: pt-br
ms.lasthandoff: 11/28/2016


---

# <a name="hardening-mobile-devices"></a>Proteção de dispositivos móveis

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Ao criar uma linha de base de configuração para dispositivos móveis para proteger seus recursos de acordo com suas necessidades de negócios, certifique-se de que você está conciliando a usabilidade e a segurança. Um modelo de proteção muito estrita pode causar problemas de usabilidade e acesso para seus funcionários, o que contraria o objetivo de ajudar os usuários a serem produtivos acessando os recursos da empresa com seus dispositivos.

Além disso, tenha em mente que nem todas as políticas de segurança estão disponíveis para todas as plataformas de dispositivo móvel. Talvez seja necessário conciliar as prioridades para permitir as plataformas de dispositivos móveis em sua organização e os requisitos de conformidade de segurança para a proteção dos dispositivos.
Uma maneira de abordar a proteção do dispositivo móvel é ter diferentes camadas de segurança. As configurações que estão disponíveis para cada camada também podem variar, dependendo da solução de MDM. A figura abaixo mostra um exemplo de como essa abordagem em camadas pode ser configurada.

![Camadas de segurança](./media/MDM_Figure_12.png)

## <a name="different-areas-of-mobile-device-hardening"></a>Diferentes áreas de proteção do dispositivo móvel

Cada camada pode ser usada para agrupar áreas que devem ser compatíveis com os requisitos de segurança de sua empresa. Por exemplo, você pode configurar o Intune para implantar [políticas de segurança](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) para dispositivos que são específicas para proteger configurações do sistema e habilitar a criptografia. As políticas também ajudam a garantir que apenas os [aplicativos compatíveis](https://technet.microsoft.com/library/dn818906.aspx) estejam disponíveis para instalação em dispositivos móveis por meio da criação de uma lista de permissões de acesso.

Em dispositivos BYOD executando o Windows 8.1 Enterprise, o AppLocker possibilita que você bloqueie ou permita um aplicativo com base em seu caminho de arquivo, hash ou propriedades que persistem nas atualizações do aplicativo (por exemplo, nome do editor, nome do produto, nome de arquivo e versão do arquivo). No Windows 10, um novo provedor de serviço de configuração do AppLocker foi adicionado a fim de permitir que você habilite as regras de AppLocker usando um servidor de MDM. Leia [AppLocker CSP](https://msdn.microsoft.com/library/windows/hardware/dn920019(v=vs.85).aspx) para saber mais sobre esse novo recurso no Windows 10.

Outra área que deve ser controlada é a experiência de navegação móvel dos usuários. Uma política de navegador gerenciado inclui uma lista de permissão ou bloqueio que restringe os sites que podem ser visitados pelos usuários do navegador gerenciado. Leia [Gerenciar o acesso à Internet usando políticas de navegador gerenciado com o Microsoft Intune](/intune/deploy-use/manage-internet-access-using-managed-browser-policies) para obter mais informações sobre como configurar essas políticas no Intune.

Em um ambiente híbrido com o ConfigMgr local, você pode criar um [linha de base de configuração](https://technet.microsoft.com/library/gg712268.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT) para definir um estado de proteção básica para dispositivos móveis gerenciados. Você pode personalizar essa linha de base para incluir todas as configurações necessárias, e implantá-la em seus dispositivos móveis. As opções de configurações de conformidade variam de acordo com a plataforma do dispositivo móvel, portanto leia [Configurações de conformidade para dispositivos móveis no Configuration Manager](https://technet.microsoft.com/library/dn376523.aspx) para saber mais sobre as opções disponíveis para cada dispositivo.

O [MDM para o Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicy.aspx) também tem um conjunto de recursos para ajudá-lo na proteção de dispositivos móveis para as seguintes categorias:

- Segurança 
- Criptografia
- Com jailbreak
- Perfil de email gerenciado

Leia o artigo [Recursos de gerenciamento interno de dispositivos móveis para o Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx) para saber mais sobre como configurar as políticas de segurança para aplicação dessas opções.

A proteção da plataforma de dispositivo móvel desempenha um papel importante em manter os dados da empresa protegidos, ao mesmo tempo que permite que os usuários usem seus dispositivos móveis sem comprometer a segurança. Use a tabela abaixo como referência para ajudar com a escolha da opção de MDM que melhor atenda aos requisitos de proteção de dados de sua organização.

## <a name="intune-standalone"></a>Intune (autônomo)

**Vantagens**

- Permite que você aplique políticas para dispositivos registrados: criptografia, malware, aplicativos, emails, perfil de email, jailbrake, sistema e segurança
- Dá suporte à implantação de política para as principais plataformas de dispositivo móvel, incluindo (Android, iOS, Windows 10, Windows 8.x e Windows Phone)

**Desvantagens**

- A falta de integração com a atual plataforma de MDM local introduzirá uma interface de gerenciamento adicional para você usar ao gerenciar dispositivos móveis
- Algumas políticas podem não estar disponíveis para algumas plataformas móveis

## <a name="mdm-for-office-365"></a>MDM para o Office 365

**Vantagens**

- Permite a aplicação de políticas para dispositivos registrados: criptografia, aplicativos, jailbrake e segurança
- Dá suporte à implantação de política para as principais plataformas de dispositivo móvel, incluindo (Android, iOS, Windows 10, Windows 8.x e Windows Phone)

**Desvantagens**

- A falta de integração com a atual plataforma de MDM local introduzirá uma interface de gerenciamento adicional para você usar ao gerenciar dispositivos móveis
- Algumas políticas podem não estar disponíveis para algumas plataformas móveis
- Não permite tanta granularidade quanto o Intune

## <a name="hybrid-intune-with-configmgr"></a>Híbrido (Intune com ConfigMgr)

**Vantagens**

- Permite que você aplique políticas para dispositivos registrados: criptografia, malware, aplicativos, emails, sistema, segurança e jailbrake
- Dá suporte à implantação de política para as principais plataformas de dispositivo móvel, incluindo (Android, iOS, Windows 10, Windows 8.x e Windows Phone)
- Um único console de gerenciamento para os dispositivos móveis registrados de dispositivos locais e na nuvem

**Desvantagens**

- Se a sua empresa não tiver uma atual infraestrutura local do ConfigMgr, ela precisará de recursos para planejar, instalar e configurar o ConfigMgr antes da integração

>[!TIP]
> Leia mais sobre as configurações do gerenciamento de dispositivo móvel que podem ser definidas em uma política de segurança de dispositivo móvel do Microsoft Intune em [Configurações da política de gerenciamento de dispositivo móvel para o Microsoft Intune](https://technet.microsoft.com/library/dn913730.aspx).

