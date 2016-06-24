<properties pageTitle="Como criar para o EMS no Markdown" description="Explica como criar imagens em markdown de acordo com as diretrizes definidas para os repositórios do Enterprise Mobility Suite." services=""     solutions="" documentationCenter="" authors="v-jocgar" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm=""  ms.workload="" ms.date="02/25/2016" ms.author="v-jocgar" />

# Como criar para o EMS no Markdown

Tarefas Pendentes: 
- [ ] Nº 23 Confirmar o layout do artigo do EMS para imagens /articles/<service-directory>/media
- [ ] Nº 24 Fornecer um exemplo para /articles/<service-directory>/media
- [ ] Nº 25 Confirmar a largura máxima das imagens na coluna central da página de documentos do EMS (580 ou 600 px?) em três parágrafos
- [ ] Nº 26 Confirmar se o EMS tem um conjunto diferente de símbolos para a arte conceitual, além daqueles oferecidos em http://aka.ms/CnESymbols. 
- [ ] Nº 27 Confirmar a URL de nosso Guia do Colaborador
- [ ] Nº 28 Confirmar todo o esquema de vinculação
- [ ] Nº 29 Os artigos são organizados por subdiretórios de serviço?
- [ ] Nº 30 A metodologia de vinculação por âncora precisa ser confirmada
- [ ] Nº 31 Confirmar a metodologia de vinculação e o uso de seletores.
- [ ] Nº 32 Testar o esquema de vinculação para garantir que está funcionando corretamente

Este artigo contém dicas sobre como escrever artigos técnicos sobre serviços e tecnologias do EMS. Essas diretrizes se aplicam se você estiver criando uma nova documentação ou atualizando uma documentação existente.

## Por que escrever para o EMS?

O Microsoft EMS (Enterprise Mobility Suite) foi criado especificamente para ajudar com a mudança atual para serviços integrados, móveis e baseados em nuvem. Seus três componentes principais, o Microsoft Azure Active Directory Premium, o Microsoft Intune e o Microsoft Azure Rights Management, foram criados desde o início como serviços de nuvem. Eles foram projetados para trabalhar juntos, fornecendo uma família de tecnologia integrada diferente de qualquer outra no mercado. Para detectar ataques locais, o EMS também inclui o Microsoft Advanced Threat Analytics. Com o EMS, os usuários corporativos podem ser produtivos em seus dispositivos preferidos, enquanto você protege os ativos da empresa.

A criação de documentação de produtos individuais é sempre uma prioridade. Porém, como o EMS é um pacote de produtos, também procuramos artigos e documentos instrutivos que ajudam nossos clientes a usar os produtos juntos de forma adequada. Nós criamos documentação para cenários com vários produtos, mas recebemos bem as informações de funcionários e usuários que estejam usando esses produtos em suas próprias empresas.

Como resultado, abrimos nossa documentação no Github, e lá você pode contribuir de várias maneiras:
- **Correção de erros no texto.** Nó sabemos, eles nos deixam loucos também, mas nem sempre conseguimos percebê-los. Então, conecte-se pelo Github e nos ajude.
- **Sugestão de novos tópicos.** Se houver um procedimento ou assunto que surja frequentemente e mereça um tópico, mas ele não existir, escreva sobre ele e verificaremos a possibilidade de incluí-lo.
- **Adição a nossas perguntas frequentes.** Se você estiver se perguntando sobre algo que não abordamos, mas for uma situação de pergunta/resposta e não um tópico inteiro, envie uma adição às perguntas frequentes e nós a analisaremos. 

Resumindo, sabemos que você tem ideias e sugestões excelentes, e queremos facilitar a sua participação no aprimoramento geral do EMS. 

## Dicas para artigos mais bem elaborados

Enquanto você escreve para o EMS, lembre-se do seguinte:

**Práticas específicas ao EMS**
- O nome oficial do produto é "Microsoft Enterprise Mobility Suite", mas podemos dizer apenas "EMS", por exemplo, "Gerenciamento de acesso e identidade em nuvem do EMS".
- Use "EMS" na primeira referência antes de um nome de serviço ou recurso, depois descarte-o (por exemplo: "Gerenciamento de acesso e identidade em nuvem do EMS" torna-se "Gerenciamento de acesso e identidade em nuvem" após a primeira ocorrência). 
- O EMS usa a capitalização de frase para todos os títulos. 
- Tente evitar acrônimos em geral, eles apenas confundem as pessoas.

**Boas práticas de escrita**
- Use um tom informal e amigável, como se você estivesse falando individualmente com outra pessoa. Confira o [tópico sobre Estilo e voz](./style-and-voice.md) para obter detalhes.
- Verifique a ortografia e a gramática de seus tópicos, mesmo que você tenha que copiar e colar o texto no Word.
- Use sentenças simples. Elas são mais fáceis de entender e podem ser traduzidas com mais facilidade tanto por tradutores humanos quanto por máquina.
- Não interrompa etapas com comentários ou itens à parte.
- Inclua as palavras "a seguir" ou "da seguinte maneira" em cada frase que preceda um trecho de código ou lista.
- Para as etapas que incluem trechos de código, coloque informações adicionais sobre a etapa no código a forma de comentários. 
    - Isso reduz a quantidade de texto que as pessoas precisam ler. 
    - Informações importantes são copiadas no projeto de código para lembrar as pessoas o que o código está fazendo quando elas consultarem ele mais tarde.

## Ajuda geral com o markdown
- Para obter dicas gerais sobre markdown, confira [Markdown Basics (Noções básicas de markdown)](https://help.github.com/articles/markdown-basics/) no site do Github.
- Você também pode baixar nossa [folha de dicas sobre markdown para EMS](./media/ems-markdown-cheat-sheet.pdf?raw=true). 
- Se você precisa criar links cruzados entre artigos em markdown, confira a [orientação sobre links](#guidelines-for-linking-technical-articles) abaixo.
- O site <span style="color:red;">Confirmar URL</span> http://docs.microsoft.com/ems oferece suporte aos [blocos de código isolados](https://help.github.com/articles/creating-and-highlighting-code-blocks/#fenced-code-blocks). Os blocos de código isolados são criados pela inserção de uma linha com três caracteres de acento grave (```) nas linhas antes e após o bloco de código. Eles são uma maneira conveniente de diferenciar o código do restante do texto.   
- O EMS também oferece suporte ao [realce de sintaxe](https://help.github.com/articles/creating-and-highlighting-code-blocks/#syntax-highlighting) dentro dos blocos de código. No entanto, ao contrário do markdown para GitHub, em que a [especificação de uma linguagem particular](https://help.github.com/articles/creating-and-highlighting-code-blocks/#syntax-highlighting) na primeira linha do código altera o esquema de cores da sintaxe, o EMS oferece suporte apenas a **um** esquema de cores para realce de sintaxe, independentemente da linguagem de programação especificada por você.

## Criar imagens em markdown
Você pode incluir imagens com seus artigos seguindo a sintaxe simples de markdown. 

### Criação de pasta de imagens e sintaxe de link

Para um novo artigo, será necessário criar uma pasta no seguinte local:
<span style="color:red;">Confirmar o layout do repositório de artigos para imagens</span>

    /articles/<service-directory>/media/

Por exemplo:
<span style="color:red;">Fornecer um exemplo</span>

    /articles/identity-access/media/

Depois de criar a pasta e adicionar imagens a ela, use a sintaxe a seguir para criar imagens em seu artigo:

```
![Alt image text](./media/your-image-filename.png)
```

## Diretrizes de imagem específicas ao Enterprise Mobility Suite

Se não for possível incluir etapas para reprodução, incentivamos o uso de capturas de tela. Escreva seu conteúdo de modo que ele possa se destacar sem as capturas de tela, se for necessário.

Use as seguintes diretrizes ao criar e incluir arquivos de arte:
- Compartilhe arquivos de arte entre documentos, se for possível. Copie a URL até o arquivo necessário e adicione-a ao artigo. 
- Há ampla preferência por arquivos .PNG (Portable Network Graphic) em vez de outros formatos.
- Use quadrados vermelhos com a largura padrão fornecida em Paint (5 px) para chamar atenção para elementos específicos nas capturas de tela.  

    Exemplo:

    ![Este é um exemplo de um quadrado vermelho usado como um texto explicativo.](./media/gs13noauth.png)

- Evite espaço em branco nas bordas das capturas de tela. Capturas de tela devem ter uma borda cinza de 1 pixel de largura para que as áreas brancas da captura de tela não se fundam com a página Web.
    - Se você recortar uma captura de tela de uma maneira que deixe o plano de fundo branco nas bordas, adicione uma borda cinza de pixel único ao redor da imagem.  
    - Se você estiver usando o Paint, usa o cinza claro na paleta de cores padrão (#C3C3C3).
![Cinza para a borda](./media/grey-border-in-paint.png)     
    - Se você estiver usando um aplicativo gráfico que exija valores RGB, os números de cor serão R195, G195, B195. 
- Você pode adicionar facilmente uma borda cinza ao redor de uma imagem no Visio. Para fazer isto: 
  - Selecione a imagem. 
  - Selecione a Linha e certifique-se de que a cor correta esteja definida. 
  - Altere a espessura da linha para 1 1/2 pt.  

    **Exemplo:**

    ![Este é um exemplo de uma borda cinza ao redor do espaço em branco.](./media/agent-700w.png)

- Imagens conceituais com espaço em branco não precisam de uma borda cinza.  

    **Exemplo:**

    ![Este é um exemplo de uma imagem conceitual com espaço em branco e sem borda cinza.](./media/ic727360.png)

- Tente não deixar uma imagem tão grande. As imagens serão automaticamente redimensionadas se forem muito grandes. No entanto, o redimensionando de uma imagem pode causar confusão, portanto, recomendamos que você limite a largura das imagens para <span style="color:red;">Confirmar a largura máxima da imagem</span> 580 px, e redimensione manualmente as imagens antes do envio, se for necessário.

- Mostre as saídas dos comandos em capturas de tela.  Se o artigo incluir etapas em que o usuário está trabalhando em um shell, convém mostrar a saída do comando em capturas de tela. Nesse caso, a restrição da largura do shell para aproximadamente 72 caracteres geralmente garante a manutenção da imagem dentro da diretriz de largura de <span style="color:red;">Confirmar a largura máxima da imagem</span> 580 px. Antes de tirar uma captura de tela da saída, redimensione a janela para que apenas o comando e a saída relevantes sejam mostrados (opcionalmente com uma linha branca em ambos os lados).
- Faça capturas de tela das janelas inteiras sempre que possível. Ao fazer uma captura de tela de uma janela do navegador, redimensione a janela do navegador para <span style="color:red;">Confirmar a largura máxima da imagem</span> 580 px ou menos de largura, e mantenha a altura da janela do navegador a mais baixa possível, de modo que seu aplicativo se encaixe dentro da janela.

    Exemplo:

    ![Este é um exemplo de uma captura de tela da janela do navegador.](./media/helloworldlocal.png)

- Tenha cuidado com as informações reveladas nas capturas de tela. Verifique se não está revelando informações internas da empresa ou suas informações pessoais.
- Em arte conceitual ou diagramas, use os ícones oficiais de símbolo e de Nuvem e Enterprise e do conjunto de ícones. Um conjunto público está disponível em <span style="color:red;">Confirmar se usamos esses ícones</span> http://aka.ms/CnESymbols.


## Diretrizes para vincular artigos técnicos

| Cenário do link | Diretrizes para o link de destino  |
|---------------|-----------|
|Vinculação de um artigo técnico do EMS com outro artigo técnico do EMS|Use links relativos.|
|Link de uma página do EMS fora do diretório de documentação para um tópico da biblioteca MSDN, um tópico da biblioteca TechNet ou para um artigo da Base de Dados de Conhecimento|​Use o link real para o artigo ou tópico. Remova a localidade do idioma en-us do link.|
|Vinculação de um artigo do EMS para qualquer outra página da Web|Use o link direto|

### Use um texto de link amigável

As palavras que você inclui em um link devem ser amigáveis, ou seja, elas devem ser palavras normais em português ou o título da página a qual você está vinculando. Não use "clique aqui". É ruim para SEO e não descreve adequadamente o destino.

**Correto:**
<span style="color:red;">Confirmar a URL de nosso Guia do Colaborador</span> 
- `For more information, see the [contributor guide index](https://github.com/Microsoft/EMDocs/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**Incorreto:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

<span style="color:red;">Confirmar a URL de nosso Guia do Colaborador</span> 
- `For more information, click [here](https://github.com/Microsoft/EMDocs/contributor-guide/contributor-guide-index.md).`

### Sintaxe de markdown para links relativos de EMS
<span style="color:red;">Confirmar todo o esquema de vinculação</span> 

Para criar um link embutido de um artigo técnico do EMS para outro artigo técnico do EMS, use este formato de link. Se você criar links novos de/para artigos nos diretórios, será necessário seguir a nova sintaxe de vinculação.

Links de artigo de um subdiretório para um artigo no diretório raiz:

    [link text](../article-name.md)

O artigo no diretório raiz leva a um artigo em um subdiretório do serviço: 
<span style="color:red;">Os artigos são organizados por subdiretórios de serviço?</span>

    [link text](service-directory/article-name.md)

O artigo no subdiretório de um serviço leva a um artigo em outro subdiretório do serviço:

    [link text](../service-directory/article-name.md)
 
O artigo em um diretório leva a outro artigo no mesmo diretório:

    [link text](article-name.md)


Não é mais necessário criar âncoras, elas são geradas automaticamente no momento da publicação para todos os títulos H2. A única coisa que você precisa fazer é criar links para as seções H2:
<span style="color:red;">A metodologia de vinculação por âncora precisa ser confirmada</span>

    [link](#the-text-of-the-H2-section-separated-by-hyphens)
    [Create cache](#create-cache)

Para vincular a uma âncora em outro artigo no mesmo subdiretório:

    [link text](article-name.md#anchor-name)
    [Configure your profile](media-services-create-account.md#configure-your-profile)

Para vincular a uma âncora em outro subdiretório de serviço:

    [link text](service-directory/article-name.md#anchor-name)
    [Configure your profile](service-directory/media-services-create-account.md#configure-your-profile)


## Sintaxe personalizada de link de markdown
<span style="color:red;">Confirmar a metodologia de vinculação e o uso de seletores.</span>

Como os arquivos de inclusão estão em outro diretório, será necessário usar caminhos relativos, conforme exibido a seguir. Para um link para um único artigo de um arquivo de inclusão, use este formato:

    [link text](../articles/service-folder/article-name.md)
    
Saiba mais sobre como usar um arquivo de inclusão nas [Diretrizes personalizadas de extensões de markdown](custom-markdown-extensions.md#includes).

Se você tiver seletores incorporados em uma inclusão, use esse tipo de vinculação: 

    > [EMS.SELECTOR-LIST (Dropdown1 | Dropdown2)]
    - [(Text1 | Example1 )](../articles/service-folder/article-name1.md)
    - [(Text1 | Example2 )](../articles/service-folder/article-name2.md)
    - [(Text2 | Example3 )](../articles/service-folder/article-name3.md)
    - [(Text2 | Example4 )](../articles/service-folder/article-name4.md)

Para vincular para uma página no EMS (como uma página de preços, uma página de Contrato de Nível de Serviço ou qualquer outra coisa que não seja um artigo de documentação), use uma URL absoluta, mas omita a localidade *en-us*. O objetivo aqui é que os links funcionem no GitHub e no site renderizado:

    [link text](https://www.microsoft.com/server-cloud/enterprise-mobility/pricing.aspx)

Para testar os links, envie a página por push para sua bifurcação, exiba-a no modo de exibição renderizado e publique-a na área restrita. Os links cruzados na versão do GitHub da página devem funcionar, contanto que os destinos das URLs estejam presentes em sua ramificação.

## Links para estilo de referência

Você pode usar links para estilo de referência a fim de facilitar a leitura de seu conteúdo de origem. Os links para estilo de referência substituem a sintaxe de link embutido pela sintaxe simplificada, que permite a movimentação das URLs longas para o final do artigo. Este é o exemplo do Daring Fireball:

Texto embutido:

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

Referências a links no final do artigo:

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/  
    [3]: http://search.msn.com/


## Voltar ao início

- [Artigo de visão geral](./../README.md)
- [Índice de artigos com diretrizes](./contributor-guide-index.md)



<!--HONumber=Mar16_HO1-->


