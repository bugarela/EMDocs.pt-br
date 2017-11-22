---
title: Proteger os sites do SharePoint Online em um ambiente de desenvolvimento/teste | Microsoft Docs
description: "Crie sites de equipe do SharePoint Online públicos, privados, confidenciais e altamente confidenciais em um ambiente de desenvolvimento/teste."
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
ms.date: 11/15/2017
ms.author: josephd
ms.openlocfilehash: 6e7050dca9c0f66f481fe6ee37fb88bf4617f982
ms.sourcegitcommit: 684c942047754e93378e271f5b1a659a9752f0ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a>Proteger os sites do SharePoint Online em um ambiente de desenvolvimento/teste

## <a name="introduction"></a>Introdução

Este artigo fornece instruções passo a passo para criar um ambiente de desenvolvimento/teste que inclui os quatro tipos diferentes de sites de equipe do SharePoint Online para a [solução de arquivos e sites do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md).

Use este ambiente de desenvolvimento/teste para experimentar com os comportamentos de proteção de informações e ajustar as configurações para suas necessidades específicas antes de implantar sites de equipe do SharePoint Online na produção.

## <a name="phase-1-create-your-devtest-environment"></a>Fase 1: Criar seu ambiente de desenvolvimento/teste
Nesta fase, você deve obter assinaturas de avaliação do Office 365 e do Enterprise Mobility + Security para uma organização fictícia.

Primeiro, siga as instruções na **Fase 2** do [ambiente de desenvolvimento/teste do Office 365](https://technet.microsoft.com/library/mt736406.aspx).

Em seguida, inscreva-se para a **assinatura de avaliação do EMS** e adicione-a à mesma organização que a assinatura de avaliação do Office 365 e siga essas etapas:

1. Se necessário, entre no **Portal do Office 365** com as credenciais da conta de administrador global da sua assinatura de avaliação. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Clique no bloco de **Administração**.
3. Na guia **Centro de Administração do Office** no navegador, no painel de navegação esquerdo, clique em **Cobrança > Comprar serviços**.
4. Na página **Comprar serviços**, localize o item **Enterprise Mobility + Security E5** e passe o ponteiro do mouse sobre ele e clique em **Iniciar avaliação gratuita**.
5. Na página **Confirmar seu pedido**, clique em **Experimentar agora**.
6. Na página **Recibo do pedido**, clique em **Continuar**.

Em seguida, habilite a licença do Enterprise Mobility + Security E5 para sua conta de administrador global.

1. Na guia **Centro de Administração do Office 365** no navegador, no painel de navegação esquerdo, clique em **Usuários > Usuários ativos**.
2. Clique em sua conta de administrador global e, em seguida, clique em **Editar para Licenças de produto**.
3. No painel **Licenças de produto**, defina a licença para **Enterprise Mobility + Security E5** como **Ativado**, clique em **Salvar**e clique duas vezes em **Fechar**.


## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>Fase 2: Criar e configurar seus grupos e usuários do Azure AD (Active Directory)
Nesta fase, você cria e configura os usuários e grupos do Azure AD para sua organização fictícia.

Primeiro, crie um conjunto de grupos para uma organização típica com o portal do Azure.

1. Crie uma guia separada no navegador e vá para o **Portal do Azure** em [https://portal.azure.com](https://portal.azure.com). Se necessário, entre com as credenciais da conta de administrador global da sua assinatura de avaliação do Office 365 E5.
2. No Portal do Azure, clique em **Azure Active Directory > Usuários e grupos > Todos os grupos**.
3. Na folha **Todos os grupos**, clique em **+ Novo grupo**.
4. Na folha **Grupo**:
 * Digite **Pacote C** em **Nome**.
 * Selecione **Atribuído** em **Associação**.
 * Selecione **Sim** para **Habilitar recursos do Office**.
5. Clique em **Criar**e, em seguida, feche a folha **Grupo**.
6. Repita as etapas 3 a 5 para os seguintes nomes de grupo:
 * Equipe de TI
 * Equipe de pesquisa
 * Equipe regular
 * Equipe de marketing
 * Equipe de vendas
7. Feche a guia do portal do Azure no navegador.

Em seguida, configure o licenciamento automático para que os membros de seus grupos recebam automaticamente a atribuição de licenças para suas assinaturas do Office 365 e EMS e, depois, siga essas etapas:

1. No Portal do Azure, clique em **Azure Active Directory > Licenças > Todos os produtos**.
2. Na lista, selecione **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** e clique em **Atribuir**.
3. Na folha **Atribuir licença**, clique em **Usuários e grupos**.
4. Na lista de grupos, selecione o seguinte:
 * Pacote C
 * Equipe de TI
 * Equipe de pesquisa
 * Equipe regular
 * Equipe de marketing
 * Equipe de vendas
5. Clique em **Selecionar** e clique em **Atribuir**.
6. Feche a guia do Portal do Azure no navegador.

Em seguida, você deve se [Conectar ao módulo PowerShell do Azure Active Directory V2](https://go.microsoft.com/fwlink/?linkid=842218).

Preencha o nome da organização, seu local e uma senha comum. Execute os comandos abaixo no prompt de comando de PowerShell ou no ISE (Ambiente de Script Integrado) para criar contas de usuário e adicioná-las aos grupos correspondentes.

```
$orgName="[organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name]"
$location="[the ISO ALPHA2 country code, such as US for the United States]"
$commonPassword="[common password for all the new accounts]"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Research staff"
$userNames=@("Researcher1")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Regular staff"
$userNames=@("Regular1", "Regular2")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Sales staff"
$userNames=@("SalesPerson1")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

>[!Note]
>O uso de uma senha comum aqui é para a automação e facilidade de configuração para um ambiente de desenvolvimento/teste. Isso nunca é recomendado assinaturas de produção.
>

Em seguida, siga as etapas abaixo para verificar se o licenciamento baseado em grupo está funcionando corretamente.

1. Na guia **Microsoft Office Home** do navegador, clique no bloco **Administração**.
2. Na nova guia **Centro de Administração do Office** do navegador, clique em **Usuários**.
3. Na lista de usuários, clique em **CEO**.
4. No painel que lista as propriedades da conta de usuário **CEO**, verifique se ele recebeu a atribuição das licenças **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** (em **Licenças de produto**).

## <a name="phase-3-create-office-365-labels"></a>Fase 3: Criar rótulos do Office 365

Nesta fase, você deve criar os rótulos para os diferentes níveis de segurança para as pastas e documentos do site da equipe do SharePoint Online.

1. Se necessário, use uma instância particular do navegador da Internet e entre no **Portal do Office 365** com a conta de administrador global da sua assinatura de avaliação do Office 365 E5. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Na guia **Microsoft Office Home**, clique no bloco **Administração**.
3. Na nova guia **Centro de Administração do Office** do navegador, clique em **Centros de Administração > Segurança e Conformidade**.
4. Na nova guia **Início – Segurança e Conformidade** do navegador, clique em **Classificações > Rótulos**.
5. No painel **Início > Rótulos**, clique em **Criar um rótulo**.
6. No painel **Atribuir nome ao seu rótulo**, digite **Público Interno** e clique em **Avançar**.
7. No painel **Configurações do Rótulo**, clique em **Avançar**.
8. No painel **Examine as configurações**, clique em **Criar este rótulo** e clique em **Fechar**.
9. Repita as etapas de 5 a 8 para os rótulos adicionais:
 * Private
 * Confidencial
 * Altamente Confidencial
10. No painel **Início > Rótulos**, clique em **Publicar rótulos**.
11. No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.
12. No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos e clique em **Concluído**.
13. No painel **Escolher rótulos para publicar**, clique em **Avançar**.
14. No painel **Escolher locais**, clique em **Avançar**.
15. No painel **Atribuir um nome à política**, digite **Organização de exemplo** em **Nome** e clique em **Avançar**.
16. No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.

## <a name="phase-4-create-your-sharepoint-online-team-sites"></a>Fase 4: Criar seus sites de equipe do SharePoint Online
Nesta fase, você cria e configura os quatro tipos de sites de equipe do SharePoint Online para sua organização de exemplo.

### <a name="organization-wide-team-site"></a>Site de equipe de toda a organização
Para criar um site de equipe do SharePoint Online público de linha de base, faça o seguinte:

1. Se necessário, use um navegador no computador local e entre no Portal do Office 365 usando sua conta de administrador global. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Na lista de blocos, clique em **SharePoint**.
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
4. Na página **Criar um site**, clique em **Site de equipe**.
5. Em **Nome do site**, digite **Toda a organização**.
6. Na **Descrição do site de equipe**, digite **Site do SharePoint para toda a organização**.
7. Em **Configurações de privacidade**, selecione **Público – qualquer pessoa na organização pode acessar esse site** e clique em **Avançar**.
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.

Em seguida, configure a pasta de documentos do site de equipe Toda a organização para o rótulo Público Interno.

1. Na guia **Toda a organização – Início** do navegador, clique em **Documentos**.
2. Clique no ícone de configurações e clique em **Configurações de biblioteca**.
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
4. Em **Configurações – Aplicar Rótulo**, selecione **Público Interno** e clique em **Salvar**.

Aqui está a configuração resultante.

 ![Proteção de site de equipe público](./media/secure-sharepoint-online-sites-dev-test/pubsite.png)

### <a name="project-1-team-site"></a>Site de equipe do projeto 1
Para criar um site de equipe do SharePoint Online privado de linha de base para um projeto dentro da organização, faça o seguinte:

1. Se necessário, use um navegador no computador local e entre no **Portal do Office 365** usando sua conta de administrador global. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Na lista de blocos, clique em **SharePoint**.
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
4. Na página **Criar um site**, clique em **Site de equipe**.
5. Em **Nome do site**, digite **Projeto 1**.
6. Na **Descrição do site de equipe**, digite **Site do SharePoint para Projeto 1**.
7. Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.

Em seguida, configure a pasta de documentos do site de equipe Projeto 1 para o rótulo Privado.

1. Na guia **Projeto 1 – Início** do navegador, clique em **Documentos**.
2. Clique no ícone de configurações e clique em **Configurações de Biblioteca**.
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
4. Em **Configurações – Aplicar Rótulo**, selecione **Privado** e clique em **Salvar**.

Aqui está a configuração resultante.

 ![Proteção de site de equipe privado](./media/secure-sharepoint-online-sites-dev-test/privsite.png)

### <a name="marketing-campaigns-team-site"></a>Site de equipe de campanhas de marketing

Para criar um site de equipe do SharePoint Online isolado de nível confidencial para recursos de campanha de marketing, faça o seguinte:

1. Usando um navegador no computador local, entre no **Portal do Office 365** usando sua conta de administrador global. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Na lista de blocos, clique em **SharePoint**.
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
4. Na página **Criar um site**, clique em **Site de equipe**.
5. Em **Nome do site de equipe**, digite **Campanhas de marketing**.
6. Em **Descrição do site de equipe**, digite **Site do SharePoint para recursos de campanha de marketing (confidencial)**.
7. Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
9. Na nova guia **Campanhas de marketing** no navegador, na barra de ferramentas, clique no ícone de configurações e clique em **Permissões do site**.
10. No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.
11. Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.
12. Na caixa de diálogo **Configurações de Solicitação de Acesso**:
13. Desmarque as caixas de seleção **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir que os membros convidem outras pessoas para o grupo de membros do site**.
14. Digite **ITAdmin1@**[nome da sua organização]**.onmicrosoft.com** em **Enviar todas as solicitações de acesso**, e clique em **OK**.
15. Clique em **Membros de campanhas de marketing** na lista.
16. Na página **Pessoas e Grupos**, clique em **Novo**.
17. Na caixa de diálogo **Compartilhar**, digite **Equipe de marketing**, selecione-a e clique em **Compartilhar**.
18. Repita as etapas acima para a conta de usuário **Researcher1**.
19. Clique no botão de voltar do navegador e, em seguida, clique em **Proprietários de campanhas de marketing** na lista.
20. Na página **Pessoas e Grupos**, clique em **Novo**.
21. Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione-a e clique em **Compartilhar**.
22. Clique no botão de voltar do navegador e feche a guia **Pessoas e Grupos** no navegador, clique na guia **Campanhas de marketing – Início** no navegador e feche o painel **Permissões do site**.

Aqui estão os resultados da configuração de permissões:

* O grupo do SharePoint **Campanhas de marketing – membros** contém apenas o grupo **Campanhas de marketing** (que contém a conta de usuário de administrador global), o grupo **Equipe de marketing** (que contém as conas de usuário Marketing1 e Marketing2) e a conta de usuário **Researcher1**.
* O grupo do SharePoint **Campanhas de marketing – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário ITAdmin1 e ITAdmin2).
* O grupo do SharePoint **Campanhas de marketing – Visitantes** não contém grupos ou contas de usuário.
* Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Campanhas de marketing – Proprietários**).
* Outras contas de usuário não podem acessar o site ou seus recursos, mas podem solicitar o acesso ao site, que envia um email para a caixa de correio da conta de usuário _ITAdmin1_.

Em seguida, configure a pasta de documentos do site de equipe Campanhas de marketing para o rótulo Confidencial.

1. Na guia **Campanhas de marketing – Início** do navegador, clique em **Documentos**.
2. Clique no ícone de configurações e clique em **Configurações de Biblioteca**.
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
4. Em **Configurações – Aplicar Rótulo**, selecione **Confidencial** e clique em **Salvar**.

Em seguida, configure uma política de DLP (prevenção de perda de dados) que notifica os usuários quando eles compartilham um documento em um site de equipe do SharePoint Online com o rótulo Confidencial, que inclui o site de Campanhas de marketing, fora da organização.

1. Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança e Conformidade**.
2. Na nova guia **Segurança e Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.
3. No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.
4. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.
5. No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Confidencial** em **Nome** e clique em **Avançar**.
6. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e clique em **Avançar**.
7. Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.
8. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.
9. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.
10. No painel **Rótulos**, clique em **+ Adicionar**, selecione o rótulo **Confidencial**, clique em **Adicionar** e clique em **Concluído**.
11. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
12. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.
13. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
14. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
15. Na caixa de texto, digite ou cole o seguinte:
 * Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, em Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.
16. Clique em **OK**.
17. No painel **O que deseja fazer se detectarmos informações confidenciais?**, desmarque a caixa de seleção **Impedir que as pessoas compartilhem e restringir o acesso ao conteúdo compartilhado** e clique em **Avançar**.
18. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Yes** para ativá-la imediatamente e clique em **Avançar**.
19. No painel **Examine as configurações**, clique em **Criar** e clique em **Fechar**.

Aqui está a configuração resultante.

 ![Proteção Confidencial](./media/secure-sharepoint-online-sites-dev-test/senssite.png)

### <a name="company-strategy-team-site"></a>Site de equipe de estratégia de empresa
Para criar um site de equipe do SharePoint Online isolado no nível altamente confidencial para recursos corporativos estratégicos dos diretores da organização, faça o seguinte:

1. Se necessário, use um navegador no computador local e entre no **Portal do Office 365** usando sua conta de administrador global. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Na lista de blocos, clique em **SharePoint**.
3. Na nova guia **SharePoint** no navegador, clique em **+ Criar site**.
4. Na página **Criar um site**, clique em **Site de equipe**.
5. Em **Nome do site da equipe**, digite **Estratégia da empresa**.
6. Em **Descrição do site da equipe**, digite **Site do SharePoint para estratégia da empresa (altamente confidencial)**.
7. Em **Configurações de privacidade**, selecione **Privado – somente membros podem acessar esse site** e clique em **Avançar**.
8. No painel **Quem você deseja adicionar?**, clique em **Concluir**.
9. Na nova guia **Estratégia da empresa** no navegador, na barra de ferramentas, clique no ícone de configurações e clique em **Permissões do site**.
10. No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.
11. Na nova guia **Permissões** no navegador, clique em **Configurações de Solicitação de Acesso**.
12. Na caixa de diálogo **Configurações de Solicitação de Acesso**, desmarque **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir que os membros convidem outros para o grupo de membros do site** (de forma que todas as três caixas de seleção estejam desmarcadas) e clique em **OK**.
13. Clique em **Membros da estratégia da empresa** na lista e, na página **Pessoas e Grupos**, clique em **Novo**.
14. Na caixa de diálogo **Compartilhar**, digite **Pacote C**, selecione-a e clique em **Compartilhar**.
15. Clique em **Proprietários da estratégia da empresa** na lista e, na página **Pessoas e Grupos**, clique em **Novo**.
16. Na caixa de diálogo **Compartilhar**, digite **Equipe de TI**, selecione-a e clique em **Compartilhar**.
17. Clique no botão de voltar do navegador e feche a guia **Pessoas e Grupos**.
18. Clique na guia **Estratégia da empresa – Início** no navegador e feche o painel **Permissões do site**.

Aqui estão os resultados da configuração de permissões:

* O grupo do SharePoint **Estratégia da empresa – Membros** contém apenas o grupo **Pacote C** (que contém apenas as contas de usuário do CEO, do CFO e do CIO) e o grupo **Estratégia da empresa** (que contém apenas a conta de usuário de administrador global).
* O grupo do SharePoint **Estratégia da empresa – Proprietários** contém apenas o grupo **Equipe de TI** (que contém apenas as contas de usuário _ITAdmin1_ e _ITAdmin2_).
* O grupo do SharePoint **Estratégia da empresa – Visitantes** não contém grupos ou contas de usuário.
* Os membros não podem modificar permissões de nível de site (isso pode ser feito apenas por membros do grupo **Estratégia da empresa – Proprietários**).
* Outras contas de usuário não podem acessar o site ou seus recursos ou solicitar o acesso ao site. As permissões adicionais para o site devem ser feias pelo administrador global ou por um membro do grupo **Estratégia da empresa – Proprietários**.

Em seguida, configure a pasta de documentos do site da equipe de estratégia da empresa para o rótulo Altamente Confidencial.

1. Na guia **Estratégia da empresa – Início** do navegador, clique em **Documentos**.
2. Clique no ícone de configurações e clique em **Configurações de Biblioteca**.
3. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
4. Em **Configurações – Aplicar Rótulo**, selecione **Altamente Confidencial** e clique em **Salvar**.

Em seguida, configure uma política de DLP que bloqueia os usuários quando eles compartilham um documento em um site de equipe do SharePoint Online com o rótulo Altamente Confidencial, que inclui o site de Estratégia da empresa, fora da organização.

1. Se necessário, use um navegador no computador local e entre no **Portal do Office 365** com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança e Conformidade**.
3. Na nova guia **Segurança e Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.
4. No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.
5. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.
6. No painel **Atribuir um nome à política**, digite **Sites de equipe do SharePoint Online de rótulo Altamente Confidencial** em **Nome** e clique em **Avançar**.
7. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e clique em **Avançar**.
8. Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.
9. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.
10. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.
11. No painel **Rótulos**, clique em **+ Adicionar**, selecione o **rótulo Altamente Confidencial**, clique em **Adicionar** e clique em **Concluído**.
12. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
13. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.
14. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
15. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
16. Na caixa de texto, digite ou cole o seguinte:
 * Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em **Arquivo**, em seguida, **Proteger Documento** e **Criptografar com Senha** e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.
17. Clique em **OK**.
18. No painel **O que deseja fazer se detectarmos informações confidenciais?**, selecione **Exigir uma justificativa de negócios para substituir** e clique em **Avançar**.
19. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Yes** para ativá-la imediatamente e clique em **Avançar**.
20. No painel **Examine as configurações**, clique em **Criar** e clique em **Fechar**.

Em seguida, siga as instruções em [Ativar o Azure RMS com o centro de administração do Office 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).

Depois, configure a Proteção de Informações do Azure com uma nova política e sub-rótulo em escopo para proteção e permissões com as seguintes etapas:

1. Em uma guia separada do navegador, em que você entrou com sua conta de administrador global, vá até o **Portal do Azure** ([http://portal.azure.com](http://portal.azure.com/)).
3. Se esta é a primeira vez que configura a Proteção de Informações do Azure, consulte [estas instruções](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).
4. No painel de lista, clique em **Mais serviços**, digite **informações** e clique em **Proteção de Informações do Azure**.
5. Na folha **Proteção de Informações do Azure**, clique em **Políticas no escopo > + Adicionar uma nova política**.
6. Digite **CompanyStrategy** em **Nome da política** e **Rótulo para documentos no site da equipe de estratégia da Empresa** em **Descrição**.
7. Clique em **Selecionar usuários ou grupos que obtêm essa política > Usuário/Grupos**e, em seguida, selecione **Pacote C**.
8. Clique em **Selecionar > OK**.
9. Para o rótulo **Altamente Confidencial**, clique nas reticências (...) e, em seguida, clique em **Adicionar um sub-rótulo**.
10. Digite **CompStrat-HC** em **Nome** e **Proteger documentos no site da equipe de estratégia da Empresa** em **Descrição**.
11. Em **Definir permissões para documentos e emails que contenham este rótulo**, clique em **Proteger**.
12. Na seção **Proteção**, clique em **Azure (chave de nuvem)**.
13. Na folha **Proteção**, em **Configurações de proteção**, clique em **+ Adicionar permissões**.
14. Na folha **Adicionar permissões**, em **Especificar usuários e grupos**, clique em **+ Procurar no diretório**.
15. No painel **Usuários e Grupos do AAD**, selecione **Pacote C** e clique em **Selecionar**.
16. Em **Escolher permissões da predefinição**, desmarque as caixas de seleção **Imprimir, copiar e extrair conteúdo** e **Encaminhar**.
17. Clique em **OK** duas vezes.
18. Na folha **Rótulo**, clique em **Salvar**.
19. Feche a nova folha de política em escopo.
20. Na folha **Proteção de Informações do Azure – Políticas em escopo**, clique em **Publicar** e depois em **Sim**.

Para proteger um documento com a Proteção de Informações do Azure e o rótulo Altamente Confidencial, você deve [instalar o cliente de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/install-client-app) em um computador de teste, instalar o Office do Portal do Office 365 e entre no Microsoft Word com uma conta no grupo Pacote C da assinatura de avaliação.

Aqui está a configuração resultante.

 ![Proteção Altamente Confidencial](./media/secure-sharepoint-online-sites-dev-test/hcsite.png)

### <a name="create-documents-and-test-access"></a>Criar documentos e testar o acesso

Agora você está pronto para criar documentos nestes quatro sites e testar o acesso a eles com várias contas de usuário em sua assinatura de avaliação.

Aqui está a configuração geral para todos os quatro sites de equipe do SharePoint Online.

 ![Configuração final](./media/secure-sharepoint-online-sites-dev-test/finalconfig.png)

## <a name="next-steps"></a>Próximas etapas

Quando você estiver pronto para a implantação dos sites do SharePoint Online seguros na produção, consulte [Arquivos e sites do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md) para obter informações detalhadas e links para os artigos de implantação passo a passo.

