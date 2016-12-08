---
title: "Previsão da solução de infraestrutura BYOD"
description: "Este artigo fornece uma definição de solução para o cenário Traga seu próprio dispositivo com base nas opções feitas durante o processo de criação."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: ecb6271f-8f38-42bd-aae7-10ba5e17a5f1
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 7dbb0c9b1b2b3b29eb54ad8cdeee527d9d7f078f


---

#<a name="envisioning-the-byod-infrastructure-solution"></a>Previsão da solução de infraestrutura BYOD

Depois de definir claramente o problema do BYOD que está tentando resolver, você pode começar a definir uma solução para o problema e os requisitos detalhados para a solução.

## <a name="solution-definition"></a>Definição da solução

Para resolver os problemas identificados anteriormente e ajudar as organizações a incentivar os usuários a levar seus próprios dispositivos para o trabalho e acessar dados corporativos com seus dispositivos, uma empresa deve passar de uma abordagem de TI centrada no dispositivo para uma abordagem de TI centrada em pessoas. As considerações de design neste guia podem ser usadas durante a definição de sua própria solução de infraestrutura BYOD para: 

- Fornecer aos usuários a flexibilidade para usar seus próprios dispositivos para acessar dados e aplicativos corporativos.
- Gerenciar dispositivos que estão acessando recursos corporativos quando local e na nuvem.
- Habilita o departamento de TI a proteger dados corporativos armazenados em dispositivos usando criptografia e a proteção de informações para proteger contra o acesso local não autorizado e apagando remotamente dados corporativos pela Internet quando um dispositivo é perdido ou desativado ou durante o processo de rescisão do contrato de um funcionário.
- Fornecer aos usuários uma identidade comum quando eles estiverem acessando os recursos locais e na nuvem.
- Habilitar a TI a gerenciar várias identidades e manter as informações sincronizadas entre ambientes diferentes.
- Habilitar serviços de autenticação da empresa, como Multi-Factor Authentication e logon único.
- Propiciar segurança da informação e atividades de conformidade como atestado de conformidade.

## <a name="solution-requirements"></a>Requisitos da solução

Antes de habilitar usuários a levarem seus próprios dispositivos e obterem acesso aos recursos da empresa, os recursos técnicos da infraestrutura existente devem ser revisados. A meta da revisão é compreender se os requisitos da solução para esse novo modelo já estão estabelecidos ou se novas tecnologias devem ser introduzidas para resolver o problema. Primeiro, você deve definir uma série de requisitos para fazer isso, bem como as restrições para o ambiente. Algumas das restrições e requisitos são definidos pelos consumidores de recursos; outros são definidos por seu ambiente, em termos de recursos técnicos, serviços, políticas e processos existentes.

Determinar os requisitos, as restrições e o design para permitir que os usuários tenham acesso aos recursos da empresa em seus dispositivos gerenciados é um processo crucial. Requisitos iniciais, juntamente com as restrições de seu ambiente, podem levar a um design inicial que não atenda aos requisitos inicial, a necessidade de alterações nos requisitos iniciais e design subsequente. Várias iterações por meio da definição de requisitos e design da solução são necessárias antes de concluir os requisitos e o design. Portanto, não espere que a sua primeira execução por este guia seja a última. Você pode considerar que as decisões tomadas no início do processo excluem opções preferenciais disponibilizadas a você mais adiante no processo.

As respostas a perguntas nas próximas seções compilam uma lista abrangente de requisitos para habilitar usuários a acessar os recursos da empresa em seus dispositivos, o que pode ser gerenciado pela IT mantendo os dados protegidos. Estas perguntas não são específicas do fornecedor e podem ser aplicadas a qualquer solução de infraestrutura de BYOD.

As considerações sobre o domínio do problema do BYOD apresentados neste guia são divididas em subdomínios. Cada subdomínio terá um conjunto de componentes. Para cada subdomínio apresentado neste guia, você tem um conjunto de requisitos:

- [Requisitos de usuários e dispositivos](byod-user-device-reqs.md)
- [Requisitos de acesso e proteção de dados](byod-data-access-protection-reqs.md)
- [Requisitos de gerenciamento](byod-management-reqs.md)
- [Requisitos de aplicativos](byod-app-reqs.md)




<!--HONumber=Nov16_HO4-->


