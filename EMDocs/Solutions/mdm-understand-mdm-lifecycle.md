---
title: Compreender o ciclo de vida do MDM
description: "Este artigo fornece diretrizes sobre como o ciclo de vida da solução de gerenciamento de dispositivo móvel da Microsoft funciona, para que os clientes possam planejar e desenvolver melhor as suas soluções de gerenciamento de dispositivo móvel usando o Microsoft Enterprise Mobility + Security."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 901b52bf-2340-4847-aaff-c94fec9ee925
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 7d9c38008b5b47ea41ff331f1de763de5c119c5e
ms.openlocfilehash: bca54803722814769b45cd30244b68121d72a114


---

# <a name="understand-the-mdm-lifecycle"></a>Compreender o ciclo de vida do MDM

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Entender as diferentes áreas do gerenciamento de dispositivos móveis é importante ao projetar sua solução de gerenciamento de dispositivos móveis. A figura abaixo descreve os estágios gerais do ciclo de vida do gerenciamento de dispositivos móveis. Cada estágio tem requisitos exclusivos e perguntas a serem consideradas ao planejar sua solução. Vamos começar com o estágio de registro nesta seção. Os outros estágios serão abordados com mais detalhes ao longo deste guia.

![Estágios do ciclo de vida do gerenciamento de dispositivos móveis](./media/MDM_Figure_03.png)

**Estágios do ciclo de vida do gerenciamento de dispositivo móvel**

## <a name="device-enrollment-and-configuration"></a>Registro e configuração de dispositivo
O gerenciamento de dispositivos móveis começa com o registro inicial e a configuração de dispositivos em sua solução de gerenciamento de dispositivos móveis. Simplicidade, facilidade de registro e registro são os principais fatores para o sucesso do ciclo de vida do gerenciamento de dispositivos móveis. Se o registro inicial do dispositivo for difícil ou excessivamente confuso, você e seus usuários poderão ficar relutantes em prosseguir com uma solução de gerenciamento de dispositivos móveis, o que significa que você não pôde aproveitar os recursos, benefícios e proteções que a solução de gerenciamento de dispositivos móveis pode oferecer.

O registro do dispositivo móvel em soluções de gerenciamento de dispositivos móveis é normalmente iniciado de duas maneiras:

- Registro gerenciado pelo administrador
- Autorregistro do usuário/proprietário
 
O registro gerenciado pelo administrador oferece uma experiência de registro gerenciada centralmente e normalmente é centralizado no registro em massa de vários dispositivos usando uma única conta de diretório. Isso será útil se você precisar registrar vários dispositivos de propriedade da empresa em sua solução de gerenciamento de dispositivos móveis.

Com o autorregistro, o usuário/proprietário do dispositivo registra seu dispositivo na solução de gerenciamento de dispositivos móveis. Isso é normalmente usado em cenários BYOD (“traga seu próprio dispositivo”), embora ele também possa ser usado em cenários em que a empresa possui o dispositivo. Esse tipo de registro normalmente usa um modelo de registro “baseado em push”, em que os dispositivos são disparados automaticamente para se registrarem na solução de gerenciamento de dispositivos móveis quando o usuário tenta se conectar à rede corporativa ou ao recurso de rede no dispositivo. Os usuários às vezes também podem optar por registrar seus dispositivos antes de se conectarem à rede ou aos recursos de uma organização.

O registro e a configuração de dispositivos móveis incluem o seguinte:

- Implantando, acessando e gerenciando serviços e aplicativos internos e externos
- Aplicar configurações de acesso e segurança do dispositivo
- Protegendo dispositivos contra ameaças de segurança

Na maioria dos casos, quando um dispositivo móvel é registrado em uma solução de gerenciamento de dispositivos móveis, o dispositivo recebe automaticamente políticas e permissões atribuídas que você associou à conta de diretório do usuário do dispositivo e/ou ao grupo ao qual o próprio dispositivo está associado nos serviços de diretório. Dependendo da solução de gerenciamento de dispositivos móveis, a maior parte da configuração e do provisionamento de permissões e políticas de dispositivo é feita antes do registro do dispositivo. Em seguida, as configurações de política e conformidade entram em vigor logo após o registro dos dispositivos, evitando lacunas entre o registro e a conformidade.

## <a name="device-enrollment-and-configuration-planning-questions"></a>Questões de planejamento de registro e configuração do dispositivo

Para planejar o gerenciamento do ciclo de vida de MDM, responda às seguintes perguntas de planejamento sobre configuração e registro do dispositivo:

- Os dispositivos móveis serão registrados por você, pelos usuários ou por ambos?
- Você precisa da capacidade de registrar dispositivos móveis em massa?
- Qual é o número máximo de dispositivos de que você precisará para registrar em massa?
- As plataformas de sistema operacional móvel em sua organização exigem diferentes recursos e requisitos de registro em massa?
- Quantos dispositivos cada usuário normalmente usará e precisará registrar?
- A solução de gerenciamento de dispositivos móveis tem um limite de registro de dispositivo por usuário?
- Quais são os requisitos (conectividade, aplicativo, agente de gerenciamento, portal da empresa, suporte) para que os usuários registrem dispositivos?
-  Isso é diferente dos requisitos para o registro gerenciado pelo administrador?
-  Quais são os requisitos de registro para o sistema operacional de cada dispositivo para o qual você precisa dar suporte?
-  Os sistemas operacionais de dispositivos móveis em sua organização exigem requisitos especiais ou exclusivos de registro?
-  A solução de gerenciamento de dispositivos móveis dá suporte a registros conectados e sem fio?
-  Quais são os requisitos de hardware (se houver) para dar suporte aos registros do dispositivo?
-  Quais são os requisitos de conectividade e segurança de rede para dar suporte aos registros do dispositivo?
-  Você precisa de políticas específicas de conformidade do dispositivo aplicadas a dispositivos após o registro inicial?
-  Você precisa de políticas específicas de segurança do dispositivo aplicadas a dispositivos após o registro inicial?
-  Você precisa da capacidade de configurar ou definir um limite de tempo máximo ou mínimo para o provisionamento de políticas de dispositivo após o registro inicial?
-  Você precisa que políticas especiais de provisionamento sejam disparadas automaticamente em caso de falhas de registro?

##<a name="device-management"></a>Gerenciamento de dispositivos
A forma como os dispositivos móveis são gerenciados, tanto da sua perspectiva quanto da perspectiva do usuário do dispositivo, é um componente fundamental de uma solução de gerenciamento de dispositivos móveis.

Por exemplo, talvez você queira integrar a maneira como os dispositivos móveis são gerenciados com a maneira como os dispositivos não móveis (servidores, desktops e outros dispositivos de rede) são gerenciados. Dependendo da organização, as soluções de gerenciamento de dispositivos não móveis podem ter sido implementadas muito antes que os dispositivos móveis foram introduzidos na organização. Isso pode ter tido um custo considerável e pode incluir investimentos de longo prazo nessas soluções de gerenciamento.

Entender por completo como a sua organização pode integrar soluções de gerenciamento de dispositivos móveis às soluções existentes de gerenciamento de dispositivos não móveis é provavelmente uma das atividades mais importantes para concluir durante a criação de uma solução de gerenciamento de dispositivos móveis que atende às necessidades de sua organização.

O gerenciamento de dispositivos móveis geralmente envolve diversas áreas administrativas:

- **Configuração e segurança de dispositivo:** a segurança de dispositivos móveis inclui uma ampla variedade de configurações que você pode implantar nos dispositivos gerenciados em sua organização. As configurações podem incluir a especificação do tempo, expiração e as características necessárias para o acesso a senha de dispositivo, criptografia de dispositivo e apagamento de dados de dispositivos perdidos ou roubados. Obtenha mais detalhes sobre segurança e configuração no tópico [Etapa 3 - Plano para proteção dos dispositivos móveis](mdm-step-3-plan-enhancing-mobile-devices-protection.md).
- **Gerenciamento de aplicativos:** essa área inclui o gerenciamento de implantação de aplicativos, instalação, atualização e gerenciamento de status e remoção de aplicativos. Você também pode gerenciar as restrições em determinados aplicativos não compatíveis, o que pode ser fundamental para uma estratégia geral de segurança e conformidade. Talvez existam cenários de gerenciamento de aplicativos nos quais você precisa gerenciar aplicativos em dispositivos móveis, mas não quer registrar os dispositivos na plataforma de gerenciamento de dispositivo móvel.
- **Acesso aos recursos da empresa:** o MDM também pode ajudar a gerenciar o acesso aos recursos da rede local, como servidores de email, redes Wi-Fi e recursos habilitados para VPN. Isso atende à dupla finalidade de ajudar a garantir a conformidade de segurança e facilitar que os usuários de dispositivos móveis acessem os recursos da empresa de acordo com a política da empresa. Se o acesso aos recursos da organização for excessivamente complexo ou difícil para os usuários de dispositivos móveis, eles podem optar por usar recursos da empresa não aprovados para armazenar os dados da empresa devido à facilidade.
- **Inventário e relatórios:** ao gerenciar dispositivos móveis, convém gravar e analisar eventos de plataforma e de dispositivo móveis para acompanhar a conformidade com as políticas de gerenciamento em sua organização. Os relatórios detalhados também podem fornecer dados e estatísticas em tempo real para que você possa tomar decisões melhores e mais rápidas com base no status dos dispositivos móveis e nos usuários de dispositivos móveis. Mais detalhes sobre o inventário e relatórios são incluídos em uma seção posterior.

### <a name="device-management-planning-questions"></a>Questões de planejamento de gerenciamento de dispositivo
Por enquanto, concentre-se apenas nos principais aspectos da administração, já que você ainda está definindo os requisitos. É possível refinar esses requisitos conforme você reitera seu plano e entende melhor as necessidades gerais de sua organização.</para><para>Responda às seguintes perguntas de planejamento sobre gerenciamento de dispositivos:

- Você precisa de políticas específicas de gerenciamento aplicadas a grupos de usuários, grupos de dispositivos e/ou grupos de sistemas operacionais de dispositivos?
- Você precisa de políticas específicas de gerenciamento para diferentes tipos de dispositivos? Por exemplo, políticas separadas para dispositivos de propriedade da empresa ou do usuário, ou dispositivos móveis e não móveis?
- Você precisa diferenciar os direitos e as permissões de gerenciamento de dispositivos entre várias funções ou cargos de TI? Nesse caso:
 - Qual separação dos níveis de permissão é necessária?
 - Os níveis de permissão com suporte da sua solução precisam ser personalizáveis?
 - As permissões precisam ser integradas em seus serviços de diretório de conta existentes?
- Você precisa da capacidade de implantar manual ou automaticamente o software ou os agentes da solução de gerenciamento de dispositivos móveis?
- Você precisa da capacidade de gerenciar aplicativos em dispositivos móveis, mas não precisa registrar o dispositivo em uma plataforma de gerenciamento de dispositivos móveis (nova ou existente)?
- Você deseja integrar o gerenciamento de dispositivos móveis com uma solução existente de gerenciamento de dispositivos não móveis? Nesse caso:
 - Você deseja gerenciar todos os dispositivos em um console de gerenciamento unificado ou de um portal?
 - Quais são os requisitos de integração de sua solução existente de gerenciamento de dispositivos não móveis?
 - Como a sua solução existente de gerenciamento de dispositivos não móveis dá suporte às funções e permissões de gerenciamento necessárias?
 - Existem requisitos de hardware ou de rede para conectar os serviços de gerenciamento entre as soluções de gerenciamento de dispositivos móveis e as soluções de gerenciamento de dispositivos não móveis?
 - Ambas as soluções têm sistemas de inventário e relatórios separados ou integrados?
- A solução de gerenciamento de dispositivos móveis tem um portal da empresa para que os usuários instalem seus aplicativos?
- A solução de gerenciamento de dispositivos móveis atende aos requisitos de escalabilidade de sua empresa?
- A solução de gerenciamento de dispositivos móveis dá suporte à administração remota?
- A solução de gerenciamento de dispositivos móveis dá suporte à automação?

## <a name="app-management"></a>Gerenciamento de aplicativos

Em alguns casos, talvez você não queira registrar um dispositivo móvel em um sistema de gerenciamento de dispositivo, mas ainda precise gerenciar aplicativos no dispositivo a fim de impedir que os dados da empresa vazem para outros aplicativos de consumidor ou serviços no dispositivo. Isso pode se aplicar aos funcionários que usam dispositivos pessoais para acessar recursos da empresa em um cenário de BYOD, ou até mesmo em cenários nos quais você precisa gerenciar dispositivos móveis em uma plataforma de gerenciamento de dispositivo, e gerenciar aplicativos em outra plataforma de gerenciamento de dispositivo.

### <a name="app-management-planning-questions"></a>Questões de planejamento de gerenciamento de aplicativo

Para planejar as considerações de gerenciamento de aplicativo, responda às seguintes perguntas de planejamento:

- Os dados da empresa precisam ser isolados dos dados do consumidor dentro de aplicativos em dispositivos móveis?
- Você precisa impedir que os dados sejam compartilhados por meio de ações de recortar/copiar/colar entre aplicativos pessoais e corporativos em dispositivos móveis?
- Você precisa impedir que os aplicativos façam backup ou salvem dados em outros aplicativos ou serviços?
- Você precisa habilitar políticas de prevenção de perda de dados por aplicativo?
- Você precisa restringir o conteúdo da Web exibido em um navegador gerenciado?

##<a name="device-retirementunenrollment"></a>Desativação/cancelamento do registro do dispositivo

Quando os usuários saírem de sua organização ou os dispositivos móveis forem desativados ou substituídos, você precisará garantir que os dados corporativos não serão perdidos nem comprometidos. Normalmente, as soluções de gerenciamento de dispositivos móveis dão suporte a redefinições e cancelamento de registro de dispositivo gerenciados pela equipe TI e pelo usuário. Com a maioria dos dispositivos móveis, o cancelamento do registro começa com a redefinição do dispositivo para os padrões de fábrica ou a execução de um apagamento seletivo de todos os aplicativos e dados corporativos. Em seguida, a conexão de registro do dispositivo à solução de gerenciamento é removida. No entanto, o processo varia entre os fabricantes de dispositivo móvel e as plataformas de sistema operacional do dispositivo.

### <a name="device-retirementunenrollment-planning-questions"></a>Questões de planejamento sobre desativação/cancelamento do registro do dispositivo

Responda às seguintes perguntas de planejamento sobre a desativação e cancelamento de registro de dispositivos:

- Você precisa da capacidade para que a equipe de TI e os usuários cancelem o registro de dispositivos móveis?
- Se um dispositivo for apagado seletivamente, seu registro deverá ser automaticamente cancelado da solução de gerenciamento de dispositivos móveis?
- Se os usuários de dispositivos móveis puderem cancelar o registro de seus dispositivos móveis, como será verificada a remoção de dados e aplicativos corporativos?
 - Isso é diferente para dispositivos apagados de forma seletiva e para dispositivos redefinidos para a configuração padrão de fábrica?

>[!TIP]
>Lembre-se de fazer anotações de cada resposta e entender a lógica por trás da resposta. As tarefas posteriores apresentarão as opções disponíveis e as vantagens/desvantagens de cada uma delas.  Responder a essas perguntas ajudará você a escolher a opção mais adequada às suas necessidades comerciais.



<!--HONumber=Nov16_HO4-->


