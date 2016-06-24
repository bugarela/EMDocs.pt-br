<properties pageTitle="Metadados para os artigos técnicos do Enterprise Mobility Suite" description="Explica os metadados necessários para os artigos." metaKeywords="" services="" solutions="" documentationCenter="" authors="v-jocgar" videoId="" scriptId="" manager="required" />

<tags ms.service="contributor-guide" ms.devlang="" ms.topic="article" ms.tgt_pltfrm="" ms.workload="" ms.date="02/24/2016" ms.author="v-jocgar" />

# Metadados para os artigos técnicos do Enterprise Mobility Suite

Tarefas Pendentes: 
- [] Nº 11 Confirmar se as instruções para cada propriedade estão corretas.
- [] Nº 12 Confirmar a URL na seção Propriedades: Descrição.
- [] Nº 13 Atualizar a lista de serviços e a lista de valores de ms-services (consulte email RobMazz nº 3 2016-02-18).
- [] Nº 14 Confirmar a URL na seção Propriedades: Marcas (local dos artigos EMS).
- [] Nº 15 Confirmar a lista curta (3) de marcas opcionais nas Propriedades: Marcas. Deve haver mais marcas? 
- [] Nº 16 Confirme a lista de serviços na seção Marcas: ms-services.
- [] Nº 17 Atualizar a lista de tipos de artigo (tipos de recursos) na seção Marcas: mstopic (email RobMazz nº 1 2016-02-18).
- [] Nº 18 Atualizar e aprovar a lista de linguagens de programação na seção Marcas: ms.devlang (email RobMazz nº 4 2016-02-18).
- [] Nº 19 Confirmar a lista de plataformas de destino na seção Marcas: ms.tgt_pltfrm (email RobMazz nº 2 2016-02-18).
- [] Nº 20 Confirmar se todos os links (especialmente âncoras) funcionam corretamente. 

Todos os artigos técnicos do EMS contém duas seções de metadados: uma seção de propriedades e uma seção de marcas. A seção de propriedades permite alguma automação de site e coisas relacionadas a SEO, enquanto a seção marcas permite a geração de muitos relatórios de conteúdo internos. As duas seções são necessárias.

- [Sintaxe]
- [Uso]
- [Atributos e valores para a seção de propriedades]
- [Atributos e valores para a seção de marcas]

## Sintaxe

A seção de propriedades usa a seguinte sintaxe:

    <properties
       pageTitle="Page title that displays in search results and the browser tab | Microsoft EMS"
       description="Article description that will be displayed on landing pages and in most search results"
       services="service-name"
       documentationCenter="dev-center-name"
       authors="GitHub-alias-of-only-one-author"
       manager="manager-alias"
       editor=""
       tags="optional"
       keywords="Separate terms with commas. Check with your SEO champ before you change content in this article containing these terms."/>

A seção de marcas usa a seguinte sintaxe:

    <tags
       ms.service="required"
       ms.devlang="may be required"
       ms.topic="article"
       ms.tgt_pltfrm="may be required"
       ms.workload="na"
       ms.date="mm/dd/yyyy"
       ms.author="Your MSFT alias or your full email address;semicolon separates two or more"/>

## Uso

- O nome do elemento e os nomes de atributo diferenciam maiúsculas de minúsculas.
- A seção Propriedades deve ser a primeira linha de seu arquivo.
- Deixe uma linha em branco depois de cada seção de metadados e antes do título de sua página para garantir que o título da página seja convertido corretamente em HTML durante o processo de publicação.

## Atributos e valores para a seção Propriedades

![](./media/checkmark-small.png)**pageTitle**: necessária; importante para SEO. O texto para este atributo é exibido na guia do navegador e como o título em um resultado de pesquisa. Use 55-60 caracteres incluindo espaços e incluindo o identificador de site *| Microsoft EMS* (digitado como: espaço pipe espaço Microsoft EMS).  pageTitle deve ser diferente de H1.

![](./media/checkmark-small.png)**description**: necessária; importante para SEO (relevância) e funcionalidade do site. A descrição deve ter pelo menos 125 caracteres até no máximo 155 caracteres, incluindo espaços. Descreva a finalidade de seu conteúdo para que os clientes saibam se devem escolhê-lo em uma lista de resultados de pesquisa. O valor é:

- Esse texto pode ser exibido como a descrição ou o resumo nos resultados da pesquisa do Google.
- Esse texto é exibido nos <span style="color:red;">Confirmar URL</span> [resultados de índice de artigo](http://docs.microsoft.com/ems/articles/).

![](./media/checkmark-small.png)**services**: necessária para artigos que tratam de um serviço. Esse valor é chamado normalmente de "campo de dados dinâmico de serviço". Lista todos os serviços aplicáveis, separados por vírgulas. O primeiro serviço que você lista orientará a trilha de navegação até a página e a navegação à esquerda exibida na página.

Em artigos que especificam um valor para os serviços e um valor para o documentationCenter, o valor para os serviços orientará a trilha de navegação. Os valores adicionais que você listar serão exibidos como marcas no artigo publicado. Valores:

- active-directory
- active-directory-b2c
- active-directory-ds
- app-service-api
- api-management
- app-service
- app-service-mobile
- app-service-web
- application-gateway
- application-insights
- automação
- backup
- batch
- best-practice
- cobrança
- biztalk-services
- cache
- cdn
- cloud-services
- data-catalog
- data-factory
- data-lake-analytics
- data-lake-store
- devtest-lab
- dns
- documentdb
- expressroute
- event-hubs
- hdinsight
- iot-hub
- key-vault
- load-balancer
- machine-learning
- marketplace
- media-services
- mobile-engagement
- mobile-services
- multi-factor-authentication
- notification-hubs
- operational-insights
- operations-management-suite
- powerapps
- recovery-manager
- redis-cache
- remoteapp
- rights-management
- agendador
- pesquisa
- security-center
- service-bus
- service-fabric
- site-recovery
- sql-database
- sql-data-warehouse
- sql-reporting
- armazenamento
- loja
- storsimple
- stream-analytics
- traffic-manager
- virtual-machines
- virtual-network
- visual-studio-online
- vpn-gateway
- web-sites

![](./media/checkmark-small.png)**documentationCenter**: necessária para artigos centrados em desenvolvedores mais bem apresentados por meio de um centro de desenvolvimento. Especifica o centro de desenvolvimento único ou idioma que se aplica ao artigo. O valor que você listar determinará a trilha de navegação para a página. Em artigos que especificam um valor para os serviços e um valor para o documentationCenter, o valor para os serviços orientará a trilha de navegação. Valores:

- **.net**
- **nodejs**
- **java**
- **php**
- **python**
- **ruby**
- **mobile**: preterido. Substitua com uma plataforma móvel específica.
- **ios**: verificando esse novo valor
- **android**: verificando esse novo valor
- **windows**: verificando esse novo valor
- **xamarin**: verificando esse novo valor

![](./media/checkmark-small.png)**authors**: necessária, somente um valor. Lista a conta do GitHub do autor principal ou SME do artigo. Esse atributo orienta o subtítulo no artigo publicado. Lista apenas um, apesar do nome no plural do atributo.

![](./media/checkmark-small.png)**manager**: necessária se você for um colaborador da Microsoft. Lista o alias de email do gerenciador de publicação de conteúdo para a área de tecnologia. Se você for um colaborador da comunidade, inclua o atributo, mas deixe-o vazio para que possamos preenchê-lo.

![](./media/checkmark-small.png)**editor**: não usado. Não use-o para outras finalidades.

![](./media/checkmark-small.png)**tags**: opcional. Inclua somente se você quiser habilitar um link, na trilha de navegação do artigo até a página de índice do artigo <span style="color:red;">Confirmar URL</span> (http://docs.microsoft.com/ems/articles/), para uma lista pré-filtrada de artigos que correspondem a um dos valores aprovados. Esses valores tem como objetivo fornecer uma maneira de agrupar o conteúdo quando o agrupamento de conteúdo não for específico do serviço. Essas marcas também podem fornecer rótulos que indicam a pilha de tecnologia a qual o artigo se aplica. Esse valor **não** oferece suporte a marcas livres ou hashtags; as marcas devem ser habilitadas no site. Você pode fornecer vários valores de marcas para um artigo, separados por vírgula. Os valores aprovados são:

<span style="color:red;">Confirmar esses valores de marca</span>
  - existente
  - cobrança
  - mysql

![](./media/checkmark-small.png)**keywords**: opcional. Apenas para uso de especialistas em SEO. Separe os termos com vírgulas. **Consulte seu especialista em SEO antes de alterar ou excluir o conteúdo deste artigo que contém esses termos.** Este atributo registra as palavras-chave que o especialista em SEO direcionou e está acompanhando para melhorar a classificação da pesquisa. As palavras-chave não processam no HTML publicado. A validação não exige esse atributo.

## Atributos e valores para a seção Marcas

![](./media/checkmark-small.png)**ms.service**: obrigatória. Especifica o serviço, a ferramenta ou o recurso ao qual o artigo se aplica. Um valor por página.

 Se uma página for aplicada a vários serviços, escolha o serviço ao qual ela se aplica mais diretamente. Por exemplo, um artigo que usa um aplicativo hospedado em sites para demonstrar a funcionalidade do Barramento de Serviço deve ter o valor **service-bus**, em vez de **web-sites**. Se uma página se aplicar igualmente a vários serviços, escolha **multiple**. Se uma página não se aplicar a todos os serviços (algo raro), escolha **NA**.

<span style="color:red;">Confirme estes valores.</span>
 - **active-directory**
 - **api-management**
 - **app-service**: aplica-se somente ao material conceitual geral no Serviço de Aplicativo
 - **app-service-api**
 - **app-service-logic**
 - **app-service-mobile**
 - **app-service-web**
 - **application-insights**
 - **automação**
 - **backup**
 - **batch**
 - **biztalk-services**
 - **cobrança**
 - **cache**
 - **cdn**
 - **cloud-services**
 - **expressroute**
 - **hdinsight**
 - **iot-hub**
 - **key-vault**
 - **machine-learning**
 - **media-services**
 - **mobile-engagement**
 - **mobile-services**
 - **multi-factor-authentication**
 - **multiple**: a página é aplicada igualmente a vários serviços
 - **na**: a página não se aplica a qualquer serviço (raro)
 - **notification-hubs**
 - **operational-insights**
 - **powerapps**
 - **recovery-manager**
 - **redis-cache**
 - **remoteapp**
 - **rights-management**
 - **agendador**
 - **service-bus**
 - **service-fabric**
 - **site-recovery**: antiga recovery-services
 - **sql-database**
 - **sql-data-warehouse**
 - **sql-reporting**
 - **armazenamento**
 - **storsimple**
 - **traffic-manager**
 - **virtual-machines**
 - **virtual-network**
 - **visual-studio-online**
 - **vpn-gateway**
 - **web-sites**

![](./media/checkmark-small.png)**ms.devlang**: obrigatória. Especifica a linguagem de programação ao qual o artigo se aplica. Valor único por página.

 Se uma página se aplica igualmente a duas linguagens de programação, escolha **multiple**. Se uma página for principalmente conceitual e seu conteúdo for geralmente aplicável a várias linguagens de programação, escolha **multiple**. Se uma página não for destinada a desenvolvedores, e a aplicabilidade de linguagem de programação não for relevante, escolha **NA**. Use **rest-api** para identificar os tópicos de referência da API REST.

<span style="color:red;">Confirme estes valores</span>
 - **cpp**
 - **dotnet**
 - **java**
 - **javascript**
 - **multiple**: a página se aplica igualmente a várias linguagens de programação.
 - **na**: a página não é destinada a desenvolvedores e não é específica a qualquer linguagem de programação.
 - **nodejs**
 - **objective-c**
 - **php**
 - **python**
 - **rest-api**
 - **ruby**


![](./media/checkmark-small.png)**ms.topic**: obrigatória. Especifica o tipo de tópico. A maioria das páginas novas criadas pelos colaboradores será um artigo ou uma referência.

<span style="color:red;">Confirme estes valores</span>
 - **article**: um tópico conceitual, tutorial, guia de recursos ou outro artigo que não é de referência

 - **get-started-article**: atribua a artigos apresentados na seção Introdução do painel de navegação esquerdo de um serviço.

 - **hero-article**: um tutorial "herói" projetado para fornecer uma introdução a um serviço ou recurso que ajuda os visitantes a começarem a usar o serviço rapidamente, e gera inscrições de avaliação gratuita e ativações do MSDN. Atribua esse valor SOMENTE para artigos apresentados na parte superior da página de aterrissagem da documentação de seu serviço.

 - **reference**: uma página de referência da API (incluindo a API REST) ou a página de referência de cmdlet do PowerShell

![](./media/checkmark-small.png)**ms.tgt_pltfrm**: obrigatório. Especifica a plataforma de destino, por exemplo, Windows, Linux, Windows Phone, iOS, Android ou plataformas de cache especial. Um valor por página. Esse valor será **NA** para a maioria dos tópicos, exceto máquinas virtuais e móveis.

<span style="color:red;">Confirme estes valores</span>
 - **cache-in-role**
 - **cache-multiple**
 - **cache-redis**
 - **cache-service**
 - **cache-shared**
 - **command-line-interface**
 - **ibiza**: conteúdo que usa o portal do Ibiza. Use apenas em casos nos quais o recurso que está sendo discutido está disponível no portal do Ibiza e no portal atual.
 - **mobile-android** 
 - **mobile-html**
 - **mobile-ios**
 - **mobile-kindle**
 - **mobile-multiple**
 - **mobile-nokia-x**
 - **mobile-phonegap**
 - **mobile-sencha**
 - **mobile-windows**
 - **mobile-windows-phone**
 - **mobile-windows-store**
 - **mobile-xamarin**
 - **mobile-xamarin-android**
 - **mobile-xamarin-ios**
 - **multiple**: a página é aplicada igualmente a várias plataformas
 - **na**: um especificador de plataforma não é aplicável a esta página
 - **powershell**
 - **vm-linux**
 - **vm-multiple**
 - **vm-windows**
 - **vm-windows-sharepoint**
 - **vm-windows-sql-server**
 - **vs-getting-started**: identifica o grupo de páginas Introdução do VS. Marca adicionada em 1/12/14.
 - **vs-what-happened**: identifica a página O que aconteceu da Introdução ao VS. Marca adicionada em 1/12/14.

![](./media/checkmark-small.png)**ms.workload**: obrigatória. Especifica a carga de trabalho a qual a página se aplica. Somente um valor por artigo. 

![](./media/checkmark-small.png) **ms.date**: obrigatória. Especifica a data na qual o artigo foi revisado pela última vez com relação à relevância, precisão, capturas de tela corretas e links úteis. Insira a data no formato mm/dd/aaaa. Essa data também aparece no artigo publicado como a data da última atualização.

![](./media/checkmark-small.png) **ms.author**: obrigatória. Especifica os autores associados ao tópico. Para especificar vários valores, separe-os por ponto-e-vírgula. Os alias ou os endereços de email completos da Microsoft são aceitáveis. O tamanho não pode ultrapassar 200 caracteres.

## Voltar ao início

- [Artigo de visão geral](./../README.md)
- [Índice de artigos com diretrizes](./contributor-guide-index.md)


<!--Anchors-->
[Syntax]: #syntax
[Usage]: #usage
[Attributes and values for the properties section]: #attributes-and-values-for-the-properties-section
[Attributes and values for the tags section]: #attributes-and-values-for-the-tags-section


<!--HONumber=Mar16_HO1-->


