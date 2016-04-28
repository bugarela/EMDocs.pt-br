---
# required metadata

title: Requisitos de usuário e de dispositivos
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 69020f79-4ce2-4984-b127-4520503fb729

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Requisitos de usuário e dispositivo

Antes de habilitar os usuários a acessarem recursos da empresa de seus dispositivos, responda às perguntas nas seções a seguir trabalhando com os consumidores desses recursos no seu ambiente e o departamento de TI. A Figura 2 mostra as interações entre usuários e dispositivos com o objetivo final de acesso e consumo de dados. Observe que o diagrama não aborda localização geográfica. Embora a localização geográfica seja uma consideração importante (e será abordada neste documento), a intenção da Figura 2 é ilustrar os componentes principais de usuários e dispositivos. Considerações de design devem ser feitas para permitir que essa comunicação ocorra.

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


<!--HONumber=Apr16_HO2-->


