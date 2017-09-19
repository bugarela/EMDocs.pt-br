---
title: "Implantar sites para três camadas de proteção | Microsoft Docs"
description: "Crie e configure sites de equipe do SharePoint Online para vários níveis de proteção de informações."
services: active-directory
keywords: Office 365, Windows 10, Enterprise Mobility and Security, Microsoft 365 Enterprise
documentationcenter: 
author: JoeDavies-MSFT
manager: laurawi
ms.assetid: 
ms.prod: microsoft-365-enterprise
ms.service: 
ms.workload: 
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 08/28/2017
ms.author: josephd
ms.openlocfilehash: 6d19a8b2fa39806e2a03ca8e3eb9ffae15605cc4
ms.sourcegitcommit: 5b34af60e3aac19d618f1c6297da91e2c050a374
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="deploy-sites-for-three-tiers-of-protection"></a>Implantar sites para três camadas de proteção

## <a name="introduction"></a>Introdução

Use as etapas neste artigo para projetar e implantar sites de equipe do SharePoint Online de linha de base, confidenciais e altamente confidenciais. Para obter mais informações sobre essas três camadas de proteção, consulte [Arquivos e sites do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md).

## <a name="baseline-sharepoint-online-team-sites"></a>Sites de equipe do SharePoint Online de linha de base
A proteção de linha de base inclui os sites de equipe públicos e privados. Os sites de equipe públicos podem ser descobertos e acessados por qualquer pessoa na organização. Os sites privados podem ser descobertos e acessados somente por membros do grupo do Office 365 associado ao site de equipe. Esses dois tipos de sites de equipe permitem que os membros compartilhem o site com outras pessoas.

### <a name="public"></a>Público
Para criar um site de equipe do SharePoint Online de linha de base com permissões e acesso público, faça o seguinte:

1. Entre no **Portal do Office 365** com uma conta que também será usada para administrar o site de equipe do SharePoint Online (um administrador do SharePoint Online). Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Na lista de blocos, clique em **SharePoint**.
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
4. Na página **Criar um site**, clique em **Site de equipe**.
5. Em **Nome do site**, digite um nome para o site de equipe público. 
6. Em **Descrição do site de equipe**, digite uma descrição do objetivo do site.
7. Em **Configurações de privacidade**, selecione **Público – qualquer pessoa na organização pode acessar esse site** e clique em **Avançar**.
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.

Abaixo está a configuração resultante.

 ![SharePoint de linha de base público](./media/deploy-sites-for-three-tiers-of-protection/pub_site.png)

### <a name="private"></a>Private
Para criar um site de equipe do SharePoint Online de linha de base com permissões e acesso privado, faça o seguinte:

1. Entre no **Portal do Office 365** com uma conta que também será usada para administrar o site de equipe do SharePoint Online (um administrador do SharePoint Online). Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Na lista de blocos, clique em **SharePoint**.
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
4. Na página **Criar um site**, clique em **Site de equipe**.
5. Em **Nome do site**, digite um nome para o site de equipe privado. 
6. Em **Descrição do site de equipe**, digite uma descrição do objetivo do site.
7. Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
8. No painel **Quem você deseja adicionar?**, em **Adicionar membros**, digite os nomes das contas de usuário que têm acesso a esse site de equipe privado.
9. Quando você terminar de adicionar o conjunto inicial de membros ao site, clique em **Concluir**.

Abaixo está a configuração resultante.

 ![SharePoint de linha de base privado](./media/deploy-sites-for-three-tiers-of-protection/priv_site.png)

## <a name="sensitive-sharepoint-online-team-sites"></a>Sites de equipe do SharePoint Online confidenciais
Um site de equipe do SharePoint Online confidencial é um site de equipe isolado, o que significa que as permissões são controladas por meio da associação em grupos do SharePoint, em vez de ser membro do grupo do Office 365 associado ao site de equipe.

Para criar um site de equipe isolado, siga estas duas etapas principais.

### <a name="step-1-design-your-isolated-site"></a>Etapa 1: Projetar o site isolado
Para projetar o site de equipe isolado, você precisa determinar:

* Seus níveis de permissão e grupos do SharePoint.
* O conjunto de grupos de acesso que serão membros dos grupos do SharePoint.
 O conjunto de grupos de acesso recomendado é um para os membros do site, um para os visualizadores do site e um para os administradores do site.
* Se você usará grupos aninhados dentro de seus grupos de acesso.

Por exemplo, os níveis de permissão e estrutura de grupo recomendados têm essa aparência:

|**Grupo do SharePoint**|**Nível de permissão**|**Grupo de acesso (exemplos)**|
|:-----|:-----|:-----|
|Membros do [nome do site]|Editar|Membros do [nome do site]|
|Visitantes do [nome do site]|Ler|Visualizadores do [nome do site]|
|Proprietários do [nome do site]|Controle total|Administradores do [nome do site]|

Os níveis de permissão e grupos do SharePoint são criados por padrão para um site de equipe. Você precisa determinar os nomes dos seus grupos de acesso.

Para obter os detalhes do processo de design, consulte [Projetar um site de equipe do SharePoint Online isolado](https://technet.microsoft.com/library/mt784687.aspx).

### <a name="step-2-deploy-your-isolated-site"></a>Etapa 2: Implantar o site isolado
Para implantar seu site isolado, primeiro você precisa:

* Determinar as contas de usuário e os grupos a serem adicionados a cada um dos seus grupos de acesso.
* Criar os grupos de acesso e adicionar os membros de usuário e grupo.

Para obter as etapas detalhadas, consulte a **Fase 1** de [Implantar um site de equipe do SharePoint Online isolado](https://technet.microsoft.com/library/mt784693.aspx).

Em seguida, crie o site de equipe do SharePoint Online com estas etapas.

1. Entre no **Portal do Office 365** com uma conta que também será usada para administrar o site de equipe do SharePoint Online (um administrador do SharePoint Online). Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Na lista de blocos, clique em **SharePoint**.
3. Na nova guia **SharePoint** do navegador, clique em **+ Criar site**.
4. Na página **Criar um site**, clique em **Site de equipe**.
5. Em **Nome do site**, digite um nome para o site de equipe privado.
6. Na descrição de **Site de equipe**, digite uma descrição opcional.
7. Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.

Em seguida, no novo site de equipe do SharePoint Online, configure as permissões com estas etapas.

1. Determine o nome UPN do administrador de TI ou outra pessoa que será responsável por responder e resolver as solicitações de acesso ao site (_belindan@contoso.com_ é um exemplo de um UPN). Anote esse UPN.
2. Na barra de ferramentas, clique no ícone configurações e, em seguida, clique em **Permissões do site**.
3. No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.
4. Na nova guia **Permissões** do navegador, clique em **Configurações de Solicitação de Acesso**.
5. Na caixa de diálogo **Configurações de Solicitações de Acesso**:
  1. Desmarque as caixas de seleção **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir que os membros convidem outras pessoas para o grupo de membros do site**.
  2. Digite o UPN do seu administrador de TI da etapa 1 em **Enviar todas as solicitações de acesso**.
  3. Clique em **OK**.
6. Na guia **Permissões** do navegador, clique em **Membros do [nome do site]** na lista.
7. Em **Pessoas e Grupos**, clique em **Novo**. Na caixa de diálogo **Compartilhar**, digite o nome do grupo de acesso dos membros do seu site para esse site, selecione-o e clique em **Compartilhar**.
8. Clique no botão de voltar do navegador e, em seguida, clique em **Proprietários do [nome do site]** na lista.
9. Em **Pessoas e Grupos**, clique em **Novo**. Na caixa de diálogo **Compartilhar**, digite o nome do grupo de acesso dos administradores do site para esse site, selecione-o e clique em **Compartilhar**.
10. Clique no botão de voltar do navegador e, em seguida, clique em **Visitantes do [nome do site]** na lista.
11. Em **Pessoas e Grupos**, clique em **Novo**. Na caixa de diálogo **Compartilhar**, digite o nome do grupo de acesso dos visualizadores do site para esse site, selecione-o e clique em **Compartilhar**.
12. Feche a guia **Permissões** do navegador.

Abaixo estão os resultados dessas configurações de permissão:

* O grupo do SharePoint **Proprietários do [nome do site]** contém o grupo de acesso de administradores de site, em que todos os membros têm o nível de permissão **Controle total**.
* O grupo do SharePoint **Membros do [nome do site]** contém o grupo de acesso de membros de site, em que todos os membros têm o nível de permissão **Editar**.
* O grupo do SharePoint **Visitantes do [nome do site]** contém o grupo de acesso de visualizadores de site, em que todos os membros têm o nível de permissão **Ler**.
* A capacidade de os membros convidarem outros membros está desabilitada. 
* A capacidade de não membros solicitarem o acesso está habilitada. 

Abaixo está a configuração resultante.

 ![Proteção Confidencial](./media/deploy-sites-for-three-tiers-of-protection/sens_site.png)

Os membros do site, por meio da associação de grupo em um dos grupos de acesso, agora podem colaborar com segurança nos recursos do site.

## <a name="highly-confidential-sharepoint-online-team-sites"></a>Sites de equipe do SharePoint Online altamente confidenciais
Um site de equipe do SharePoint Online altamente confidencial é um site de equipe isolado, o que significa que as permissões são controladas por meio da associação em grupos do SharePoint, em vez de ser membro do grupo do Office 365 associado ao site de equipe.

Para criar um site de equipe isolado para colaboração e informações altamente confidenciais, há duas etapas principais.

### <a name="step-1-design-your-isolated-site"></a>Etapa 1: Projetar o site isolado
Para projetar o site de equipe isolado, você precisa determinar:

* Seus níveis de permissão e grupos do SharePoint.
* O conjunto de grupos de acesso que serão membros dos grupos do SharePoint.
 O conjunto de grupos de acesso recomendado é um para os membros do site, um para os visualizadores do site e um para os administradores do site.
* Se você usará grupos aninhados dentro de seus grupos de acesso.

Por exemplo, os níveis de permissão e estrutura de grupo recomendados têm essa aparência:
 
|**Grupo do SharePoint**|**Nível de permissão**|**Grupo de acesso (exemplos)**|
|:-----|:-----|:-----|
|Membros do [nome do site]|Editar|Membros do [nome do site]|
|Visitantes do [nome do site]|Ler|Visualizadores do [nome do site]|
|Proprietários do [nome do site]|Controle total|Administradores do [nome do site]|

Os níveis de permissão e grupos do SharePoint são criados por padrão para um site de equipe. Você precisa determinar os nomes dos seus grupos de acesso.

Para obter os detalhes do processo de design, consulte [Projetar um site de equipe do SharePoint Online isolado](https://technet.microsoft.com/library/mt784687.aspx).

### <a name="step-2-deploy-your-isolated-site"></a>Etapa 2: Implantar o site isolado
Para implantar seu site isolado, primeiro você precisa:

* Determine os membros do grupo e usuário de cada um dos grupos de acesso.
* Criar os grupos de acesso e adicionar os membros de usuário e grupo.
* Crie um site de equipe isolado que usa os grupos de acesso.

Para obter as etapas detalhadas, consulte [Implantar um site de equipe do SharePoint Online isolado](https://technet.microsoft.com/library/mt784693.aspx).

Abaixo estão os resultados das configurações de permissão:

* O grupo do SharePoint **Proprietários do [nome do site]** contém o grupo de acesso de administradores de site, em que todos os membros têm o nível de permissão **Controle total**.
* O grupo do SharePoint **Membros do [nome do site]** contém o grupo de acesso de membros de site, em que todos os membros têm o nível de permissão **Editar**.
* O grupo do SharePoint **Visitantes do [nome do site]** contém o grupo de acesso de visualizadores de site, em que todos os membros têm o nível de permissão **Ler**.
* A capacidade de os membros convidarem outros membros está desabilitada. 
* A capacidade de não membros solicitarem o acesso está desabilitada. 

Aqui está a configuração resultante.

 ![Proteção Altamente Confidencial](./media/deploy-sites-for-three-tiers-of-protection/hc_site.png)

Os membros do site, por meio da associação de grupo em um dos grupos de acesso, agora podem colaborar com segurança nos recursos do site. 

Para obter mais informações, consulte [Proteger arquivos com rótulos do Office 365 e com o DLP](protect-files-with-o365-labels-dlp.md).

## <a name="next-steps"></a>Próximas etapas
[Diretrizes de segurança da Microsoft para campanhas políticas, organizações sem fins lucrativos e outras organizações ágeis](https://technet.microsoft.com/library/mt493213.aspx)

[Proteger sites e arquivos do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md)

[Proteger os sites do SharePoint Online em um ambiente de desenvolvimento/teste](secure-sharepoint-online-sites-dev-test.md)

[Adoção da nuvem e soluções híbridas](https://technet.microsoft.com/library/dn262744.aspx)







