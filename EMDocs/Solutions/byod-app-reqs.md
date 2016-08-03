---
title: Requisitos de aplicativo
description: 
keywords: 
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 0c1313b9-361f-4732-a92c-23d0dac07733
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7585b9924aabd63114657a99552af9b3e47b0a80
ms.openlocfilehash: a6a4a73495776c85a5288791a835d065460a928e


---

# Requisitos de aplicativo

Cada organização usa uma variedade de recursos técnicos para permitir que a equipe de trabalho realize suas tarefas de forma otimizada e, na maioria das vezes, a principal ferramenta é um aplicativo. Esses recursos poderiam ser combinados em uma abordagem de várias plataformas em que tecnologias diferentes são usadas para atingir uma meta determinada ou criando um aplicativo personalizado capaz de executar uma tarefa ou automatizar certos processos. É importante considerar os aplicativos ao criar a estratégia de BYOD. Os usuários usarão diferentes formatos para consumir esses aplicativos; portanto, você precisa considerar a variedade de recursos a que esses aplicativos devem ter suporte. A figura abaixo mostra como usuários e dispositivos usam aplicativos para consumir dados e as considerações para cada componente do subdomínio de aplicativos.

![Requisitos de aplicativo](./media/BYOD_Figure5.png)

A seção a seguir contém perguntas sobre os requisitos de aplicativo que você precisará responder para formular os requisitos para o design da sua solução.

## Perguntas a fazer

os requisitos de aplicativo são categorizados em seis áreas:

- Experiência
- Plataforma
- Implantação
- Armazenamento
- Rede
- Segurança


### Experiência

- Você planeja preservar a mesma experiência de usuário, independentemente dos dispositivos nos quais os aplicativos serão executados?
- Os aplicativos exigem acesso à Internet de dispositivos dos usuários?
- Os aplicativos exigem entrada via teclado?
- Os aplicativos coletam informações de usuário, como a localização geográfica?
    - Nesse caso, os aplicativos informam os usuários sobre questões de privacidade e coleta de dados durante a instalação?
- Os aplicativos exigem integração com serviços de nuvem?
- Que tipos de aplicativos você planeja disponibilizar para os usuários de BYOD (como aplicativos baseados na web e aplicativos modernos)?
- Os aplicativos foram desenvolvidos para execução em um sistema operacional específico ou eles podem ser executados em qualquer sistema operacional?
- Você planeja habilitar os usuários a usar aplicativos por meio da Área de Trabalho Remota em seus próprios dispositivos?
- Os aplicativos exigem acesso integral aos recursos corporativos, ou podem executar no modo offline?
- Os aplicativos possuem alguma integração com redes sociais?


### Plataforma

- Que tipo de plataforma de back-end é necessário para a executar esses aplicativos?
- Você prevê um aumento na atividade com a adoção de BYOD que exigirá a atualização da plataforma de back-end para os aplicativos que planeja permitir que os usuários remotos usem?
- A plataforma de back-end que oferecerá suporte aos aplicativos está localizada na mesma infraestrutura de outros servidores?
- A plataforma oferecerá suporte a esses aplicativos totalmente local ou haverá ainda servidores localizados na nuvem?


### Implantação

- Você sabe quais aplicativos estarão disponíveis para os usuários de BYOD?
- Como você planeja implantar esses aplicativos para dispositivos dos usuários?
- Quais são as opções de implantação para esses aplicativos?
- O requisito de instalação varia de acordo com o dispositivo de destino ou é o mesmo?
- Os aplicativos precisam de algum MDM (Mobile Device Management, gerenciamento de dispositivo móvel) para funcionarem corretamente?
- Você usará a Windows Store ou qualquer outra loja de aplicativos para implantar esses aplicativos?
- Os aplicativos instalam algum certificado digital durante a implantação?
    - Nesse caso, que autoridade de certificação será usada (pública ou privada)?
- Os usuários precisam estar fisicamente conectados à rede corporativa para executarem a instalação ou é possível instalar o aplicativo através da Internet?

### Armazenamento

- Que quantidade de espaço em um dispositivo de destino é necessária para instalar cada aplicativo?
- Os aplicativos criptografam os dados localizados no armazenamento do dispositivo?
- É possível instalar os aplicativos no armazenamento externo em um dispositivo de destino?
- Você prevê um aumento na atividade de armazenamento no servidor de aplicativos de back-end com a adoção de BYOD?
    - Nesse caso, você tem planos para estender a capacidade de armazenamento do servidor de aplicativos?
- Os dados consumidos pelos aplicativos estão localizados no armazenamento local, na nuvem ou em ambos?
- Os dados são consumidos por aplicativos criptografados no armazenamento do data center ou na nuvem?

### Rede

- Quais são os requisitos de rede para os aplicativos que você planeja implantar para usuários de BYOD?
- Os aplicativos criptografam os dados antes de transmiti-los por meio da rede a partir dos dispositivos dos usuários para o servidor de aplicativos no back-end?
    - Nesse caso, qual é o método de criptografia que os aplicativos usa?
- Você prevê um aumento na atividade de rede com a adoção de BYOD?
- Os aplicativos exigem conectividade de rede completa para funcionarem?
- Os aplicativos funcionam em uma rede de baixa latência?
- Os aplicativos podem ser remotamente desinstalados através da rede ou precisam ser desinstalado usando consoles os dispositivos?

### Segurança

- Os aplicativos são desenvolvidos com algum método de desenvolvimento de segurança?
- Os aplicativos fornecem recursos de autenticação?
    - Nesse caso, que método de autenticação os aplicativos usam?
- O método de autenticação aproveita serviços de nuvem?
- Os aplicativos fornecem recursos de autorização?
    - Nesse caso, que níveis de autorização os aplicativos fornecem?
- Os aplicativos utilizam a infraestrutura existente para lidar com autorização?
- Os aplicativos fornecem recursos de log?
    - Nesse caso, que dados são registrados? É possível controlar o nível de log?
- Os aplicativos fornecem validação de entrada?
- As políticas da empresa têm padrões específicos para a validação de entrada e manipulação?
    - Nesse caso, os aplicativos serão compatíveis com esses requisitos?
- Há um subsistema comum de validação ou limpeza de entrada que processe os dados de fora do sistema?
- Esses aplicativos consumirão alguma biblioteca externa, como a biblioteca JavaScript?
    - Nesse caso, você executou uma avaliação de risco de segurança para essas chamadas externas?
- Os aplicativos foram validados usando o método [STRIDE](https://msdn.microsoft.com/library/ee823878.aspx) (Falsificação, Violação, Repúdio, Divulgação de Informações Confidenciais, Negação de Serviço e Elevação de Privilégio)?
- Os aplicativos lidam com dados de identificação pessoal?
- Você executa alguma análise de privacidade para esses aplicativos?
- Os aplicativos usará blocos dinâmicos?
    - Nesse caso, esses blocos dinâmicos poderiam, inadvertidamente, causar divulgação de informações?




<!--HONumber=Aug16_HO1-->


