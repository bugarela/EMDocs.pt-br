---
title: "Cenários de produtividade móvel gerenciada"
description: "A abordagem moderna da Microsoft ao EMM fornece gerenciamento inigualável de aplicativos do Office 365 e permite que sua equipe realize seu melhor trabalho em qualquer dispositivo, mantendo os dados da empresa seguros simultaneamente."
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 09/16/2016
ms.topic: article
ms.prod: 
ms.service: ems
ms.technology: 
ms.assetid: 452d7991-fa90-4100-afc4-47c4e7b18949
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e90ab882127f59e73eb739f073b96d80f4c0e429
ms.openlocfilehash: 72bed249099bd40a15e06d0ef7250ac87364cf1b


---

# Cenários de produtividade móvel gerenciada do EMS
O Microsoft Enterprise Mobility + Security adota uma abordagem moderna para gerenciamento de mobilidade e fornece gerenciamento inigualável de aplicativos do Office 365 e permite que sua equipe realize seu melhor trabalho em qualquer dispositivo, mantendo os dados da empresa seguros simultaneamente. É claro que antes de entrarmos em tarefas de implementação você deve saber o que deseja fazer. Para começar a implementar o EMS para cenários de produtividade móvel, você precisará ter algumas metas de negócios bem definidas e um entendimento de como recursos e serviços EMS podem ajudá-lo a atingir essas metas. Isso é importante se você for novato em mobilidade corporativa ou estiver migrando de outro produto.

A melhor maneira de alinhar as tarefas de implementação do EMS às metas de negócios expressar o que você deseja realizar em termos dos cenários que você deseja habilitar para seus funcionários, parceiros e TI.  Abaixo estão introduções curtas para os cenários mais comuns de produtividade móvel gerenciada que dependem do Intune, juntamente com links para obter mais informações sobre como implementar cada um deles.

>[!NOTE]
>Você deseja saber como a equipe de TI da Microsoft utiliza o Intune para permitir que os funcionários da Microsoft acessem recursos corporativos em seus dispositivos móveis enquanto também mantêm os dados corporativos protegidos? [Leia este estudo de caso técnico](https://www.microsoft.com/itshowcase/Article/Content/588) para ver em detalhes como o a equipe de TI da Microsoft utiliza o Intune e outros serviços para gerenciar identidades, dispositivos e aplicativos e dados.

## Proteger o acesso e os dados da empresa do Office 365 em dispositivos gerenciados com o Microsoft Intune
Usar o Intune para proteger dados corporativos no Office 365 (email, documentos, mensagens instantâneas, contatos) não poderia ser mais fácil para você ou perfeito para seus usuários. O Intune fornece uma solução de acesso condicional integrada de modo exclusivo que garante os usuários não possam acessar dados do Office 365, a menos que eles atendam aos requisitos de conformidade da empresa (coisas como ter realizado a MFA (autenticação multifator), registrado seu dispositivo no Intune, estar usando o aplicativo gerenciado, versão do sistema operacional com suporte, PIN do dispositivo, etc). Os aplicativos móveis do Office 365 disponíveis em suas respectivas lojas de aplicativos são fornecidos com recursos de contenção de dados especificamente projetados para serem configurados pelo Intune. Esses recursos permitem a você impedir que os dados sejam compartilhados com aplicativos (por exemplo, o aplicativo de email nativo) e locais de armazenamento (por exemplo, Dropbox) que não são gerenciados pelo TI. Toda essa funcionalidade é integrada diretamente no Office 365 para que você não precise implantar ou gerenciar nenhuma infraestrutura adicional para obter esse valor.

Saiba mais: [Proteger o acesso e os dados da empresa do Office 365 com o Intune](https://docs.microsoft.com/intune/understand/secure-office365-data-with-intune).


## Proteger o acesso e os dados da empresa locais com o Intune
A maioria das estratégias de mobilidade empresarial começam com um plano para permitir que dispositivos móveis de funcionários acessem dados locais e de email da empresa armazenados em servidores de aplicativos, como o Microsoft Exchange, hospedado em sua rede corporativa. O Intune fornece uma solução de acesso condicional integrada de modo exclusivo para Exchange Server, que garante que nenhum aplicativo móvel possa acessar emails até que o dispositivo seja registrado com o Intune e seja compatível com as políticas da empresa. E ele faz isso sem precisar implantar outro computador do gateway na borda da sua rede corporativa!

Indo além do email, o Intune dá suporte à habilitação do acesso a aplicativos móveis que precisam de acesso seguro aos dados locais, como um servidor de aplicativo de linha de negócios. Isso geralmente é feito usando certificados gerenciados pelo Intune para o controle de acesso combinado com um gateway de VPN padrão ou o proxy no perímetro, como o Proxy de Aplicativo do Microsoft Azure AD. Nesses casos, a única maneira de acessar os dados corporativos é registrar o dispositivo no gerenciamento. Depois de registrado, o Intune garante que os dispositivos que acessam dados corporativos sejam compatíveis com suas políticas.  Além disso, a Ferramenta de Encapsulamento de Aplicativos e o SDK de Aplicativo do Intune podem ser usados para ajudar a conter os dados acessados dentro de seu aplicativo de linha de negócios, portanto, ele não pode passar dados corporativos para serviços ou aplicativos não gerenciados do consumidor.

<!-- Learn more -->


## Proteger o acesso e os dados da empresa do Office 365 em dispositivos não gerenciados com o Intune
Uma prática de implantação comum do Office 365 é exigir que os dispositivos se registrem no gerenciamento, caso eles precisem ser totalmente provisionados com configurações de aplicativos/certificados/Wi-Fi/VPN corporativas, que geralmente é o caso para dispositivos corporativos. No entanto, se o usuário simplesmente precisar acessar email corporativo e documentos, que é geralmente o caso para dispositivos de propriedade pessoal, eles poderão simplesmente usar os aplicativos móveis do Office 365 e ignorar o registro de seu dispositivo completamente! Nessa situação, o Intune pode ser usado para habilitar funcionários, fornecedores e parceiros a acessar dados da empresa em seus dispositivos não gerenciados, facilmente e com segurança.

As políticas de restrição de dados do Intune para dispositivos não gerenciados ajudam a manter o controle de quem e quais aplicativos podem acessar dados do Office 365 com recursos avançados de prevenção contra perda de dados. Não importa se o dispositivo já estiver sendo gerenciado por uma solução de MDM não Microsoft. Na verdade, se você desejar, poderá continuar usando essa solução e, além disso, ainda será capaz de adicionar os recursos avançados de prevenção contra perda de dados e controle de acesso para aplicativos móveis do Office 365 que Intune fornece. De todo modo, ao proteger os dados da empresa sem exigir o registro, você economizará dinheiro sem necessidade de manter servidores e atingirá um percentual mais elevado de usuários em conformidade com as políticas da empresa, sem que eles precisem permitir que o TI gerencie seus dispositivos pessoais.

<!-- Learn more -->


## Habilitar um programa BYOD na sua organização
O BYOD continua a crescer em termos de popularidade entre organizações como um meio para reduzir os custos com hardware ou aumentar as opções de produtividade móvel para os funcionários. Praticamente todos têm um smartphone pessoal hoje em dia, então por que colocar outro no seu bolso? O principal desafio sempre foi convencer os funcionários a registrar seu dispositivo pessoal no gerenciamento, uma vez que eles têm receio do que seu departamento de TI poderá ver e fazer com seus dispositivos. Quando o registro de dispositivo não é uma opção viável, o Intune oferece uma abordagem alternativa de BYOD de simplesmente gerenciar os aplicativos que contêm dados corporativos. O Intune protege os dados corporativos mesmo se o aplicativo em questão acessa dados corporativos e pessoais, como no caso de aplicativos móveis do Office.  Como administrador, você pode exigir que os usuários acessem o Office 365 dos aplicativos móveis do Office e configurem os aplicativos com políticas que mantêm os dados protegidos (criptografados, protegidos por PIN, etc.).

<!-- Learn more -->


## Gerenciar dispositivos da empresa com o Intune
A maioria dos trabalhadores responsáveis por informações são móveis hoje em dia e precisam ser produtivos ao usar dispositivos móveis da empresa. Esses funcionários precisam de acesso contínuo a todos os aplicativos e dados corporativos e a qualquer momento, onde quer que eles estejam; você, enquanto isso, precisa garantir que os dados corporativos estejam seguros e que os custos administrativos sejam mantidos baixos.

Para o TI, tentar manter o ritmo registrando muitos dispositivos móveis da empresa manualmente, um de cada vez, pode ser um grande desafio. Para ajudar a solucionar esse problema, o Intune oferece soluções de gerenciamento e provisionamento em massa que estão integradas com as principais plataformas de gerenciamento de dispositivos corporativos no mercado, incluindo o Programa de Registro de Dispositivo Apple e a plataforma de segurança móvel Samsung KNOX.  A criação centralizada das configurações de dispositivo com o Intune torna o provisionamento de dispositivos corporativos algo que pode ser altamente automatizado e lhe poupar muito tempo.

O Intune torna fácil para você atribuir um dispositivo da empresa novo a um funcionário de modo que tal dispositivo, quando ligado, guie o funcionário por um fluxo de configuração personalizado pela empresa que, por sua vez, configura tal dispositivo perfeitamente com políticas de segurança para proteger os recursos da empresa (criptografia de disco rígido, PIN do dispositivo, etc), políticas de configuração que ajudam a mantê-los produtivos (perfis de certificado/email/Wi-Fi/VPN) e um conjunto de linha de base de aplicativos. Depois, o funcionário pode usar o aplicativo do Portal da Empresa do Intune para acessar aplicativos corporativos opcionais disponíveis para ele. E o melhor de tudo é que isso é feito sem você fazer nada após entregar o dispositivo a ele.

<!-- Learn more -->

## Alinhar uma estratégia de implantação e gerenciamento do Windows 10 do EMS com necessidades comerciais
O EMS oferece a flexibilidade, por meio de ambos os processos tradicional e moderno de ciclo de vida de gerenciamento, de escolher a melhor forma de implantar e gerenciar o Windows 10 em sua organização. Você pode continuar usando o System Center Configuration Manager para implantar e gerenciar dispositivos Windows 10 com controles de política avançados ou gerenciá-los na nuvem com apenas o Intune para o gerenciamento moderno de dispositivos. Na verdade, você ainda poderia usar ambos com MDM híbrido e ter alguns dispositivos com gerenciamento baseado em agente com o Configuration Manager, enquanto outros seriam gerenciados pelo Intune via OMA-DM e MDM.

<!-- Learn more -->


## Habilitar uma solução de dispositivo compartilhado de uso limitado com o Intune
Às vezes, seus funcionários precisam usar dispositivos, aplicativos ou navegadores que você não pode gerenciar, como os computadores públicos em feiras de negócios e lobbies de hotel. Você deve permitir que seus funcionários acessem o email corporativo deles? Os trabalhadores responsáveis por tarefas estão fazendo cada vez mais uso de tecnologias móveis. Por exemplo, tablets compartilhados agora são comuns para os funcionários de lojas varejistas. Proteger os dados da empresa e a simplicidade da experiência do usuário são requisitos críticos nesse caso. Por esse motivo, os tablets geralmente são entregues para os funcionários em um modo de uso limitado, de modo que um único aplicativo de linha de negócios é a única coisa com a qual o funcionário pode interagir. O Intune permite que você provisione, proteja e gerencie centralmente em massa esses tablets iOS e Android compartilhados ou de quiosque configurando-os para funcionar nesse modo de uso limitado.

<!-- Learn more -->

### Saiba mais



<!--HONumber=Oct16_HO1-->


