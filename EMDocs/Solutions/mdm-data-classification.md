---
title: "Classificação de dados"
description: "Este artigo fornece um conjunto de considerações de design para classificação de dados, que devem ser usadas em um cenário de gerenciamento de dispositivo móvel."
keywords: 
author: YuriDio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f3486381-66d5-469a-93a3-013eaaa17c07
ms.reviewer: 
ms.suite: ems
ms.openlocfilehash: fd0d97871dfca2f1b1b94d32d4961e12c51e8126
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="data-classification"></a>Classificação de dados

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

A maioria das empresas já tem uma política de [classificação de dados](http://blogs.microsoft.com/cybertrust/2014/01/28/the-importance-of-data-classification/) em vigor, e você precisará entender como a implantação de uma solução de gerenciamento de dispositivos móveis afetará essa política. Se a sua empresa não tiver uma política atual de classificação de dados, você deverá apresentar essa funcionalidade em conjunto com o planejamento de sua solução de gerenciamento de dispositivos móveis. Algumas organizações realizam a classificação de dados local no nível do servidor de arquivos usando o [ADRMS (Active Directory Rights Management Services)](https://technet.microsoft.com/windowsserver/dd448611.aspx). Outra ferramenta usada por algumas empresas é o [Microsoft Data Classification Toolkit](http://www.microsoft.com/download/details.aspx?id=27123), que ajuda as empresas a identificar, classificar e proteger dados em seus servidores de arquivos.

O Office 365 fornece alguma classificação automática de dados de email que pode ajudar a trazer à tona as informações confidenciais que devem ser protegidas. O Office 365 usa regras de transporte, incorporadas ao processamento do fluxo de email, para detectar informações confidenciais. Em seguida, o [recurso DLP](http://blogs.office.com/2013/10/28/office-365-compliance-controls-data-loss-prevention/) executa a análise detalhada do conteúdo por meio de correspondências de palavra-chave, correspondências de dicionário, avaliação de expressão regular, funções internas como validação da soma de verificação em números de cartão de crédito e outros exames de conteúdo para detectar tipos de conteúdo específico no corpo da mensagem ou anexos.

O Intune e o ConfigMgr não têm a classificação de dados interna, portanto dependem da classificação baseada em nuvem com o Azure RMS ou o ADRMS local. Outra opção é usar o [Enterprise Mobility + Security](http://www.microsoft.com/server-cloud/enterprise-mobility/overview.aspx) como a sua solução de MDM. Com o EMS, você terá acesso ao [Azure AD Premium](https://msdn.microsoft.com/library/azure/dn532272.aspx) e ao [Azure RMS](https://technet.microsoft.com/library/jj585026.aspx), que pode ser usado para classificar os dados. A classificação de dados com o Azure RMS pode ser integrada a uma solução de gerenciamento local em um ambiente híbrido.

O Intune permite ao departamento de TI atender às políticas usando políticas de conformidade, que são conjuntos de regras e configurações às quais um dispositivo deve obedecer para ser considerado compatível pelas políticas de acesso condicional. Você também pode usar as políticas de conformidade para monitorar e corrigir problemas com dispositivos, independentemente do acesso condicional. Leia [Gerenciar políticas de conformidade do dispositivo para o Microsoft Intune](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) para saber mais.

Use a tabela abaixo como referência para ajudá-lo a escolher a opção de MDM que melhor atenda aos requisitos de *classificação de dados* de sua organização.

## <a name="intune-standalone"></a>Intune (autônomo)

**Vantagens**

- Não disponível

**Desvantagens**

- Não disponível

## <a name="mdm-for-office-365"></a>MDM para o Office 365

**Vantagens**

- Regras de transporte do Exchange podem ser usadas para detectar informações confidenciais
- Aproveita a política de [DLP (prevenção de perda de dados)](https://technet.microsoft.com/library/ms.o365.cc.DLPLandingPage.aspx) no Centro de Conformidade para identificar informações confidenciais entre vários local

**Desvantagens**

- A classificação de dados não é executada com o próprio arquivo. Depois que o arquivo estiver localizado no dispositivo móvel, ele poderá ser usado sem restrições

## <a name="hybrid-intune-with-configmgr"></a>Híbrido (Intune com ConfigMgr)

**Vantagens**

- Não disponível

**Desvantagens**

- Não disponível

## <a name="enterprise-mobility--security"></a>Enterprise Mobility + Security

**Vantagens**

- Aproveita o Azure RMS para realizar a classificação de dados
- A assinatura do Azure RMS está incluída com o EMS
- Não requer uma infraestrutura local para a classificação de dados
- Pode ser integrado às soluções existentes de AD RMS locais
- A proteção está localizada no próprio arquivo, o que significa que o arquivo manterá sua classificação, mesmo que ele tenha sido salvo em um local diferente

**Desvantagens**

- Não disponível para clientes que não estão adotando a solução baseada em nuvem
