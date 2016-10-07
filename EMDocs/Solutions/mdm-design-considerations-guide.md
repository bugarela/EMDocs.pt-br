---
title: "Guia de considerações de design de gerenciamento de dispositivos móveis"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 7083b6b8-27a3-427b-b505-25d007d63cdd
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0808c833aa2b6f36baa8d8f48ce797cc9f18aafa
ms.openlocfilehash: 8f279f528cab2a747f12d5e372ec7e9442bd87e4


---

# Guia de considerações de design de gerenciamento de dispositivos móveis

Com todas as diferentes opções de design e configuração para soluções MDM (gerenciamento de dispositivo móvel), às vezes é difícil determinar qual solução melhor atenderá às necessidades de sua organização. Este guia de design ajudará você a entender os requisitos de design do MDM e fornecerá detalhes de uma série de etapas e tarefas que você pode realizar para criar uma solução de MDM melhor se adapte às necessidades de tecnologia e de negócios de sua organização. 

## Introdução

Durante as etapas e tarefas, o guia apresentará as tecnologias relevantes e as opções de recursos disponíveis para as organizações atenderem aos requisitos de nível de funcionalidade e qualidade de serviço (como disponibilidade, escalabilidade, desempenho, capacidade de gerenciamento e segurança).

Especificamente, os objetivos deste guia são ajudá-lo a responder às seguintes perguntas:

- Quais perguntas eu preciso responder para gerar adoção de uma solução de gerenciamento de dispositivo móvel que melhor atenda às necessidades de meu negócio?
- Qual é a sequência de atividades que preciso concluir para projetar uma solução de gerenciamento de dispositivo móvel para minha organização?
- Quais opções de tecnologia de gerenciamento móvel e configuração da Microsoft estão disponíveis para ajudar a atender às minhas necessidades, e quais são as desvantagens entre essas opções?

**A quem este guia se destina?** Arquitetos de tecnologia da informação e profissionais responsáveis pela criação de uma solução de gerenciamento de dispositivos móveis para organizações médias ou grandes.

**Como este guia pode ajudar?** Você pode usar este guia para entender como criar uma solução de gerenciamento de dispositivos móveis que possa gerenciar dispositivos de propriedade da empresa, bem como dispositivos de propriedade do usuário em diferentes fatores forma.

![Exemplo de uma solução do Intune e o do System Center Configuration Manager MDM híbrida](./media/MDM_Figure_01.png)
**Exemplo de uma solução do Intune e do System Center Configuration Manager MDM híbrida**

A figura acima é um exemplo de uma solução de gerenciamento híbrida, em que aproveita os serviços de nuvem para integrá-los aos recursos locais, a fim de gerenciar todos os tipos de dispositivos, independentemente de sua localização. Embora esse seja um cenário bastante comum, o design de MDM de cada organização pode ser diferente do exemplo, devido aos requisitos exclusivos de gerenciamento de cada organização.
 
Este guia fornece detalhes sobre uma série de etapas e tarefas que você deve seguir para ajudá-lo a criar uma solução de MDM personalizada que atende às necessidades exclusivas de sua organização. Ao longo das etapas e tarefas a seguir, este guia aborda as tecnologias relevantes e as opções de recursos disponíveis para que você atenda aos requisitos funcionais e de nível de qualidade de serviço para MDM. 

Embora este guia possa ajudá-lo a projetar uma solução de MDM, ele não aborda opções específicas de operações ou de implementação das soluções de gerenciamento, nem como migrar de uma solução MDM de terceiros existente. Encontre etapas detalhadas de implantação e configuração do [Microsoft Intune](/Intune/), [Gerenciamento de Dispositivo Móvel para Office 365](https://technet.microsoft.com/library/ms.o365.cc.devicepolicy.aspx) e [Microsoft System Center Configuration Manager](https://technet.microsoft.com/library/cc507089.aspx) no docs.microsoft.com e nas bibliotecas TechNet usando os links disponíveis na seção **Próximas etapas e recursos adicionais** ao final deste guia.

Você também pode encontrar diretrizes sobre como migrar de outras soluções MDM para o Microsoft Intune [aqui](https://blogs.technet.microsoft.com/intunesupport/2016/02/10/new-guide-on-how-to-migrate-from-other-mdm-technologies-to-microsoft-intune/).

**Suposições:** você tem alguma experiência com Microsoft Intune, System Center 2012 R2 Configuration Manager (ConfigMgr), Windows Server 2012 R2 e com dispositivos móveis executando Android, iOS e Windows Phone. Você pode até mesmo ter implantado uma dessas soluções em um ambiente de produção limitado ou de teste inicial de MDM. Neste guia, presumimos que você esteja procurando descobrir como essas soluções podem atender melhor às suas necessidades de negócios por si só ou em uma solução integrada.

## Considerações sobre o design do MDM
Este guia abrange um conjunto de etapas e tarefas que você pode seguir para projetar uma solução que melhor atende às suas necessidades. As etapas são apresentadas em uma sequência ordenada. No entanto, as considerações sobre design que você aprenderá nas próximas etapas podem solicitar que você mude as decisões feitas nas etapas anteriores, à medida que o seu design amadurece ou devido a escolhas de design conflitantes. Ao longo deste guia, nós o alertaremos sobre possíveis conflitos de design.

Você desenvolverá um design de gerenciamento de dispositivos móveis que melhor atenda às suas necessidades somente após percorrer as seguintes etapas quantas vezes forem necessárias para incorporar todas as considerações contidas neste guia: 

- [Etapa 1: Identificar os requisitos de gerenciamento de dispositivos móveis](mdm-step-1-identify-your-mobile-device-management-requirements.md)
- [Etapa 2: Planejar o gerenciamento de dispositivos móveis](mdm-step-2-plan-for-mobile-device-management.md)
- [Etapa 3: Planejar a proteção de dispositivos móveis](mdm-step-3-plan-enhancing-mobile-devices-protection.md)
- [Etapa 4: Planejar o gerenciamento de dispositivos móveis de software como Serviço](mdm-step-4-plan-for-software-as-a-service-mobile-device-management.md)
- [Próximas etapas e recursos adicionais](mdm-next-steps-and-additional-resources.md)
        
## Procurando uma versão para download?
Obtenha uma cópia baixável deste tópico completo na [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).



<!--HONumber=Oct16_HO1-->


