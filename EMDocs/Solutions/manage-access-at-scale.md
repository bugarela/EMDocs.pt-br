---
title: Gerenciar acesso em escala
description: Este artigo descreve como o Enterprise Mobility + Security pode ser usado para capacitar uma organização com o gerenciamento de acesso de identidade aproveitando as ferramentas do Azure Active Directory.
keywords: ''
author: andredm7
ms.author: andredm
manager: swadhwa
ms.date: 12/07/2016
ms.topic: solution
ms.prod: ''
ms.service: active-directory
ms.technology: ''
ms.assetid: 0292919a-af10-4a25-8916-c704aed643f6
ROBOTS: ''
ms.reviewer: atkladak, jsnow
ms.suite: ems
ms.openlocfilehash: aba57397c4e66d03f89a7e9c9d872903520f5c0c
ms.sourcegitcommit: 573bba4fa70ce651971ec5bafd9967ebdd6bd6c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="manage-access-at-scale"></a>Gerenciar acesso em escala
A Microsoft capacita empresas desde que foi criada. A Microsoft não só fornece uma identidade que leva você a qualquer lugar, mas também fornece um conjunto de ferramentas para automatizar, ajudar a proteger e gerenciar a TI em sua organização. Mesmo após o advento da computação em nuvem, ainda há demanda para gerenciar e controlar tarefas de TI como chamadas de assistência técnica para redefinir senhas de usuários, gerenciamento de grupo de usuários e solicitações de aplicativos.

## <a name="how-enterprise-mobility--security-can-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você
O EMS (Enterprise Mobility + Security) é a única solução de nuvem abrangente que ajuda a proteger nativamente dados corporativos no próprio dispositivo e além dele, com quatro camadas de proteção de identidades, dispositivos, aplicativos e dados. O EMS também ajuda você a resolver um dos principais desafios de um mundo que prioriza dispositivos móveis e a nuvem – como fornecer um conjunto abrangente de ferramentas dentro do Azure AD (Azure Active Directory) que o ajudará com o seguinte:
- Gerenciamento avançado de ciclo de vida do usuário
- Baixo custo e sobrecarga de TI
- Monitorar a ponte de identidade

## <a name="recommended-solution"></a>Solução recomendada
O Azure AD Premium é a solução recomendada para capacitar sua organização com o gerenciamento de acesso de identidade.

### <a name="advanced-user-lifecycle-management"></a>Gerenciamento avançado de ciclo de vida do usuário
O Azure AD fornece gerenciamento automatizado e avançado de ciclo de vida do usuário usando regras dinâmicas de associação de grupo e recursos de gerenciamento de aplicativos. Veja mais detalhes:

- Para organizações com HR local, o Microsoft Identity Manager estabelece identidades de usuário no Active Directory do Windows Server.
- Para organizações cujo RH usa SaaS (software como serviço), o Azure AD atualmente se integra com o Workday.
- O Azure AD Connect sincroniza usuários e grupos entre o Windows Server Active Directory e o Azure AD.
- O Azure AD fornece licenciamento automatizado baseado em grupos para o Office 365 e outros serviços online da Microsoft.

![Gráfico mostrando como o Azure AD Connect sincroniza usuários e grupos entre o Windows Server Active Directory e o Azure Active Directory](./media/manage-access-at-scale/manage-access-at-scale-fig1.png)

### <a name="application-management"></a>Gerenciamento de aplicativos
Quantos usuários gostam de se lembrar de senhas para cada aplicativo que usam todos os dias? O [logon único](https://azure.microsoft.com/documentation/articles/active-directory-appssoaccess-whatis/) trata desse problema comum. É possível fazer logon em vários aplicativos de SaaS usando uma única conta de usuário e senha. O logon único pode ser provisionado automaticamente para todos os aplicativos de sua organização. Essa capacidade está disponível para aplicativos de nuvem da Microsoft, como o Office 365 e para aplicativos de terceiros, como Salesforce, ServiceNow e Workday.

Veja mais detalhes sobre o logon único:

 - Ele funciona na nuvem, de modo que você pode economizar tempo e dinheiro. Soluções locais exigem que você configure e mantenha redes de perímetro, servidores de borda ou outras infraestruturas complexas.
 - Ele é mais fácil de configurar e proteger do que soluções locais porque você não precisa abrir conexões de entrada através do firewall.
 - Ele oferece excelente segurança. Quando publica seus aplicativos usando o Proxy de Aplicativo do Azure AD, você pode tirar proveito dos controles de autorização e análise de segurança no Azure. Isso significa que você obtém recursos avançados de segurança para todos os aplicativos existentes sem a necessidade de alterar nenhum aplicativo.
 - Ele oferece aos usuários uma experiência consistente de autenticação. O logon único oferece aos usuários acesso a todos os aplicativos de que precisam para serem produtivos usando uma senha.

### <a name="low-it-overhead-and-cost"></a>Baixo custo e sobrecarga de TI
O Azure AD Premium oferece autoatendimento para redefinição de senha, gerenciamento de grupos e recursos de gerenciamento de aplicativos para aumentar a produtividade do setor de TI e dos usuários em sua organização. Não é necessário que os usuários façam chamadas de assistência técnica e forneçam muitas informações para obter uma senha temporária, que é enviada por email ou compartilhada durante a chamada de maneira não segura.

Veja mais detalhes sobre a redefinição de senha:

- Ele funciona com a federação, a sincronização de senha ou contas de usuário somente em nuvem. Ele também aplica todas as suas políticas de senha local.
- Todo o tráfego é criptografado com uma chave específica do locatário e via HTTPS.
- Os usuários podem atualizar suas senhas do AD ou desbloquear suas próprias contas do AD em tempo real.
- Notificações em tempo real são enviadas para os usuários e administradores.

![Gráfico que mostra como o Azure Active Directory funciona localmente e na nuvem para fornecer recursos de autoatendimento para redefinição de senha aos usuários finais](./media/manage-access-at-scale/manage-access-at-scale-fig2.png)

### <a name="monitor-your-identity-bridge"></a>Monitorar a ponte de identidade
O Azure AD Connect Health ajuda as organizações a monitorar e se aprofundar em sua infraestrutura de identidade local e nos serviços de sincronização. Ele também ajuda as organizações a manter uma conexão confiável com o Office 365 e Microsoft Online Services fornecendo recursos de monitoramento para os principais componentes de identidade. Esses componentes incluem servidores do AD FS (Serviços de Federação do Active Directory), servidores do Azure AD Connect e DCs (controladores de domínio) do Active Directory.

Veja mais detalhes sobre a integridade do Azure AD:

- Auditoria e conformidade com um clique por meio do portal do Azure
- Investigação e análise forense: ajuda os administradores de TI a responder "quem fez o quê, onde e quando"
- Relatórios de atividade: fornece auditoria, entradas, autoatendimento de redefinição de senha, atividade de grupos, atividade de aplicativos, provisionamento de aplicativos e mais
- Relatórios de segurança: fornece atenuação e resolução de anomalias de segurança por meio da proteção de identidade

![Gráfico que mostra como o Azure AD Connect Health ajuda organizações a monitorar seus principais componentes de identidade, como servidores do AD FS, servidores do Azure AD Connect e controladores de domínio do Active Directory](./media/manage-access-at-scale/manage-access-at-scale-fig3.png)

## <a name="how-to-implement-an-advanced-user-lifecycle-management"></a>Como implementar um gerenciamento avançado de ciclo de vida do usuário
Vamos examinar alguns exemplos e as etapas que você poderia adotar para implementar a solução:

1. Em um cenário do mundo real, sua empresa contrata um profissional e o adiciona como usuário ao sistema de RH como membro da equipe de Marketing.
2.  Supondo que você já tenha integrado sua instância do Active Directory local com o Azure AD por meio da sincronização de diretórios, o Azure AD Connect local sincronizará a conta de usuário com o Azure AD.
3.  Após a conta de usuário aparecer no Azure AD, você poderá criar regras de associação de grupo dinâmico que atribuem automaticamente os usuários de Marketing a ela.
4.  Após o grupo de Marketing ser populado automaticamente com seus usuários, você poderá usar o licenciamento seletivo baseado em grupos. Esse tipo de licenciamento possibilita adicionar usuários a um grupo de licenças específico, como Azure AD Premium ou Office 365 Enterprise E5.
    Neste exemplo, isso fornece aos usuários acesso a todos os aplicativos do Office 365 de que eles precisam para realizar seu trabalho, bem como acesso do Azure AD Premium para realizar outras tarefas automatizadas.

Se um funcionário precisar deixar a empresa, você poderá removê-lo do sistema de RH. Isso remove automaticamente o acesso a todos os aplicativos e recursos provisionados anteriormente para ele. Se o funcionário precisar apenas ser movido para outro departamento, as regras de associação de grupo dinâmico removerão automaticamente o acesso a aplicativos de Marketing e adicionarão acesso aos aplicativos de outro departamento, com o usuário sendo removido da equipe de Marketing e adicionado ao grupo dinâmico do novo departamento.

## <a name="how-to-manage-cloud-and-on-premises-applications"></a>Como gerenciar aplicativos locais e na nuvem
Estas são as etapas que você pode seguir para adicionar, implantar e gerenciar aplicativos de SaaS da Microsoft e de terceiros com o Azure AD:
- Saiba mais sobre como [integrar o Azure AD com aplicativos](https://azure.microsoft.com/documentation/articles/active-directory-integrating-applications-getting-started/).
- Saiba mais sobre como [habilitar o logon único para aplicativos de SaaS](https://azure.microsoft.com/documentation/articles/active-directory-sso-integrate-saas-apps/).
- Saiba mais sobre como [gerenciar o acesso a aplicativos](https://azure.microsoft.com/documentation/articles/active-directory-managing-access-to-apps/).

## <a name="how-to-implement-password-reset-self-service-portal"></a>Como implementar o portal de autoatendimento de redefinição de senha
Por padrão, o Azure AD vem com um recurso gratuito que permite que todo administrador execute seu próprio autoatendimento de redefinição de senha.

Usando o Azure AD Premium, você poderá além dos administradores de TI, fornecendo recursos de portal de autoatendimento para redefinição de senha para seus usuários. Você pode, rapidamente, habilitar políticas de redefinição de senha do usuário que estenderão os mesmos recursos de administração avançada para todos os usuários no diretório.

Saiba mais sobre o [pré-requisitos, como habilitar e como configurar o portal de autoatendimento de senha](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/) em seu locatário do Azure AD.

## <a name="how-to-use-azure-ad-connect-health"></a>Como usar o Azure AD Connect Health
Você pode verificar a [documentação do Azure AD Connect Health](https://azure.microsoft.com/en-in/documentation/articles/active-directory-aadconnect-health/) para coletar mais informações sobre a ferramenta, seus recursos e as etapas que você pode executar para começar a usá-la em sua organização.

O Azure AD Connect Health está disponível no [portal do Azure](https://ms.portal.azure.com) e requer que um agente de integridade seja instalado nos controladores de domínio locais que você deseja monitorar. Saiba mais sobre [como instalar o agente de integridade](https://azure.microsoft.com/en-in/documentation/articles/active-directory-aadconnect-health-agent-install/).

O painel **Controladores de Domínio** fornece uma exibição única da integridade e do status operacional do ambiente. Nele, o administrador pode encontrar facilmente quais DCs são proprietários da função FSMO (Flexible Single Master Operations), quais DCs têm alertas ativos e quais são catálogos globais. Outras colunas incluem **acessível por controlador de domínio primário**, **acessível por GC** e **estado de SYSVOL**.

![Captura de tela que mostra o painel Controladores de Domínio com informações sobre o controlador de domínio selecionado](./media/manage-access-at-scale/manage-access-at-scale-fig4.png)

Além disso, os DCs podem ser agrupados pelo domínio correspondente ou o administrador pode agrupá-los por site.

![Captura de tela que mostra controladores de domínio agrupados por site](./media/manage-access-at-scale/manage-access-at-scale-fig5.png)

O painel **Status de Replicação** mostra a aparência da topologia de replicação dentro do ambiente, em conjunto com informações sobre a última tentativa de replicação para cada contexto de nomeação.

![Captura de tela que mostra o painel de Status de Replicação com informações sobre a última tentativa de replicação](./media/manage-access-at-scale/manage-access-at-scale-fig6.png)

Os detalhes de um alerta têm mais informações sobre o problema que está causando o alerta, a correção necessária e um link para mais recursos de solução de problemas.

![Captura de tela que mostra detalhes sobre um alerta especificado](./media/manage-access-at-scale/manage-access-at-scale-fig7.png)

O monitoramento de desempenho do AD Connect Health fornece uma maneira fácil de comparar o desempenho dos DCs monitorados em relação uns aos outros, bem como comparar diferentes métricas de interesse.

![Captura de tela que mostra o monitoramento de desempenho de controladores de domínio selecionados](./media/manage-access-at-scale/manage-access-at-scale-fig8.png)
