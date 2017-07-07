---
title: "Implementação de uma solução para proteger o email e os anexos da empresa"
description: "Prepare e implemente uma solução para proteger o conteúdo de email e os anexos da empresa."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: edc744d8-97d9-42e0-8906-6f0dedd8d629
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: 4a7537775ce2c6c19850720f789ea5882d062aec
ms.contentlocale: pt-br
ms.lasthandoff: 07/07/2017


---

# <a name="implementing-your-solution-for-protecting-email-and-attachments"></a>Implementação de sua solução para proteger o email e os anexos
Este artigo ajuda você a se preparar e implementar uma solução para proteger o conteúdo de email e os anexos da empresa.

## <a name="what-you-should-consider-when-planning-your-implementation"></a>O que você deve considerar ao planejar sua implementação:

-   **Suporte à plataforma do dispositivo**: você também deve considerar se deseja permitir acesso a email em plataformas que não tenham suporte no Intune. O gerenciamento de dispositivos móveis do Intune dá suporte aos seguintes sistemas operacionais:

    -   Apple iOS 7.1 e posterior (dispositivos iOS 6.0 e 7.0 já registrados anteriormente permanecem registrados, mas não é possível registrar novos dispositivos)

    -   Google Android 2.3.4 e posterior (inclui Samsung KNOX)

    -   Windows Phone 8.0 e posterior

    -   Windows RT e posterior

    -   Computadores com Windows 8.1 e posterior

-   **Tipos de aplicativos de email**: a solução EMS atualmente dá suporte a clientes que usam o protocolo EAS e aplicativos do Outlook (anteriormente Accompli no iOS e Android).

-   **Políticas**: a solução EMS e seus componentes têm várias políticas através das quais acesso e segurança são gerenciados. Determine quais políticas seu administrador de TI precisa configurar. As três políticas chave a serem usadas para pesquisar e planejar ao proteger o acesso ao email e dados de email são:

    -   **Políticas de conformidade do aplicativo**: determine o que conformidade significa para a sua empresa. O Intune inclui várias regras que podem ser definidas, mas todas essas regras podem ou não se aplicar à sua empresa. Você pode alterar as políticas a qualquer momento, mas é recomendável determinar um conjunto básico de políticas para a sua empresa. Políticas de conformidade são direcionadas a grupos de usuários e de dispositivos do Intune.

    -   **Políticas de acesso condicional**: políticas de acesso condicional são destinadas a grupos de segurança do Azure AD. Determine quais usuários serão direcionados pelas políticas e se há usuários que precisam ser isentos. O acesso condicional tem suporte tanto na solução baseada em nuvem quanto na implementação híbrida.

    -   **Gerenciamento de dispositivo móvel**: determine quais aplicativos devem ser gerenciados e as políticas MAM que você precisa aplicar a eles.

-   **Considerações sobre o gerenciamento de dispositivos:**selecione a opção de gerenciamento de dispositivo que melhor atende aos requisitos da sua organização antes de implementar a solução. Há duas opções:

    -   Unificar o System Center Configuration Manager com o Microsoft Intune para gerenciar todos os dispositivos por meio de um único console. Isso é chamado de *implementação híbrida*. Vantagens dessa abordagem:

        -   Console de gerenciamento único com controles avançados de gerenciamento de direitos para gerenciar PCs tanto localmente quanto em dispositivos móveis

        -   Recursos avançados de direcionamento e implantação

        -   Alta escala para empresas muito grandes

    -   Gerencie os dispositivos móveis através do Microsoft Intune separadamente dos dispositivos locais usando o System Center Configuration Manager. Isso é chamado de *Implementação autônoma do Intune*. Vantagens dessa abordagem:

        -   Console simples baseado na Web desenvolvido especificamente para gerenciamento de dispositivos móveis

        -   Acesso rápido aos recursos mais recentes

    Embora a migração sempre seja possível, é altamente recomendável que você tome essa decisão antes de implementá-la, uma vez que ela influenciará muitas decisões que serão tomadas no processo de implantação.

-   **Seu ambiente Exchange**:

    -   Implantação de conectores do Exchange e como eles se conectam ao balanceadores de carga de rede são implementados.

    -   Exchange Online – é multilocatário ou dedicado? Se for dedicado, descubra em que arquitetura seu locatário está. Isso determinará se o acesso condicional baseado no Azure AD pode ser usado ou se é necessário um conector local.

-   **Sincronização do Azure AD e ADFS (Serviços de Federação do Active Directory) ou outro serviço federado de terceiros**:

    -   O acesso condicional deve funcionar para clientes que tenham federado seus serviços de identidade para o ADFS. Regras de acesso de cliente geralmente ainda serão aplicadas, no entanto, é recomendável realizar um teste completo. Os requisitos para sincronização de diretórios e do ADFS são não diferentes para o Office 365.

    -   Serviços de federação de terceiros, como o Ping, também devem funcionar. Recomenda-se testar antes da implementação.

## <a name="on-premises-implementation"></a>Implementação local
Se você tiver uma implementação existente do System Center Configuration Manager, Active Directory e/ou do Exchange Server, pode estender a infraestrutura existente com integração com Intune, Azure AD e Office 365. Usando essa implementação híbrida, você pode fornecer uma experiência de gerenciamento consistente entre vários dispositivos locais e na nuvem. O Intune e o Configuration Manager oferecem um conjunto similar de recursos para permitir o acesso restrito de email com base no estado do dispositivo.

Para implementações de Exchange Online Dedicado, se você pode aproveitar a nuvem com base a solução descrita anteriormente ou a implementação híbrida depende de como é a sua implementação atual. Converse com sua equipe de conta para determinar o que a sua implementação envolverá.

## <a name="operations-and-incidence-response"></a>Operações e resposta de incidência
Depois de implementar a solução, será preciso gerenciar o ambiente e identificar possíveis riscos à segurança. O Intune e o Azure AD têm recursos de monitoramento e relatórios que podem ajudar a monitorar e a responder rapidamente no caso de um incidente de segurança.

Aqui estão alguns dos recursos de relatório:

-   Alertas e relatórios Intune ajudam a monitorar o status e a integridade dos dispositivos gerenciados pelo Intune.

-   O Azure AD tem auditoria e registro em log de atividades. Você pode monitorar itens como alterações de senha e gerenciamento de usuários. O Azure Active Directory Premium inclui alertas e relatórios de segurança de anomalia avançados. Esses alertas são baseados em relatórios com base em aprendizado de máquina detalhados mostrando atividade de logon, padrões de acesso inconsistentes e áreas de ameaças em potencial.

## <a name="where-to-go-from-here"></a>Onde ir daqui
Para obter instruções passo a passo sobre como implantar uma solução para proteger o conteúdo de email e anexos da empresa, consulte um destes tópicos, dependendo de seu ambiente específico:

- [Usar o acesso condicional com o Microsoft Intune](conditional-access-intune.md)
- [Usar o acesso condicional com o Microsoft Intune e o Configuration Manager](conditional-access-intune-configmgr.md)

