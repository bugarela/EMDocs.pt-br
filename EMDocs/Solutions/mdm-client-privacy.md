---
title: Privacidade do cliente
description: "Este artigo fornece um conjunto de considerações de design para privacidade do cliente que devem ser usadas em um cenário de gerenciamento de dispositivo móvel."
keywords: 
author: YuriDio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c799a6c4-fe0a-4148-8e75-29e6ffdb7e6e
ms.reviewer: 
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 916404d1aaad5b4db01dff84c544e3364b7ec6ee
ms.contentlocale: pt-br
ms.lasthandoff: 11/28/2016


---

#<a name="client-privacy"></a>Privacidade do cliente

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Quando sua empresa distribui o gerenciamento de dispositivos móveis, é importante estar ciente dos limites entre a privacidade do usuário e a privacidade da organização. De preferência, sua organização já deve ter uma política de privacidade clara informando o que é esperado dos usuários a respeito da privacidade de dados. Como os dispositivos móveis podem armazenar dados da empresa e esses dispositivos viajarão com o usuário, é importante que os limites sejam bem definidos e que os usuários saibam antecipadamente qual é sua função em manter a privacidade para a sua organização.

Outra consideração é como você garantirá que os usuários estejam cientes do que esperar quando eles registrarem seus dispositivos na solução de MDM de sua organização. Com o [Portal da Empresa do Microsoft Intune](https://technet.microsoft.com/library/dn646957.aspx), é possível personalizar a política de privacidade de sua empresa para incluir uma URL com a descrição do que será coletado dos usuários quando eles usarem os dispositivos gerenciados.

Você também pode publicar os termos e condições que os usuários verão quando eles usarem o portal da empresa em seus dispositivos, independentemente de o dispositivo estar registrado ou não na solução de MDM. Os usuários devem aceitar os termos antes de acessarem o portal da empresa. Quando você atualizar os termos e condições e desejar que os usuários vejam e aceitem os novos termos, é possível marcar os novos termos e condições como uma nova versão e os usuários seguirão o mesmo processo de aceitação na próxima vez que visitarem o portal da empresa.

A mesma capacidade para exigir a aceitação dos termos e condições também está disponível quando você tem um ambiente híbrido com o ConfigMgr conectado ao Intune. Além disso, o ConfigMgr pode usar as configurações de conformidade para determinar se os dispositivos estão em conformidade com os itens de configuração que você implantou usando as linhas de base de configuração. Algumas configurações podem ser corrigidas automaticamente se estiverem fora de conformidade.

As informações de conformidade são enviadas para o servidor do site pelo ponto de gerenciamento e armazenadas no banco de dados do site. Essas informações são criptografadas quando os dispositivos as enviam para o ponto de gerenciamento, mas não são armazenadas em um formato criptografado no banco de dados do site. As informações são retidas no banco de dados até que a tarefa de manutenção de site *Excluir dados antigos de gerenciamento da configuração* as exclua a cada 90 dias.  Você também tem a capacidade de configurar o intervalo de exclusão. Essas informações de conformidade não são enviadas à Microsoft.

Como o Intune e o Office 365 são serviços baseados em nuvem, talvez os usuários também desejem estar cientes de como a Microsoft trata a privacidade do usuário em relação a esses serviços. Você pode fornecer indicadores para as informações de privacidade desses serviços, da seguinte forma:

- Central de Confiabilidade do Office 365
- Central de confiabilidade do Microsoft Intune

Privacidade é importante tanto para os usuários quanto para sua organização, e a solução de MDM que você usa deve equilibrar adequadamente as necessidades de privacidade, bem como informar os usuários sobre a política de privacidade e expectativas de sua organização. A tabela a seguir compara as opções para ajudar com requisitos de privacidade em diferentes soluções de MDM, a fim de ajudar você a escolher a opção de MDM que melhor atenda às exigências de privacidade de sua organização.

## <a name="intune-standalone"></a>Intune (autônomo)

**Vantagens**

- Usa o Portal da Empresa do Intune para publicar a política de privacidade de sua organização

**Desvantagens**

- Não tem um modelo para uma política de privacidade. Há uma pressuposição de que a sua organização tem uma política de privacidade em vigor e que o Portal da Empresa só anunciará essa política que está armazenada em outro local

## <a name="office-365-with-mdm"></a>Office 365 com MDM

**Vantagens**

- Nenhum recurso para publicar declarações de privacidade

**Desvantagens**

- Nenhum recurso para publicar declarações de privacidade

## <a name="hybrid-intune-with-configmgr"></a>Híbrido (Intune com ConfigMgr)

**Vantagens**

- Usa o Portal da Empresa do Intune para publicar a política de privacidade de sua organização
- Um único console de gerenciamento para os dispositivos móveis registrados de dispositivos locais e na nuvem

**Desvantagens**

- Se a organização não tiver uma infraestrutura local do ConfigMgr atual, será necessário planejar, instalar e configurar essa plataforma antes da integração

