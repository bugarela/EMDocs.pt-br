---
title: Proteger na porta da frente | Microsoft Docs
description: "Um cenário que descreve como o Enterprise Mobility + Security pode ser usado para proteger a identidade para acesso seguro aos recursos da empresa, aproveitando os recursos Microsoft Azure Active Directory Identity Protection e Azure Active Directory Privileged Identity Management."
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: techgroup-identity
ms.assetid: c9aeabcf-db9b-4a35-b1bc-61331c464165
ms.reviewer: v-craic
ms.suite: ems
ms.custom: microsoft-identity-manager
ms.translationtype: Human Translation
ms.sourcegitcommit: 5d9a4bd18660a573b2dd76c0263b89ecf5ae4610
ms.openlocfilehash: 7912b13666c9b08af0c6d962fe1ea592335ca73d
ms.contentlocale: pt-br
ms.lasthandoff: 01/24/2017


---

# <a name="protect-at-the-front-door"></a>Proteger na porta da frente

As soluções tradicionais de segurança costumavam ser o suficiente para proteger seus negócios. Mas isso foi antes do crescimento do setor de mobilidade, que criou um cenário mais amplo de ataques, e da transição para a nuvem, que torna mais complexas as interações de funcionários com outros usuários, dispositivos, aplicativos e dados. Para realmente proteger seus negócios agora, você precisa adotar uma abordagem de segurança mais holística e inovadora, que possa proteger, detectar e responder a ameaças de todos os tipos locais, bem como na nuvem.

Em mais de 63% das violações de dados, os invasores obtêm acesso à rede corporativa por meio de credenciais de usuário roubadas, padrão ou fracas.  A segurança controlada pela Identidade da Microsoft se concentra credenciais do usuário, fechando a porta para roubo de credenciais gerenciando e protegendo suas identidades, incluindo suas identidades privilegiadas e não privilegiadas.


## <a name="how-can-enterprise-mobility--security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?

A abordagem de segurança do EMS (Enterprise Mobility + Security) começa com uma identidade comum protegida para proteger o acesso a todos os recursos corporativos locais e na nuvem, com o [acesso condicional](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access/) baseado em riscos. Usando essa abordagem, a TI pode proteger os recursos da empresa na porta da frente com avançados e inovadores acessos condicionais baseados em risco. O EMS fornece uma identidade comum protegida para acesso a milhares de aplicativos, o que ajuda a TI a gerenciar e proteger identidades com privilégios.

## <a name="recommended-solution"></a>Solução recomendada

Para atender aos requisitos deste cenário, o EMS usa o [Azure AD Identity Protection](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/) e o [Privileged Identity Management](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-configure/). Implementando essas tecnologias, as organizações poderão:

- aprofundar-se usando uma exibição consolidada de detecção de ameaças baseada em machine learning
- corrigir recomendações
- calcular a gravidade dos riscos
- executar o acesso condicional baseado em riscos automaticamente para proteger contra logons suspeitos e credenciais comprometidas
- impor o acesso administrativo just-in-time sob demanda quando necessário
- usar alertas, relatórios de auditoria e análise de acesso

O diagrama a seguir resume as funcionalidades envolvidas neste cenário e como eles são usados para proteger seus recursos:

![Protegendo recursos](./media/protect-front-door/protect-front-door-fig1.png)

## <a name="how-to-implement-this-solution"></a>Como implementar esta solução

Siga estas etapas para implementar o Azure AD Identity Protection e o Azure AD Privileged Identity Management:

- Etapa 1: Habilitar o Azure AD Identity Protection
- Etapa 2: Configurar o Azure AD Identity Protection
- Etapa 3: Monitorar o acesso a recursos
- Etapa 4: Habilitar o Azure AD Privileged Identity Management
- Etapa 5: Configurar o Azure AD Privileged Identity Management
- Etapa 6: Operações do Privileged Identity Management


## <a name="how-to-protect-your-resources-at-the-front-door"></a>Como proteger seus recursos na porta da frente

Diferentes organizações terão pontos de vista diferentes quanto à prioridade dos incidentes. O que é essencial para uma linha de negócios pode não ser para outra. Por esse motivo, primeiro você precisa aprender como o Azure AD Identity Protection categoriza o [nível de risco](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#detection-and-risk), que é uma indicação (alta, média ou baixa) da gravidade do evento de risco. O Azure AD Identity Protection também avalia a probabilidade de que a identidade de um usuário tenha sido comprometida e atribui seu próprio nível de risco, que é chamado de [nível de risco do usuário](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#what-is-a-user-risk-level). O Azure AD Identity Protection identificará uma [vulnerabilidade](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-vulnerabilities/) e atribuirá um nível de risco a ela. Há diferentes [tipos de riscos](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-risk-events-types/) e cada um deles é classificado de acordo com seu nível de importância. Realize as etapas 1 a 3 para habilitar, implementar e monitorar recursos usando o Azure AD Identity Protection.

O segundo estágio da solução (etapas 4 a 6) implementará o Azure AD (Active Directory) Privileged Identity Management para descobrir, restringir e monitorar identidades com privilégios. As organizações que usam o Azure podem [atribuir funções no Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-assign-admin-roles/) e o Azure AD Privileged Identity Management pode gerenciar [algumas dessas funções](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-roles/).

### <a name="step-1-enable-azure-ad-identity-protection"></a>Etapa 1: Habilitar o Azure AD Identity Protection

Antes de implementar essa solução, verifique se há uma [licença do Azure AD Premium](https://azure.microsoft.com/documentation/articles/active-directory-get-started-premium/) atribuída ao usuário final. Caso esteja usando um domínio federado e queira impor que a alteração da senha na nuvem seja gravada localmente, você precisa habilitar o [write-back de senha](https://azure.microsoft.com/documentation/articles/active-directory-passwords-getting-started/). Após revisar esses requisitos, [habilite o Azure AD Identity Protection](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-enable/) instalando-o do Marketplace. Depois de concluir a instalação, você terá acesso ao painel do Azure AD Protection Identity, que poderá ser exibido vazio, conforme mostrado na imagem a seguir.

![Azure AD Identity Protection](./media/protect-front-door/protect-front-door-fig2.png)

### <a name="step-2-configure-azure-ad-identity-protection"></a>Etapa 2: Configurar o Azure AD Identity Protection

Quando estiver planejando a implementação do Azure AD Identity Protection, você deve começar definindo as políticas a seguir:

- [Política de registro de autenticação multifator](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#multi-factor-authentication-registration-policy): permite que a TI imponha a MFA (autenticação multifator) para os usuários.
- [Política de risco do usuário](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#user-risk-security-policy): permite que a TI defina uma política de segurança de risco do usuário para bloquear os usuários no momento da entrada dependendo do nível de risco.
- [Política de risco de entrada](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#sign-in-risk-security-policy): permite que a TI avalie o risco de uma entrada específica e, com base no resultado, aplica atenuações usando regras e condições predefinidas.

Essas políticas ficam no painel do Azure AD Identity Protection, na seção **Configurar**, conforme mostrado na seguinte imagem:

![Políticas](./media/protect-front-door/protect-front-door-fig3.png)

Além de configurar políticas de segurança, você também pode personalizar quais usuários receberão alertas. Use a opção **Alertas** na seção Configurações do painel do Azure AD Identity Protection, conforme mostrado na imagem a seguir:

![Alertas](./media/protect-front-door/protect-front-door-fig4.png)

Observado que, nessa configuração, os usuários receberão alertas somente se o nível de risco do usuário for **Alto**.

### <a name="step-3-monitor-and-remediation"></a>Etapa 3: Monitorar e corrigir

O monitoramento contínuo é uma parte integral de qualquer operação segura. Aproveitando a funcionalidade de [investigação](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#investigation) do Azure AD Identity Protection, a TI terá uma exibição aprofundada da detecção de ameaças baseada em machine learning, com recomendações de correção e notificações. Você pode usar o painel do Azure AD Identity Protection para avaliar rapidamente seu ambiente atual e identificar com facilidade problemas que precisam ser solucionados de acordo com sua gravidade. Ou pode restringir a investigação às seguintes áreas localizadas na seção de investigação no painel do Azure AD Identity Protection:

![Investigação](./media/protect-front-door/protect-front-door-fig5.png)

Após a investigação de cada uma dessas áreas, os administradores podem tomar medidas para atenuar [usuários em risco](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#mitigating-user-risk-events) ou [eventos de entrada](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#mitigating-sign-in-risk-events). Por exemplo, se identificar um evento de segurança como [Viagem impossível a localizações atípicas](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection-risk-events-types/#impossible-travel-to-atypical-locations) (o segundo evento na tela a seguir), você poderá adotar medidas para [corrigir](https://azure.microsoft.com/documentation/articles/active-directory-identityprotection/#remediating-user-risk-events) essa ameaça, como forçar a redefinição da senha.

![Eventos de risco](./media/protect-front-door/protect-front-door-fig6.png)

Você também pode aproveitar os [relatórios de acesso e uso do Azure AD Premium](https://azure.microsoft.com/documentation/articles/active-directory-view-access-usage-reports/) para obter mais informações sobre os comportamento e as potenciais ameaças de um usuário.

### <a name="step-4-enable-azure-ad-privileged-identity-management"></a>Etapa 4: Habilitar o Azure AD Privileged Identity Management

Para ter acesso ao Azure AD Privileged Identity Management, você precisa primeiro [instalá-lo do Marketplace](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-getting-started/). O Azure AD Privileged Identity Management e a MFA (Autenticação Multifator) do Azure funcionam em conjunto para ajudar a TI a gerenciar o acesso a aplicativos e serviços seguros. Após a instalação do Azure AD Privileged Identity Management, será feito um teste para verificar se você é capaz de utilizar a MFA. Quando clicar na opção para verificar sua conta, você será redirecionado para uma página da Web em que precisa inserir suas credenciais. Se sua conta ainda não estiver habilitada para MFA, você verá uma mensagem semelhante ao mostrado na seguinte imagem:

![Tela de logon](./media/protect-front-door/protect-front-door-fig7.png)

Clique em **Configurar agora** e siga o assistente. Você precisa inserir seu número de telefone ou celular para fins de verificação. Depois de concluir o assistente, você verá a mensagem de verificação concluída:

![Verificação](./media/protect-front-door/protect-front-door-fig8.png)

### <a name="step-5-configure-azure-ad-privileged-identity-management"></a>Etapa 5: Configurar o Azure AD Privileged Identity Management

A configuração inicial é feita usando um [Assistente de Segurança](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-security-wizard/), que tem três etapas, conforme mostrado na folha **Proteger sua organização**:

![Assistente de segurança](./media/protect-front-door/protect-front-door-fig9.png)

Na primeira etapa, você examinará as [funções privilegiadas](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-roles/), que foram descobertas pelo Azure AD Privileged Identity Management. A segunda etapa tem o objetivo de reduzir o número de usuários em sua organização que têm atribuições de função com privilégios permanentes, o que minimiza diretamente sua vulnerabilidade a violações de segurança. A última tapa permite examinar as alterações dos usuários com funções privilegiadas.

Se, durante esse processo, você tiver concedido a outro usuário uma função administrativa, você qualificou esse usuário a desempenhar essa função, o que significa que você pode [ativar a função](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-activate-role/) quando precisar executar uma tarefa que exigir a função.

### <a name="step-6-privileged-identity-management-operations"></a>Etapa 6: Operações do Privileged Identity Management

Agora que tem o Azure AD Privileged Identity Management instalado e configurado, você pode realizar a avaliação inicial para verificar seu esquema de função e alertas atual. Na folha **Gerenciamento de Identidades com Privilégio**, clique em **Gerenciar funções com privilégio** e você verá um painel semelhante ao mostrado na imagem a seguir:

![Funções com privilégio](./media/protect-front-door/protect-front-door-fig10.png)

Neste painel, você pode ver a atividade atual, como [alertas de segurança](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-configure-security-alerts/) e [acessar análise](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-start-security-review/). Você também pode usar esse painel para [adicionar](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-give-access-to-pim/) ou [remover](https://azure.microsoft.com/documentation/articles/active-directory-privileged-identity-management-how-to-give-access-to-pim/#remove-another-users-access-rights-for-managing-pim) o acesso de um ou mais usuários ao Azure AD Privileged Identity Management.

