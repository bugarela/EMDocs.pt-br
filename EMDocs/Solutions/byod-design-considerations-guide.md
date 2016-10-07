---
title: "Guia de considerações sobre design para BYOD"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: ed940ba8-866c-477f-a59b-beb620300a79
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0808c833aa2b6f36baa8d8f48ce797cc9f18aafa
ms.openlocfilehash: 3c88e0a7e82581d6ae6452ae13a44442c63923b6


---

# Guia de considerações sobre design para BYOD

Com a proliferação de dispositivos usados pelos funcionários, a maioria das empresas enfrenta um grande dilema: como permitir que os usuários usem seus próprios dispositivos, enquanto protegem os dados corporativos que residem nesses dispositivos? As empresas estão mudando do modelo tradicional, em que elas eram as proprietárias e forneciam dispositivos aos seus funcionários, para um modelo em que os funcionários usam seus dispositivos pessoais para algumas das suas tarefas de trabalho. Esse modelo é frequentemente mencionado como [BYOD (traga seu próprio dispositivo)](https://technet.microsoft.com/library/dn645493.aspx). Nesse modelo, os funcionários têm permissão para usar seus dispositivos pessoais para algumas tarefas de trabalho, mas somente se os funcionários permitirem que a empresa gerencie alguns aspectos dos seus dispositivos para garantir a segurança dos dados corporativos. Geralmente, isso significa que os usuários permitem que a empresa aplique políticas personalizadas, execute proteção dos dispositivos ou padronize o sistema operacional estabelecido pela política da empresa. Executivos e tomadores de decisão que lerem o artigo [CIO considerations for workstyle transformation](http://download.microsoft.com/download/5/3/A/53A96632-02E3-416C-B209-D8725AA80AFE/CIO%20Considerations%20for%20Workstyle%20Transformation2.pdf) (Considerações do CIO para transformação do estilo de trabalho) da Microsoft também poderão identificar os benefícios de adotar um modelo em que as pessoas possam usar os próprios dispositivos para serem produtivas no trabalho.

Embora a proteção de acesso a dados seja um dos principais desafios do BYOD, outros desafios exigem abordar o problema com uma abordagem mais abrangente:

- Os usuários e seus dispositivos: como os usuários podem usar seus próprios dispositivos e permanecer em conformidade com as políticas da empresa?
- Gerenciamento: como os dispositivos não corporativos serão gerenciados pela TI?
- Aplicativos: como aplicativos LOB (line-of-business, linha de negócios) serão acessados de dispositivos dos usuários?

Esta discussão será determinada pelos requisitos, recursos e considerações de design para uma infraestrutura de gerenciamento de dispositivo. As tecnologias da Microsoft são mencionadas no contexto dos recursos e requisitos — e não vice-versa. É nossa expectativa que essa abordagem tenha maior repercussão com arquitetos e designers interessados nos problemas que devem ser resolvidos e nas abordagens disponíveis para solucioná-los. Somente então a discussão da tecnologia é relevante.

Este guia fornece o arquiteto de sistema e o designer de sistema com uma coleção de considerações de design essenciais que precisam ser atendidas antes de projetar uma infraestrutura de BYOD (Bring Your Own Device, traga seu próprio dispositivo), que permite aos funcionários usar seus próprios dispositivos e protege os dados da empresa.

## Público-alvo

O principal público deste guia é o arquiteto ou o designer de sistema interessado em entender os problemas que precisam ser considerados antes de implementar uma infraestrutura BYOD. Outras pessoas que podem se interessar por este documento incluem implementadores de TI, especialistas em segurança da empresa e especialistas em gerenciamento de dispositivo.</para>
    
## Finalidade
  
A finalidade deste guia é:

1. Fornecer ao arquiteto ou designer de sistema um conjunto de problemas e perguntas a serem respondidas. As respostas a essas perguntas podem servir como os requisitos para um design de infraestrutura BYOD.
2. Fornecer ao arquiteto ou designer de sistema um conjunto de opções de design que podem ser avaliadas e escolhidas com base em requisitos identificados. 

Embora as perguntas possam ser usadas com qualquer fornecedor, exemplos das opções disponíveis se concentrarão em recursos do Windows Server 2012 R2, do System Center 2012 R2 e do Windows Intune.

Além disso, este guia inclui:

- Considerações de design de fornecedor independente para adaptar uma infraestrutura para habilitar o modelo BYOD. 
- Considerações de design para usuários, dispositivos, plataformas de gerenciamento, aplicativos e acesso e proteção de dados.

Antes de embarcar em um modelo BYOD em um ambiente de produção, os problemas de segurança, disponibilidade, desempenho e escalabilidade precisam ser considerados nas áreas de rede, armazenamento, cálculo e identidade. Há uma tendência a desejar adotar BYOD antes de haver uma análise concreta do ambiente atual e do que precisa ser feito para permitir que os usuários trabalhem de qualquer dispositivo, em qualquer lugar, com segurança.

*Não* é a finalidade deste guia:

- Fornecer uma linha de base do desempenho para os componentes de infraestrutura de um modelo BYOD. 
- Fornecer ajustes de desempenho e práticas recomendadas para os componentes da infraestrutura de BYOD.
- Fornecer diretrizes de desenvolvimento de aplicativos para dispositivos móveis.
- Fornecer práticas recomendadas de desenvolvimento de aplicativo para dispositivos móveis.
- Fornecer orientações e práticas recomendadas para componentes de terceiros.

## Definição do problema

Os seguintes problemas ou desafios normalmente são aqueles encontrados por empresas tentando adotar BYOD:

- A plataforma de gerenciamento existente não permite que os usuários levem seus próprios dispositivos e obtenham acesso aos recursos da empresa.
- A estratégia de segurança já estabelecida não aborda os desafios de segurança que BYOD apresenta ao ambiente.
- Os usuários estão adotando novas tecnologias e solicitam acesso aos recursos da empresa para executarem seus trabalhos.
- Os tomadores de decisão entendem os benefícios que a estratégia de BYOD traz aos negócios, principalmente na produtividade do usuário, que pode reduzir os custos de operação. No entanto, os tomadores de decisão não têm certeza de como adotar BYOD e ao mesmo tempo manter a conformidade com regras e regulamentos.

Organizações com uma grande infraestrutura precisam determinar requisitos antes de passarem de gerenciar os dispositivos elas mesmas — o que presume que a TI tem controle total dos dispositivos — para um modelo em que a TI deve supor que ela tem menos controle dos dispositivos e, ao mesmo tempo, precisa para atender às necessidades dos usuários para acessar dados corporativos. Isso geralmente é chamado de mudança de TI centrada em dispositivo para TI centrada em pessoas. As mesmas considerações e requisitos devem também ser cuidadosamente planejados para aplicativos novos e existentes ou para levar os aplicativos existentes para um ambiente em nuvem. A Figura 1 inclui um diagrama conceitual de domínio do problema do BYOD e as áreas que serão abordadas neste guia.

![Domínio do problema](./media/BYOD_Figure1.png)




<!--HONumber=Oct16_HO1-->


