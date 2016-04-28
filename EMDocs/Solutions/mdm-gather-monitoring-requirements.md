---
# required metadata

title: Reunir os requisitos de monitoramento
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: ac136523-8089-409b-b74d-2d4c0ce399d4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Reunir os requisitos de monitoramento

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Monitorar e capturar informações de status e eventos para dispositivos móveis é essencial para garantir que os usuários e dispositivos estejam em conformidade com suas políticas corporativas e estratégia de segurança. Isso é especialmente importante para as organizações que precisam estar em conformidade com as normas regulamentares governamentais e diretrizes de conformidade do setor.

Os relatórios também podem fornecer informações valiosas sobre software, hardware e licenças de software em sua organização para ajudar no gerenciamento de inventário. 

Lembre-se da importância da privacidade do usuário ao estabelecer diretrizes de monitoramento e de relatórios, especialmente quando for possível para os usuários registrarem dispositivos pessoais na solução de gerenciamento de dispositivos móveis de sua organização. Sua organização não deve ser capaz de capturar, monitorar, relatar nem compartilhar qualquer atividade nem informação pessoal.

Em geral, as soluções de gerenciamento de dispositivos móveis dividem o monitoramento em duas áreas gerais:

- **Registro em log:** captura e armazenamento de informações e status de aplicativos de dispositivo móvel e dispositivos móveis.
- **Relatórios:** exibição de relatórios ou notificações, inclusive relatórios padrão e personalizáveis que podem ser criados sob demanda e relatórios de status de painel e de resumo automáticos.

## Perguntas de planejamento do monitoramento

Responda às seguintes perguntas sobre o planejamento do monitoramento de dispositivos:

- De que tipos de relatórios regulares para dispositivos móveis você precisará?
 - Inventário de dispositivo?
 - Uso do dispositivo?
 - Acesso ao dispositivo?
 - Aplicativos de dispositivo?
- Os relatórios precisam ser compartilhados?
 - Entre as funções de TI?
 - Fora da organização de TI?
 - Acessados remotamente (fora da rede corporativa)?
- Que tipos de problemas com dispositivos você precisará identificar?
- Que tipos de eventos capturados no monitoramento precisarão ser tratados? Em qual período?
- Você precisará de relatórios personalizados e sob demanda?
- Depois que o registro de um dispositivo é cancelado, eventos de inventário e relatório específicos devem ser capturados?
- Depois que o registro de um dispositivo é cancelado, os eventos de inventário e relatório herdados devem ser arquivados/mantidos?
 
>[!TIP]
>Lembre-se de fazer anotações de cada resposta e entender a lógica por trás da resposta. As tarefas posteriores apresentarão as opções disponíveis e as vantagens/desvantagens de cada uma delas.  Responder a essas perguntas ajudará você a escolher a opção mais adequada às suas necessidades comerciais.


<!--HONumber=Apr16_HO2-->


