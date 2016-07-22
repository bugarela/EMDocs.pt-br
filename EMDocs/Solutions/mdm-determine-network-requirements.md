---
title: Determinar os requisitos de rede
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 77e7cab9-2fae-4857-be5d-2b6f57e981be
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 73c37109735567642ff1dc11f9729e3ab3affd3b
ms.openlocfilehash: 40fbc4d61c4ccf574f41753bd4795562ccc82be0


---

# Determinar os requisitos de rede

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Habilitar o acesso seguro e gerenciado para uma ampla variedade de recursos corporativos por dispositivos móveis é um recurso importante de uma solução de gerenciamento de dispositivos móveis. Embora esses recursos normalmente sejam localizados em redes locais, é mais comum agora que os recursos sejam hospedados além de serviços Web baseados em nuvem e redes externas.</para><para>Como os dispositivos móveis se conectam a plataformas de email corporativo, redes virtuais privadas (VPNs) e redes sem fio (WiFi) corporativas, todos desempenham uma função importante em manter dados corporativos e outros recursos protegidos de acesso não autorizado. Igualmente importante é tornar fácil e conveniente para os usuários de dispositivos móveis terem acesso seguro a estes recursos para evitar que eles encontrem um método mais conveniente, mas não seguro de armazenar e acessar os recursos.</para></content>


## Gerenciamento de email
O email corporativo normalmente é o principal recurso de dados que a maioria dos usuários precisa acessar em uma rede corporativa, seja de um dispositivo móvel pessoal ou de propriedade da empresa. O acesso a email normalmente também é a conexão que dispara o registro do dispositivo móvel inicial. Ser capaz de gerenciar o acesso a email para dispositivos móveis em sua solução existente de gerenciamento de dispositivos não móveis e na solução de gerenciamento de dispositivos móveis ajuda a evitar falhas de cobertura do dispositivo e aumenta a proteção para os dados armazenados nos servidores de email.

A maioria das soluções de gerenciamento de dispositivo móveis fornece a proteção de acesso a email usando um ou os dois seguintes recursos:

- **Perfis de email:** ao configurar e implantar perfis de email, os administradores podem configurar automaticamente dispositivos móveis com informações apropriadas do servidor de email para que os usuários se conectem às suas caixas de correio de email. Isso ajuda os usuários a se conectarem ao servidor de email correto sem ter de lembrar os nomes corretos do ponto de extremidade do servidor de email nem os endereços de rede. Além disso, ao remover um perfil de email, os administradores podem remover email de dispositivos como parte do processo de apagamento seletivo ou redefinição do dispositivo. O gerenciamento de perfis de email pode ser um recurso na solução de gerenciamento de dispositivos não móveis ou pode ser integrado a uma solução de gerenciamento de dispositivos móveis.
- **Acesso a email condicional:** o acesso a email condicional, ou acesso a email “gerenciado”, normalmente se concentra na segurança e conformidade para acessar o email em um dispositivo móvel, em vez de a qual ponto de extremidade o dispositivo móvel se conecta. Com o acesso a email condicional, uma política de conformidade é definida e atribuída a usuários ou dispositivos individuais ou a grupos de usuários e/ou dispositivos. A política descreve os pré-requisitos que devem estar em vigor antes que um dispositivo móvel possa se conectar a um recurso de email; por exemplo, pode ser necessário um PIN no dispositivo. A política é normalmente imposta quando o dispositivo é registrado pela primeira vez, mas permanece em vigor e ativa desde que o dispositivo móvel esteja registrado no sistema de gerenciamento de dispositivos móveis.

###Perguntas de planejamento de gerenciamento de email

 Responda às seguintes perguntas de planejamento sobre o gerenciamento de email:

- Como os dispositivos móveis se conectarão ao sistema existente de email local ou hospedado na nuvem?
- Os administradores ou usuários (ou uma combinação de ambos) serão responsáveis por conectar dispositivos móveis ao seu sistema de email? Se os usuários conectarem os dispositivos móveis ao sistema de email, como eles:
 - Escolherão o ponto de conexão apropriado para acessar suas caixas de correio de email?
 - Escolherão o protocolo de conexão ou o método de conexão apropriado?
- Os dispositivos móveis precisarão atender a certos padrões de segurança e conformidade antes e durante sua conexão ao seu sistema de email?
- Você precisa da capacidade de criar políticas personalizadas de conexão de segurança de email e conformidade? Nesse caso, quais são os requisitos específicos?
- Você precisará da capacidade de importar ou exportar políticas de conexão de segurança de email e conformidade?
- Como você precisa gerenciar as conexões com o sistema de email?
 - Por usuário do dispositivo?
 - Por tipo de dispositivo?
 - Por SO do dispositivo?
 - Por grupo ou função do usuário?
- Quando um dispositivo móvel precisar ser desconectado do seu sistema de email, como os dados de email serão excluídos do dispositivo móvel?
- Os administradores e usuários também precisarão da capacidade de excluir dados de email ou a conexão ao sistema de email?
- Como a confirmação de exclusão de dados de email será verificada ou confirmada?
- Se você estiver usando um sistema de email local e baseado em nuvem, como eles são integrados à solução de gerenciamento de dispositivos móveis? 
- Os perfis de email ou as políticas de acesso gerenciado são administrados do mesmo modo ou de modo diferente da perspectiva de TI? A experiência de conexão de email do usuário é igual ou diferente, dependendo de onde sua caixa de correio está hospedada?

## Gerenciamento de conectividade de rede

Os dispositivos móveis geralmente se conectam a redes e recursos corporativos usando as seguintes tecnologias de acesso:

- **Wi-Fi:** o acesso sem fio aos recursos corporativos normalmente é fornecido como um serviço de extensão de rede local para dispositivos que estão em estreita proximidade física à rede local. Isso normalmente envolve permitir que os dispositivos móveis se conectem aos recursos da rede, conforme os usuários usam um perfil móvel de local a local em um escritório local, como salas de conferência e reunião, diferentes escritórios ou outras áreas locais. Também pode incluir o acesso sem fio de locais remotos em pontos de acesso de rede sem fio gerenciado não corporativo, como a rede doméstica do usuário ou um ponto de acesso sem fio público. Para simplificar as conexões com redes sem fio, os administradores geralmente gerenciam essas conexões usando os perfis sem fio que descrevem as configurações específicas que os dispositivos móveis devem ter aplicadas antes que eles possam se conectar à rede sem fio. Isso pode incluir a configuração automática de um nome da rede personalizado, SSID de rede, configurações de segurança, proxy de rede e se o dispositivo deve se conectar automaticamente ou não à rede sem fio quando o dispositivo estiver no intervalo.
- **VPN (Rede Virtual Privada):** o acesso remoto seguro aos recursos corporativos geralmente inclui o uso de um tipo de conexão VPN definido no dispositivo móvel. Isso geralmente é específico do fornecedor e inclui a instalação de um aplicativo de VPN no dispositivo móvel. Além disso, esses aplicativos VPN quase sempre usam certificados digitais ou credenciais de conta de usuário gerenciadas separadamente para autenticar a conexão VPN. Para simplificar as conexões às VPNs, os administradores podem normalmente gerenciar essas conexões usando perfis de VPN ou as ferramentas de gerenciamento de VPN incluídas na solução de VPN. Dependendo do suporte à integração, gerenciar conexões VPN com a solução de gerenciamento de dispositivos móveis pode ou não ser uma opção com algumas plataformas de VPN.

>[!NOTE]
>É possível ter outros recursos baseados na Web, como o SharePoint, que aproveitam o acesso seguro via SSL (Secure Socket Layer) ou TLS (Transport Layer Security). Certifique-se de que entendeu como os dispositivos móveis acessarão esses recursos ou os recursos com métodos de acesso seguro ou VPN separados.

### Perguntas de planejamento de gerenciamento de conectividade de rede

Responda às seguintes perguntas de planejamento sobre o gerenciamento de conectividade de rede:
 
- Que tipo de plataforma de VPN você implantou em sua rede local?
- A plataforma de VPN tem o suporte ou a capacidade de ser integrada à solução de gerenciamento de dispositivos móveis?
- Se a plataforma de VPN já está integrada ou tem o suporte de uma solução existente de gerenciamento de dispositivos não móveis – a solução de gerenciamento de dispositivos móveis é integrada a ambos os sistemas?
- Sua infraestrutura de Wi-Fi exigirá a atualização para acomodar um aumento das conexões de dispositivo e uma maior demanda de largura de banda?
- Como os dispositivos móveis se conectarão à sua plataforma sem fio ou de VPN local existente?
- Se os dispositivos móveis já estiverem se conectando à sua plataforma sem fio ou de VPN existente, que tipo de conexão ou protocolo os dispositivos estão usando para se conectarem?
- Serão necessárias alterações a essas conexões caso os dispositivos sejam registrados em uma solução de gerenciamento de dispositivos móveis?
- Os administradores ou usuários (ou uma combinação de ambos) serão responsáveis por conectar dispositivos móveis à sua plataforma de VPN ou sem fio? Se os usuários conectarem os dispositivos móveis à plataforma sem fio ou de VPN, como eles:
 - Escolherão o ponto de conexão apropriado para acessar a rede corporativa?
 - Escolherão o protocolo de conexão ou o método de conexão apropriado?
 - Escolherão o certificado digital apropriado para o método de conexão?
- Você deseja configurar automaticamente as propriedades e configurações da conexão VPN e sem fio nos dispositivos móveis do usuário?
 - Você precisa fornecer diferentes definições de segurança ou configuração de rede sem fio para diferentes tipos de usuários, dispositivos, sistemas operacionais de dispositivos ou grupos e funções de usuários?
 - Você precisará da capacidade de importar ou exportar políticas de conexão de segurança ou configuração sem fio e/ou de VPN?

## Gerenciamento de certificados

Certificados digitais, sejam autoassinados ou emitidos por CAs (Autoridades de Certificação) de terceiros, podem ser usados para autenticar dispositivos móveis em conexões de rede ou em recursos de rede específicos. Para simplificar o gerenciamento de certificados digitais, os administradores normalmente gerenciam os certificados usando perfis de certificados. Isso permite um método uniforme e centralizado para gerenciar certificados, incluindo como eles são criados, emitidos e renovados. Isso também ajuda os usuários se conectarem a recursos corporativos sem a necessidade de solicitar e instalar certificados manualmente ou usando um processo de segurança não aprovado.</para><para>No entanto, usar certificados para esse tipo de autenticação geralmente requer requisitos de infraestrutura local adicionais. Isso pode incluir todos ou alguns dos seguintes componentes de rede, dependendo do nível de integração com suporte da solução de gerenciamento de dispositivos móveis:

- **Serviços de diretório:** serviços de diretório, como o Active Directory da Microsoft, geralmente são necessários para conectar com segurança e gerenciar todos os outros componentes de rede.
- **Servidor de AC (autoridade de certificação):** se você estiver emitindo certificados autoassinados para a sua organização, você precisará de uma autoridade de certificação para criar, emitir, gerenciar e renovar os certificados digitais.
- **Servidor NDES (Serviço de Registro de Dispositivo de Rede):** este servidor permite que o software e os dispositivos móveis obtenham certificados com base no protocolo SCEP.
- **Servidor proxy:** dependendo de sua configuração de rede local, você poderá precisar de um servidor proxy que permita que dispositivos móveis recebam certificados usando uma conexão de Internet e sem se conectar diretamente à sua rede corporativa interna.

### Questões de planejamento de gerenciamento de certificado

Responda às seguintes perguntas de planejamento sobre o gerenciamento de certificado:

- Sua organização já exige ou usa certificados digitais para autenticar o acesso aos recursos de rede?
- Você tem uma PKI (infraestrutura de chave pública) empresarial?
- Você precisa emitir automaticamente certificados digitais para dispositivos móveis?
- Como os certificados digitais são criados, emitidos, renovados ou revogados dos dispositivos móveis?
- Os certificados digitais são gerenciados centralmente por uma AC (Autoridade de Certificação) local ou de terceiros?
- Você precisa ter diferentes certificados atribuídos para acesso a diferentes serviços de rede? Isso depende do tipo de dispositivo móvel que acessa a rede?

>[!TIP]
>Lembre-se de fazer anotações de cada resposta e entender a lógica por trás da resposta. As tarefas posteriores apresentarão as opções disponíveis e as vantagens/desvantagens de cada uma delas.  Responder a essas perguntas ajudará você a escolher a opção mais adequada às suas necessidades comerciais.


<!--HONumber=Jun16_HO4-->


