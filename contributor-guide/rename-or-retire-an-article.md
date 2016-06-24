<properties pageTitle="Etapas a serem seguidas ao remover ou alterar o nome de um artigo técnico do EMS" description="Etapas a serem seguidas ao remover ou alterar o nome de um artigo técnico do EMS." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar" />

# Etapas a serem seguidas ao renomear ou remover um artigo técnico do EMS

Tarefas Pendentes:
- [] Nº 57 Confirmar isso é como remover conteúdo que funcionará para o EMS. Isso se parece mais com um conjunto de procedimentos apenas interno. 
- [ ] Nº 58 Confirme se os autores externos poderão executar uma ferramenta de análise da Web no conteúdo da Microsoft. 
- [ ] Nº 59 Teste o procedimento para descobrir links cruzados no repositório.
- [ ] Nº 60 Confirme a URL para os documentos do EMS.  
- [] Nº 61 Confirme se é possível remover links cruzados de autores externos. 
- [] Nº 62 Confirme se um autor externo pode criar um redirecionamento.
- [ ] Nº 63 Confirme se um autor externo pode excluir um artigo do repositório.
- [ ] Nº 64 Confirme se um autor externo pode solicitar remoção do conteúdo da Microsoft dos mecanismos de pesquisa.


<span style="color:red;">Confirmar isso é como remover conteúdo que funcionará para o EMS. Isso se parece mais com um conjunto de procedimentos apenas interno. </span>
Este guia é para SMEs (Especialistas no Assunto) que estão listados como autor de um artigo que precisa ser removido da seção de documentação técnica de http://docs.microsoft.com/ems. As etapas também se aplicarão se um arquivo for renomeado.

Os autores SME precisam seguir várias etapas para remover conteúdo, de modo que os usuários do site não tenham uma experiência desagradável quando retirarmos conteúdo do site. Excluir o artigo ou alterar seu nome deve ser a última coisa a ser feita!

Se você é um membro da nossa comunidade EMS e acha que um artigo deve ser removido por qualquer motivo, deixe um comentário para que o autor saiba que algo está errado com o artigo.

## Etapa 1: Gerenciar links de entrada

Verifique se há algum link de entrada que não seja da Microsoft em seu conteúdo. Com muita frequência, blogs, fóruns e outros tipos de conteúdo na Web apontam para artigos. É comum poder trabalhar com proprietários de blog para alterar esses links e remover ou atualizar links em postagens de fóruns. <span style="color:red;">Confirme se os autores externos poderão executar uma análise da Web no conteúdo da Microsoft. </span>Ferramentas de análise da Web podem informar se há algum link de entrada de tráfego intenso que talvez você precise gerenciar.

## Etapa 2: Remover todos os links cruzados no artigo do repositório de conteúdo técnico
<span style="color:red;">Teste o procedimento para descobrir links cruzados no repositório.</span>
1. Verifique se você está trabalhando em uma ramificação local atualizada — execute `git pull origin master` (ou a variação apropriada nesse comando).

2.  <span style="color:red;">Confirme os caminhos no repositório.</span> Examine as pastas \EMDocs\Solutions e \EMDocs\Token em busca de artigos e tokens que se vinculem ao artigo que você deseja remover. Em seguida, remova os links cruzados ou substitua-os por novos links cruzados adequados. Você pode usar um utilitário de pesquisa ou substituição, caso tenha um instalado, para encontrar os links cruzados. Se não, você poderá usar o Windows PowerShell gratuitamente! Veja como usar o PowerShell para encontrar os links cruzados:

 a. Inicie o Windows PowerShell.

 b. No prompt do PowerShell, mude para a pasta \EMDocs\Solutions:

 `cd \EMDocs\Solutions`

 c. Digite esse comando, que listará todos os arquivos que contêm uma referência ao artigo que você está excluindo:

 `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name`

  Se preferir enviar a lista de nomes de arquivo para um arquivo de texto (nesse caso, denominado psoutput.txt), você poderá:

  `Get-ChildItem -Recurse -Include *.md* | Select-String "<the name of the topic you are deleting>" | group path | select name | Out-File C:\Users\<your account>\psoutput.txt`

3. Adicionar e confirmar todas as alterações, enviá-las por push à origem e criar uma solicitação pull para mover as alterações da origem para a ramificação mestre do repositório principal.

## Etapa 3: Remover todos os links cruzados 
<span style="color:red;">Confirme se é possível remover links cruzados de autores externos. </span>
Se houver para artigos de outras páginas <span style="color:red;">Confirme a URL para os documentos do EMS. </span> http://docs.microsoft.com/ems, você precisa removê-los e criar um redirecionamento para a página removida, se adequado. Nessa parte, você precisará trabalhar com a pessoa que mantém e atualiza a página inicial de documentação do seu serviço. Se você não souber quem é essa pessoa, entre em contato com seu parceiro da equipe de conteúdo. A pessoa que mantém e atualizada a página inicial de documentos precisará executar duas tarefas:

1. No Visual Studio, verificar **toda** a solução Web do EMS em busca de referência cruzadas no arquivo a ser removido. Remover as referências cruzadas ou substituí-las por uma referência cruzada atualizada. Você precisará remover os links HTML, bem como as cadeias de caracteres de recurso relacionadas dos links HTML. 

2. <span style="color:red;">Confirme se um autor externo pode criar um redirecionamento.</span>Se existir um artigo de substituição, crie um redirecionamento para o artigo. 

3. Verifique as alterações no repositório.

## Etapa 4: Desativar o artigo
<span style="color:red;">Confirme se um autor externo pode excluir um artigo do repositório.</span>
Depois de concluir as três etapas anteriores e essas alterações estiverem em vigor, você poderá excluir o artigo do repositório.

## Etapa 5: Remover páginas armazenadas em cache dos mecanismos de pesquisa
<span style="color:red;">Confirme se um autor externo pode solicitar remoção do conteúdo da Microsoft dos mecanismos de pesquisa.</span>
Faça isso SOMENTE se o conteúdo precisar ser removido rapidamente devido a questões legais ou problemas graves com o cliente. As exclusões de página de prioridade normal devem ser tratadas apenas por processos naturais do mecanismo de pesquisa. Acesse estas páginas da Web para remover páginas da Web em cache dos mecanismos de pesquisa:

[Bing](https://www.bing.com/webmaster/tools/content-removal?rflid=1)
[Google](https://www.google.com/webmasters/tools/removals?pli=1)


### Voltar ao início

- [Artigo de visão geral](./../README.md)
- [Índice de artigos com diretrizes](./contributor-guide-index.md)


<!--HONumber=Mar16_HO1-->


