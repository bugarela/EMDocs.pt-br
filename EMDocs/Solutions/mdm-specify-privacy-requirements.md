---
# required metadata

title: Especificação dos requisitos de privacidade
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: d02d3ec2-706a-4e03-977c-b7c06cbd4ebd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Especificação dos requisitos de privacidade

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).


Na etapa anterior, você definiu as tarefas de gerenciamento de dispositivos, incluindo gerenciamento de distribuição de conteúdo e gerenciamento de dispositivos. Nesta tarefa, o objetivo é definir os requisitos de privacidade para o conteúdo da empresa que residirá no dispositivo móvel. 

>[!TIP] Leia a solução Gerenciamento simplificado de dispositivos móveis e computadores em um ambiente híbrido para saber mais sobre a distribuição de conteúdo para dispositivos móveis.

Os requisitos de privacidade e conformidade de uma organização variam de acordo com o setor, regulamentos aplicáveis e tipo de negócio. Por exemplo, talvez você queira que a sua solução de MDM permita executar inventários básicos de hardware, inventários de software, coleções de arquivo e distribuição de software em dispositivos móveis. O inventário de hardware e a distribuição de software geralmente têm suporte por padrão. 

Tenha em mente de que as questões de privacidade que se aplicam aos computadores cliente em relação ao inventário e distribuição de software também se aplicam aos dispositivos móveis. 

Antes de escolher uma solução de gerenciamento de dispositivos móveis, considere seus requisitos exclusivos de privacidade. Considere o seguinte exemplo:

- Privacidade do cliente: permitir que os usuários usem seus dispositivos móveis para se conectar e usar os recursos da empresa também significa que eles devem entender a política de privacidade de sua organização e como isso afeta sua privacidade.
    - Você precisa fornecer aos usuários a política de privacidade de sua empresa, e o que ela deve incluir?
        - Em caso afirmativo, a solução de MDM inclui a capacidade de fornecer facilmente uma política de privacidade aos usuários?
    - A solução de MDM armazena informações ou dados de dispositivo móvel do usuário na nuvem?
        - Em caso afirmativo, como privacidade do usuário é mantida na nuvem? 
- Quem tem acesso aos dados?
- Como a privacidade dos dados é mantida?
- Classificação e conformidade dos dados: é importante definir o que constitui os dados da empresa e como eles serão protegidos. Ter políticas e mecanismos em vigor para classificar os dados deve fazer parte do plano para garantir a privacidade ao gerenciar dispositivos móveis.
    - Você pode identificar ou classificar os documentos ou dados da empresa que residirão no dispositivo móvel?
        - Em caso afirmativo, que tipo de direitos ou permissões de dados ou documentos tem suporte?
    - Essa classificação será transmitida com os dados ou o documento, independentemente do dispositivo móvel que o usuário estiver usando?
    - Qual tipo de dados ou documentos pode (ou não) ser classificado?
    - Os requisitos de conformidade afetarão o modo como você escolhe a plataforma de gerenciamento de dispositivo móvel?
        - Em caso afirmativo, enumere esses requisitos antes de selecionar sua plataforma de gerenciamento de dispositivo móvel.

Leia a [Política de Privacidade do Microsoft Online Services](http://www.microsoft.com/server-cloud/products/intune-trust-center/privacy.aspx) para entender melhor como os serviços do Microsoft Cloud, incluindo o Intune, manterão a privacidade do usuário

<!--HONumber=Apr16_HO2-->


