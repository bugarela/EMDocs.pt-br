---
# required metadata

title: Consideração sobre gerenciamento
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: ba8cc256-2075-457f-a827-7ec9213c5235

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Consideração sobre gerenciamento

Um domínio de gerenciamento é obrigatório em uma infraestrutura que oferece suporte a um modelo de BYOD. Para dar suporte total às demandas de BYOD, o domínio de gerenciamento deve ser capaz de habilitar a TI a monitorar recursos, fornecer recursos de relatórios, gerenciar recursos de computação e armazenamento, habilitar configuração e automação de dispositivo e gerenciar o provisionamento e a implantação de aplicativos.

## Monitoramento

Uma das funções do domínio de gerenciamento é monitorar as configurações de conformidade, não apenas para os ativos corporativos, mas também dispositivos móveis de propriedade dos usuários. Considerações sobre conformidade devem ser avaliadas de acordo com a de linha de negócios da empresa. Algumas empresas podem permitir que os dados corporativos residam em dispositivos dos usuários apenas se estiverem criptografados. As configurações de segurança devem ser controladas pela TI para aplicar essas políticas.

O nível de gerenciamento de dispositivos dos usuários variará de acordo com a política da empresa e a infraestrutura de BYOD que a empresa adotar. Se a empresa estabelecer que é necessário fornecer recursos de limpeza completa para ter acesso aos recursos da empresa, a TI deve aplicar essa configuração em todos os dispositivos monitorados. A TI também precisa da capacidade de redefinir os dispositivos para os padrões do fabricante, apagando todos os dados e configurações pessoais, se necessário. Use a seção a seguir para determinar as opções de monitoramento que serão necessárias para sua infraestrutura BYOD.

### Opções de monitoramento — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens de cada opção de monitoramento:

- Agente de gerenciamento instalado nos dispositivos dos usuários
    - Vantagens
        - Mais controle sobre os dispositivos dos usuários
        - Capacidade de limpeza remota
        - Capacidade de limpeza seletiva
        - Implantação mais rápida de aplicativos e gerenciamento do ciclo de vida
    - Desvantagens
        - É necessário instalar um agente de gerenciamento nos dispositivos dos usuários
        - Mais invasivo sob a perspectiva dos usuários
        - Exige uma infraestrutura de gerenciamento de back-end para compatibilidade com o agente
- Agente de gerenciamento não instalado
    - Vantagens
        - Nenhum agente de gerenciamento é instalado nos dispositivos dos usuários
        - Imposição de políticas disponíveis apenas da perspectiva do aplicativo (por exemplo, ActiveSync)
    - Desvantagem
        - Limitação de opções disponíveis de TI para gerenciamento de dispositivos

Como você pode ver na tabela anterior, ao criar a solução de infraestrutura BYOD, você precisará de um agente instalado nos dispositivos dos usuários se desejar impor a política da empresa.

Se a empresa optar por dar suporte a diferentes tipos de dispositivos, você precisará compreender os recursos dos dispositivos, como criptografia de armazenamento, opções de conectividade VPN e linguagens de programação com suporte. Avalie o que pode ser implementado para estar em conformidade com as políticas da empresa. Monitoramento de dispositivos para atender a conformidade pode ser feito impondo políticas. Considere habilitar a criptografia de dispositivo enquanto os dados estiverem em repouso em dispositivos de usuários; isso pode ajudá-lo em sua estratégia de vazamento de dados. Impor políticas como desbloqueio de senha, histórico de senhas e senhas fortes pode dar segurança semelhante em dispositivos locais e móveis.

Configurações de conformidade no Configuration Manager permitem à TI gerenciar a configuração e a conformidade de servidores, laptops, computadores desktop e dispositivos móveis da empresa. Considere usar as configurações de conformidade padrão integradas no Gerenciador de Configurações para dispositivos móveis como uma linha de base e, a partir daí, personalizar de acordo com as necessidades da empresa. Para saber mais sobre configurações de conformidade no Configuration Manager, consulte [Introdução às configurações de conformidade no Configuration Manager](https://technet.microsoft.com/en-us/library/gg682139.aspx).

Usando a limpeza seletiva do Windows, a TI pode proteger os dados corporativos da empresa que serão distribuídos entre dispositivos pessoais ou corporativos. Os desenvolvedores podem criar aplicativos para usar uma política de limpeza seletiva do Windows em dados e protegê-los em um domínio da Internet que pertença à empresa. Para saber mais sobre a Limpeza Seletiva do Windows, confira Windows Selective Wipe for Device Data Management (Limpeza Seletiva do Windows para gerenciamento de dados de dispositivo).

## Relatórios

Relatar os recursos do dispositivo ou simplesmente compreender como esses dispositivos estão funcionando é fundamental para a TI manter o controle dos dispositivos conhecidos. Os relatórios podem ser usados para entender melhor o ambiente atual. Estas são algumas perguntas que surgirão quando você estiver tentando entender não apenas o ambiente, mas também os recursos de alguns dispositivos móveis:

- Quantos dispositivos iOS estão sendo usados na sua organização?
- Que versões do iOS esses dispositivos executam?
- Quais aplicativos corporativos estão instalados nos dispositivos?
- Algum dispositivo na sua organização é desbloqueado?

Considere o uso de uma solução de gerenciamento que possa fornecer relatórios personalizáveis e inventário de dispositivos. Ao escolher essa opção, você permitirá uma abordagem mais flexível para a TI quando for necessário obter mais informações sobre dispositivos dos usuários. A TI deve poder ter relatórios sobre todos os dispositivos registradas locais e na nuvem. A capacidade de geração de relatórios para o sistema de gerenciamento pode estar localizada local ou na nuvem — ou pode ser uma combinação de ambos, o que é chamado de solução híbrida. Use a tabela a seguir para determinar qual opção de relatório é apropriada para sua empresa.

### Opções de relatório — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens de cada opção de relatório:

- No local
    - Vantagens
        - Relatório centralizado
        - Totalmente controlado pela TI
        - Personalizável
        - Controles de segurança gerenciados no local
    - Desvantagens
        - Não é possível enumerar nativamente dispositivos localizados externamente
        - Maior sobrecarga administrativa em relação às soluções baseadas em nuvem
- Baseado em nuvem
    - Vantagens
        - Capacidade de relatar dispositivos que ingressaram no serviço de nuvem
        - Custo efetivo
        - Disponibilidade de relatório (criar e exibir relatórios de qualquer lugar)
        - Menores custos administrativos em comparação com uma solução local
    - Desvantagens
        - Não é possível enumerar nativamente dispositivos que estão no local
        - Geralmente requer assinatura mensal do serviço
- Híbrida
    - Vantagens
        - Capacidade de relatar dispositivos que ingressaram no serviço de nuvem
        - Custo efetivo
        - Disponibilidade de relatório (criar e exibir relatórios de qualquer lugar)
        - Integração à solução de gerenciamento local
    - Desvantagens
        - Geralmente requer assinatura mensal do serviço.

Ao combinar o Microsoft Intune com o System Center 2012 R2, você pode obter relatórios do local e de dispositivos baseados em nuvem. O Gerenciador de Configurações inclui vários relatórios integrados prontos para uso para UDM, incluindo relatórios de aplicativos, inventário de hardware e gerenciamento de configurações. Você não precisará criar relatórios personalizados ou separados para gerenciamento de PC e dispositivo móvel; essas funções podem ser integradas.

Para saber mais sobre os recursos de relatórios do Configuration Manager, confira [Introdução à geração de relatórios no Configuration Manager](https://technet.microsoft.com/library/gg682105.aspx).

## Computação e armazenamento

Depois de novos aplicativos serem desenvolvidos e acessados remotamente por usuários usando seus próprios dispositivos, o desempenho de aplicativos poderá ser prejudicado se a solução não tiver sido bem planejada. Embora este guia de considerações de design não pretenda oferecer uma análise mais profunda sobre considerações de desempenho, é preciso responder perguntas sobre a infraestrutura de gerenciamento:

- A solução de gerenciamento atual que a empresa usa é capaz de gerenciar o armazenamento e recursos para a plataforma que ofereçam suporte aos aplicativos acessados de dispositivos dos usuários de computadores? 
- A solução de gerenciamento atual que sua empresa usa pode aumentar os recursos de computação e armazenamento para a plataforma que oferece suporte ao acesso de aplicativos de dispositivos dos usuários de acordo com um conjunto de regras pré-estabelecido?
Se a solução de gerenciamento estabelecida não for capaz de resolver esses dois requisitos, considere usar uma solução de gerenciamento que possa gerenciar computação e armazenamento abordando os dois requisitos principais mostrados na tabela a seguir.

### Recursos de gerenciamento de computação e armazenamento — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens de cada recurso de gerenciamento de armazenamento:

- Pool de recursos
    - Vantagens
        - Capaz de alocar recursos de computação e pool de armazenamento de diferentes locais
        - Alto nível de disponibilidade.
        - Mais robusto que soluções que não são capazes de aproveitar o pool de recursos
    - Desvantagens
        - Poucas soluções de gerenciamento são capazes de aproveitar o pool de recursos
        - Sobrecarga inicial para implementação pode ser maior se a empresa ainda não estiver usando princípios de computação em nuvem em seu datacenter
- Resiliência
    - Vantagens
        - É possível alocar dinamicamente recursos de computação e pool de armazenamento com base na demanda
        - Alto nível de disponibilidade
        - Mais fácil de gerenciar depois da implementação
    - Desvantagens
        - Poucas soluções de gerenciamento são capazes de aproveitar o recurso de elasticidade
        - Sobrecarga inicial para implementação pode ser maior se a empresa ainda não estiver usando princípios de computação em nuvem em seu datacenter

O System Center 2012 R2 tem a capacidade de usar o pool de recursos e a elasticidade para gerenciar o armazenamento e computação. O System Center 2012 R2 também integra o armazenamento com a otimização de diferenciação discos para reduzir os requisitos de armazenamento, permitindo que uma grande porcentagem de dados de disco seja compartilhada entre vários discos virtuais, otimizando os custos de armazenamento. Servidores virtualizados usando o System Center 2012 R2 e que serão consumidos por aplicativos usados por usuários remotos podem aproveitar essa tecnologia.

Para saber mais sobre recursos de armazenamento do System Center 2012 R2, confira [O que há de novo no VMM no System Center 2012 R2](https://technet.microsoft.com/library/dn246490.aspx). 

## Automação

A automação pode ser empregada para corrigir dispositivos fora de conformidade, e a TI pode atribuir diferentes níveis de gravidade de não conformidade. Você deve considerar o uso de automação em diferentes áreas de BYOD. Por exemplo, como automatizar a implantação de novos serviços que serão consumidos pelos dispositivos móveis? E como você deve automatizar o processo de autorização para dispositivos móveis?

Embora você vá ver que todos os subdomínios BYOD apresentados podem aproveitar automação, a responsabilidade de automatizar recursos é do subdomínio de gerenciamento. A automação pode ser integrada no sistema operacional. No entanto, a solução de gerenciamento que a empresa adotará será responsável por estender esses recursos e fornecer maneiras de aliviar tarefas diárias da TI durante o monitoramento e o relatório dos resultados da automação.
A opção de automação mais avançada no System Center 2012 R2 é o Windows PowerShell. Para saber mais sobre a automação do System Center 2012 R2, confira [System Center Automation with Windows PowerShell](https://technet.microsoft.com/library/dn507037(v=sc.20).aspx) (Automação do System Center com o Windows PowerShell). No entanto, outra opção está disponível, fornecendo uma forma mais simples, mas não muito robusta, de automatizar tarefas: sequência de tarefas. Use a tabela a seguir para avaliar as vantagens e desvantagens de cada opção.

### Opções de automação — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens de cada opção de automação:

- Windows PowerShell
    - Vantagem
        - Integrado ao sistema operacional Windows
        - Mais robusto que a sequência de tarefas
        - Passível de script
        - Pode usar princípios de programação, como procedimentos, loops e matrizes
        - Fornece recursos além da plataforma de gerenciamento
    - Desvantagens
        - Seu uso exige mais habilidades técnicas
        - Dependendo da tarefa em questão, desenvolver o script de automação inicial poderá exigir mais tempo
- Sequência de tarefas
    - Vantagens
        - Fácil de usar
        - Capacidade nativa disponível no System Center
    - Desvantagens
        - Funcionalidade limitada
        - Não passível de script
        - Os recursos estão limitados a algumas tarefas no System Center

## Implantação e provisionamento

A próxima etapa é entender as considerações para implantação e provisionamento de aplicativos para dispositivos remotos. Dois perguntas importantes devem ser respondidas:

- Como os usuários acessam os aplicativos de seus próprios dispositivos?
- Como a TI irá provisionar esses aplicativos para os usuários de forma eficiente e amigável?

A solução de gerenciamento adotada pela empresa também é responsável por abordar a distribuição e o provisionamento de software, não importa a plataforma que o usuário esteja usando. Os usuários devem poder acessar com segurança um local centralizado de seus dispositivos e instalar os aplicativos que estão autorizados a usar para executarem seus trabalhos.

Um desafio nesta área é poder gerenciar plataformas diferentes e preservar a uma interface de gerenciamento centralizado que permita à TI identificar rapidamente os dispositivos que estão conectados locais e na nuvem. Você deve considerar a adoção de uma plataforma de gerenciamento que possa consolidar ambos (local e nuvem) e também uma plataforma de gerenciamento que seja capaz de gerenciar sistemas Windows e não Windows.

Para gerenciamento centralizado local, você pode usar o Gerenciador de Configurações. Usando essa opção, a TI pode aproveitar o recurso Registro Enterprise para registrar os dispositivos com o servidor do Gerenciador de Configurações da empresa. Para saber mais sobre como gerenciar dispositivos usando o Configuration Manager, confira [Gerenciar Dispositivos Móveis com o Configuration Manager e o Microsoft Intune](https://technet.microsoft.com/en-us/library/jj884158.aspx).

Para gerenciar outras plataformas que não sejam dispositivos baseados em Windows, você pode aproveitar o serviço de nuvem Microsoft Intune. O Portal da empresa Microsoft Intune pode ser usado para registrar, gerenciar e instalar aplicativos licenciados. Os usuários podem ter acesso fácil a aplicativos e instalá-los em seus dispositivos. 

>[!TIP] 
>Para saber mais sobre o Microsoft Intune, consulte a [página do Microsoft Intune](/intune/understand-explore/introduction-to-microsoft-intune). 

Embora essas sejam duas opções, você pode integrar ambas para oferecer implantação e provisionamento de aplicativo de um único local. Use a tabela a seguir para identificar qual opção se ajusta ao seu projeto de BYOD.

| **Requisitos de design**                                             | **Opções de implantação e provisionamento**                |
|---------------------------------------------------------------------|--------------------------------------------------------|
| Implantar e provisionar aplicativos aos dispositivos localizados locais apenas.      | Microsoft System Center 2012                           |
| Implantar e provisionar aplicativos para dispositivos localizados fora da empresa.   | Microsoft Intune                                       |
| Implantar e provisionar aplicativos para dispositivos não Windows.                   | Microsoft Intune                                       |
| Implante e provisione aplicativos em dispositivos localizados apenas no local, implante e provisione aplicativos em dispositivos localizados fora da empresa ou implante e provisione aplicativos em dispositivos não baseados em Windows.       | Microsoft Intune integrado ao Configuration Manager
                                                                    


<!--HONumber=Apr16_HO4-->


