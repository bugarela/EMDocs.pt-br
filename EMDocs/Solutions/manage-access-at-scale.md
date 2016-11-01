---
title: Gerenciar acesso em escala
description: Gerenciar acesso em escala
keywords: 
author: andredm7
manager: swadhwa
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 0292919a-af10-4a25-8916-c704aed643f6
ROBOTS: noindex
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c20f69b821a2acfbf2fa399b960b60fc31dbf502
ms.openlocfilehash: 28b83995ab2689cffa048cbf2ccdd53a3d9b1421


---

# Gerenciar acesso em escala
A Microsoft capacita empresas desde que foi criada. A Microsoft não só fornece uma identidade que leva você a qualquer lugar, mas também fornece um conjunto de ferramentas para automatizar, proteger e gerenciar a TI em sua organização. Mesmo após o advento da computação em nuvem, ainda há demanda para gerenciar e controlar operações de TI como chamadas de assistência técnica para redefinir senhas de usuário, gerenciamento de grupo de usuários e solicitações de aplicativos.

## Como o Enterprise Mobility + Security pode ajudar você?
O EMS (Enterprise Mobility + Security) é a única solução de nuvem abrangente que protege nativamente dados corporativos no próprio dispositivo e além dele, com quatro camadas de proteção de identidades, dispositivos, aplicativos e dados. O EMS também ajuda você a resolver um dos principais desafios de um mundo centrado em dispositivos móveis e na nuvem – como fornecer um conjunto abrangente de ferramentas dentro do Azure AD (Azure Active Directory) que o ajudará com o seguinte:
- Gerenciamento avançado de ciclo de vida do usuário
- Baixo custo e sobrecarga de TI
- Monitorar a ponte de identidade


### Solução recomendada
O Azure AD Premium é a solução recomendada para capacitar sua organização com o gerenciamento de acesso de identidade.
#### Gerenciamento avançado de ciclo de vida do usuário
O Azure AD fornece gerenciamento avançado de ciclo de vida do usuário aproveitando regras de associação de grupo dinâmico e recursos de gerenciamento de aplicativos.

- Para organizações com HR local, o Microsoft Identity Manager estabelece identidades de usuário no Active Directory do Windows Server.
- Para organizações cujo RH usa SaaS (software como serviço), o Azure AD atualmente se integra com o Workday e se integrará com mais aplicativos no futuro.
- O Azure AD Connect sincroniza usuários e grupos entre o Active Directory do Windows Server e o Azure AD.
- O Azure AD fornece licenciamento automatizado baseado em grupo para o Office 365 e outros serviços online da Microsoft.

![Gráfico mostrando como o Azure AD Connect sincroniza usuários e grupos entre o Active Directory do Windows Server e o Azure Active Directory](./media/ManageAccessAtScale/fig1.png)
#### Gerenciamento de aplicativos
Quantos usuários gostam de se lembrar de senhas para cada aplicativo que usam todos os dias? O [logon único](https://azure.microsoft.com/en-us/documentation/articles/active-directory-appssoaccess-whatis/) aborda esse problema comum: você pode fazer logon em vários aplicativos de SaaS usando uma única conta de usuário e senha, que pode ser provisionada automaticamente para todos os aplicativos de sua organização. Essa capacidade está disponível para aplicativos de nuvem da Microsoft, como o Office 365, e para aplicativos de terceiros, como Salesforce, ServiceNow e Workday.

 Ele também está disponível para aplicativos locais por meio do [Proxy de Aplicativo do Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), que oferece acesso remoto simples, seguro e econômico como uma solução de serviço para todos os aplicativos locais. Seus funcionários remotos podem acessar seus recursos locais sem ficarem restritos à rede corporativa e sem que a TI precise implementar VPN, ambientes DMZ ou proxies reversos.

 - Ele funciona na nuvem, de modo que você pode economizar tempo e dinheiro. Soluções locais exigem que você configure e mantenha DMZs, servidores de borda ou outras infra-estruturas complexas.
 - Ele é mais fácil de configurar e proteger do que soluções locais porque você não precisa abrir conexões de entrada através do firewall.
 - Ele oferece excelente segurança. Quando publica seus aplicativos usando o Proxy de Aplicativo do Azure AD, você pode tirar proveito dos controles avançados de autorização e análise de segurança no Azure. Isso significa que você obtém recursos avançados de segurança para todos os aplicativos existentes sem a necessidade de alterar nenhum aplicativo.
 - Ele oferece aos usuários uma experiência consistente de autenticação. O logon único oferece aos usuários finais a facilidade e a simplicidade de acessar todos os aplicativos de que precisam para serem produtivos usando uma senha.

#### Baixo custo e sobrecarga de TI
O Azure AD Premium também oferece autoatendimento para redefinição de senha, gerenciamento de grupo e recursos de gerenciamento de aplicativos para capacitar a TI e a produtividade do usuário final em sua organização. Não é necessário que os usuários façam chamadas de assistência técnica e passem vários minutos em uma chamada, forneçam muitas informações para obter uma senha temporária, que é enviada por email ou compartilhada durante a chamada de maneira não segura.
- Ele funciona com a federação, a sincronização de senha ou contas de usuário somente em nuvem. Ele também aplica todas as suas políticas de senha local.
- Todo o tráfego é criptografado com uma chave específica do locatário e via HTTPS.
- Os usuários podem atualizar suas senhas do AD ou desbloquear suas próprias contas do AD em tempo real.
- Notificações em tempo real são enviadas para os usuários e administradores.

![Gráfico mostrando como o Azure Active Directory funciona com segurança local e na nuvem para fornecer recursos de autoatendimento para redefinição de senha aos usuários finais.  ](./media/ManageAccessAtScale/fig2.png)

#### Monitorar a ponte de identidade
O Azure AD Connect Health ajuda as organizações a monitorar e obter informações sobre sua infraestrutura de identidade local e os serviços de sincronização, bem como a manter uma conexão confiável com o Office 365 e o Microsoft Online Services, fornecendo recursos de monitoramento para os principais componentes de identidade, como servidores do AD FS, servidores do Azure AD Connect e controladores de domínio do Active Directory.

- Auditoria e conformidade com um clique por meio do portal do Azure.
- Investigação e análise forense: ajuda os administradores de TI a responder "quem fez o quê, onde e quando".
- Relatórios de atividade: fornece auditoria, entradas, SSPR, atividade do grupo, atividade do aplicativo, provisionamento de aplicativo etc.
- Relatórios de segurança: fornece atenuação avançada e resolução de anomalias de segurança por meio da proteção de identidade.

![Gráfico mostrando como o Azure AD Connect Health ajuda organizações a monitorar os seus principais componentes de identidade, como servidores do AD FS, servidores do Azure AD Connect e controladores de domínio do Active Directory. ](./media/ManageAccessAtScale/fig3.png)

## Como implementar um gerenciamento avançado de ciclo de vida do usuário
Vamos examinar alguns exemplos e as etapas que você poderia adotar para implementar esta solução:
1. Em um cenário do mundo real, sua empresa contrata um profissional e adiciona seu usuário ao sistema de RH como um membro da equipe de Marketing.
2.  Supondo que você já tenha integrado seu Active Directory local com o Azure AD por meio da sincronização de diretórios, o Azure AD Connect local sincronizará a conta de usuário com o Azure AD.
3.  Após a conta de usuário aparecer no Azure AD, você pode criar uma regra de associação de grupo dinâmico que atribui automaticamente os usuários de Marketing a ela.
4.  Após o grupo de Marketing ser preenchido automaticamente com seus usuários, você pode aproveitar o licenciamento seletivo baseado em grupo, que fornece a capacidade de adicionar usuários a um grupo de licenças específico, como o Azure AD Premium ou o Office 365 Enterprise E5.
  - Neste exemplo, isso fornece aos usuários acesso a todos os aplicativos de Office 365 de que eles precisam para realizar seu trabalho, bem como acesso do Azure AD Premium para realizar outras tarefas automatizadas.

Se, por algum motivo, um funcionário precisar deixar a empresa, você poderá removê-lo do sistema de RH, o que removerá automaticamente o acesso a todos os aplicativos e recursos provisionados anteriormente. Se o funcionário precisar apenas ser movido para outro departamento, as regras de associação de grupo dinâmico removerão automaticamente o acesso a aplicativos de Marketing e adicionarão acesso a aplicativos de outro departamento, com o usuário sendo removido da equipe de Marketing e adicionado ao grupo dinâmico do novo departamento.

### Como gerenciar aplicativos locais e na nuvem
Estas são as etapas que você pode seguir para adicionar, implantar e gerenciar aplicativos de SaaS da Microsoft e de terceiros com o Azure AD.
- Saiba mais sobre como [Integrar o Azure AD com aplicativos](https://azure.microsoft.com/documentation/articles/active-directory-integrating-applications-getting-started/).
- Saiba mais sobre como [Habilitar o logon único para aplicativos de SaaS](https://azure.microsoft.com/documentation/articles/active-directory-sso-integrate-saas-apps/).
- Saiba mais sobre como [Gerenciar o acesso a aplicativos](https://azure.microsoft.com/documentation/articles/active-directory-managing-access-to-apps/).

## Como implementar o portal de autoatendimento de redefinição de senha
Por padrão, o Azure AD vem com um recurso gratuito que permite que todo administrador execute seu próprio autoatendimento de redefinição de senha.

Usando o Azure AD Premium, você poderá além dos administradores de TI, fornecendo recursos portal de autoatendimento de redefinição de senha para os usuários. Você pode, rapidamente, habilitar políticas de redefinição de senha do usuário que estenderão os mesmos recursos de administração avançada para todos os usuários no diretório.

Saiba mais sobre o [pré-requisitos, como habilitar e como configurar o portal de autoatendimento de senha](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/) em seu locatário do Azure AD.

## Como implementar o Azure AD Connect Health
Você pode verificar a [documentação do Azure AD Connect Health](https://azure.microsoft.com/en-in/documentation/articles/active-directory-aadconnect-health/) para coletar mais informações sobre a ferramenta, seus recursos e as etapas que você pode executar para começar a usá-la em sua organização.

O Azure AD Connect Health está disponível no [portal do Azure](https://ms.portal.azure.com) e requer que um agente de integridade seja instalado nos controladores de domínio locais que você deseja monitorar. Saiba mais sobre [como instalar o agente de integridade](https://azure.microsoft.com/en-in/documentation/articles/active-directory-aadconnect-health-agent-install/).

O painel de DCs (controladores de domínio) fornece um único ponto de vista do status de integridade e operacional do ambiente, em que o administrador poderá encontrar facilmente quais DCs são proprietários de função FSMO, têm alertas ativos, são catálogos globais, em conjunto com colunas adicionais como "Acessível por PDC", "Acessível por GC", "Estado de SYSVOL" e outros:

![Captura de tela mostrando o painel de controladores de domínio com informações sobre o controlador de domínio selecionado. ](./media/ManageAccessAtScale/fig4.png)

Além disso, os controladores de domínio podem ser agrupados por seu domínio correspondente ou o administrador pode agrupá-los por site:

![Captura de tela mostrando controladores de domínio agrupados por site. ](./media/ManageAccessAtScale/fig5.png)

O painel de Status de Replicação mostra a aparência da topologia de replicação dentro do ambiente, em conjunto com informações sobre a última tentativa de replicação para cada contexto de nomeação:

![Captura de tela mostrando o painel de Status de Replicação com informações sobre a última tentativa de replicação. ](./media/ManageAccessAtScale/fig6.png)

Os detalhes de um alerta contêm mais informações sobre o problema que causa o alerta, a correção necessária e um link para recursos adicionais de solução de problemas:

![Captura de tela mostrando detalhes sobre um alerta especificado. ](./media/ManageAccessAtScale/fig7.png)

O monitoramento de desempenho do AD Connect Health fornece uma maneira fácil de comparar o desempenho dos DCs monitorados em relação uns aos outros, bem como comparar diferentes métricas de interesse:

![Captura de tela mostrando o monitoramento de desempenho dos controladores de domínio selecionados. ](./media/ManageAccessAtScale/fig8.png)



<!--HONumber=Oct16_HO3-->


