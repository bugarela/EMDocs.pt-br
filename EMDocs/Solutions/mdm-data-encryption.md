---
title: Desenvolver seus requisitos de criptografia de dados
description: "Este tópico tem criptografia de dados de considerações design em dispositivos móveis. Este tópico faz parte de um conjunto maior de artigos sobre Considerações de Design de Gerenciamento de Dispositivos Móveis."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 10/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1072858e-dc0a-44ad-a512-d938f20310b6
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2342889a686db8a6496c97979cb222af8347241a
ms.openlocfilehash: a7382ec71d94d0b08cc4c89e8dbe90bcd1a4c1d7


---

# <a name="data-encryption"></a>Criptografia de dados

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Agora que você respondeu às perguntas na Tarefa 1 sobre os requisitos de criptografia de dados em repouso e em trânsito, você avaliará as opções disponíveis para atender a cada requisito. Mesmo quando os dados estiverem em repouso, eles poderão ser criptografados de maneiras diferentes, como mostra a figura abaixo.

![Disco de dispositivo móvel](./media/MDM_Figure_09.png)

## <a name="different-levels-of-encryption"></a>Diferentes níveis de criptografia

Você pode usar a criptografia completa de disco ou a criptografia baseada nos dados manipulados por um aplicativo. O [ConfigMgr](https://technet.microsoft.com/library/dn919655.aspx) permite que você imponha políticas que executarão a criptografia de arquivos em dispositivos móveis. Embora alguns dispositivos móveis, como os dispositivos com Windows 8, sejam criptografados automaticamente, outros apenas criptografam dados se outra opção for habilitada. Por exemplo, para dispositivos com iOS, a criptografia ocorre automaticamente somente depois que você definir a configuração para exigir uma senha no dispositivo.

O Windows 10 Mobile usa criptografia no dispositivo, com base na tecnologia BitLocker, para criptografar todo o armazenamento interno, incluindo o sistema operacional e as partições de armazenamento de dados. O usuário pode ativar a criptografia no dispositivo, ou o departamento de TI pode ativar e aplicar a criptografia para dispositivos gerenciados pela empresa por meio de ferramentas de MDM. Quando a criptografia do dispositivo é ativada, todos os dados armazenados no telefone são criptografados automaticamente. Um dispositivo com Windows 10 Mobile com criptografia ativada ajuda a proteger a confidencialidade dos dados armazenados em caso de perda ou roubo do dispositivo. Leia o Guia de segurança do Windows 10 Mobile para saber mais.

>[!TIP]
> Para saber mais sobre os dispositivos móveis que podem ter a criptografia habilitada usando o ConfigMgr, leia [Configurações de conformidade para dispositivos móveis no Configuration Manager](https://technet.microsoft.com/library/dn376523.aspx).

Para aplicativos associados a uma política de gerenciamento de aplicativos móveis do Intune, a criptografia é fornecida pela Microsoft. Os dados são criptografados de forma síncrona durante operações de E/S de arquivos, de acordo com a configuração na política de gerenciamento de aplicativos móveis. Nos dispositivos com Android, os aplicativos gerenciados usam a criptografia AES-128 no modo CBC (Encadeamento de Blocos de Criptografia) usando as bibliotecas de criptografia da plataforma, que não são certificadas pelo FIPS 140-2.

Essa opção permite que você especifique que todos os dados associados a um determinado aplicativo sejam criptografados, incluindo dados armazenados em mídia externa, como cartões SD. A mesma funcionalidade também está disponível com o [MDM para Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx).

Serviços de armazenamento de nuvem pública, como o OneDrive for Business, também podem ser integrados ao Intune Autônomo e ao [System Center 2012 R2 Configuration Manager SP1](https://technet.microsoft.com/library/mt131422.aspx). É possível implantar o aplicativo OneDrive para Empresas no dispositivo do usuário para que, em seguida, todos os documentos da conta do OneDrive para Empresas do usuário sejam criptografados.

A maioria das soluções de MDM usa o SSL para proteger dados em trânsito, portanto, você apenas precisa decidir se usará uma PKI existente para emitir certificados ou se usará uma AC (autoridade de certificação) de um fornecedor terceiro. A vantagem de usar uma AC de terceiros é que os usuários que usam seus próprios dispositivos para acessar os recursos da empresa confiarão automaticamente em uma CA pública bem reconhecida.

## <a name="intune-standalone"></a>Intune (autônomo)

**Vantagens**

- Criptografar dados associados a aplicativos controlados pela política de gerenciamento do Intune

**Desvantagens**

- Não inclui a criptografia nativa para o armazenamento de dispositivo móvel
- A falta de integração com a atual plataforma de MDM local significa uma interface de gerenciamento adicional para você usar

## <a name="mdm-of-office-365"></a>MDM para Office 365

**Vantagens**

- Criptografar dados com base na capacidade da plataforma de dispositivo móvel

**Desvantagens**

- Se a organização não tiver uma infraestrutura local do ConfigMgr atual, será necessário planejar, instalar e configurar essa plataforma antes da integração

## <a name="hybrid-intune-with-configmgr"></a>Híbrido (Intune com ConfigMgr)

**Vantagens**

- Criptografar dados associados a aplicativos controlados pela política de gerenciamento do Intune
- Criptografar o armazenamento do dispositivo móvel
- Fornece um controle mais granular do que pode ser criptografado em dispositivos móveis e como a criptografia é feita, incluindo a seleção do algoritmo de criptografia

**Desvantagens**

- Se a organização não tiver uma infraestrutura local do ConfigMgr atual, será necessário planejar, instalar e configurar essa plataforma antes da integração

Para saber mais sobre como combinar os recursos do Intune e do ConfigMgr para aumentar a proteção de dados e configurar a criptografia, leia [Managing Encryption on Mobile Devices with Configuration Manager and Intune](http://blogs.technet.com/b/pauljones/archive/2014/08/04/managing-encryption-on-mobile-devices-with-configuration-manager-and-intune.aspx) (Como gerenciar a criptografia em dispositivos móveis com o Configuration Manager e o Intune).



<!--HONumber=Jan17_HO1-->


