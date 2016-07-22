---
title: "Identificar as necessidades de integração de infraestrutura da solução SaaS"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 26b15471-b496-4404-934d-67e621655bca
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 73c37109735567642ff1dc11f9729e3ab3affd3b
ms.openlocfilehash: 7e43f590182e6a2eacfa60114290848de0b24baa


---

# Identificar as necessidades de integração de infraestrutura da solução SaaS

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Uma das principais decisões que precisam ser feitas ao considerar o gerenciamento de dispositivos móveis com uma solução de SaaS é:

- Como as contas locais existentes de diretório do usuário e do dispositivo serão integradas à solução de SaaS?
- Você precisa integrar a solução de SaaS com plataformas existentes de gerenciamento local de clientes?

As decisões tomadas nessas duas áreas afetarão significativamente a implantação geral, a administração e as experiências de usuário final de sua solução de gerenciamento de dispositivos móveis.

## Identidade e conectividade de diretório

A conexão e sincronização do seu diretório local de contas de dispositivo e usuário com a solução de SaaS é realmente a liga que na verdade conecta os usuários, dispositivos móveis, aplicativos móveis e o gerenciamento de dispositivos móveis. Saber quem é um usuário (identidade) e associar a identidade a dispositivos móveis específicos é essencial para gerenciar o acesso aos recursos e aos dados da empresa no dispositivo móvel. Em muitos aspectos, maximizar a forma como essas áreas são conectadas à solução de SaaS determina o valor geral para você e seus usuários de dispositivos móveis.  Conectividade onipresente significa que as pessoas e dispositivos podem usar dispositivos e aplicativos em qualquer lugar, e é essencial que o gerenciamento de identidade de usuário acompanhe as demandas dessa conectividade. Nunca é demais enfatizar que o modo como você gerencia a identidade e autenticação de usuário é fundamental para o sucesso de sua solução de gerenciamento de dispositivos móveis.

A sincronização de serviços de diretório local para a solução de SaaS é outra área fundamental a ser considerada ao definir sua estratégia de gerenciamento de dispositivos móveis. A maioria das organizações prefere manter uma infraestrutura local de diretório de dispositivo e usuário, mas precisa estender essas contas para uma variedade de serviços baseados em nuvem. Isso pode incluir apenas uma solução de gerenciamento de dispositivos móveis baseada em SaaS, mas na maioria dos cenários, as organizações precisam integrar as contas de usuários e dispositivos em vários tipos diferentes de serviços baseados em nuvem. Isso pode incluir aplicativos, dados ou serviços Web de terceiros baseados em nuvem. Manter suas contas de diretório de usuário e dispositivo sincronizadas é a base de uma solução de gerenciamento de identidade bem projetada. Depois de integrar seu diretório local ao diretório na nuvem, você também poderá habilitar o SSO (logon único) para permitir que os usuários entrem em todos os serviços usando suas credenciais locais. O <token>Intune</token> e o Office 365 podem aproveitar essa integração para habilitar o SSO com aplicativos SaaS que a organização talvez queira usar.

### Perguntas sobre identidade e conectividade de diretório

Como parte do planejamento de ciclo de vida do gerenciamento de SaaS, você deve responder às seguintes perguntas de planejamento sobre gerenciamento de identidade e conectividade de diretório:

- A solução de SaaS dá suporte a serviços integrados de autenticação de usuário? Nesse caso, ela dá suporte ao tipo de serviços de diretório que você está usando em sua infraestrutura local?
- Você precisa dar suporte à autenticação de dispositivos móveis e usuários para aplicativos ou serviços locais e/ou internos?
- A solução de SaaS dá suporte à autenticação de usuário e dispositivo móvel para outros aplicativos ou serviços baseados em SaaS externos ou de terceiros?
- Como a solução de SaaS gerencia ameaças e anormalidades relacionadas à identidade?
- A solução de SaaS dá suporte à implementação e ao gerenciamento de MFA (autenticação multifator)?
- Quais tipos de objetos de serviços de diretório você precisa estender para a solução de SaaS? A solução de SaaS tem restrições para determinados tipos de objeto?
- Quais requisitos locais são necessários para estender os serviços de diretório para a solução de SaaS?
- Depois de conectados à solução de SaaS, como os objetos de diretório de usuário e dispositivo móvel são replicados ou sincronizados com o serviço de nuvem? As configurações de sincronização são personalizáveis ou fixas?
- Todos os atributos de objeto de diretório são sincronizados com a solução de SaaS? Você precisa sincronizar atributos personalizados de objeto de diretório?
- Os serviços de diretório locais são hospedados em um único local ou em um agrupamento lógico? Caso contrário, a solução de SaaS dá suporte à sincronização de vários serviços de diretório em vários locais e agrupamentos lógicos?

## Conectando-se com as plataformas existentes de gerenciamento de clientes

A maioria das organizações tem uma plataforma existente de gerenciamento local de clientes para gerenciar servidores e computadores desktop. A forma como você integra o gerenciamento de dispositivos móveis neste sistema provavelmente terá um impacto substancial nos custos de infraestrutura de TI, processos de administração de gerenciamento de dispositivos, suporte de inventário e relatórios de dispositivos e a integração total com outros serviços e aplicativos críticos para os negócios. Ao conectar essas duas plataformas, as empresas podem aproveitar as economias de escala de uma única plataforma de gerenciamento unificado.

### Perguntas sobre como se conectar às plataformas existentes de gerenciamento de clientes

Como parte do planejamento de ciclo de vida do gerenciamento de SaaS, você deve responder às seguintes perguntas de planejamento sobre conexão da solução de SaaS com as plataformas existentes de gerenciamento de clientes:

- Sua plataforma de gerenciamento local de clientes dá suporte à integração com a solução de SaaS? Nesse caso, existem:
 - Limitações do tipo de solução de SaaS?
 - Limitações nos tipos de dispositivos com suporte?
- Quais são os requisitos para conectar sua plataforma de gerenciamento local de clientes à solução de SaaS? Especificamente, existem:
 - Requisitos de servidor físico ou dispositivo?
 - Requisitos de serviços de diretório ou esquema de diretório?
 - Requisitos de DNS (Serviço de Nomes de Domínio)?
 - Requisitos de identidade?
 - Requisitos de configuração ou atualizações de plataforma de gerenciamento de cliente?
 - Conectividade de rede e/ou requisitos de configuração de segurança de rede?
- As informações existentes de configuração de cliente ou dispositivo (políticas, perfis e configurações) podem ser compartilhadas ou utilizadas na solução de SaaS? Essas informações precisam ser recriadas?
- Depois que as duas plataformas forem conectadas, como os clientes são gerenciados? Os diferentes tipos de clientes são gerenciados em um sistema de administração unificada ou gerenciados separadamente?
- Como as atualizações e alterações na solução de SaaS são integradas à plataforma de gerenciamento local de clientes? Este é um processo de configuração automática ou manual?

>[!TIP]
>Lembre-se de fazer anotações de cada resposta e entender a lógica por trás da resposta. As tarefas posteriores apresentarão as opções disponíveis e as vantagens/desvantagens de cada uma delas.  Responder a essas perguntas ajudará você a escolher a opção mais adequada às suas necessidades comerciais.


<!--HONumber=Jul16_HO3-->


