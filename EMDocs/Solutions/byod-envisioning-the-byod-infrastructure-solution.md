---
# required metadata

title: Previsão da solução de infraestrutura BYOD
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 9596531a-2eef-4c91-af11-091088c52929

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

#Previsão da solução de infraestrutura BYOD

Depois de definir claramente o problema do BYOD que está tentando resolver, você pode começar a definir uma solução para o problema e os requisitos detalhados para a solução.

## Definição da solução

Para resolver os problemas identificados anteriormente e ajudar as organizações a incentivar os usuários a levar seus próprios dispositivos para o trabalho e acessar dados corporativos com seus dispositivos, uma empresa deve passar de uma abordagem de TI centrada no dispositivo para uma abordagem de TI centrada em pessoas. As considerações de design neste documento podem ser usadas durante a definição de sua própria solução de infraestrutura BYOD para: 

- Fornecer aos usuários a flexibilidade para usar seus próprios dispositivos para acessar dados e aplicativos corporativos.
- Gerenciar dispositivos que estão acessando recursos corporativos quando local e na nuvem.
- Habilita o departamento de TI a proteger dados corporativos armazenados em dispositivos usando criptografia e gerenciamento de direitos para proteger contra o acesso local não autorizado e apagando remotamente dados corporativos pela Internet quando um dispositivo é perdido ou desativado ou durante o processo de desligamento de um funcionário.
- Fornecer aos usuários uma identidade comum quando eles estiverem acessando os recursos locais e na nuvem.
- Habilitar a TI a gerenciar várias identidades e manter as informações sincronizadas entre ambientes diferentes.
- Habilitar serviços de autenticação da empresa, como Multi-Factor Authentication e logon único.
- Propiciar segurança da informação e atividades de conformidade como atestado de conformidade.

## Requisitos da solução

Antes de habilitar usuários a levarem seus próprios dispositivos e obterem acesso aos recursos da empresa, os recursos técnicos da infraestrutura existente devem ser revisados. A meta da revisão é compreender se os requisitos da solução para esse novo modelo já estão estabelecidos ou se novas tecnologias devem ser introduzidas para resolver o problema. Primeiro, você deve definir uma série de requisitos para fazer isso, bem como as restrições para o ambiente. Algumas das restrições e requisitos são definidos pelos consumidores de recursos; outros são definidos por seu ambiente, em termos de recursos técnicos, serviços, políticas e processos existentes.

Determinar os requisitos, as restrições e o design para permitir que os usuários tenham acesso aos recursos da empresa em seus dispositivos gerenciados é um processo crucial. Requisitos iniciais, juntamente com as restrições de seu ambiente, podem levar a um design inicial que não atenda aos requisitos inicial, a necessidade de alterações nos requisitos iniciais e design subsequente. Várias iterações por meio da definição de requisitos e design da solução são necessárias antes de concluir os requisitos e o design. Portanto, não espere que a sua primeira execução por este documento seja a última. Você pode considerar que as decisões tomadas no início do processo excluem opções preferenciais disponibilizadas a você mais adiante no processo.

As respostas a perguntas nas próximas seções compilam uma lista abrangente de requisitos para habilitar usuários a acessar os recursos da empresa em seus dispositivos, o que pode ser gerenciado pela IT mantendo os dados protegidos. Estas perguntas não são específicas do fornecedor e podem ser aplicadas a qualquer solução de infraestrutura de BYOD.

As considerações sobre o domínio do problema do BYOD apresentados neste guia são divididas em subdomínios. Cada subdomínio terá um conjunto de componentes. Para cada subdomínio apresentado neste guia, você tem um conjunto de requisitos:

- Requisitos de usuários e dispositivos
- Requisitos de acesso e proteção de dados
- Requisitos de gerenciamento
- Requisitos de aplicativos



<!--HONumber=Apr16_HO2-->


