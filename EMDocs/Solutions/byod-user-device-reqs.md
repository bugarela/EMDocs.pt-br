---
title: "Requisitos de usuário e de dispositivos"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: a6319952-e9cd-4308-b9b9-b2e6005e6506
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0808c833aa2b6f36baa8d8f48ce797cc9f18aafa
ms.openlocfilehash: 8c53476e8b5995ecd6e40213304e20ba1a939266


---

# Requisitos de usuário e dispositivo

Antes de habilitar os usuários a acessarem recursos da empresa de seus dispositivos, responda às perguntas nas seções a seguir trabalhando com os consumidores desses recursos no seu ambiente e o departamento de TI. A Figura abaixo mostra as interações entre usuários e dispositivos com o objetivo final de acesso e consumo de dados. Observe que o diagrama não aborda localização geográfica. Embora a localização geográfica seja uma consideração importante (e será abordada neste documento), a intenção da figura é ilustrar os componentes principais de usuários e dispositivos. Considerações de design devem ser feitas para permitir que essa comunicação ocorra.

![Usuários, dispositivos e dados](./media/BYOD_Figure2.png)

O resultado desse processo é uma definição clara de funcionalidade a ser fornecida. A seção abaixo contém perguntas sobre usuários e dispositivos que você precisará responder para formular os requisitos de design da sua solução.

## Perguntas a fazer

Os requisitos de usuário e dispositivo são categorizados em três áreas:

- Perfil
- Dispositivo
- Rede

### Perfil

- Quais são os tipos de perfis de usuário que você tem em sua empresa (por exemplo, funcionários remotos, viajantes ocasionais e funcionários do escritório doméstico em tempo integral)?
- Todos os usuários têm os mesmos requisitos para realizarem seus trabalhos?
- Você tem uma matriz que estabelece as necessidades dos usuários de acordo com os trabalhos/funções?


### Dispositivos

- Quais são os tipos de dispositivo que os usuários levarão (como smartphones, tablets e laptops)?
- Você planeja oferecer a capacidade de limpeza remota de todos os tipos de dispositivos?
- Você planeja gerenciar dispositivos dos usuários?
- Há algum cenário em que não é necessário gerenciar o dispositivo, mas é preciso controlar quem possui o dispositivo mesmo assim?
- Você planeja autenticar dispositivos de acordo com os usuários que são trouxeram os dispositivos para a empresa?
- Sua empresa segue algum requisito de conformidade que deve ser aplicado a todos os dispositivos que possivelmente terão acesso aos dados da sua empresa?
- Sua empresa tem uma política em vigor para lidar com dispositivos roubados?

### Rede

- Sua empresa tem algum recurso na nuvem que poderá ser acessado através da Internet usando dispositivos dos usuários?
- Sua empresa tem restrições de política para usuários que acessam os dados da empresa de localizações geográficas diferentes?
- Você planeja fornecer criptografia de rede para permitir que os usuários acessem recursos da empresa usando seus dispositivos?
    - Nesse caso, a lista atual de dispositivos compatíveis dá suporte ao protocolo de criptografia que será usado?
- Você tem a segmentação de rede estabelecida?
    - Nesse caso, você todos os dispositivos dos usuários conectados a uma rede separada para isolá-los da rede de produção?
- Para funcionários de escritório residencial, como os usuários se conectarão à sua rede? Com fio, sem fio ou ambos?
    - Se a rede for sem fio, como você pretende controlar o AAA (Autenticação, Autorização e Contabilização) dos dispositivos para que nenhum dispositivo sem registro e sem autorização possa usar recursos da rede sem liberação adequada?

### Suporte técnico
- Sua equipe de rede/segurança está pronta para acomodar auditorias de conformidade do dispositivo regular?
- Você tem procedimentos e políticas de gerenciamento de alterações em vigor para dar suporte à implementação de BYOD?




<!--HONumber=Oct16_HO1-->


