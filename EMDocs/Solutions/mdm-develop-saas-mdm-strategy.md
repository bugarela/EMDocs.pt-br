---
title: "Desenvolver uma estratégia de gerenciamento de dispositivo móvel SaaS"
description: "Este artigo visa ajudar os clientes a desenvolver uma estratégia de software como serviço para o seu gerenciamento de dispositivo móvel, usando o Microsoft Enterprise Mobility + Security."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: b3cefcc5-b045-48f9-91f5-6d282a4428f3
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: 735874e0f5c30628fbc4bdcdce18e6db3a2ec735


---

# <a name="develop-saas-mobile-device-management-strategy"></a>Desenvolver uma estratégia de gerenciamento de dispositivo móvel SaaS

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

## <a name="identify-your-saas-solution-requirements"></a>Identificar os requisitos da solução de SaaS

Dependendo de como você respondeu às perguntas na Tarefa 1, você precisa conseguir determinar o que a solução de SaaS precisa para dar suporte em sua solução de gerenciamento de dispositivos móveis. A Tabela 20 abaixo ajudará você a entender as vantagens e desvantagens de cada cenário de solução de SaaS:

## <a name="intune-standalone"></a>Intune (autônomo)

**Vantagens**

- Oferecido como uma arquitetura multilocatária de nuvem pública
- É escalado para dar suporte para até 50.000 dispositivos móveis
- Não requer investimentos adicionais em infraestrutura local, hardware ou software
- Atualizações e melhorias de recurso são feitas diariamente. Principais aprimoramentos de recursos e funcionalidades feitos mensalmente
- Os serviços podem ser atribuídos a datacenters em locais geográficos específicos
- Os failovers do datacenter podem ser restritos a locais geográficos específicos
- A certificação e conformidade com a maioria dos SLAs (Contratos de Nível de Serviço) padrão do setor e governamentais é respaldada financeiramente. Se o serviço ou os recursos não estiverem disponíveis, os encargos mensais serão cancelados

**Desvantagens**

- Não há suporte para instâncias de nuvem privada
- Se você precisar oferecer suporte a mais de 50.000 dispositivos móveis, será necessário conectar o Intune ao ConfigMgr para gerenciar os dispositivos adicionais

## <a name="mdm-for-office-365"></a>MDM para o Office 365

**Vantagens**

- Totalmente integrado com locatários comerciais do Office 365, fornecendo um console único de gerenciamento de dispositivos móveis e serviços de locatário do Office 365 (Exchange Online, SharePoint Online e Skype for Business Online).
- Oferecido em tipos de plataforma do Office 365 multilocatário (público) ou privada (dedicado)
- Sem custos adicionais de usuário ou licenciamento de dispositivo, incluídos por padrão nos planos comerciais do Office 365 (Business, Enterprise, Education e Government)

**Desvantagens**

- Não oferece suporte ao gerenciamento de sistemas operacionais não móveis
- Interface de gerenciamento adicional para o provisionamento de dispositivos móveis (somente) se for usada uma plataforma de gerenciamento local para dispositivos não móveis.

## <a name="hybrid-intune-with-configmgr"></a>Híbrido (Intune com ConfigMgr)

**Vantagens**

- Todas as vantagens do Intune autônomo, além das seguintes: integração nativa entre o Intune (serviço de gerenciamento de dispositivo baseado em nuvem) com o ConfigMgr (plataforma de gerenciamento de dispositivo local)
- Dá suporte a opções avançadas de provisionamento de dispositivos para dispositivos móveis por meio da conectividade do Intune
- Novos recursos de serviço do Intune e funcionalidade estendida à infraestrutura local do ConfigMgr por meio de extensões de plataforma, seja de modo automático ou personalizado.

**Desvantagens**

- Exige configuração adicional para conectar o Intune à infraestrutura local do ConfigMgr.
- Para as organizações que não têm uma infraestrutura do ConfigMgr configurada, será necessário planejá-la, instalá-la e configurá-la antes da integração com o Intune.

Não deixe de ler o artigo **[Ajudar a proteger seus dados com apagamento remoto, bloqueio remoto ou redefinição de senha com o Microsoft Intune](https://technet.microsoft.com/library/jj676679.aspx)** para entender quais dados são removidos e o efeito nos dados que permanece no dispositivo após um apagamento seletivo por plataforma. Se você tiver um ambiente híbrido, confira o artigo [Como apagar dispositivos móveis remotamente usando o Configuration Manager](https://technet.microsoft.com/library/dn956981.aspx) para entender como o ConfigMgr pode ser usado para realizar essa tarefa.

Para obter mais detalhes sobre as funcionalidades e os requisitos da solução de SaaS, leia o tópico **[descrição do serviço para Microsoft Intune](https://technet.microsoft.com/library/dn600286.aspx)** para entender as diferenças no suporte a SaaS no [MDM para Office 365](https://technet.microsoft.com/library/faa7d8e5-645d-4d59-839c-c8d4c1869e4a(v=technet.10).aspx) e em uma infraestrutura [híbrida](https://technet.microsoft.com/library/jj884158.aspx) do Intune e do ConfigMgr.



<!--HONumber=Nov16_HO4-->


