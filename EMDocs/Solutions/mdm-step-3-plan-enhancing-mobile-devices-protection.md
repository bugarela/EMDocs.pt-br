---
# required metadata

title: Planejar o aprimoramento da proteção de dispositivos móveis
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: a4504456-a241-4380-ab92-3bc14c91347c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Planejar o aprimoramento da proteção de dispositivos móveis

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Enquanto os usuários remotos e locais podem ser mais produtivos acessando os recursos da empresa em seus dispositivos móveis, permitir que eles façam isso também aumenta as ameaças de segurança que você precisará reduzir para ajudar a proteger os dados de sua empresa e manter a privacidade do usuário. Sua empresa pode ter requisitos específicos sobre como conciliar essas necessidades. As regras de conformidade podem variar dependendo do setor no qual sua empresa opera, por exemplo, o que pode levar a diferentes decisões sobre design.
 
No entanto, há alguns aspectos gerais de segurança no gerenciamento de dispositivos móveis para explorar e estar em conformidade, independentemente do setor. Eles são mostrados na figura abaixo.

![Principais recursos de segurança para a plataforma do MDM](./media/MDM_Figure_08.png)

## Recursos de segurança em uma solução de MDM

Este diagrama mostra os principais recursos de segurança necessários em qualquer solução de MDM. As áreas principais a serem consideradas são as seguintes:

1. Considerações sobre proteção de dados no nível do dispositivo móvel:
    - Criptografia de dados
    - Classificação de dados
    - Privacidade do cliente
    - Conteinerização
    - Imposição de política
    - Políticas de conformidade
    - Proteção
2. Considerações sobre proteção de dados em trânsito:
    - Criptografia de dados
    - Autenticação
    - Autorização
3. Considerações sobre proteção de dados em repouso em sua organização local:
    - Criptografia de dados
    - Autenticação
    - Autorização
4. Considerações sobre proteção de dados em repouso na nuvem:
    - Criptografia de dados
    - Autenticação
    - Autorização

As tarefas descritas nas seções a seguir podem ajudar você a entender como necessidades de segurança específicas influenciarão em sua decisão sobre a melhor solução de MDM para seus requisitos de negócios.

## Sobre esta etapa

Há 12 etapas nesta seção do guia. O tempo total para leitura das seções é de cerca de 36 minutos, ou você pode ir para uma seção específica

- [Reunir requisitos de proteção de dados](mdm-gather-data-protection-requirements.md)
- [Especificar os requisitos de privacidade](mdm-specify-privacy-requirements.md)
- [Especificar os requisitos de acesso](mdm-specify-your-access-requirements.md)
- [Desenvolver os requisitos de resposta a incidentes](mdm-develop-incident-response-requirements.md)
- [Planejar a criptografia de dados](mdm-data-encryption.md)
- [Planejar a segregação de dados](mdm-data-segregation.md)
- [Proteção de dispositivos móveis](mdm-hardening-mobile-devices.md)
- [Privacidade do cliente](mdm-client-privacy.md)
- [Classificação de dados](mdm-data-classification.md)
- [Autenticação e autorização](mdm-authentication-authorization.md)
- [Controle de acesso aos recursos](mdm-access-control-resources.md)




<!--HONumber=Apr16_HO2-->


