---
title: Descrição de Serviços do Enterprise Mobility + Security para o governo dos Estados Unidos
description: Os planos de Alta GCC do EMS são assinaturas mensais e licenciados por usuário.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: ems
ms.suite: ems
ms.openlocfilehash: a9f886f5d9d0851c79ab163cff22125c1aebd6f0
ms.sourcegitcommit: cfa80b7829abb2fca321ebb9cfcd96dbd8c06990
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2018
ms.locfileid: "29721440"
---
# <a name="enterprise-mobility--security-for-us-government-service-description"></a>Descrição de Serviços do Enterprise Mobility + Security para o governo dos Estados Unidos 
Para atender aos requisitos únicos e em evolução do setor público norte-americano, a Microsoft criou os planos do EMS (Enterprise Mobility + Security) para os clientes do governo dos Estados Unidos. Este documento apresenta uma visão geral dos recursos específicos dos planos do EMS.  

## <a name="how-to-use-this-service-description"></a>Como usar esta Descrição de Serviços 
A Descrição de Serviços do EMS for US Government foi projetada para servir como uma visão geral de nossa oferta e abordará (1) os serviços e os recursos incluídos nesta oferta, (2) a maneira como as ofertas da versão para o governo diferem das nossas ofertas comerciais existentes e (3) o nosso compromisso atual de conformidade. Este documento define as diferenças e os compromissos exclusivos em comparação com as ofertas comerciais do EMS.  

## <a name="ems-offers-for-us-government-and-office-365-interoperability"></a>Ofertas do EMS para o governo dos EUA e interoperabilidade com o Office 365 
O Office 365 está atualmente disponível em ambientes de GCC e Alta GCC. Para saber mais sobre essas ofertas, consulte a Descrição de Serviços do Office 365 Government. A oferta comercial do EMS é totalmente interoperável com o Office 365 GCC e, no momento, estamos visando a certificação FedRAMP-Moderate para esta oferta. 

A oferta de Alta GCC do EMS é baseada na nuvem do Microsoft Azure Governamental e projetada para interoperar com as ofertas de Alta GCC e DoD do Office 365. Estamos visando a certificação FedRAMP-High para a oferta de Alta GCC do EMS. (No momento, o Microsoft Cloud App Security e a Proteção Avançada contra Ameaças do Azure não estão no escopo desta oferta.)

|Oferta do EMS|Oferta correspondente do Office 365 Government|Compromisso de Conformidade|
|-----------|-----------|-----------|
|EMS (comercial)</br>Disponível no E3 e no E5|Office 365 GCC|FedRAMP-Moderate*|
|Alta GCC do EMS</br>Disponível no E3 e no E5|Office 365 Alta GCC|FedRAMP-High| 

> [!Note]    
> A data prevista para a conformidade com a FedRAMP é o segundo semestre do ano calendário de 2018. (*Isso não inclui a certificação para o Microsoft Cloud App Security ou para a Proteção Avançada contra Ameaças do Azure.)

## <a name="about-ems-for-us-government"></a>Sobre o EMS for US Government 
Os planos de Alta GCC do EMS são assinaturas mensais e licenciados por usuário. Organizações que usam o EMS de Alta GCC se beneficiam dos seguintes recursos exclusivos:  

- O conteúdo da sua organização está fisicamente separado do conteúdo nos serviços comerciais do EMS da Microsoft. 

- O conteúdo da sua organização é armazenado nos Estados Unidos. 

- O acesso aos sistemas da Microsoft que contém seu conteúdo é restrito a uma equipe selecionada da Microsoft. 

- O EMS de Alta GCC está em conformidade com certificações e referências comuns necessárias para os clientes no setor público dos EUA. 

## <a name="customer-eligibility"></a>Elegibilidade do Cliente 
As ofertas do EMS Government estão disponíveis para (1) entidades governamentais federais, estaduais, locais e tribais dos EUA e (2) outras entidades que controlam dados sujeitos aos regulamentos e requisitos governamentais e nas quais o uso do EMS é apropriado para cumprir com esses requisitos, sujeitos à validação de elegibilidade. A validação de elegibilidade pela Microsoft incluirá a confirmação da manipulação de dados controlados ou regulados pelo governo. Esta oferta é limitada aos clientes que tenham, pelo menos, 500 estações. As entidades que tenham dúvidas sobre a elegibilidade para o EMS devem consultar sua equipe de contas.  

## <a name="location-of-customer-data"></a>Localização dos Dados do Cliente 
Os serviços do EMS de Alta GCC são prestados de datacenters fisicamente localizados nos Estados Unidos. Todo o conteúdo é armazenado em repouso apenas nos datacenters fisicamente localizados nos Estados Unidos.  

## <a name="ems-gcc-high-and-third-party-services"></a>EMS de Alta GCC e serviços de terceiros 
Vários serviços do EMS oferecem a capacidade de trabalhar perfeitamente com serviços e aplicativos de terceiros. Esses aplicativos e serviços de terceiros podem abranger o armazenamento, a transmissão e o processamento do conteúdo do cliente da sua organização em sistemas de terceiros que estão fora da infraestrutura do EMS e, portanto, não estão cobertos por nossos compromissos de conformidade e de proteção de dados. É recomendável que você examine as declarações de privacidade e de conformidade fornecidas por terceiros ao avaliar o uso apropriado desses serviços para sua organização.  

## <a name="parity-with-ems-commercial-offerings"></a>Paridade com as ofertas comerciais do EMS 
Embora nossa meta seja fornecer todos os recursos e funcionalidades comerciais aos clientes governamentais com nossa oferta de Alta GCC do EMS, há algumas funcionalidades ainda não disponíveis que gostaríamos de destacar.  
    
Estas são as lacunas conhecidas existentes entre a Alta GCC do EMS e a nossa oferta comercial de setembro de 2018:  

- Active Directory do Azure:

  - B2B

  - A galeria do Azure Active Directory com aplicativos pré-configurados não estará disponível. 

  - A auditoria do FedRAMP no MFA é separada da auditoria do FedRAMP no Azure AD e está com atraso. No lançamento, o MFA não terá a certificação FedRAMP e os clientes deverão aceitar esse serviço. 

- Microsoft Intune:

  - Só dá suporte a implantações autônomas. Ele não dá suporte à configuração híbrida com o SCCM.

  - Não dá suporte ao gerenciamento de PC herdado (com o agente do Intune). Há suporte para o gerenciamento do Windows 10 por meio do canal MDM moderno.

  - Não dá suporte ao Exchange Connector local.

  - Os recursos do Windows Autopilot e da Business Store não estão disponíveis para clientes do governo nesse momento, embora o planejamento esteja em andamento.

  - O suporte de cogerenciamento não está disponível neste momento, mas esse recurso estará disponível para nossos clientes do governo futuramente.


- Proteção de Informações do Azure:

  - O acompanhamento e a revogação de documentos não estarão disponíveis.

  - Haverá suporte para o suplemento de classificação e rotulagem apenas para Office 365 Pro Plus (versão 9126.1001 ou superior). Não há suporte para Office 2010, Office 2013 e outras versões do Office 2016.

  - Haverá suporte para o IRM (Gerenciamento de Direitos de Informação) apenas para o Office 365 Pro Plus (versão 9126.1001 ou superior). Não há suporte para Office 2010, Office 2013 e outras versões do Office 2016.

  - Não há suporte para a migração do AD RMS (Active Directory Rights Management Services) para a Proteção de Informações do Azure.

  - Não há suporte para o aplicativo do visualizador da Proteção de Informações do Azure no iOS e no Android.

  - Não há suporte para o compartilhamento de documentos e emails protegidos com usuários na nuvem comercial. Isso inclui usuários do Office 365 na nuvem comercial, usuários que não são do Office 365 na nuvem comercial e usuários com um RMS para licenças individuais.

  - Não haverá suporte para o Gerenciamento de Direitos de Informação com o SharePoint Online. Bibliotecas e sites protegidos pelo IRM não estarão disponíveis. 

- Licenciamento baseado em grupo. No momento, ele está na versão prévia na nuvem comercial. Uma vez que este recurso estiver disponível na nuvem comercial, trabalharemos para trazer essa funcionalidade para a Alta GCC do Azure Active Directory Premium.

- O Microsoft Cloud App Security e a Proteção Avançada contra Ameaças do Azure não estão incluídos na oferta do EMS E5 para Alta GCC nesse momento.
