---
title: "Habilitar negócios sem fronteiras"
description: "Este artigo descreve como o Enterprise Mobility + Security pode ser usado para fornecer uma única identidade que funcione em ativos na nuvem e no local, além de manter a produtividade máxima dos usuários aproveitando as ferramentas do Azure Active Directory."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 38e9802b-d8c0-4f5c-b89d-8ce1e04f7387
ROBOTS: 
ms.reviewer: atkladak, jsnow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fdb0852611551daaa2aad7d3839a3431abd8b445
ms.openlocfilehash: 8f79e391813c7a15e522f07ff27a2f6abd8536cc


---

# <a name="enable-business-without-borders"></a>Habilitar negócios sem fronteiras
A identidade não é algo secundário, mas a principal parte de uma força de trabalho eficiente. As organizações precisam capacitar seus funcionários para acessar todos os dados e aplicativos de qualquer dispositivo e de qualquer lugar. Os usuários precisam colaborar entre si e com parceiros, bem como se conectar com clientes. As ferramentas que eles usam não ficam mais em um ambiente protegido e controlado; elas podem ser encontradas em qualquer nuvem pública.

Esse novo mundo introduz desafios e ameaças avançadas que não podem ser atenuadas com ferramentas tradicionais. Não faz sentido proteger apenas sua rede enquanto o novo limite é o usuário. A chave para ser produtivo e estar protegido nesse ambiente é uma robusta solução de identidade.

## <a name="how-can-enterprise-mobility-security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?
O EMS (Enterprise Mobility + Security) é a única solução de nuvem abrangente que protege nativamente dados corporativos no próprio dispositivo e além dele, com quatro camadas de proteção de identidades, dispositivos, aplicativos e dados. O EMS ajuda a enfrentar um dos principais desafios no mundo dos dispositivos móveis e da nuvem — como fornecer uma única identidade que funcione em ativos na nuvem e no local e manter a produtividade máxima dos usuários.

### <a name="access-to-single-sign-on-applications"></a>Acesso a aplicativos de logon único
Com a Federação de Identidades e o logon único, os usuários podem ter um conjunto de credenciais de logon e senhas, e a TI é capaz de gerenciar com mais eficiência a identidade do usuário.
### <a name="multi-factor-authentication"></a>Autenticação Multifator
Os usuários também têm a capacidade de levar novos dispositivos para dentro empresa, mas a TI pode validar esses dispositivos que se conectam à rede, que são de propriedade dos indivíduos e controlados por eles, com as credenciais apropriadas. A MFA (Autenticação Multifator) ajuda a fornecer uma camada de proteção.
### <a name="self-service-group-management"></a>Gerenciamento de grupos de autoatendimento
Quando os usuários esquecem as senhas, eles podem redefini-las, o que reduz a carga sobre a TI e os torna mais eficientes, sendo capazes de resolver o problema rapidamente.
### <a name="cross-organization-collaboration"></a>Colaboração entre organizações
A colaboração entre empresas é importante para 97% dos clientes da Microsoft, que a consideram um importante requisito para trabalhar com parceiros. A colaboração B2B (entre empresas) do Azure Active Directory dá suporte a relações entre empresas permitindo que os parceiros acessem seletivamente aplicativos e dados corporativos usando identidades autogerenciadas.

## <a name="recommended-solution"></a>Solução recomendada
[A colaboração B2B (entre empresas) do Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-b2b-what-is-azure-ad-b2b/) é a solução recomendada que fornece às organizações acesso a tudo de que precisam de qualquer lugar, de maneira segura e produtiva, em colaboração com investimentos já feitos em ferramentas tradicionais.
- Profissionais de TI que fornecem acesso aos dados e aplicativos da organização aos colaboradores e organizações do parceiro.
- Usuários parceiros que estão agindo "em nome de", como representantes ou funcionários da respectiva organização.
- Revisões de acesso, verificação de email, lista de permissões, lista de negações, etc., administram o acesso aos recursos e aplicativos host.
- Usuários do parceiro podem ser descobertos e ver outros usuários de sua própria organização (sujeitos à política).

### <a name="how-azure-ad-b2b-collaboration-works"></a>Como a colaboração B2B do Azure AD funciona

A colaboração B2B do Azure AD se baseia em um modelo de convite e resgate, que utiliza os endereços de email dos parceiros com que você quer trabalhar e os respectivos aplicativos que quer usar.

1. O administrador faz logon no portal do Azure e convida usuários parceiros importando um arquivo CSV que contém informações de usuário do parceiro.
2. O portal do Azure envia emails aos parceiros.
3. Os parceiros clicam no link do email que recebem do portal do Azure. Se o usuário do parceiro já estiver no Azure AD, ele será solicitado a inserir suas credenciais de trabalho; caso contrário, o usuário do parceiro precisará se inscrever como um usuário de colaboração da B2B do Azure AD.
4. O usuário do parceiro é automaticamente redirecionado para o aplicativo para o qual ele foi convidado a colaborar.

![Gráfico mostrando o processo no qual um usuário do parceiro é convidado a colaborar por meio da B2B do Azure AD.](./media/enable-business-without-borders/enable-business-without-borders-fig1.png)

## <a name="how-to-implement-this-solution"></a>Como implementar esta solução
As etapas a seguir descrevem como implementar cada colaboração B2B do Azure AD discutida anteriormente. Cada link representa um conjunto diferente de artigos com um conjunto diferente de instruções/etapas a serem implementadas na sua organização:
- Saiba [Como usar a colaboração B2B do Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-b2b-detailed-walkthrough/).
- Saiba [como usar o arquivo CSV para especificar informações de usuário do parceiro](https://azure.microsoft.com/en-us/documentation/articles/active-directory-b2b-references-csv-file-format/).



<!--HONumber=Dec16_HO2-->


