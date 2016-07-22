<properties title="Create tables in markdown" pageTitle="Criar tabelas em markdown para artigos do EMS" description="Explica como codificar tabelas em markdown." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="robmazz" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/26/2016" ms.author="v-jocgar" />

# Criar tabelas em markdown

Tarefas Pendentes:
- [ ] Nº 33 Adicionar a sintaxe de Observação Markdown personalizada à Observação abaixo.

As tabelas devem ser usadas moderadamente nos artigos. Use-as apenas se os dados forem realmente tabulares.

**Observação**
As tabelas markdown têm capacidade limitada para tratar de cadeias de caracteres de texto longas; não há conceito de quebra automática de linha em uma célula de tabela. Uma célula simplesmente se expandirá até a largura máxima do conteúdo, o que torna a exibição da tabela em telas menores uma tarefa desafiadora. Use tabelas para conjuntos menores de informações, e encontre outras formas significativas de exibir conjuntos de conteúdo mais longos.

## Sintaxe da tabela markdown
A maneira mais simples de criar uma tabela em markdown é usando pipes e hifens. Você precisa de pelo menos 3 hifens na segunda linha para cada coluna para criar o cabeçalho da tabela. O texto do cabeçalho da tabela é automaticamente centralizado e renderizado como texto em negrito.  

 ![1]

O markdown renderiza automaticamente o sombreamento da linha da tabela alternativa.  
 ![2]

Você pode justificar as colunas com dois-pontos:

  	|:-----|   - this is left aligned (default -- can be omitted)
  	|-----:|   - this is right aligned
  	|:-----:|  - this is centered

Os pipes externos são opcionais, e você não precisa alinhar perfeitamente o texto e os pipes para sua tabela a fim de renderizá-la corretamente. Este exemplo de formatação rápida:

 ![3]

está pronto e renderizado corretamente pelo Markdown.  
 ![4]

Se você usar tabelas HTML e seu Markdown não estiver renderizando entre as duas tabelas, será preciso adicionar uma marca BR de fechamento depois da marca TABLE de fechamento.

![5]

Para ver uma maneira rápida e fácil de criar tabelas em markdown, teste o gerador de tabelas Markdown: http://www.tablesgenerator.com/markdown_tables


## Voltar ao início

- [Artigo de visão geral](./../README.md)
- [Índice de artigos com diretrizes](./contributor-guide-index.md)

<!--image references-->
[1]: ./media/table-markdown-1.png
[2]: ./media/table-markdown-2.png
[3]: ./media/table-markdown-3.png
[4]: ./media/table-markdown-4.png
[5]: ./media/break-tables.png


<!--HONumber=Mar16_HO1-->


