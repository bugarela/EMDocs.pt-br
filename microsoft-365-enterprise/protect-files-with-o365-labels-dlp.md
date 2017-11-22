---
title: "Proteger arquivos do SharePoint Online com rótulos e prevenção de perda de dados do Office 365| Microsoft Docs"
description: "Aplique rótulos do Office 365 e políticas de DLP (prevenção de perda de dados) aos sites de equipe do SharePoint Online com vários níveis de proteção de informações."
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
ms.openlocfilehash: ec400ac466aeb5a20473c00f7a7df488e4b23725
ms.sourcegitcommit: 684c942047754e93378e271f5b1a659a9752f0ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="protect-sharepoint-online-files-with-office-365-labels-and-data-loss-prevention"></a>Proteger arquivos do SharePoint Online com rótulos do Office 365 e prevenção de perda de dados

## <a name="introduction"></a>Introdução
Use as etapas neste artigo para projetar e implantar políticas de DLP (prevenção de perda de dados) e rótulos do Office 365 para sites de equipe do SharePoint Online de linha de base, confidenciais e altamente confidenciais. Para obter mais informações sobre essas três camadas de proteção, consulte [Arquivos e sites do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md).

## <a name="office-365-labels-for-your-sharepoint-online-sites"></a>Rótulos do Office 365 para seus sites do SharePoint Online
Você deve concluir as três fases a seguir ao criar e atribuir rótulos do Office 365 aos sites de equipe do SharePoint Online.

### <a name="phase-1-determine-the-office-365-label-names"></a>Etapa 1: Determinar os nomes de rótulo do Office 365

Nesta fase, você determina os nomes dos rótulos do Office 365 para os quatro níveis de proteção de informações aplicados a sites de equipe do SharePoint Online. A tabela a seguir lista os nomes recomendados para cada nível.
 
|**Nível de proteção do site de equipe do SharePoint Online**|**Nome do rótulo**|
|:-----|:-----|
|Linha de base público|Público interno|
|Linha de base privado|Private|
|Confidencial|Confidencial|
|Altamente Confidencial|Altamente Confidencial|

### <a name="phase-2-create-the-office-365-labels"></a>Fase 2: Criar os rótulos do Office 365
Nesta fase, você cria e publica seus determinados rótulos para os diferentes níveis de proteção de informações.

Para criar os rótulos, você pode usar o Centro de administração do Office 365 ou o Microsoft PowerShell.

**Criar rótulos do Office 365 com o Centro de administração do Office 365**

1. Entre no **Portal do Office 365** com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Na guia **Microsoft Office Home**, clique no **bloco Administração**.
3. Na nova guia **Centro de Administração do Office** do navegador, clique em **Centros de Administração > Segurança e Conformidade**.
4. Na nova guia **Início – Segurança e Conformidade** do navegador, clique em **Classificações > Rótulos**.
5. No painel **Início > Rótulos**, clique em **Criar um rótulo**.
6. No painel **Atribuir nome ao seu rótulo**, digite o nome do rótulo e clique em **Avançar**.
7. No painel **Configurações do Rótulo**, clique em **Avançar**.
8. No painel **Examine as configurações**, clique em **Criar este rótulo** e clique em **Fechar**.
9. Repita as etapas de 5 a 8 para os rótulos adicionais.

**Criar rótulos do Office 365 com o PowerShell**

1. [Conecte-se ao Centro de Segurança e Conformidade do Office 365 usando o PowerShell remoto](http://go.microsoft.com/fwlink/?LinkID=799771&clcid=0x409) e especifique as credenciais da conta que têm a função de Administrador de Segurança ou Administrador da Empresa.
2. Preencha a lista de nomes de rótulo e execute esses comandos no prompt de comando do PowerShell:

```
$labelNames=@([list of label names, each enclosed in quotes and separated by commas])
ForEach ($element in $labelNames){ New-ComplianceTag -Name $element }
```

Em seguida, use estas etapas para publicar os novos rótulos do Office 365.

1. No painel **Início > Rótulos** no Centro de Segurança e Conformidade, clique em **Publicar rótulos**.
2. No painel **Escolher rótulos para publicar**, clique em **Escolher rótulos para publicar**.
3. No painel **Escolher rótulos**, clique em **Adicionar** e selecione todos os quatro rótulos.
4. Clique em **Concluído**.
5. No painel **Escolher rótulos para publicar**, clique em **Avançar**.
6. No painel **Escolher locais**, clique em **Avançar**.
7. No painel **Atribuir um nome à política**, digite um nome para o conjunto de rótulos em **Nome** e clique em **Avançar**.
8. No painel **Examine as configurações**, clique em **Publicar rótulos** e clique em **Fechar**.

### <a name="phase-3-apply-the-office-365-labels-to-your-sharepoint-online-sites"></a>Etapa 3: Aplicar os rótulos do Office 365 aos sites do SharePoint Online
Use estas etapas para aplicar os rótulos do Office 365 às pastas de documentos de seus sites de equipe do SharePoint Online.

1. Na guia **Microsoft Office Home** do navegador, clique no bloco **SharePoint**.
2. Na nova guia **SharePoint** no navegador, clique em um site que precisa de um rótulo do Office 365 atribuído.
3. Na nova guia de site do SharePoint do navegador, clique em **Documentos**.
4. Clique no ícone de configurações e clique em **Configurações de biblioteca**.
5. Em **Permissões e Gerenciamento**, clique em **Aplicar o rótulo aos itens nessa biblioteca**.
6. Em **Configurações – Aplicar Rótulo**, selecione o rótulo adequado e clique em **Salvar**.
7. Feche a guia para o site do SharePoint Online.
8. Repita as etapas 3 a 8 acima para atribuir rótulos do Office 365 aos sites adicionais do SharePoint Online.

Aqui está a configuração resultante.

 ![Proteção de Linha de Base](./media/protect-files-with-o365-labels-dlp/site_labels.png)

### <a name="dlp-policies-for-your-sharepoint-online-sites"></a>Políticas DLP para seus sites do SharePoint Online
Use estas etapas para configurar uma política DLP que notifica os usuários quando eles compartilham um documento em um site de equipe confidencial do SharePoint Online fora da organização.

1. Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança e Conformidade**.
2. Na nova guia **Segurança e Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.
3. No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.
4. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e em **Avançar**.
5. No painel **Atribuir um nome à política**, digite o nome da política DLP de nível confidencial em Nome e clique em **Avançar**.
6. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e, em seguida, clique em **Avançar**.
7. Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.
8. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Editar**.
9. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.
10. No painel **Rótulos**, clique em **+ Adicionar**, selecione o rótulo **Confidencial**, clique em **Adicionar** e clique em **Concluído**.
11. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
12. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.
13. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
14. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
15. Na caixa de texto, digite ou cole o seguinte:
 * Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em Arquivo, em seguida, Proteger Documento e Criptografar com Senha e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.
 * Digite ou cole em sua própria dica de política que instrui os usuários sobre como compartilhar um arquivo fora da organização.
16. Clique em **OK** no painel **O que você quer fazer se detectamos informações confidenciais?**, desmarque a caixa de seleção **Impedir que as pessoas compartilhem e restringir o acesso ao conteúdo compartilhado** e clique em **Avançar**.
17. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Yes** para ativá-la imediatamente e clique em **Avançar**.
18. No painel **Examine as configurações**, clique em **Criar** e clique em **Fechar**.

Aqui está a configuração resultante dos sites confidenciais da equipe do SharePoint Online.

 ![Proteção Confidencial](./media/protect-files-with-o365-labels-dlp/sensitive_w_dlp.png)

Em seguida, use estas etapas para configurar uma política DLP que bloqueia os usuários quando eles compartilham um documento em um site de equipe altamente confidencial do SharePoint Online fora da organização.

1. Na guia **Microsoft Office Home** no navegador, clique no bloco **Segurança e Conformidade**.
2. Na nova guia **Segurança e Conformidade** no navegador, clique em **Prevenção de perda de dados > Política**.
3. No painel **Prevenção de perda de dados**, clique em **+ Criar uma política**.
4. No painel **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** e clique em **Avançar**.
5. No painel **Atribuir um nome à política**, digite o nome da política DLP de nível altamente confidencial em **Nome** e clique em **Avançar**.
6. No painel **Escolher locais**, clique em **Deixe-me escolher locais específicos** e clique em **Avançar**.
7. Na lista de locais, desabilite os locais **Email do Exchange** e **Contas do OneDrive** e clique em **Avançar**.
8. No painel **Personalizar os tipos de informações confidenciais que você quer proteger** e clique em **Editar**
9. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** na caixa suspensa e clique em **Rótulos**.
10. No painel **Rótulos**, clique em **+ Adicionar**, selecione o **rótulo Altamente Confidencial**, clique em **Adicionar** e clique em **Concluído**.
11. No painel **Escolher os tipos de conteúdo para proteger**, clique em **Salvar**.
12. No painel **Personalizar os tipos de informações confidenciais que deseja proteger** e clique em **Avançar**.
13. No painel **O que deseja fazer se detectarmos informações confidenciais?**, clique em **Personalizar a dica e o email**.
14. No painel **Personalizar dicas de política e notificações de email**, clique em **Personalizar o texto da dica da política**.
15. Na caixa de texto, digite ou cole o seguinte:
 * Para compartilhar com um usuário de fora da organização, baixe o arquivo e abra-o. Clique em **Arquivo**, em seguida, **Proteger Documento** e **Criptografar com Senha** e especifique uma senha forte. Envie a senha em um email separado ou outros meios de comunicação.
 * Digite ou cole em sua própria dica de política que instrui os usuários sobre como compartilhar um arquivo fora da organização.
16. Clique em **OK**.
17. No painel **O que deseja fazer se detectarmos informações confidenciais?**, selecione **Exigir uma justificativa de negócios para substituir** e clique em **Avançar**.
18. No painel **Deseja ativar a política ou testar primeiro?**, clique em **Yes** para ativá-la imediatamente e clique em **Avançar**.
19. No painel **Examine as configurações**, clique em **Criar** e clique em **Fechar**.

Aqui está a configuração resultante para sites de equipe do SharePoint Online de alta confidencialidade.

 ![Proteção Altamente Confidencial](./media/protect-files-with-o365-labels-dlp/hc_w_dlp.png)

## <a name="next-steps"></a>Próximas etapas

[Proteger arquivos do SharePoint Online com a Proteção de Informações do Azure](protect-files-with-aip.md)






