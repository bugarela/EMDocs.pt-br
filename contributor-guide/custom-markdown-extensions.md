<properties pageTitle="Extensões markdown personalizadas usadas em nossos artigos técnicos"  description="Lista as extensões markdown personalizadas que permitem vídeos, observações e dicas, conteúdo reutilizável e outros itens inseridos nos artigos técnicos em docs.microsoft.com/ems." services="" solutions="" documentationCenter="" authors="v-jocgar" manager="robmazz" editor=""/>

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm=""  ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar"/>

## Extensões markdown personalizadas para EMS
Tarefas Pendentes:
- [ ] Nº 34 Verifique se estamos usando as extensões Markdown para Observação, Importante etc. 
- [ ] Nº 35 Confirme se o EMS está usando tokens e o local de diretório correto.
- [ ] Nº 36 Confirme se os arquivos de ícone personalizados estão disponíveis e instalados no local correto.
- [ ] Nº 37 Confirme o nome do diretório para tokens que usam arquivos de mídia
- [ ] Nº 38 Confirme os procedimentos corretos para uso de tokens.
- [ ] Nº 39 Forneça um exemplo da sintaxe para uso de tokens. 
- [ ] Nº 40 Confirme a URL da Documentação do EMS.
- [ ] Nº 41 Confirme se os vídeos do Channel 9 podem ser usados pelos autores externos. 
- [ ] Nº 42 Confirme o local dos vídeos do EMS no Channel 9.
- [ ] Nº 43 Confirme o uso dos vídeos do EMS no Channel 9.
- [ ] Nº 44 Confirme a sintaxe para inserção do vídeo.
- [ ] Nº 45 Necessidade de um exemplo renderizado do Github.
- [ ] Nº 46 Necessidade de um exemplo renderizado de vídeo do Github.
- [ ] Nº 47 Necessidade de um exemplo renderizado do site de documentos do EMS. 
- [ ] Nº 48 Confirme se os Seletores estão disponíveis para artigos do EMS
- [ ] Nº 49 Necessidade de um exemplo de substituição de seletores simples
- [ ] Nº 50 Confirme a sintaxe de seletores simples
- [ ] Nº 51 Necessidade da sintaxe de seletores simples para substituição
- [ ] Nº 52 Necessidade de um exemplo de seletores simples para substituição
- [ ] Nº 53 Confirme a função de seletores bidirecionais, conforme descrito.
- [ ] Nº 54 Necessidade de um exemplo de seletores bidirecionais para substituição
- [ ] Nº 55 Confirme a sintaxe de seletores bidirecionais
- [ ] Nº 56 Necessidade de um exemplo de seletores bidirecionais para substituição


## Ajuda geral com o markdown

Se ainda não leu o tópico [Authoring for EMS in Markdown](./authoring-in-markdown.md) (Criando para o EMS em Markdown), sugerimos que você leia esse tópico antes de continuar com este. 

## Extensões markdown personalizadas usadas em nossos artigos técnicos

Nossos artigos usam uma versão do markdown para o GitHub em grande parte da formatação de artigos — parágrafos, links, listas, cabeçalhos, etc. Porém, usamos extensões markdown onde precisamos de formatação mais avançada nas páginas renderizadas em Microsoft.com/ems. Veja a extensões que estamos usando atualmente:

+ [Observações e dicas]
+ [Tokens]
+ [Vídeos inseridos]
+ [Seletores de plataforma e tecnologia]

## Observações e dicas
<span style="color:red;">Verifique se estamos usando as extensões Markdown para Observação, Importante, etc.</span>
Você pode escolher dentre 4 tipos de observações e dicas:

- EMS.NOTE
- EMS.WARNING
- EMS.TIP
- EMS.IMPORTANT

### Uso
No geral, use observações e dicas moderadamente em todos os seus artigos. Quando usá-las, escolha o tipo apropriado de observação ou dica:

- Use EMS.NOTE para realçar informações neutras ou positivas que enfatizem ou complementem pontos importantes do texto principal. Uma observação fornece informações que se aplicam apenas em casos especiais.

  ![](./media/notes-note.png)

- Use EMS.WARNING para alertar o usuário sobre uma condição que pode causar um problema no futuro. Por exemplo, selecionar uma determinada opção ou fazer uma determinada escolha pode prender você permanentemente a um cenário específico.

  ![](./media/notes-warning.png)

- Use EMS.TIP para ajudar os usuários a aplicar técnicas e procedimentos descritos no texto às suas necessidades específicas. Uma dica também pode sugerir métodos alternativos que talvez não sejam óbvios. No entanto, as dicas não são essenciais ao entendimento básico do texto.

  ![](./media/notes-tip.png)

- Use EMS.IMPORTANT para fornecer informações que são essenciais à conclusão de uma tarefa.

  ![](./media/notes-important.png)

Embora essas observações e dicas sejam compatíveis com blocos de código, imagens, listas e links, tente mantê-las simples e diretas. Se acabar criando observações complexas com muita formatação, esse pode ser um sinal de que você precisa apenas de outra seção no texto principal do artigo. Além disso, muitas anotações em um artigo podem ser distrativas e difíceis de examinar ou ler.

### Exemplo de markdown

Todos os exemplos mostram um EMS.NOTE. Para usar um TIP, WARNING ou IMPORTANT, substitua "NOTE" em markdown:

    > [EMS.TIP]

    > [EMS.WARNING]

    > [EMS.IMPORTANT]

Parâmetro único:

    > [EMS.NOTE] To complete this tutorial, you must have an active Microsoft account. If you don't have an account, you can create a free account in just a couple of minutes.

Vários parágrafos:

    > [EMS.NOTE] To complete this tutorial, you must have an active Microsoft account.
    >
    > If you don't have an account, you can [create a free account](https://signup.live.com/signup) in just a couple of minutes.

## Tokens
<span style="color:red;">Confirme se o EMS está usando tokens e o local de diretório correto.</span>
Os fragmentos de texto reutilizáveis em nosso repositório GitHub são chamados de "tokens". Quando você tem um texto que precisa ser usado em vários artigos, inclua uma referência aos fragmentos de texto nos arquivos markdown. O fragmento de texto (o token) em si é um arquivo (.md) markdown simples. Ele pode conter qualquer markdown válido, incluindo texto, links e imagens. 

Todos os arquivos markdown de token devem estar em <span style="color:red;">Confirmar se os arquivos de ícone personalizados estão disponíveis e instalados no local correto</span> [o diretório /tokens](necessidade do local correto) na raiz do repositório. Quando o artigo for publicado, o texto do token será totalmente integrado ao tópico publicado.

- Usamos uma sintaxe específica para fazer referência a um token.

- Os arquivos de mídia que você coloca em um token devem ser criados na pasta `/media` específica para o token. As pastas de mídia para tokens pertencem a <span style="color:red;">Confirmar o nome do diretório para tokens que usam arquivos de mídia</span> [a pasta ems-content/tokens/media](necessidade do local correto). 

## Uso
<span style="color:red;">Confirme os procedimentos corretos para uso de tokens.</span>
- Use tokens onde for necessário para que o mesmo texto apareça em vários artigos.
- Os tokens destinam-se a ser usados para quantidades significativas de conteúdo — um parágrafo ou dois, um procedimento compartilhado ou uma seção compartilhada. Não os use para nada menor que uma frase; eles não servem para nomes de produto ou frases incompletas.
- Não insira tokens em outros tokens. Coisas ruins acontecem no sistema de publicação!
- Não compartilhe mídia entre arquivos. Use um arquivo separado com um nome exclusivo para cada token e artigo. Armazene o arquivo de mídia na pasta de mídia associada ao token.
- Não use um token como o único conteúdo de um artigo. Os tokens são complementares ao conteúdo no restante do artigo.
- Como todos os tokens devem estar no diretório `/token`, o caminho para um token de um artigo é sempre

    ../token

- NÃO repita uma referência de nome de arquivo de imagem ou link no artigo e no token. Adicione "-token" ao nome do arquivo de mídia ou à referência do link para evitar repetir a referência:

 **Referência do link**

 Alterar: odata.org
 Para: odata.org-token

 **Referência de imagem**

 Alterar: table.png
 Para: table-token.png

### Exemplo de markdown para tokens
<span style="color:red;">Forneça um exemplo da sintaxe para uso de tokens. </span>
A sintaxe para adicionar um token a um artigo de documentação é:

    [EMS.TOKEN [token-short-name](../tokens/token-file-name.md)]

Exemplo

    [EMS.INCLUDE [howto-blob-storage](../tokens/howto-blob-storage.md)]

A primeira parte do token é o nome token sem o caminho e sem a extensão .md. A segunda parte é o caminho relativo para o token no diretório /token, com a extensão .md.

### Renderização

Na página GitHub renderizada, o token será renderizado como se segue:

 [EMS.TOKEN howto-blob-storage]

No HTML renderizado em <span style="color:red;">Confirmar URL da Documentação do EMS</span> http://docs.microsoft.com/ems, o HTML dos tokens é mesclado com o restante do HTML do documento. No entanto, o HTML conterá um comentário HTML com o nome do arquivo markdown do token original e o hash de confirmação do GitHub. Esse comentário é incluído para fins de solução de problemas, para que o conteúdo de origem possa ser facilmente identificado e encontrado no GitHub:

  ![](./media/token.png)


## Vídeos inseridos
<span style="color:red;">Confirme se os vídeos do Channel 9 podem ser usados pelos autores externos.</span>
Nossos artigos técnicos permitem vídeos inseridos em artigos técnicos, contanto que os vídeos sejam do site [Channel 9](http://channel9.msdn.com/) da Microsoft. Os vídeos do Channel 9 devem ser integrados a <span style="color:red;">Confirmar local de vídeos do EMS no Channel 9.</span> [o Centro de Vídeo docs.microsoft.com](necessidade do local real). Atualmente, não permitimos vídeos inseridos do YouTube; como um colaborador da comunidade, sinta-se à vontade para **vincular-se — ao YouTube se o vídeo que quiser apresentar estiver postado lá.

### Uso
<span style="color:red;">Confirme o uso dos vídeos do EMS no Channel 9.</span>
- Certifique-se de que o vídeo esteja no Centro de Vídeo do Channel 9.

- Copie a ID do vídeo da URL amigável do vídeo no Channel 9. Por exemplo, a ID do vídeo em [https://channel9.msdn.com/Shows/This+Week+On+Channel+9/TWC9-Stacking-Microsoft-Windows-10-Pi-Bobble-Head-your-Nodejs-and-more](https://channel9.msdn.com/Shows/This+Week+On+Channel+9/TWC9-Stacking-Microsoft-Windows-10-Pi-Bobble-Head-your-Nodejs-and-more) é ** ??? **.

### Sintaxe
<span style="color:red;">Confirme a sintaxe para inserção do vídeo. </span>
    > [EMS.VIDEO video-id-string]

### Renderização
<span style="color:red;">Necessidade de um exemplo renderizado de vídeo do Github. </span>
No GitHub: [necessidade de um exemplo da aparência de um artigo quando adicionado ao Github](something.md)

<span style="color:red;">Necessidade de um exemplo renderizado do site de documentos do EMS. </span>
Artigo publicado: [necessidade de exemplo da aparência de um artigo no site de documentos quando incorporado](necessidade do local atual)

## Seletores de plataforma e tecnologia
<span style="color:red;">Confirme se os Seletores estão disponíveis para artigos do EMS</span>
Use alternadores de tecnologia e plataforma em artigos técnicos ao criar várias versões do mesmo artigo para abordar diferenças na implementação entre tecnologias ou plataformas. Normalmente, isso é mais comum em nosso conteúdo de plataforma móvel para desenvolvedores. Atualmente, há dois tipos diferentes de seletor: [seletores simples](#simple-selectors) e [seletores bidirecionais](#two-way-selectors).

Como o mesmo seletor Markdown é usado em cada tópico na seleção, é recomendável colocar o seletor para seu tópico em um token e fazer referência a esse token em todos os tópicos que usam o mesmo seletor.

### Seletores simples

Seletores simples (unidirecionais) são renderizados como um conjunto de botões de opção logo abaixo do título. Use esses botões quando os clientes precisarem escolher tópicos em um única plataforma ou tecnologia definida, como .NET, Node.js e Java.  Use a extensão markdown personalizada para quaisquer seletores — não use HTML para seletores.  

<span style="color:red;">Necessidade de um exemplo de substituição de seletores simples; deixe essa versão do Azure aqui para referência.</span>
Confira [Introdução aos Hubs de Notificação](http://azure.microsoft.com/documentation/articles/notification-hubs-windows-phone-get-started/) para ver como o autor criou 8 versões do mesmo artigo, mas usou seletores para permitir a navegação entre todas elas.

![Exemplo de seletor simples](./media/selectors.png)

#### Sintaxe
<span style="color:red;">Confirme a sintaxe de seletores simples</span>
    > [EMS.SELECTOR]
    - [Link #1 Label](link #1 url)
    - [Link #2 Label](link #2 url)

#### Exemplo
<span style="color:red;">Necessidade de sintaxe de seletores simples para substituição</span>
    > [EMS.SELECTOR]
    - [Tempo de execução universal do Windows 8.1](../articles/notification-hubs-windows-store-dotnet-get-started/)
    - [Windows Phone Silverlight 8.x](../articles/notification-hubs-windows-phone-get-started/)
    - [iOS](../articles/notification-hubs-ios-get-started/)
    - [Android](../articles/notification-hubs-android-get-started/)
    - [Kindle](../articles/notification-hubs-kindle-get-started/)
    - [Baidu](../articles/notification-hubs-baidu-get-started/)
    - [Xamarin.iOS](../articles/partner-xamarin-notification-hubs-ios-get-started/)
    - [Xamarin.Android](../articles/partner-xamarin-notification-hubs-android-get-started/)
    - [Chrome](../articles/notification-hubs-chrome-get-started/)

#### Renderização

<span style="color:red;">Necessidade de um exemplo de seletores simples para substituição; deixe esse aqui para referência.</span>
A imagem acima mostra a renderização em docs.microsoft.com/ems. Nas páginas renderizadas do GitHub, os seletores são renderizados como uma lista de links com marcadores.

### Seletores bidirecionais
<span style="color:red;">Confirme a função de seletores bidirecionais, conforme descrito.</span>
Os seletores bidirecionais permitem aos usuários selecionar um tópico em uma matriz bidirecional. Isso é essencial quando uma tecnologia EMS, como os Serviços Móveis, é compatível com várias plataformas de back-end e com vários clientes. Lembre-se do seguinte:

- Embora ele tenha sido projetado como `(Platform | Backend)`, o texto do menu suspenso agora pode ser personalizado.
- Você não precisa de um item de lista para cada ponto em sua matriz, mas tem apenas um item onde uma URL de tópico existe e não é uma duplicação.
- O link pode ser qualquer URL, embora geralmente seja outro tópico GitHub.

<span style="color:red;">Necessidade de um exemplo de seletores bidirecionais para substituição; deixe essa versão do Azure aqui para referência.</span>
Confira [Introdução aos Serviços Móveis](http://azure.microsoft.com/en-us/documentation/articles/mobile-services-ios-get-started/) para ver como o autor criou 15 versões do mesmo artigo (9 plataformas de cliente móvel e 2 plataformas de back-end), mas usou seletores para permitir a navegação entre todas elas. Observe que os 3 artigos não têm ambas as versões de back-end.

![Exemplo de seletores bidirecionais](./media/selector-list.png)

#### Sintaxe
<span style="color:red;">Confirme a sintaxe de seletores bidirecionais</span>
    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]
    - [(Dropdown1Text1 | Dropdown2Text1 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text1 | Dropdown2Text2 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text2 | Dropdown2Text3 )](../articles/dropdown1-text1-dropdown2-text1.md)
    - [(Dropdown1Text3 | Dropdown2Text4 )](../articles/dropdown1-text1-dropdown2-text1.md)

#### Exemplo
<span style="color:red;">Necessidade de um exemplo de seletores bidirecionais para substituição</span>
    > [AZURE.SELECTOR-LIST (Platform | Backend )]
    - [(iOS | .NET)](./mobile-services-dotnet-backend-ios-get-started-push.md)
    - [(iOS | JavaScript)](./mobile-services-javascript-backend-ios-get-started-push.md)
    - [(Tempo de execução universal do Windows 8.1 | C#)](./mobile-services-dotnet-backend-windows-universal-dotnet-get-started-push.md)
    - [(Tempo de execução universal do Windows 8.1 C# | Javascript)](./mobile-services-javascript-backend-windows-universal-dotnet-get-started-push.md)
    - [(Windows Phone | .NET)](./mobile-services-dotnet-backend-windows-phone-get-started-push.md)
    - [(Windows Phone | Javascript)](./mobile-services-javascript-backend-windows-phone-get-started-push.md)
    - [(Android | .NET)](./mobile-services-dotnet-backend-android-get-started-push.md)
    - [(Android | Javascript)](./mobile-services-javascript-backend-android-get-started-push.md)
    - [(Xamarin iOS | Javascript)](./partner-xamarin-mobile-services-ios-get-started-push.md)
    - [(Xamarin Android | Javascript)](./partner-xamarin-mobile-services-android-get-started-push.md)
    - [HTML](../articles/mobile-services-html-get-started/)
    - [PhoneGap](../articles/mobile-services-javascript-backend-phonegap-get-started/)
    - [Sencha](../articles/partner-sencha-mobile-services-get-started/)

#### Renderização
<span style="color:red;">Necessidade de um exemplo de seletores bidirecionais para substituição; deixe esse aqui para referência.</span>
A imagem acima mostra a renderização em azure.microsoft.com. Nas páginas renderizadas do GitHub, os seletores são renderizados como uma lista de links com marcadores.

<!--Anchors-->
[Notes and tips]: #notes-and-tips
[Tokens]: #tokens
[Embedded videos]: #embedded-videos
[Technology and platform selectors]: #technology-and-platform-selectors

## Voltar ao Início

- [Overview article](./../README.md)
- [Index of guidance articles](./contributor-guide-index.md)


<!--HONumber=Mar16_HO1-->


