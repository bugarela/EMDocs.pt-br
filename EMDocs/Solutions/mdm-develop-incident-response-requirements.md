---
# required metadata

title: Desenvolver os requisitos de resposta a incidentes
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 6f9fd9b3-492b-48e1-871c-e5abefe1293a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Desenvolver os requisitos de resposta a incidentes

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Embora muitas organizações já tenham um plano de IR (resposta a incidentes) em vigor, verifique se o plano inclui dispositivos móveis e as etapas necessárias no caso de um incidente ser relatado nesses dispositivos. Se a sua empresa estiver adotando apenas agora uma solução de mobilidade, provavelmente o plano de IR atual não cobre dispositivos móveis. 
Se a sua organização não tiver um plano de IR, é importante trabalhar junto à sua equipe de segurança para entender os requisitos à medida que você desenvolve um, e para que você saiba as perguntas certas a serem feitas e escolha a melhor solução de MDM para as suas necessidades. 
 
>[!TIP]Leia [Respondendo a incidentes de segurança de TI](https://technet.microsoft.com/library/cc700825.aspx) para entender melhor os requisitos mínimos de um plano de IR.

Ao projetar sua solução de MDM, lembre-se de responder às seguintes perguntas para garantir que os dispositivos móveis possam ser gerenciados se houver um incidente.

- Sua organização tem um Plano de Resposta a Incidentes existente?
    - Em caso afirmativo, inclui processos e procedimentos para lidar com dispositivos móveis comprometidos?
- A política de resposta a incidentes abrange cenários em que um usuário final relata a perda de seu dispositivo móvel?
    - É permitido apagar todo o dispositivo para evitar o vazamento de dados? 
        - Em caso afirmativo, sua empresa tem uma política de backup em vigor para os dados que residem em dispositivos móveis?
- Sua organização tem procedimentos diferentes para dispositivos de propriedade da empresa e dispositivos pessoais em caso de perda?
    - Se sim, quais são esses procedimentos?
    - Esses procedimentos afetarão a seleção da solução de MDM?
- Se um usuário perder seu dispositivo móvel pessoal, mas não autorizar sua empresa a apagar todo o dispositivo, a solução de MDM permite apagamentos seletivos do dispositivo?
- Quando um dispositivo móvel estiver comprometido e você precisar impedir que esse dispositivo distribua aplicativos maliciosos para a rede corporativa, a solução de MDM permite impor políticas que possam rapidamente conter o dispositivo comprometido?
- A solução de MDM permite planejar possíveis ataques a fim de poder tomar medidas proativas para resolver problemas?
- A solução de MDM permite identificar quando um arquivo está infectado com malware, usando um console de gerenciamento?



<!--HONumber=Apr16_HO2-->


