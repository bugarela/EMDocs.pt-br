---
title: "Proteção habilitada para a nuvem"
description: "Este artigo descreve como o Enterprise Mobility + Security pode ser usado para fornecer um conjunto abrangente de ferramentas de segurança para ajudar de modo proativo a identidade e a reagir às ameaças à segurança na sua organização aproveitando as ferramentas do Azure Active Directory."
keywords: 
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 10/24/2016
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 46654ab0-0d0a-47ad-8715-b149a1092a37
ROBOTS: 
ms.reviewer: atkladak, jsnow
ms.suite: ems
ms.openlocfilehash: 0ed7704a832f3567f14c6eec5ae7da9ea5e9f22a
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="cloud-powered-protection"></a>Proteção habilitada para a nuvem
A Microsoft vem protegendo identidades baseadas em nuvem há mais de uma década e, com o Azure Active Directory, a Microsoft está disponibilizando esses mesmos sistemas de proteção para clientes corporativos, a fim de garantir a responsabilidade do usuário e do administrador com melhor segurança e governança.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?
O EMS (Enterprise Mobility + Security) é a única solução de nuvem abrangente que protege nativamente dados corporativos no próprio dispositivo e além dele, com quatro camadas de proteção em identidades, dispositivos, aplicativos e dados. O EMS ajuda a enfrentar um dos principais desafios no mundo dos dispositivos móveis, no mundo da nuvem — como fornecer um conjunto abrangente de ferramentas de segurança para ajudar de modo proativo a identidade e a reagir às ameaças à segurança na sua organização:
- Controlar o acesso aos recursos
- Proteger a autenticação do usuário
- Reagir às ameaças avançadas com políticas baseadas em risco e monitoramento
- Atenuar riscos administrativos
- Governança de identidades no local e na nuvem

O Azure Active Directory Identity Protection é único. Ela usa aprendizado de máquina para analisar mais de 10 TB de dados comportamentais e contextuais todos os dias, o que proporciona visibilidade sobre atividades suspeitas, além de permitir que você tome medidas, caso seja necessário.

Além disso, as regras de acesso condicional do Azure AD permitem que os clientes controlem o acesso aos serviços online, com base em atributos como conformidade do dispositivo ou local da rede. Veja a seguir o que pode ser diferenciado:
- Acesso condicional baseado na MFA do Azure AD
- Acesso condicional baseado em local do Azure AD
- Acesso condicional baseado em dispositivo do Azure AD


## <a name="recommended-solution"></a>Solução recomendada
### <a name="azure-active-directory-identity-protection"></a>Azure Active Directory Identity Protection

O Azure AD Identity Protection é um serviço de segurança que proporciona uma visão consolidada dos eventos de risco e de possíveis vulnerabilidades que afetam as identidades da organização:
- Reagir às ameaças avançadas com políticas baseadas em risco e monitoramento (Azure AD Identity Protection)
- Atenuar o risco administrativo (Privileged Identity)
- Governança de identidade

Em um mundo em que os incidentes de roubo de identidades, as pessoas que persistem em fazer maldades e as frequentes violações de segurança não param de aumentar, o Azure Active Directory Identity Protection é uma questão de sobrevivência.

O painel do Azure AD Identity Protection dá acesso a relatórios como usuários sinalizados por risco, eventos de risco e vulnerabilidades. Ele também fornece definições como a configuração das políticas de segurança, notificações e registro da autenticação multifator.
### <a name="azure-ad-conditional-access"></a>Acesso condicional do Azure AD
A mudança para os serviços de nuvem e uma necessidade constante e cada vez maior por mobilidade estão obrigando as organizações a buscar soluções que protejam os dados ao mesmo tempo que melhoram a produtividade do usuário e a flexibilidade dos dispositivos. Os clientes exigem a capacidade de controlar o acesso ao Office 365 com base em vários atributos, como local da rede ou imposição de MFA. Isso é particularmente importante para os clientes regulamentados, como os governamentais ou financeiros.

Uma vez que proteger os dados no perímetro da rede já não é o bastante, as organizações também exigem a capacidade de controlar o acesso do usuário com base em outros fatores, como conformidade do dispositivo.

As regras de acesso condicional do Azure AD são aplicadas por aplicativo e estão disponíveis para que os clientes controlem o acesso com base em diferentes condições. Usando o MDM (Gerenciamento de Dispositivo Móvel) para Office 365 ou Intune, os clientes devem poder restringir o acesso ao Office 365 apenas aos usuários que estão usando um dispositivo da empresa ou cujo dispositivo pessoal foi registrado para gerenciamento.

Por exemplo, os clientes podem configurar regras de acesso condicional para impor controles, como:
- Permitir acesso apenas de dispositivos que ingressaram no domínio ou compatíveis
- Impor a MFA para todos os acessos aos serviços do Exchange Online
- Impedir o acesso ao SharePoint Online, para clientes fora da rede corporativa.

## <a name="how-to-implement-these-solutions"></a>Como implementar essas soluções?

Vamos discutir as etapas necessárias para começar a usar o Azure AD Identity Protection e o Acesso Condicional. Esta seção também apresenta artigos de instruções que fornecerão mais detalhes de etapas específicas.

### <a name="azure-ad-identity-protection"></a>Azure AD Identity Protection
O Azure AD Identity Protection está disponível com a oferta Azure AD Premium 2, em combinação com o Azure AD Privileged Identity Management, para fornecer diretamente recursos de política de acesso condicional.

Você pode habilitar o Azure AD Identity Protection acessando o Azure Marketplace e procurando: "identity protection"; em seguida, clique no bloco do Azure AD Identity Protection, o que abrirá o painel com uma visão consolidada dos dados de risco do seu locatário. Vamos destacar alguns exemplos de como o Identity Protection pode ajudar sua organização com as ameaças à segurança da conta.

#### <a name="risk-events"></a>Eventos de risco
Os eventos de risco são aqueles sinalizados como suspeitos pelo Identity Protection e indicam que uma identidade pode ter sido comprometida.

A Microsoft continua investindo nessa área e planeja, de modo contínuo, melhorar a precisão de detecção de eventos de risco existentes e adicionar novos tipos de evento de risco. Por exemplo, você pode investigar o evento de risco Viagens impossíveis.

Veja mais detalhes no [manual de estratégia do Azure AD Identity](https://azure.microsoft.com/en-us/documentation/articles/active-directory-identityprotection-playbook/).

Veja um exemplo de alguns eventos de risco no painel do Identity Protection:

![Captura de tela mostrando alguns eventos de risco listados no painel do Azure AD Identity Protection.](./media/cloud-powered-protection/cloud-powered-protection-fig1.png)

#### <a name="impossible-travels-risk"></a>Risco de Viagens impossíveis
Na folha Viagem impossível, todos os incidentes sinalizados são exibidos por 1º e 2º locais de logon e tempo de cada logon ocorrido.

![Captura de tela do painel do Azure AD Identity Protection mostrando locais dos eventos de risco de "viagens impossíveis".](./media/cloud-powered-protection/cloud-powered-protection-fig2.png)

Você pode encontrar mais detalhes em [tipos de evento de risco detectados pelo Azure Active Directory Identity Protection](https://azure.microsoft.com/en-us/documentation/articles/active-directory-identityprotection-risk-events-types/).

#### <a name="remediation"></a>Remediação
Além de resolver incidentes individualmente, o Azure AD Identity Protection fornece a capacidade de solucionar possíveis problemas por meio de uma abordagem proativa configurando uma política de correção de risco de usuário. Nas configurações de política, seus alvos podem ser usuários individuais, grupos ou todos os usuários. Você também pode definir condições específicas, que acionarão a política.

![Captura de tela mostrando como corrigir eventos de risco diretamente no painel do Azure AD Identity Protection.](./media/cloud-powered-protection/cloud-powered-protection-fig3.png)

Por fim, você tem a opção de bloquear o acesso completamente ou permitir o acesso, mas com os requisitos de:
- Autenticação Multifator
- Registro do Azure MFA
- Uma alteração de senha

Você pode encontrar mais detalhes no [Azure AD Identity Protection](https://azure.microsoft.com/en-us/documentation/articles/active-directory-identityprotection/) e nesta [postagem do blog de segurança e mobilidade corporativa](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/07/azuread-identity-protection-azure-ad-privileged-identity-management-and-azure-ad-premium-p2-will-be-generally-available-sept-15th/).

### <a name="azure-ad-conditional-access"></a>Acesso condicional do Azure AD
Os links abaixo fornecem informações de como usar o acesso condicional do Azure AD com base na MFA (Autenticação Multifator), no local e nas políticas do dispositivo.
- Saiba [como implementar o acesso condicional do Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access/).
- Saiba mais sobre [MFA e políticas de local](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-azuread-connected-apps/).
- Saiba mais sobre [políticas baseadas em dispositivo](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).
