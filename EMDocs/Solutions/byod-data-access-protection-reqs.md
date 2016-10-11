---
title: "Requisitos de acesso e proteção de dados"
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 29eddc34-5ca5-4169-89b6-8137b03ab7f0
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0808c833aa2b6f36baa8d8f48ce797cc9f18aafa
ms.openlocfilehash: e0e38db16bf4e2479fc4d068287dd0c713eeab15


---

# Requisitos de acesso e proteção de dados

Um dos elementos mais importantes ao permitir que os usuários acessem recursos da empresa de seus próprios dispositivos é preservar os dados da empresa e proteger essas informações. Sua empresa pode ter uma variedade de requisitos de conformidade que devem estar disponíveis para garantir que os dados estejam seguros, independentemente de onde estão localizados. A figura abaixo mostra as interações entre usuários e dispositivos durante o acesso a dados e os componentes que devem ser considerados para esse subdomínio.

![Requisitos de proteção de acesso aos dados](./media/BYOD_Figure3.png)

A seção a seguir contém perguntas sobre acesso a dados e proteção que você precisará responder para formular os requisitos para o design da sua solução.

## Perguntas a fazer

As perguntas sobre requisitos de acesso e proteção dos dados são categorizadas em seis áreas:

- Armazenamento
- Rede
- Diretório
- Authorization
- Política e conformidade

### Armazenamento

- Enquanto os dados estão em repouso no data center, você tem criptografia habilitada?
- Sua empresa fornece acesso offline aos dados localizados em armazenamento do datacenter (em outras palavras, você sincronizará dados com dispositivos de usuários)?
    - Se for o caso, a sua empresa deseja manter o mesmo formato de dados (simples ou criptografado) em dispositivos de usuários?
- Você tem qualquer cota de armazenamento implementada atualmente no seu sistema por usuário?
    - Se assim, você planeja aumentar essa cota para usuários autorizados a usar seus próprios dispositivos?
- A política da sua empresa permite que os usuários usem as unidades de armazenamento externo nos computadores corporativos?
    - Caso contrário, você planeja estender essa política para usuários que estão acessando os dados em seus próprios dispositivos?
- A política da sua empresa permite que os usuários usem o armazenamento baseado em nuvem a partir de computadores corporativos?
    - Caso contrário, você planeja estender essa política para usuários que estão acessando os dados em seus próprios dispositivos?

### Rede

- Você tem qualquer tipo de criptografia de rede local?
    - Nesse caso, é limitado a comunicação entre servidores, ou toda a rede é criptografada?
- Você planeja ter diferentes requisitos de acesso aos dados para quando os usuários estiverem fisicamente fora da rede corporativa e para quando estiverem fisicamente dentro da rede corporativa?
    - Nesse caso, quais são os requisitos?
- Você prevê um aumento na atividade de rede quando habilitar os usuários a usarem seus próprios dispositivos na rede corporativa?
    - Nesse caso, a capacidade da sua rede atual pode lidar com esse tráfego novo?
- Sua empresa usa algum mecanismo de inspeção de rede?
    - Nesse caso, você planeja estender esse recurso para usuários que levem seus próprios dispositivos e conectem-se à rede corporativa?

### Diretório

- Sua empresa usa um diretório de único usuário ou tem vários provedores?
- O diretório da sua empresa está localizado local, na nuvem ou em ambos (híbrido)?
- Quando os usuários acessam aplicativos em seus dispositivos, em relação ao qual diretório eles estarão autenticando?
- A sua empresa planeja agrupar autenticação entre serviços locais e de nuvem?

### Autenticação

- Que tipo de autenticação é usado atualmente no seu ambiente?
- Você planeja preservar esse método de autenticação ou deseja aprimorá-lo antes de habilitar os usuários a usarem seus próprios dispositivos para acessarem os recursos da empresa?
- Você tem Multi-Factor Authentication em execução no ambiente atual?
- Você planeja autenticar dispositivos dos usuários ou somente usuários?
- Você planeja habilitar logon único para os aplicativos acessados a partir de dispositivos dos usuários?
- Você pretende utilizar recursos de nuvem para fornecer um nível adicional de autenticação para usuários remotos?

### Authorization

- No ambiente atual, depois que os usuários são autenticados, você tem quaisquer outros controles estabelecidos para validar se o usuário está autorizado a acessar as informações solicitadas?
- Você planeja fornecer acesso condicional com base em um conjunto de regras predefinidas para usuários remotos?
- Sua empresa executa imposição de autorização para dados localizados locais ou na nuvem?
- Sua empresa usa o [princípio de necessidade de saber](http://en.wikipedia.org/wiki/Need_to_know) para autorizar o acesso a dados?

### Política e conformidade

- Sua empresa tem políticas estabelecidas para definir como o acesso a dados é classificado?
- Sua empresa precisa estar em conformidade com todas as regulamentações de manipulação de dados e privacidade?
    - Nesse caso, como essas normas conduzem as políticas de acesso de dados atuais para recursos locais?
- Sua empresa tem políticas em vigor para [MDM (Gerenciamento de Dispositivo Móvel)](mdm-design-considerations-guide.md) e [MAM (Gerenciamento de Aplicativo Móvel)](https://blogs.technet.microsoft.com/cbernier/2016/01/05/microsoft-intune-mobile-application-management-mam-standalone/)?
- Sua empresa tem políticas estabelecidas para confiscação de dispositivo no caso de litígio judicial ou investigação criminal?



<!--HONumber=Oct16_HO1-->


