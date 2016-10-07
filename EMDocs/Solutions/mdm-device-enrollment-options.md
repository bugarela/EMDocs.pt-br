---
title: "Opções de registro do dispositivo"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/3/2016
ms.topic: solution
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 54082b94-1d21-44d5-9fba-af6e04397def
ms.reviewer: 
ms.suite: ems
ms.custom: microsoft-intune
translationtype: Human Translation
ms.sourcegitcommit: 0808c833aa2b6f36baa8d8f48ce797cc9f18aafa
ms.openlocfilehash: 9b4956f7a4e48bebbbc41fdef050198a06e53525


---


# Opções de registro do dispositivo

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

O registro de dispositivos no Microsoft Intune, seja autônomo ou conectado ao System Center 2012 R2 Configuration Manager (ConfigMgr), exige a preparação do serviço para os dispositivos. O registro de dispositivos móveis no MDM para Office 365 também exige a ativação do MDM, definição das configurações básicas e inclusão de cada usuário em uma [política de segurança](https://technet.microsoft.com/library/ms.o365.cc.newdevicepolicy.aspx), sendo que cada usuário deverá responder a uma mensagem de registro na próxima vez que entrar no Office 365 em seu dispositivo móvel. Eles devem concluir as etapas de ativação e registro em cada dispositivo móvel que usarão para acessar os emails e documentos do Office 365.

O Intune autônomo precisa ser configurado para definir a solução de Autoridade de Gerenciamento de Dispositivos Móveis, que pode ser uma infraestrutura do Intune ou do ConfigMgr local. Isso significa basicamente “qual plataforma de gerenciamento você deseja usar para gerenciar dispositivos registrados pelo Intune – Intune *ou* ConfigMgr?”” É *muito importante* entender o [impacto de escolher a melhor opção](/Intune/deploy-use/enroll-devices-in-microsoft-intune) para a sua organização, já que a solução de gerenciamento não pode ser facilmente alterada depois de escolhida. Se precisar alterar essa configuração posteriormente, você precisará entrar em contato com o Suporte da Microsoft para obter assistência. Para locatários do Office 365, você pode designar e alterar com mais facilidade a autoridade de MDM entre o MDM para Office 365 e o Intune. Você pode alternar facilmente a autoridade de gerenciamento no nível do usuário alterando a atribuição de licença de um usuário. 

Para a maioria das organizações que já está usando o ConfigMgr para gerenciar PCs, servidores e outros dispositivos, conectar a solução local ao Intune e gerenciar dispositivos com o ConfigMgr geralmente é a melhor opção. Para atribuir a autoridade de gerenciamento de dispositivo móvel ao ConfigMgr, você precisará criar uma [assinatura do Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) e selecionar a opção para permitir que o ConfigMgr gerencie a assinatura do Intune e os dispositivos registrados pelo Intune. A assinatura do Intune também pode ser criada [dentro do console do ConfigMgr](https://technet.microsoft.com/library/jj884158.aspx).

Além disso, antes de poder registrar certos tipos de dispositivos móveis que executam diferentes tipos de sistemas operacionais móveis, você precisará preparar o serviço do Intune ou o MDM para Office 365 com requisitos específicos de configuração. Por exemplo, se você pretende registrar dispositivos baseados em iOS da Apple, você precisará **[configurar o Intune com um certificado de serviço APN (Notificação por Push da Apple)](https://technet.microsoft.com/library/dn408185.aspx)** antes do registro de dispositivos baseados em iOS. Se isso não estiver configurado, o Intune não poderá se comunicar com o serviço APN e com os dispositivos baseados em iOS. Os dispositivos móveis que executam os sistemas operacionais **[Android](https://technet.microsoft.com/library/dn764960.aspx)** ou **[Windows Phone](https://technet.microsoft.com/library/dn764959.aspx)** têm requisitos de registro separados

Suas respostas às perguntas na Etapa 1 ajudarão você a decidir como deseja que os dispositivos sejam registrados em sua solução de gerenciamento de dispositivos móveis. A tabela abaixo compara as vantagens e desvantagens de cada cenário de registro:

| Área  | Os administradores registram os dispositivos | Os usuários registram por conta própria os dispositivos |
| ------------- | ------------- | ------------ |
| Custos | Os custos de suporte/suporte técnico podem diminuir, já que administradores experientes estão realizando os registros do dispositivo. | Possível aumento nos custos de suporte ou nas chamadas de suporte técnico, os usuários menos experientes podem precisar de ajuda com o registro |
| Conveniência  | Cada dispositivo é registrado sem a interação do usuário, reduzindo erros de registro do dispositivo. Os usuários podem precisar organizar horários com você para devolver e retirar os dispositivos móveis, o que exige o agendamento e o acompanhamento do registro de dispositivo.| Registro de dispositivo mais rápido do que um processo de registro centralizado na maioria dos casos. Talvez seja mais conveniente e flexível para usuários/proprietários do dispositivo. |
| Administração | Mais fácil de dar suporte a processos de registro de dispositivo mais complexos, automatizados, em massa ou altamente personalizados Os administradores controlam de perto o registro de todos os dispositivos, fazendo uma pré-triagem efetiva de qualquer dispositivo ou usuário no início do processo de registro. | Tira de seus ombros tarefas de administração relativamente simples atribuídas aos seus usuários, economizando tempo e removendo a sobrecarga de agendamento, acompanhamento e administração |
| Segurança  | Se estiver dando suporte a uma estratégia de BYOD, há uma maior probabilidade de que os administradores possam ver ou expor informações pessoais confidenciais do usuário se controles apropriados de segurança não estiverem em vigor. | Os usuários modernos de dispositivos móveis podem achar que essa centralização é complicada e inconveniente, levando a soluções alternativas definidas pelo usuário que podem comprometer processos de conformidade e segurança de registro |

Sua organização pode desejar permitir ambos os cenários de registro, adotando uma abordagem flexível para permitir diferentes métodos para diferentes departamentos ou situações. Nesse caso, sua solução de gerenciamento de dispositivos móveis deve ter a capacidade de dar suporte a ambos os cenários.



<!--HONumber=Oct16_HO1-->


