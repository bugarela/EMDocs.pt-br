---
title: "Considerações sobre usuários e dispositivos"
description: "Este artigo fornece um conjunto de considerações de design para usuários que acessam os recursos da empresa usando seus dispositivos ou dispositivos de propriedade da empresa em um cenário Traga seu próprio dispositivo."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1653116-3922-40d3-bc4f-3d845b6aaecb
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 717183b0b7f94277379ebbeee2136227d29f88ef


---

# <a name="user-and-device-considerations"></a>Considerações sobre usuários e dispositivos

O primeiro problema de usuários e dispositivos que precisa ser abordado é como as tecnologias estabelecidas afetarão a experiência do usuário ao acessar com segurança os recursos da empresa. Abordar a experiência do usuário em diferentes dispositivos pode ser um desafio, não apenas de um ponto de vista de segurança, mas também de uma perspectiva de desenvolvimento de aplicativo. O canal de comunicação entre o dispositivo e os recursos da empresa deve ser considerado para o nível adequado de segurança de rede necessário para evitar perda de dados enquanto os dados estão em trânsito.

As seções a seguir se baseiam nos componentes de subdomínio de Usuários e Dispositivos mostrados na seção [Definição de problemas do BYOD](byod-design-considerations-guide.md#problem-definition) deste guia, que é o diagrama conceitual para o domínio de problema do BYOD.

## <a name="profiles"></a>Perfis

Entender as necessidades e os requisitos dos usuários para executar seus trabalhos em dispositivos de sua escolha é essencial ao projetar sua solução de infraestrutura BYOD. Nem todos os usuários terão os mesmos requisitos; alguns usuários sempre acessarão dados locais e a imposição de políticas para eles pode ser diferente. Funcionários remotos acessam dados da empresa de uma variedade de locais e circunstâncias. Você deve considerar as opções disponíveis para atender a essas necessidades. Determine cada perfil de usuário de acordo com suas necessidades:

- Eles precisam acessar apenas os aplicativos?
- Eles precisam acessar pastas localizadas em um servidor de arquivos?

Embora a tabela a seguir sugira um conjunto de requisitos para cada perfil de usuário, você pode personalizar essa tabela, adicionando ou removendo requisitos com base nas necessidades da sua empresa. A lógica de cada categoria de perfil em comparação com o que ele deve conter é baseada nos recursos consumidos. Por exemplo, o perfil leve significa baixa utilização de recursos no dispositivo e baixos requisitos de rede. Certifique-se de entender o volume do perfil de cada usuário; isso permitirá fazer escolhas mais apropriadas em todo o restante do processo de design.

Os perfis de usuário propostos neste guia são:

- **Leves**
    - Acesso a aplicativos baseados na Web local ou na nuvem
    - Acesso a aplicativos móveis corporativos
- **Moderados**
    - Acesso a aplicativos baseados na Web local ou na nuvem
    - Acesso a aplicativos móveis corporativos
    - Acesso a aplicativos de negócios virtualizados
    - Acesso a arquivos localizados em servidores de arquivos locais
    - Acesso a arquivos localizados na nuvem
- **Intensos**
    - Acesso a aplicativos baseados na Web local ou na nuvem
    - Acesso a aplicativos móveis corporativos
    - Acesso a arquivos localizados em servidores de arquivos locais
    - Acesso a arquivos localizados na nuvem
    - Acesso a computadores usando Área de Trabalho Remota
    - Acesso a outros computadores locais

Você precisará determinar qual perfil de usuário é mais adequado para a sua solução de infraestrutura BYOD. Você pode considerar o estabelecimento de perfis de vários usuários de acordo com suas necessidades de trabalho. Idealmente, a tecnologia usada para implementar a solução de infraestrutura BYOD deve ser capaz de acomodar todos os perfis de usuário, pois os requisitos podem variar de acordo com cada pessoa.

## <a name="devices"></a>Dispositivos

A TI deve determinar se requer conhecimento de dispositivos. Por exemplo, um cenário BYOD é de funcionários por hora consultando suas folhas de ponto de ou revisando avisos corporativos ou sites sociais quando estão fora do escritório. Em muitas organizações, esses requisitos eram tradicionalmente serviços apena de LAN, mas agora podem ser abertos para dispositivos pessoais. Alguém seu consultando sua programação exige gerenciamento de dispositivos? Entender os volumes de dispositivos ajudará a TI a:

- Controlar que usuário está registrando dispositivos: um usuário registrando vários dispositivos semanalmente pode indicar atividade suspeita.
- Entenda os volumes dos dispositivos: saber quais tipos de dispositivos estão em uso na rede pode ajudar a TI a dar suporte a eles.

Considere ter um link entre o dispositivo e o usuário armazenado em um local central que possa ser usado mais tarde pela TI ao executar auditoria ou relatórios. A TI precisa passar de um estado de dispositivo desconhecido para um estado de dispositivo conhecido para habilitar BYOD. Isso permitirá à equipe de TI ter mais controle dos dispositivos que são ativos corporativos. Geralmente, as empresas abordam esse requisito de três maneiras diferentes:

- Abordagem 1: Instalação de um agente de gerenciamento no dispositivo de cada usuário.
- Abordagem 2: Registro de cada dispositivo em um repositório central sem instalar um agente de gerenciamento.
- Abordagem 3 (1+2): Registro e instalação de um agente de gerenciamento no dispositivo de cada usuário.


### <a name="unknown-to-known-device-options--advantages-and-disadvantages"></a>Opções de dispositivo desconhecidas a conhecidas — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens das opções de dispositivo desconhecidas a conhecidas:

- Instalação de um agente de gerenciamento no dispositivo de cada usuário
    - Vantagens
        - Mais controle dos dispositivos dos usuários
        - Capacidade de limpeza remota
        - Capacidade de implantação do aplicativo
        - Mais controles de segurança disponíveis para o departamento de TI controlar o dispositivo
    - Desvantagens
        - Exige que os usuários instalem um agente de gerenciamento
        - O agente de gerenciamento deve poder ser instalado em plataformas de dispositivos diferentes
        - Mais sobrecarga administrativa
- Registro de cada dispositivo em um repositório central sem instalar um agente de gerenciamento
    - Vantagens
        - Nenhum agente de gerenciamento é necessário
        - Menos sobrecarga administrativa
        - Autenticação de dois fatores de dispositivos
        - Validação do link entre usuários e dispositivos
    - Desvantagens
        - Menos controle de dispositivos dos usuários
        - Menos controles de segurança disponíveis
        - Falta de recursos para realizar a implantação e a limpeza remotas de aplicativos
- Registro e instalação de um agente de gerenciamento no dispositivo de cada usuário
    - Vantagens
        - Mais controle dos dispositivos dos usuários
        - Capacidade de limpeza remota
        - Capacidade de implantação do aplicativo
        - Mais controles de segurança
        - Autenticação de dois fatores de dispositivos
        - Validação do link entre usuários e dispositivos
    - Desvantagens
        - Exige que os usuários instalem um agente de gerenciamento
        - O agente de gerenciamento deve poder ser instalado em plataformas de dispositivos diferentes
        - Mais sobrecarga administrativa

No Windows Server 2012 R2, o novo conceito de [Ingresso no Local de Trabalho](https://technet.microsoft.com/library/dn280945.aspx) permite a TI mover o dispositivo de estado desconhecido para um estado conhecido. O dispositivo também pode ser usado como autenticação de dois fatores e logon único para aplicativos e recursos de local de trabalho. O Ingresso no Local de Trabalho está disponível nativamente no Windows 10, mas também é compatível com outras plataformas, como iOS e Android. O ingresso aproveita o DRS (Device Registration Service, serviço de registro de dispositivo). Para saber mais sobre o DRS, confira [Configurar um servidor de federação com o Serviço de Registro de Dispositivos](https://technet.microsoft.com/library/dn486831.aspx). Ingresso é uma nova tecnologia e funciona com casos de uso específicos. Confira [Proteger acesso a rec. da empresa de qualquer local e dispositivo](https://technet.microsoft.com/library/dn550982.aspx) para saber mais sobre uma solução que aproveite o Ingresso no Local de Trabalho com logon único.

Se você considerar o uso DRS, entenda que ele não fornece recursos de gerenciamento. Se sua empresa precisar de mais controles de segurança para ter mais opções disponíveis de modo a controlar os dispositivos dos usuários, considere usar o DRS em conjunto com o [registro do dispositivo móvel](https://technet.microsoft.com/library/jj733620.aspx) como a solução de agente de gerenciamento. No entanto, ao escolher essa opção, você deve ter uma assinatura do Microsoft Intune. Para saber mais sobre o Microsoft Intune, consulte a [página do Microsoft Intune](/intune/understand-explore/introduction-to-microsoft-intune).

## <a name="network"></a>Rede

O acesso à rede corporativa da perspectiva do usuário e do dispositivo deve ser abordado. Como os usuários acessarão os dados da empresa usando os próprios dispositivos? A maioria das soluções de infraestrutura BYOD somente foca minimamente no acesso remoto a partir de dispositivos dos usuários; no entanto, de uma abordagem centrada em pessoas, você deve considerar onde os usuários se encontram fisicamente. Então é preciso se concentrar não apenas no acesso remoto, mas também em como os usuários acessarão os dados locais. Além disso, você precisará considerar as questões de regulamentação específicas para alinhamento geopolítico da sua organização. Por exemplo, como os usuários que estão fisicamente localizados em um país ou região diferente podem ter acesso personalizado à rede?

Se sua empresa tiver recursos na nuvem pública que estarão acessíveis pela Internet em dispositivos dos usuários, deve considerar como será tratado o tráfego. Considere o uso de criptografia enquanto os dados estão em trânsito de dispositivos dos usuários para o provedor de nuvem. Quando os usuários acessarem recursos internos, você também deve usar a criptografia de dados.

### <a name="network-connectivity-options--advantages-and-disadvantages"></a>Opções de conectividade de rede — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens das opções de conectividade:

- VPN tradicional
    - Vantagens
        - Tecnologia desenvolvida
        - Fácil de configurar
        - Amplamente disponível em muitas plataformas
    - Desvantagens
        - Sobrecarga de protocolo VPN e protocolos de criptografia
        - Deve ser iniciado antes dos aplicativos
        - Requer interação do usuário para estabelecer a conexão
- Microsoft Direct Access
    - Vantagens
        - Experiência perfeita para os usuários (sempre ativada)
        - Permite acesso ao servidor selecionado e a autenticação IPsec com um servidor de rede de Internet
        - Permite criptografia e autenticação de ponta a ponta
    - Desvantagens
        - Exige uma infraestrutura local para compatibilidade com esse recurso
        - A solução de problemas pode ser desafiadora
        - Maior sobrecarga administrativa
        - Não está disponível em todas as plataformas
- VPN de gatilho automático
    - Vantagens
        - Fácil de configurar
        - A conexão com o servidor local é iniciada quando um aplicativo precisa ter acesso aos recursos corporativos
    - Desvantagens
        - Sobrecarga de protocolo VPN e protocolos de criptografia
        - Não está disponível em todas as plataformas
- Área de Trabalho Remota com VDI
    - Vantagens
        - Experiência do usuário perfeita
        - Mais controle sobre a área de trabalho (proteção)
        - Amplamente disponível em muitas plataformas
    - Desvantagens
        - Exige uma infraestrutura local para compatibilidade com esse recurso
        - Planejamento de capacidade de rede, armazenamento e computação deve ser cuidadosamente executado para evitar um gargalo de desempenho
        - Cada dispositivo requer um aplicativo cliente de acesso remoto
- Acesso à Web
    - Vantagens
        - Amplamente disponível em muitas plataformas
        - Criptografia disponível usando HTTPS
        - Tecnologia desenvolvida
        - Fácil de configurar
    - Desvantagem
        - Exige certificados
        - Se a infraestrutura de certificado for interna, exige uma infraestrutura PKI.
        - Exige uma infraestrutura de borda para publicar aplicativos com segurança

Depois de definir o design para acesso remoto à rede, considere como dispositivos pertencentes ao usuário irão se conectar à sua rede enquanto estiverem fisicamente conectados a ela. Os usuários que levarem seus dispositivos para o trabalho provavelmente usarão recursos Wi-Fi para conectarem-se aos recursos corporativos. Você deve considerar o uso de segmentação de rede (física ou lógica) para dispositivos de usuários para isolá-los.

Você também pode segmentar os dispositivos que se conectarão à rede Wi-Fi de acordo com a plataforma em que são executados. Considere também como proteger sua comunicação e autorização enquanto estiverem acessando recursos corporativos locais.

Você pode escolher uma segmentação física no ponto de acesso sem fio e componentes de rede (comutadores e roteadores) para isolar usuários que se conectam usando os próprios dispositivos. Também é possível implementar esse tipo de segmentação usando [Perfis Wi-Fi no Configuration Manager](https://technet.microsoft.com/library/dn261221.aspx). Uma ampla variedade de configurações de segurança está disponível, como certificados para autenticação do cliente e validação do servidor que foram provisionados usando [Como implantar perfis de certificado no Configuration Manager](https://technet.microsoft.com/library/dn270540.aspx).


### <a name="wi-fi-network-segmentation-options---advantages-and-disadvantages"></a>Opções de segmentação de rede Wi-Fi — vantagens e desvantagens

Use a lista abaixo para entender as vantagens e desvantagens das opções de segmentação Wi-Fi:

- Segmentação física
    - Vantagens
        - Segmentação de segurança de nível inferior
        - Relativamente fácil de configurar
        - Abstrai-se da plataforma (sistema operacional)
    - Desvantagens
        - A capacidade de gerenciamento pode variar de acordo com o fornecedor
        - A integração entre os fornecedores de hardware diferentes pode ser um desafio
        - Custo mais alto para implementar e manter
- Segmentação lógica (perfis de Wi-Fi)
    - Vantagens
        - Experiência perfeita para os usuários.
        - Mais fácil de gerenciar (quando comparada à segmentação física)
        - Menor custo para implementar (quando comparada à segmentação física)
        - Abstrai-se do hardware usado para conectar dispositivos
        - Compatível com várias plataformas (sistemas operacionais)
    - Desvantagens
        - Não fornece segmentação de segurança de nível inferior que a solução de hardware fornece
- Segmentação dinâmica
    - Vantagens
        - Pontos de acesso sem fio usam uma infraestrutura e SSID comuns
        - Atributos de usuário final e dispositivo provisionam dinamicamente o acesso à rede
    - Desvantagens
        - Requer o IPsec para implementação usando [NAP (Proteção de Acesso à Rede) da Microsoft](https://technet.microsoft.com/library/cc731276(v=ws.10).aspx), o que pode ser um problema em um cenário de BYOD que exija suporte para "qualquer dispositivo".

> [!NOTE]
> Para saber mais sobre Perfis de Wi-Fi no Configuration Manager, confira [Introdução a perfis Wi-Fi no Configuration Manager](https://technet.microsoft.com/library/dn261224.aspx).

O local da rede desempenha uma função importante para considerações de usuário e dispositivo. Você pode aproveitar o controle de acesso de vários fatores no AD FS para habilitar políticas de autorização por aplicativo, em que é possível permitir ou negar acesso com base em usuário, dispositivo e local de rede. Confira [Manage Risk with Multi-Factor Access Control](https://technet.microsoft.com/library/dn280936.aspx) (Gerenciar risco com controle de acesso de vários fatores) para obter mais informações sobre como configurar um ambiente para validar esse recurso.



<!--HONumber=Nov16_HO4-->


