---
title: Identificar requisitos de SaaS
description: "Este artigo ajuda a identificar os requisitos do software como serviço ao planejar e desenvolver o gerenciamento de dispositivo móvel da Microsoft usando as soluções do Enterprise Mobility + Security."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 5380e56c-9c48-459e-aea5-95ad90dbb7d1
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: 68a42159dfbf6b0d435b0543466d4cec26e55b67


---

# <a name="identify-saas-requirements"></a>Identificar requisitos de SaaS

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Cada solução de SaaS terá diferentes requisitos, recursos de gerenciamento de dispositivos móveis e níveis de integração com redes e plataformas locais. Muitas soluções de SaaS oferecem locatários ou serviços de avaliação para avaliar seus recursos e funcionalidades, o que é uma parte importante de determinar qual solução realmente atende às suas necessidades. No entanto, várias soluções de SaaS podem ter diferenças sutis nos recursos e funcionalidades, dependendo do tipo de plataforma.

A maioria das soluções de SaaS tem base em três tipos de nuvem:

- Multilocatário:
- Privada (dedicada)
- Híbrido

Antes de tomar decisões sobre como você usará uma solução de SaaS para gerenciar seus dispositivos móveis, você também precisará examinar as diferenças entre esses tipos de arquiteturas de plataforma de nuvem e escolher aquela que melhor se adapta às necessidades gerais de sua organização. As soluções de SaaS individuais têm diferentes níveis de suporte para áreas como personalização, configuração de recurso, integração e funcionalidade colaborativa.

## <a name="cloud-types"></a>Tipos de nuvem

Soluções de SaaS *multilocatárias* são normalmente chamadas de infraestruturas de nuvem “pública”. Isso ocorre quando a arquitetura de software do serviço está localizada em uma única instância, mas atende a vários locatários ou organizações. A solução foi projetada para fornecer a cada locatário um compartilhamento reservado de seus serviços, como o gerenciamento de usuário ou dispositivo, configuração e suporte de dados. As contas e os serviços de locatário são separados virtualmente, com cada locatário acessando a infraestrutura da plataforma em instâncias separadas. As soluções de SaaS multilocatárias normalmente também oferecem uma economia de custo obtida do compartilhamento da infraestrutura e da distribuição dos custos indiretos entre vários locatários. A maioria das plataformas de gerenciamento de dispositivos móveis é oferecida em uma infraestrutura de plataforma SaaS multilocatária.
                
Serviços *privados* ou de nuvem dedicados são instâncias de soluções de SaaS operadas para uma única organização ou locatário. Eles podem ser serviços de nuvem privada hospedados pela organização ou serviços de nuvem privada hospedados por um provedor terceiro. As soluções de nuvem privada geralmente oferecem mais oportunidades para personalização, tanto na área de segurança quanto na área de serviços. Algumas soluções de SaaS dedicadas oferecem serviços de gerenciamento de dispositivos móveis como parte de opções mais amplas de locatário de nuvem privada.

As soluções *híbridas* de SaaS podem oferecer uma combinação de infraestruturas multilocatárias e de nuvem privada, ou uma combinação de infraestruturas hospedadas (multilocatárias ou privadas) e locais na nuvem. Uma infraestrutura híbrida também pode incluir o uso de uma solução de SaaS de nuvem externa para entregar determinados tipos de serviços (como aplicativos), mas aproveitando os recursos internos para outros tipos de serviços. A maioria das soluções de SaaS oferece a capacidade de dar suporte a uma configuração de nuvem híbrida, mas a profundidade e abrangência da integração às plataformas locais ou outras plataformas de nuvem hospedadas podem variar significativamente.

### <a name="cloud-questions"></a>Perguntas sobre nuvem

Como parte do planejamento do ciclo de vida de gerenciamento de SaaS, convém responder às seguintes perguntas de planejamento sobre tipos de nuvem:

- Qual nível de segurança é necessário para dados de dispositivo móvel armazenados em minha solução de SaaS?
- Como a solução de SaaS aborda a detecção de intrusão e a prevenção de perda de dados para dispositivos móveis?
- Sua organização precisa cumprir requisitos regulamentares, de certificação ou de conformidade para dispositivos móveis ou dados armazenados em dispositivos móveis? Nesse caso, eles exigem um nível específico de segurança, personalização, escalabilidade ou resiliência? Como a conformidade é auditada e relatada?
- A solução de SaaS precisa de conectividade com outros serviços ou plataformas de nuvem que gerenciarão os dispositivos móveis? Nesse caso, é a seguinte conectividade:
 - Pré-configurado ou padronizado?
 - Personalizável?
 - Compatível com as plataformas às quais você precisa se conectar?
- Você precisa conectar sua solução de SaaS com uma infraestrutura existente de gerenciamento local de dispositivos? Nesse caso, é a seguinte conectividade:
 - Compatível com sua plataforma de gerenciamento local de dispositivos?
 - Com suporte da solução de SaaS?
 - Compatível sem a necessidade de recursos físicos locais adicionais?
- Os serviços, aplicativos e processos baseados em nuvem para dispositivos móveis exigirão diferentes níveis de segurança, personalização, escalabilidade e resiliência?

## <a name="scalability"></a>Escalabilidade

A facilidade de escalabilidade é um dos principais motivos para considerar ou implantar uma solução de SaaS para gerenciar dispositivos móveis em sua organização. Por definição, as soluções de SaaS públicas normalmente oferecem uma capacidade praticamente ilimitada para dar suporte a qualquer quantidade de usuários ou dispositivos móveis. As soluções de SaaS privada e híbrida podem estar sujeitas a limites de escala, com base nos recursos organizacionais disponíveis. O aumento ou redução da escala para dar suporte a um número maior ou menor de usuários ou dispositivos normalmente depende de um modelo de licenciamento específico ou de um pacote de preços por usuário/dispositivo para nuvens públicas.

### <a name="scalability-questions"></a>Perguntas sobre escalabilidade

Como parte do planejamento do ciclo de vida de gerenciamento de SaaS, convém responder às seguintes perguntas de planejamento sobre escalabilidade de nuvem:

- Que tipo de planos de curto e longo prazo sua organização tem para a expansão ou contração na infraestrutura de suporte de aplicativos e dispositivos móveis?
- Com que rapidez sua organização precisará escalar serviços de suporte de gerenciamento de dispositivos móveis para cima ou para baixo?
- Qual é o número inicial de dispositivos móveis e/ou usuários que precisam de suporte na solução de SaaS? Qual é a probabilidade que esse número seja alterado no próximo ano? Os próximos 3 anos? Os próximos 5 anos?
- O número de dispositivos móveis que precisam da solução de SaaS dá suporte à alteração em um padrão regular (como periodicamente)? Ele muda de acordo com o número de projetos ativos ou inativos da organização?
- O desempenho da solução de SaaS muda dependendo da escala de usuários e dispositivos móveis com suporte? Nesse caso, em quais áreas? (nós, dados, processamento, etc.) Como o desempenho de escala é medido, relatado e auditado?

## <a name="accessibility"></a>Acessibilidade

O fácil acesso à solução de SaaS é outro componente fundamental da arquitetura de SaaS. Como a solução de SaaS está hospedada em uma infraestrutura baseada em nuvem, ela é acessível por administradores, usuários e dispositivos em qualquer local que tenha acesso à Internet. A administração de dispositivos móveis é feita por meio de um navegador. Como muitos fornecedores de soluções de SaaS operam datacenters geograficamente dispersos, os usuários e dispositivos podem acessar a plataforma “localmente”, muitas vezes evitando a latência e atrasos que podem estar associados à conexão a pontos de extremidade geograficamente distantes. A acessibilidade normalmente também pode ser expandida, integrando a solução de SaaS com plataformas de gerenciamento local de dispositivos.

### <a name="accessibility-questions"></a>Perguntas sobre acessibilidade

Como parte do planejamento do ciclo de vida de gerenciamento de SaaS, convém responder às seguintes perguntas de planejamento sobre acessibilidade de nuvem:

- Existem requisitos específicos de navegador de dispositivo móvel em sua organização? Nesse caso, a solução de SaaS dá suporte ao(s) navegador(es) necessário(s)?
- Os usuários de dispositivos móveis precisam de algum requisito especial de acessibilidade para aplicativos ou serviços?
- Sua organização precisa acessar a infraestrutura de SaaS localizada na mesma área geográfica que os dispositivos do usuário ou sua infraestrutura local? Existem implicações legais se os dados do dispositivo móvel forem armazenados ou movidos entre fronteiras internacionais?

## <a name="resiliency"></a>Resiliência

Como a infraestrutura de SaaS é baseada em nuvem e hospedada em vários datacenters, a resiliência costuma estar sujeita a menos instabilidade ou interrupções do que os tradicionais serviços hospedados localmente. Os hosts de serviço de vários locais oferecem proteção contra interrupções baseadas em geografia e interrupções de serviço usando a infraestrutura de failover e processos para replicar os dados em vários nós do datacenter. Dependendo da solução de SaaS, o acesso ao serviço pode ou não permanecer na área geográfica original durante um failover.

### <a name="resiliency-questions"></a>Perguntas sobre resiliência
 
Como parte do planejamento do ciclo de vida de gerenciamento de SaaS, convém responder às seguintes perguntas de planejamento sobre resiliência de nuvem:

- No caso de failover primário da solução de SaaS, como os serviços de gerenciamento de dispositivos móveis serão afetados?
- Como os dados de dispositivo móvel armazenados na solução de SaaS serão compartilhados na infraestrutura baseada em nuvem?
- Se o datacenter primário de SaaS do dispositivo móvel não estiver disponível, os datacenters de failover estão localizados na mesma região geográfica que o data center primário? Não há problemas se os datacenters de failover estiverem localizados fora das fronteiras internacionais das quais os dispositivos móveis estão funcionando?
- A solução de SaaS tem um SLA (contrato de nível de serviço) definido que descreve o suporte para o gerenciamento de dispositivos móveis?


## <a name="up-to-date-services"></a>Serviços atualizados

As soluções de SaaS também podem manter os aplicativos e serviços atualizados com a versão do aplicativo, recursos, atualizações de segurança e correções de bugs mais recentes. Geralmente, essas atualizações são publicadas muito rapidamente, às vezes, até mesmo diariamente. Dependendo da solução de SaaS, as atualizações podem estar imediatamente disponíveis para todos os clientes ou serem lançadas em uma abordagem em fases para pequenos grupos de clientes. Uma das maiores vantagens é que quando um bug for corrigido para um cliente, a correção poderá ser facilmente aplicada a todos os clientes que usam o serviço.

### <a name="services-questions"></a>Perguntas sobre serviços

Como parte do planejamento do ciclo de vida de gerenciamento de SaaS, convém responder às seguintes perguntas de planejamento sobre serviços de nuvem:

- Com que frequência os recursos e as funcionalidades de gerenciamento de dispositivos móveis são atualizados no serviço de SaaS?
- Qual será o impacto das atualizações de recursos e funcionalidades em seus aplicativos e serviços críticos de dispositivos móveis?
- As atualizações de recursos e funcionalidades da solução de SaaS são implantadas nos clientes em um agendamento ad hoc ou planejado?
- A solução de SaaS dá suporte a isenções de atualizações de todo o serviço para organizações individuais?
- A solução de SaaS tem diferentes agendamentos de atualização de serviço para recursos e funcionalidades de aplicativo e gerenciamento de dispositivos móveis?

>[!TIP]
>Lembre-se de fazer anotações de cada resposta e entender a lógica por trás da resposta. As tarefas posteriores apresentarão as opções disponíveis e as vantagens/desvantagens de cada uma delas.  Responder a essas perguntas ajudará você a escolher a opção mais adequada às suas necessidades comerciais.



<!--HONumber=Nov16_HO4-->


