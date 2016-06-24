<properties pageTitle="Instalar e configurar ferramentas para criação no GitHub" description="Ferramentas e etapas para preparar a configuração a fim de criar conteúdo de EMS no GitHub." services="contributor-guide" documentationCenter="" authors="v-jocgar" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/25/2016" ms.author="v-jocgar" />

# Instalar e configurar ferramentas para criação no GitHub
Tarefas Pendentes:
- [] Nº 21 Todo o procedimento precisa ser testado com uma conta de terceiros e o computador. 

Execute as etapas neste artigo para configurar as ferramentas para colaboração com a documentação técnica do EMS. 

- Se você não estiver familiarizado com o Git, convém examinar a terminologia do Git: [https://help.github.com/articles/github-glossary](https://help.github.com/articles/github-glossary).
- Também recomendamos bastante este conjunto de vídeos sobre [Git e Github Foundations](https://www.youtube.com/playlist?list=PLg7s6cbtAD15G8lNyoaYDuKZSKyJrgwB-). Eles são rápidos e fáceis de acompanhar.  

## Instruções passo a passo

- [Criar uma conta do GitHub e configurar seu perfil](#create-a-github-account-and-set-up-your-profile)
- [Permissões no GitHub](#permissions-in-github)
- [Instalar o Git para Windows](#install-git-for-windows)
- [Habilitar a autenticação de dois fatores](#enable-two-factor-authentication)
- [Criar um token de acesso pessoal](#create-a-personal-access-token)
- [Instalar um editor de Markdown](#install-a-markdown-editor)
- [Configurar o Atom](#configure-atom)
- [Criar uma ramificação do repositório](#create-a-branch-from-the-repository)
- [Definir a conexão do repositório remoto e configurar as credenciais](#set-remote-repository-connection-and-configure-credentials)
- [Configurar seu nome de usuário e o email localmente](#configure-your-user-name-and-email-locally)
- [Próximas etapas](#next-steps)

## Criar uma conta do GitHub e configurar seu perfil

Para contribuir com conteúdo técnico de EMS, você precisará de uma conta do [GitHub](http://www.github.com).

- **Imagem do perfil**: uma imagem sua (obrigatório)
- **Nome**: seu nome e sobrenome (obrigatório)
- **Email**: seu endereço de email (obrigatório)
- **Empresa**: sua empresa (obrigatório)
- **Local**: lista seu local (obrigatório)

Seu perfil deve ser semelhante a este perfil:

 ![Exemplo de perfil do GitHub](./media/githubprofile.png)

## Permissões no GitHub

Qualquer pessoa com uma conta do GitHub pode colaborar com conteúdo técnico do EMS por meio de nosso repositório público em [http://www.github.com/microsoft/emdocs](http://www.github.com/microsoft/emdocs). Nenhuma permissão especial é necessária.

## Instalar o Git para Windows

Instale o **Git para Windows** em [http://git-scm.com/download/win](http://git-scm.com/download/win). Esse download instala o sistema de controle de versão Git, e instala o Git Bash, o aplicativo de linha de comando que você usará para interagir com seu repositório Git local.

**Observação**
Este programa não é o mesmo que o "Github para Windows". "Github para Windows" é uma ferramenta diferente baseada em GUI, que também funcionará, caso você queira ler mais sobre ela. [https://windows.github.com/](https://windows.github.com/)) 

Durante a instalação, você tem a oportunidade de selecionar como você interagirá com o repositório do Github. Recomendamos que você use o Git apenas do Git Bash. 
 ![Exemplo de perfil do GitHub](./media/gitbashinstall.png)

## Habilitar a autenticação de dois fatores

Você precisa habilitar a autenticação de dois fatores (2FA) em sua conta do GitHub se estiver trabalhando no repositório de conteúdo particular. Para habilitar isso, siga as instruções no tópico de ajuda do GitHub abaixo:

- [Sobre a autenticação de dois fatores](https://help.github.com/articles/about-two-factor-authentication/)

## Criar um token de acesso pessoal
O token de acesso pessoal realiza a sua autenticação no GitHub e do computador no qual você está trabalhando.
1. No GitHub, clique em si mesmo e clique em Configurações.
2. Na guia Token de Acesso Pessoal, clique em Gerar novo token.
3. Forneça uma descrição ao token. 
4. Defina o escopo. Convém ter acesso completo ao repositório e ao usuário marcando essas caixas de seleção de permissão.
5. Clique em Gerar token.
6. Copie o token exibido e cole-o em um local seguro, como um email ou um documento do Word. Você precisa desse token para enviar e receber do GitHub.

## Instalar um editor de markdown

Criamos conteúdo usando a notação simples "Markdown" nos arquivos, em vez da "marcação" complexa (HTML, XML etc.). Portanto, você precisará instalar um editor de Markdown. Usamos o Markdown para Github. 

- **Atom**: a maioria dos colaboradores usa o editor de Markdown do GitHub, Atom: [http://atom.io](http://atom.io). Ele não exige uma licença para uso comercial e tem verificação ortográfica. 
- **Bloco de notas**: você pode usar o Bloco de notas como uma opção muito leve.
- **Prose**: este é um editor de markdown leve, elegante, online e de software livre que oferece uma visualização. Visite [http://prose.io](http://prose.io) e autorize o Prose em seu repositório.
- **[Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx)** - entrada da Microsoft neste espaço.
- **MarkdownPad 2**: você pode usar o [MarkdownPad 2](http://markdownpad.com/) gratuitamente, mas se você comprar uma licença, poderá aproveitar a vantagem da renderização de Markdown com o toque para Github na Visualização Dinâmica.  

## Configurar o editor Atom Markdown

Se você usar o Atom, precisará configurar algumas coisas.

- O Atom assume o padrão de dois espaços para tabulações, mas o Markdown espera quatro espaços. Se você deixar o padrão de dois, o artigo terá uma aparência excelente na visualização local, mas quando for importado para docs.microsoft.com não será tão excelente. Então, configure o Atom para usar quatro espaços. Para encontrar essa configuração, acesse File->Settings->Editor Settings->Tab Length (Arquivo -> Configurações -> Configurações do Editor -> Tamanho da Tabulação). 
- Provavelmente você também vai querer ativar o Soft Wrap (Quebra automática) nessa seção, que faz o mesmo que a "quebra automática de linha" no Bloco de Notas. 
- Para ativar a visualização de markdown, clique em Packages->Markdown Preview->Toggle Preview (Pacotes->Visualização de Markdown->Ativar/Desativar Visualização). Você pode usar Ctrl-Shift-M para ativar ou desativar a visualização em HTML. 

## Criar uma ramificação do repositório

Criar uma ramificação do repositório no GitHub. 

1. Abra o Git Bash. 
2. No prompt de comando, digite o seguinte comando. 

        git clone https://[your GitHub user name]:[token]@github.com/microsoft/emdocs.git

Este comando cria um diretório `emdocs` em seu computador.  Se você estiver usando o local padrão, ele estará em `c:\users\<your Windows user name>\emdocs`. Por exemplo, este comando de clone pareceria com o seguinte:

        git clone https://smithj:b428654321d613773d423ef2f173ddf4a312345@github.com/microsoft/emdocs.git  

## Definir a conexão do repositório remoto e configurar as credenciais

Configure o Git para usar por padrão sua ID e token de acesso pessoal do GitHub, para que você não precise digitar ou colar esse token de acesso manualmente para cada ação `push` ou `pull`. 

Execute o seguinte comando no git bash:

        cd emdocs
        git remote –v 
        git remote remove origin
        git remote add origin http://<githubID>:<token>@github.com/microsoft/emdocs
        git remote -v

Isso normalmente demora algum tempo. Depois de fazer isso, não será mais necessário digitar suas credenciais. Você só precisará repetir o processo se configurar as ferramentas em outro computador.

## Configurar seu nome de usuário e o email localmente

Para garantir que você esteja aparecendo corretamente como um colaborador, é necessário configurar seu nome de usuário e email localmente no Git.

1. Inicie o Git Bash e alterne para emdocs
   ````
   cd emdocs
   ````
2. Configure seu nome de usuário para que coincida com o nome configurado em seu perfil do GitHub:

    ````
    git config --global user.name "John Doe"
    ````
3. Configure seu email para que coincida com o email principal indicado em seu perfil do GitHub:

    ````
    git config --global user.email "alias@example.com"
    ````
4. Digite `git config -l` e revise as configurações locais para garantir que o nome de usuário e o email estejam corretos na configuração.

## Próximas etapas

- Leia e siga as instruções em [Como trabalhar com o Git](./work-with-git.md) para que você possa começar a escrever.


## Voltar ao início

- [Artigo de visão geral](./../README.md)
- [Índice de artigos com diretrizes](./contributor-guide-index.md)


<!--Anchors-->
[Create a GitHub account and set up your profile]: #create-a-github-account-and-set-up-your-profile
[Permissions in GitHub]: #permissions-in-github
[Install Git for Windows]: #install-git-for-windows
[Enable two-factor authentication]: #enable-two-factor-authentication
[Create a personal access token]: #create-a-personal-access-token
[Install a markdown editor]: #install-a-markdown-editor
[Configure Atom]:#configure-atom
[Create a branch from the repository]: #create-a-branch-from-the-repository
[Set remote repository connection and configure credentials]: #set-remote-repository-connection-and-configure-credentials
[Configure your user name and email locally]: #configure-your-user-name-and-email-locally
[Next steps]: #next-steps

<!--HONumber=Mar16_HO1-->


