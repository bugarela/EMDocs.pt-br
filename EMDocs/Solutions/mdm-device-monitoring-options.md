---
title: "Opções de monitoramento de dispositivo"
description: "Este artigo fornece orientações sobre as opções de monitoramento de dispositivo existentes ao planejar e desenvolver uma solução de Gerenciamento de dispositivo móvel da Microsoft, usando o Enterprise Mobility + Security."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 23cfc12a-fa96-4fb3-8de1-af4569e8cb71
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: 4160e2f2ad20e862b6ab2caf68e4f86add32143e
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="device-monitoring-options"></a>Opções de monitoramento de dispositivo

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Monitorar e entender o status e a configuração de todos os dispositivos móveis gerenciados pela sua organização ajuda a descobrir problemas e não conformidade, além de gerenciar o inventário de dispositivos. Sem relatórios detalhados sobre hardware, software e status de conformidade, é impossível garantir que as suas políticas de dispositivo estejam de fato em vigor e funcionando corretamente. O monitoramento proativo ajuda a reduzir pequenos problemas antes que eles se tornem maiores e mais caros.

O [Intune](/Intune/deploy-use/monitoring-and-reports-with-microsoft-intune), o [MDM para Office 365](https://technet.microsoft.com/library/faa7d8e5-645d-4d59-839c-c8d4c1869e4a(v=technet.10).aspx) e uma [implantação híbrida](https://technet.microsoft.com/library/gg699377.aspx) do Intune e do ConfigMgr incluem monitoramento e relatórios para ajudar a gerenciar dispositivos, usuários e a conformidade com as políticas e procedimentos de sua organização. Ao usar os relatórios internos junto com os relatórios personalizados, é possível monitorar o gerenciamento de dispositivos móveis em áreas como:

- Relatórios de atualização de software
- Relatórios de inventário de software
- Relatórios de inventário de hardware
- Relatórios de licenciamento
- Relatórios de não conformidade

Dependendo da configuração de sua infraestrutura, você poderá criar uma variedade de relatórios para ajudá-lo a monitorar sua organização. Os recursos de monitoramento e relatórios baseados no Intune são a espinha dorsal dos relatórios no MDM para Office 365, bem como implantações autônomas do Intune. Esses relatórios também podem ser totalmente integrados aos recursos de relatório do ConfigMgr quando ele estiver conectado ao Intune em uma implantação híbrida. Cada produto, como mostrado abaixo, tem recursos de relatório diferentes, mas complementares. É importante explorar as nuances dos recursos de relatório de cada solução de gerenciamento de dispositivos móveis para ajudar a garantir que você escolha uma solução que tenha os relatórios de que você precisa.

![Monitoramento e relatórios integrados de dispositivos móveis](./media/MDM_Figure_05.png)

**Monitoramento e relatórios integrados de dispositivos móveis**

As respostas para as perguntas na Tarefa 2 podem ajudar a determinar as necessidades de monitoramento e relatórios de seus dispositivos móveis. As listas abaixo mostram as vantagens e desvantagens dos recursos de monitoramento e relatórios em cada solução de MDM.

## <a name="intune-standalone"></a>Intune (autônomo)

**Vantagens**

- Visão geral/painel de monitoramento
- Alertas quando forem detectados erros em dispositivos de rede gerenciados diretamente
- Um RSS feed do serviço do Intune pode notificá-lo sobre problemas com o serviço e a próxima manutenção
- Três níveis de alertas (crítico, aviso e informativo) com limites e notificações de alerta de email
- Pode filtrar alertas por tipo de dispositivo
- Pode examinar o status de qualquer dispositivo gerenciado
- Fornece relatórios sobre dispositivos que não atendem à política de TI
- Pode monitorar detalhes nas seguintes áreas:
 - Sistema
 - SO
 - Armazenamento
 - Exchange ActiveSync
 - Compartimento do sistema
 - Rede
 - Serviço

**Desvantagens**

- Apenas alertas por email, sem alertas de voz nem baseados em texto

## <a name="mdm-for-office-365"></a>MDM para o Office 365

**Vantagens**

- Visão geral/painel de monitoramento
- Três níveis de alertas (crítico, aviso e informativo) com limites e notificações de alerta de email
- Pode filtrar alertas por tipo de dispositivo
- Pode examinar o status de qualquer dispositivo gerenciado
- Fornece relatórios sobre dispositivos que não atendem à política de TI

**Desvantagens**

- Somente relatórios de status de conformidade do dispositivo móvel

## <a name="hybrid-intune-with-configmgr"></a>Híbrido (Intune com ConfigMgr)

**Vantagens**

- Todos os recursos de monitoramento e relatório do Intune autônomo, além dos seguintes:
 - Monitoramento e relatórios consolidados, abrangentes e baseados em limites para todos os dispositivos de sua empresa, incluindo dispositivos não móveis e não registrados no Intune
 - Recursos avançados de relatórios do SSRS (SQL Server Reporting Services) e a sofisticada experiência de criação que o Reporting Services Report Builder oferece.

**Desvantagens**

- Exige configuração adicional para conectar o Intune à infraestrutura local do ConfigMgr
- Para as organizações que não tenham uma infraestrutura do ConfigMgr atual configurada, será necessário planejá-la, instalá-la e configurá-la antes da integração com o Intune

Explore os detalhes sobre as opções de monitoramento de dispositivos móveis examinando o seguinte:

- Intune: **[Como monitorar os dispositivos móveis](https://technet.microsoft.com/library/jj733634.aspx)** e [gerenciar relatórios](/Intune/deploy-use/monitoring-and-reports-with-microsoft-intune)
- ConfigMgr: [Como monitorar dispositivos móveis](https://technet.microsoft.com/library/gg682128.aspx) e [gerenciar relatórios](https://technet.microsoft.com/library/gg699377.aspx)
- MDM para Office 365: [Visão geral das tarefas de gerenciamento de dispositivo](https://technet.microsoft.com/en-us/library/ms.o365.cc.devicepolicy.aspx)
