---
# required metadata

title: Desenvolver sua estratégia de adoção de gerenciamento de dispositivos móveis
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 10172816-b52d-4a55-8803-6a6805126fab

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Desenvolver sua estratégia de adoção de gerenciamento de dispositivos móveis

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Nesta tarefa, você desenvolverá a estratégia de adoção de gerenciamento de dispositivos móveis que atenderá aos requisitos de negócios identificados nas Tarefas 1 e 2. 

## Propriedade do dispositivo

Depois de examinar a atual política e estratégia de sua organização para gerenciar dispositivos, você deve ter uma lista de cenários que a sua organização pretende implementar. A seção a seguir ajudará você a entender as vantagens e desvantagens de cada cenário:

## O funcionário possui o dispositivo (BYOD)

**Vantagens** 

- Sua empresa não precisa comprar dispositivos móveis para os funcionários
- Geralmente permite que os funcionários sejam mais produtivos, já que eles usarão o dispositivo móvel de sua preferência
- Os custos de suporte diminuirão, já que a organização terá suporte mínimo em relação aos dispositivos móveis

**Desvantagens**

- Aumenta a quantidade de considerações sobre segurança para proteger os dados da empresa localizados em dispositivos pessoais
- Aumenta a probabilidade de vazamento de dados, especialmente quando não existem controles de segurança apropriados
- Capacidade de gerenciamento limitado devido às restrições de privacidade

## Dispositivo de propriedade da empresa

**Vantagens** 

- Funcionalidade de gerenciamento completo, incluindo controles de proteção e segurança de dispositivo
- Mais controle sobre os dispositivos móveis
- Capacidade de definir quais dispositivos serão usados pelos funcionários

**Desvantagens**

- Possível aumento nos custos de suporte, já que a organização manterá os dispositivos móveis
- Menos flexibilidade para os usuários finais, o que pode afetar sua produtividade
- O custo aumenta, já que a organização precisa comprar os dispositivos móveis

Em alguns cenários, as organizações adotarão os dois modelos: BYOD e dispositivos de propriedade da empresa. Nesse caso, a plataforma de gerenciamento de dispositivos deve ter a capacidade de gerenciar várias plataformas e integrá-las à atual infraestrutura local. Se a sua organização se encaixar nesse cenário, verifique se as políticas de segurança podem cobrir os dois modelos com relação à conformidade. Requisitos diferentes podem ser aplicados para cada modelo, e sua solução de gerenciamento de dispositivo móvel deve ser capaz de lidar com ambos, permitindo ao mesmo tempo que o departamento de TI mantenha o controle.

## Plataformas de dispositivos móveis com suporte

A decisão tomada em relação à propriedade do dispositivo ajudará você a identificar para quais plataformas de dispositivos móveis você dará suporte. A solução de gerenciamento de dispositivos móveis que você escolher terá de acomodar essa decisão. Em um cenário de plataforma única de dispositivo móvel, a escolha da plataforma não será tão relevante quanto no cenário de várias plataformas. Use a seção a seguir para ajudar com a escolha da solução de gerenciamento de dispositivos móveis para um cenário com várias plataformas:

### Intune (autônomo)

**Vantagens**

- Serviço de nuvem sempre ativo que dá suporte às atualizações e recursos mais recentes de MDM
- Dá suporte ao provisionamento de todos os principais sistemas operacionais de dispositivos móveis (Android, iOS, Windows 8, Windows 10 e Windows Phone)
- Permite gerenciar qualquer dispositivo móvel em qualquer local
- Opções mais avançadas de gerenciamento para dispositivos móveis
- [Gerenciamento de aplicativos móveis](http://blogs.technet.com/b/microsoftintune/archive/2015/06/18/now-available-intune-mobile-application-management-and-conditional-access-for-outlook.aspx)

**Desvantagens**

- A falta de integração com a atual solução de gerenciamento de dispositivos localizada localmente introduzirá uma interface de gerenciamento adicional para você usar
- As políticas criadas com a solução de MDM local não são replicadas para o serviço de nuvem

### MDM para o Office 365

**Vantagens**

- Integrado ao Office 365
- Se você já estiver usando o Office 365, os recursos de MDM serão facilmente utilizados para gerenciar os dispositivos móveis
- Se você já estiver usando o Office 365, não precisará usar outro console para gerenciar os dispositivos móveis

**Desvantagens**

- Conjunto limitado de recursos (veja a observação após esta tabela) para gerenciar os dispositivos móveis
- A falta de integração com a atual solução de gerenciamento de dispositivos localizada localmente introduzirá uma interface de gerenciamento adicional para você usar

### Híbrido (Intune com ConfigMgr)

**Vantagens**

- Integração nativa entre o Intune e o ConfigMgr
- Permite usar um console centralizado para implantar políticas e gerenciar PCs, servidores e dispositivos móveis locais

**Desvantagens** 

- Requer etapas adicionais de configuração para conectar o Intune e o ConfigMgr
- Se a organização não tiver uma infraestrutura atual local do ConfigMgr, será necessário planejar, instalar e configurar essa plataforma antes da integração

Se você precisar gerenciar apenas o acesso ao email de trabalho, calendário, contatos e tarefas em dispositivos móveis, saiba mais sobre os [recursos de gerenciamento de dispositivos do Exchange ActiveSync disponíveis no Office 365](https://technet.microsoft.com/library/dn792010.aspx#tasks).

## Requisitos de aplicativo

Com base nos requisitos definidos na Tarefa 1, você pode escolher a solução de gerenciamento de dispositivos móveis que melhor se adapta à sua organização. Use a tabela abaixo para comparar as opções de MDM, bem como as vantagens e desvantagens de cada opção:


### Intune (autônomo)

**Vantagens**

- Permite gerenciar aplicativos móveis durante seu ciclo de vida, incluindo a implantação de aplicativos por meio de arquivos de instalação e lojas de aplicativos, monitoramento detalhado de status de aplicativos e remoção de aplicativos. Leia Implantar software em dispositivos móveis no Microsoft Intune para saber mais.
- Permite especificar uma lista de aplicativos compatíveis que os usuários podem instalar e aplicativos não compatíveis que não devem ser instalados pelos usuários. Leia Gerenciar dispositivos usando políticas de configuração com o Microsoft Intune para saber mais.
- Permite que você defina restrições para aplicativos usando uma política de gerenciamento de aplicativo móvel. Isso ajuda você a aumentar a segurança dos dados de sua empresa restringindo operações como copiar e colar, backup de dados externos e transferência de dados entre aplicativos. Leia Controlar aplicativos usando políticas de gerenciamento de aplicativos móveis com o Microsoft Intune para saber mais.
- Oferece suporte a diferentes plataformas móveis. Leia mais sobre os dispositivos móveis com suporte em Recursos de gerenciamento de dispositivos móveis no Microsoft Intune para saber mais.
- Controle quais aplicativos estão disponíveis para usuários de VPN. Você pode selecionar os aplicativos que se conectam automaticamente à sua rede corporativa por VPN criando uma lista de aplicativos durante a configuração do perfil da VPN
- Oferece suporte a políticas MAM (gerenciamento de aplicativo móvel) que ajudam a evitar que dados corporativos vazem dos aplicativos ou serviços do consumidor.
- As políticas MAM do Intune ajudam o departamento de TI a permitir um acesso seguro aos dados corporativos de SaaS (como o Office 365) para parceiros, contratados e fornecedores, sem gerenciar seus dispositivos.


**Desvantagens**

- Não tem integração com soluções de gerenciamento de dispositivo locais, o que introduz uma interface de gerenciamento adicional para você usar ao gerenciar dispositivos móveis se você tiver uma solução local. 
- As políticas criadas com uma plataforma de MDM local não são replicadas para o serviço de nuvem, o que exige dois conjuntos de políticas de gerenciamento e conformidade (se você tiver uma solução de MDM local)


### MDM para o Office 365

**Vantagens**

- Fornece recursos de MDM em plataformas de sistema operacional, como requisitos de senha                                                                                                                                                                                                                                                                                                                                                           

**Desvantagens**

- Conjunto limitado de recursos para controlar aplicativos
- Não tem integração com soluções de gerenciamento de dispositivo locais, o que introduz uma interface de gerenciamento adicional para você usar ao gerenciar dispositivos móveis se você tiver uma solução local.
- Nenhuma capacidade de implantar aplicativos e aplicar recursos de gerenciamento de aplicativos móveis


### Híbrido (Intune com ConfigMgr)

**Vantagens**

- Herda as configurações de controle do aplicativo do Intune autônomo
- Fornece uma experiência de gerenciamento integrado (entre o Intune e o ConfigMgr)
- Aproveita os recursos de gerenciamento de aplicativo do Configuration Manager. Leia Gerenciamento de aplicativos no Configuration Manager para saber mais.
- Aproveita os recursos de gerenciamento de aplicativo do Configuration Manager. Leia Gerenciamento de aplicativos no Configuration Manager para saber mais.
- Permite usar um único console para implantar políticas e gerenciar políticas de aplicativo para PCs, servidores e dispositivos móveis locais
- Controle quais aplicativos estão disponíveis para usuários de VPN. Você pode selecionar os aplicativos que se conectam automaticamente à sua rede corporativa por VPN criando uma lista de aplicativos durante a configuração do perfil da VPN.

**Desvantagens**

- Exige etapas adicionais para configurar a integração
- Se a sua organização não tiver uma infraestrutura local do ConfigMgr, será necessário planejar, instalar e configurar a plataforma do ConfigMgr primeiro
- Sem a integração com o Intune, o ConfigMgr tem uma solução de gerenciamento de dispositivo móvel limitada com base em plataformas de dispositivos móveis com suporte. Leia Determinar como gerenciar dispositivos móveis no Configuration Manager para saber mais.


## Requisitos de acompanhamento

Entender o comportamento do usuário e conseguir identificar sua localização são fatores importantes para incluir em sua estratégia de gerenciamento de dispositivos móveis. A forma como os dispositivos serão acompanhados varia de acordo com suas necessidades e requisitos de negócios.  Diferentes recursos de acompanhamento estão disponíveis em cada sistema operacional móvel; portanto, as plataformas de dispositivos móveis que você escolher para dar suporte afetarão suas opções. Por exemplo, os requisitos de conformidade podem influenciá-lo a priorizar a adoção de plataformas de dispositivos móveis que permitam acompanhar o local do usuário e usar o isolamento geográfico.

>[!TIP]O isolamento geográfico permite monitorar a localização geográfica de um dispositivo móvel e habilitar/desabilitar os recursos de dispositivo e de rede com base nesse local. Por exemplo, o suporte ao Windows 8.1 permite que um aplicativo defina uma região geográfica e faça com que o sistema alerte o aplicativo quando o dispositivo estiver em execução ou entre ou saia dessa área. Para saber mais sobre esse recurso no Windows 8.1, leia [Isolamento geográfico, do início ao fim (XAML)](https://msdn.microsoft.com/library/windows/apps/xaml/dn342943.aspx). 




<!--HONumber=Apr16_HO2-->


