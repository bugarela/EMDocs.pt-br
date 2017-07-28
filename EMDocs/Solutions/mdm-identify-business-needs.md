---
title: Identificar as necessidades comerciais
description: "Este artigo fornece diretrizes para identificar necessidades comerciais para justificar a adoção do gerenciamento de dispositivo móvel."
keywords: 
author: YuriDio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 85783069-14fb-4ead-a159-657d694eb1a7
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: e109d6025513fde7a9cf09afc6e6dbb31222c467
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="identify-your-business-needs"></a>Identificar suas necessidades comerciais

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Cada empresa terá requisitos diferentes. Mesmo que essas empresas fizerem parte do mesmo setor, os requisitos de negócios reais poderão variar. Você ainda pode aproveitar as práticas recomendadas do setor, mas, em última análise, são as necessidades de negócios da empresa que identificarão os requisitos para a solução de gerenciamento de dispositivos móveis.
Para ajudar você a identificar suas necessidades comerciais, responda às seguintes perguntas:

- **Usuários:** um dos principais pontos ao adotar a mobilidade é colocar o usuário no centro da solução de mobilidade e permitir que ele seja mais produtivo, ao mesmo tempo que mantém os dados da empresa seguros e disponíveis. Isso é importante para entender quais são os requisitos do usuário.
    - O usuário poderá trazer seu próprio dispositivo e acessar os recursos da empresa?
        - Em caso afirmativo, quais são os requisitos para acessar recursos da empresa?
    - Sua empresa tem diferentes necessidades de usuário?
        - Em caso afirmativo, como cada perfil de usuário afetará a estratégia de mobilidade?
    - Os usuários poderão acessar todos os aplicativos aos quais tenham acesso no ambiente local por meio de seus dispositivos móveis?
        - Caso contrário, quais aplicativos estarão disponíveis para os usuários?
            - Esses aplicativos estão disponíveis para todas as plataformas de dispositivos móveis com suporte?
            - Será necessário modificar ou atualizar aplicativos para executá-los em todas as plataformas de dispositivos móveis com suporte?
    - Os usuários precisam apenas do acesso básico a recursos de email (incluindo calendário, contatos e tarefas)?

- **Propriedade do dispositivo:** você deve entender a política de propriedade do dispositivo de sua empresa.
    - Quem possui o dispositivo móvel?
        - O funcionário?
        - A empresa?  
        - Ambos?
- **Plataforma:** entender quais sistemas operacionais de dispositivos móveis serão usados pela empresa é muito importante para decisões sobre adoção e capacidade de suporte.
    - Quais sistemas operacionais de dispositivos móveis terão suporte?
        - Android?
        - iOS?
        - Windows?
        - Windows Phone?
        - Todos eles?
        - Uma combinação das opções acima?
    - Qual versão do SO móvel terá suporte?
        - Somente a mais recente?
        - Atual -1 (versão atual e a versão anterior)?
- **Aplicativo:** como o principal motivo para adotar a mobilidade é aumentar a produtividade, os aplicativos usados pelos funcionários devem poder executar todos os sistemas operacionais de dispositivos móveis usados em sua organização. Esse é um ponto importante a considerar, porque, embora algumas empresas possam fazer com que seus aplicativos mais importantes sejam totalmente portáteis para ser executados em um ambiente móvel, outras podem precisar entender quais opções estão disponíveis que podem ajudá-las a implantar seus aplicativos em dispositivos móveis. Para ajudar a identificar os requisitos de aplicativos individuais, faça as seguintes perguntas.
    - Os aplicativos exigem acesso à Internet de dispositivos dos usuários?
    - Os aplicativos coletam informações pessoais do usuário?
        - Nesse caso, os aplicativos informam os usuários sobre questões de privacidade e coleta de dados durante a instalação?
    - Os aplicativos exigem integração com serviços de nuvem?
        - Os aplicativos foram desenvolvidos para execução em um sistema operacional específico ou eles podem ser executados em qualquer sistema operacional?
    - Você planeja habilitar os usuários a usar aplicativos por meio da área de trabalho remota em seus próprios dispositivos?
    - Os aplicativos exigem acesso integral aos recursos corporativos, ou podem executar no modo offline?
    - Os aplicativos possuem alguma integração com redes sociais?
    - Todos os aplicativos estarão disponíveis para os usuários BYOD?
    - Como você planeja implantar esses aplicativos para dispositivos dos usuários?
    - Quais são as opções de implantação para esses aplicativos?
    - O requisito de instalação varia de acordo com o dispositivo de destino ou é o mesmo?
    - Que quantidade de espaço em um dispositivo de destino é necessária para instalar cada aplicativo?
    - Os aplicativos criptografam os dados antes de transmiti-los por meio da rede a partir dos dispositivos dos usuários para o servidor de aplicativos no back-end?
    - Os aplicativos podem ser remotamente desinstalados através da rede ou precisam ser desinstalado usando consoles os dispositivos?
    - Sua empresa precisa fornecer acesso aos dados de aplicativos SaaS para seus parceiros?
    - Os aplicativos funcionam em uma rede de baixa latência?
    - Os aplicativos fornecem recursos de autenticação?
        - Nesse caso, que método de autenticação os aplicativos usam?

Durante esta tarefa, você deve também avaliar se a empresa tem políticas existentes em vigor de gerenciamento e conformidade para dispositivos móveis e como essas políticas podem afetar a seleção da solução de gerenciamento de dispositivos móveis.

>[!TIP]
> Lembre-se de fazer anotações de cada resposta e entender a lógica por trás da resposta. A próxima seção apresentará as opções disponíveis e as vantagens/desvantagens de cada uma delas.  Ao responder a essas perguntas, você poderá selecionar a solução que melhor atende às suas necessidades de negócios.
