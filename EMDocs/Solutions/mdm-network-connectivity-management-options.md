---
# required metadata

title: Opções de gerenciamento de conectividade de rede
description:
keywords:
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: bc7cdb8f-3485-45ae-9493-f840ad9ed3ea

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opções de gerenciamento de conectividade de rede

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Dependendo de sua infraestrutura, os dispositivos móveis poderão se conectar aos recursos corporativos por meio de uma variedade de serviços de conectividade da Internet, que geralmente são protegidos por pontos de extremidade protegidos por VPN.

Ao usar o [Intune](/Intune/deployuse/wi-fi-connections-in-microsoft-intune) ou uma [implantação híbrida](https://technet.microsoft.com/library/dn261221.aspx) com o ConfigMgr, é possível implantar perfis de Wi-Fi para provisionar redes Wi-Fi, para que um dispositivo possa se conectar automaticamente à rede quando ele estiver no intervalo. Por exemplo, os dispositivos móveis podem ser configurados para se conectarem a uma rede Wi-Fi segmentada a uma sala de conferência, mas, em seguida, alternarem para se conectarem a um segmento de rede Wi-Fi quando estiverem usando o perfil móvel para um local diferente. Os usuários não precisam digitar senhas nem escolher uma rede; a conexão funciona automaticamente.

O [Intune](/Intune/deployuse/vpn-connections-in-microsoft-intune) e o [ConfigMgr](https://technet.microsoft.com/library/dn261217.aspx) também podem implantar perfis de VPN diretamente em dispositivos móveis, para permitir que o usuário acesse recursos corporativos internos sem configuração adicional ou trabalho manual. Além disso, o Intune pode configurar dispositivos móveis para iniciar automaticamente uma conexão VPN que é baseada no recurso de tipo ou no método de acesso. Lembre-se, no entanto, de que existem requisitos de configuração diferentes para fazer isso para diferentes tipos de sistemas operacionais de dispositivos móveis.

Suas respostas às perguntas na Tarefa 3 podem ajudá-lo a determinar como você deseja que os dispositivos sejam conectados aos recursos corporativos. Lembre-se de que, atualmente, o <token>MDM para Office 365</token> não dá suporte ao gerenciamento de recursos de rede VPN e sem fio para dispositivos móveis.

As listas abaixo relacionam as vantagens e desvantagens do gerenciamento de redes sem fio e de VPN usando o Intune autônomo e o Intune com o ConfigMgr híbridos.

## Intune (autônomo)

**Vantagens**

- Dá suporte aos perfis de VPN e sem fio em todos os principais sistemas operacionais de dispositivos móveis (Android, iOS, Windows 10, Windows 8.x e Windows Phone) 
- Dá suporte a tipos de conexão VPN líderes do setor, incluindo Cisco, Juniper, Dell SonicWall, Checkpoint e outros
- Perfis de VPN e sem fio podem ser integrados a perfis de certificado SCEP para aumentar a segurança
- Dá suporte à configuração de perfis de VPN e sem fio personalizados para diferentes tipos de usuários, dispositivos, sistemas operacionais de dispositivos ou grupos e funções de usuários
- Suporte de inicialização baseado no nome DNS para Windows 10, Windows 8.1, Windows Phone 8.1 e iOS
- Suporte de inicialização baseado na ID de aplicativo para Windows 10 e Windows 8.1
- Selecione os aplicativos que se conectam automaticamente à rede corporativa por VPN em perfis de VPN.

**Desvantagens**

- Para dar suporte a perfis de VPN, você precisará implantar e manter uma infraestrutura de VPN local

## MDM para o Office 365

Não há suporte para perfis de Wi-Fi e de VPN no MDM para Office 365.

## Híbrido (Intune com ConfigMgr)

**Vantagens**

- Todas as vantagens do Intune autônomo, além das seguintes:
    - Há suporte para os perfis de VPN da infraestrutura local existente de VPN empresarial

**Desvantagens**

- Para dar suporte a perfis de VPN, você precisará implantar e manter uma infraestrutura de VPN local 
- Permissões de segurança específicas devem ser concedidas para gerenciar [perfis de Wi-Fi](https://technet.microsoft.com/library/dn408646.aspx) e [perfis de VPN](https://technet.microsoft.com/library/dn408643.aspx) no ConfigMgr.

Explore os detalhes sobre as opções de gerenciamento de configuração de email do dispositivo móvel examinando o seguinte:

- Intune: habilitar os perfis [sem fio](/Intune/deployuse/wi-fi-connections-in-microsoft-intune) e de [VPN](/Intune/deployuse/vpn-connections-in-microsoft-intune)
- ConfigMgr: habilitar os perfis [sem fio](https://technet.microsoft.com/library/dn261221.aspx) e de [VPN](https://technet.microsoft.com/library/dn261217.aspx)

<!--HONumber=Jun16_HO1-->


