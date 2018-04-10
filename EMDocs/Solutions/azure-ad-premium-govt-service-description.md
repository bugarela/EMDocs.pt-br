---
title: Descrição de serviços do Azure Active Directory Premium Government
description: Os planos do Azure Active Directory Premium Government são assinaturas mensais e licenciados por usuário.
keywords: de autenticação
author: arob98
ms.author: mtillman
manager: mtillman
ms.date: 12/21/2017
ms.topic: get-started-article
ms.prod: ''
ms.service: active-directory
ms.technology: ''
ms.assetid: 112289b0-0336-4cc0-b471-42fc2c015c64
ms.reviewer: ''
ms.suite: ''
ms.custom: ''
ms.openlocfilehash: 7eb4740e44a5b4104de7d39667e9653e29213315
ms.sourcegitcommit: 4401a878f88cc60b3cfd90a915747fe37e333014
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2018
---
# <a name="azure-active-directory-premium-government-service-description"></a>Descrição de serviços do Azure Active Directory Premium Government

Em resposta aos requisitos exclusivos e em evolução do setor público dos Estados Unidos, a Microsoft criou os Planos do Azure Active Directory Premium Government (ou “Azure Active Directory Premium Government”). Este documento oferece uma visão geral dos recursos que são específicos do Azure Active Directory Premium Government. 

## <a name="how-to-use-this-service-description"></a>Como usar esta Descrição de Serviços

A Descrição de Serviços do Azure Active Directory Premium Government foi projetada para servir como uma visão geral de nossa oferta e cobrirá (1) os serviços e os recursos incluídos nesta oferta, (2) a maneira como as ofertas da versão para o Governo diferem das nossas ofertas comerciais existentes e (3) o nosso compromisso atual de conformidade. Este documento define as diferenças e os compromissos exclusivos em comparação com as ofertas comerciais do Azure Active Directory Premium.

## <a name="about-azure-active-directory-premium-government-environments"></a>Sobre os ambientes do Azure Active Directory Premium Government

Os planos do Azure Active Directory Premium Government são assinaturas mensais e licenciados por usuário. As organizações que utilizam o Azure Active Directory Premium Government aproveitam os seguintes recursos exclusivos:

* O conteúdo da sua organização é logicamente separado do conteúdo nos serviços comerciais do Azure Active Directory Premium da Microsoft.
* O conteúdo da sua organização é armazenado nos Estados Unidos.
* O acesso aos sistemas da Microsoft que contém seu conteúdo é restrito a uma equipe selecionada da Microsoft.
* O Azure Active Directory Premium Government está em conformidade com certificações e referências comuns necessárias para os clientes no setor público dos EUA.

## <a name="customer-eligibility"></a>Elegibilidade do Cliente 

O Azure Active Directory Premium Government está disponível para (1) entidades governamentais federais, estaduais, locais, tribais e territoriais dos EUA e para (2) outras entidades que controlam dados que estão sujeitos aos regulamentos e requisitos governamentais e nas quais o uso do Azure Active Directory Premium Government é apropriado para cumprir com esses requisitos, sujeitos a validação de elegibilidade. A validação de elegibilidade pela Microsoft incluirá a confirmação da manipulação de dados controlados ou regulados pelo governo. A validação poderá exigir uma prova de registro no Departamento de Estado dos Estados Unidos ou o patrocínio de uma instituição governamental com requisitos específicos para a manipulação de dados. Esta oferta é limitada aos clientes que tenham, pelo menos, 500 estações. Após a renovação do contrato de um cliente para o Azure Active Directory Premium Government, uma nova validação de elegibilidade será necessária. As entidades que tenham dúvidas sobre a elegibilidade para o Azure Active Directory Premium Government devem consultar sua equipe de contas.

## <a name="location-of-customer-data"></a>Localização dos Dados do Cliente

Os serviços do Azure Active Directory Premium Government são prestados de datacenters fisicamente localizados nos Estados Unidos. Todo o conteúdo é armazenado em repouso apenas nos datacenters fisicamente localizados nos Estados Unidos.

## <a name="azure-active-directory-premium-government-and-third-party-services"></a>Azure Active Directory Premium Government e Serviços de Terceiros

Vários serviços do Azure Active Directory Premium oferecem a capacidade de trabalhar perfeitamente com serviços e aplicativos de terceiros. Esses aplicativos e serviços de terceiros podem abranger o armazenamento, a transmissão e o processamento do conteúdo do cliente da sua organização em sistemas de terceiros que estão fora da infraestrutura do Azure Active Directory Premium e, portanto, não estão cobertos por nossos compromissos de conformidade e de proteção de dados. É recomendável que você examine as declarações de privacidade e de conformidade fornecidas por terceiros ao avaliar o uso apropriado desses serviços para sua organização.

## <a name="azure-active-directory-premium-government-offers-and-office-365-interoperability"></a>Ofertas do Azure Active Directory Premium Government e interoperabilidade do Office 365

O Office 365 está atualmente disponível em ambientes de GCC e Alta GCC. Para saber mais sobre essas ofertas, consulte a [Descrição de Serviço](https://technet.microsoft.com/library/mt774581.aspx) do Office 365 Government. A oferta comercial do Azure Active Directory Premium é totalmente interoperável com o Office 365 GCC e, no momento, estamos visando a certificação FedRAMP-Moderate para esta oferta. A oferta de Alta GCC do Azure Active Directory Premium é baseada na [nuvem do Microsoft Azure Governamental](https://docs.microsoft.com/azure/azure-government/documentation-government-welcome) e é projetada para interoperar com as ofertas do Office 365 GCC High e do Office 365 DoD. Estamos visando a certificação FedRAMP-High para a oferta de Alta GCC do Azure Active Directory Premium.

|Oferta do Azure Active Directory Premium Government|Oferta correspondente do Office 365 Government|Compromisso de Conformidade|
|-----------|-----------|-----------|
|Azure Active Directory Premium P1/P2 (comercial)|Office 365 <br/> GCC|FedRAMP-Moderate|
|Azure Active Directory Premium P1/P2 Alta GCC|Office 365 <br/> Alta GCC|FedRAMP-High|

> [!NOTE]
> A data prevista para a conformidade com a FedRAMP é o ano civil de 2018

## <a name="parity-with-azure-active-directory-premium-commercial-offerings"></a>Paridade com as ofertas comerciais do Azure Active Directory Premium

Enquanto nossa meta é fornecer todos os recursos e funcionalidades comerciais aos clientes governamentais com nossa oferta de Alta GCC do Azure Active Directory Premium, há algumas funcionalidades ausentes que gostaríamos de destacar. 

Estas são as lacunas conhecidas existentes entre a Alta GCC do Azure Active Directory Premium e a nossa oferta comercial de dezembro de 2017: 
* Azure Active Directory B2B.
* A galeria do Azure Active Directory com aplicativos pré-configurados não estará disponível.
* A auditoria do FedRAMP no MFA é separada da auditoria do FedRAMP no Azure AD e está com atraso. No lançamento, o MFA não terá a certificação FedRAMP e os clientes deverão aceitar esse serviço.
* Licenciamento baseado em grupo. No momento, ele está na versão prévia na nuvem comercial. Uma vez que este recurso estiver disponível na nuvem comercial, trabalharemos para trazer essa funcionalidade para a Alta GCC do Azure Active Directory Premium.

