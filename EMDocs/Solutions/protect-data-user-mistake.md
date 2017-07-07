---
title: "Proteger dados contra erros do usuário | Microsoft Docs"
description: "Um cenário que descreve como o Enterprise Mobility + Security pode ser usado para proteger dados corporativos contra os erros do usuário e impedir a perda de dados aproveitando os recursos Cloud App Security e Proteção de Informações do Azure."
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: solution
ms.prod: 
ms.service: cloud-app-security
ms.technology: techgroup-identity
ms.assetid: 0af3894c-7b0e-4c0c-8874-31e041d81300
ms.reviewer: v-craic
ms.suite: ems
ms.custom: information-protection
ms.translationtype: Human Translation
ms.sourcegitcommit: bc112d81a2b0e59f9ae67efe2a914b0c64ac76ba
ms.openlocfilehash: 4c6c81cd9d59f402c1ce458e54063e2986324c5b
ms.contentlocale: pt-br
ms.lasthandoff: 07/07/2017


---

# <a name="protect-data-against-user-mistakes"></a>Proteger dados contra erros do usuário

Embora a transição para a mobilidade e a nuvem tenha aumentado consideravelmente a produtividade do funcionário, a interação complexa entre usuários, dispositivos, aplicativos e dados (no local e na nuvem) gerou novos pontos cegos para as equipes de TI. Mesmo que as organizações não adotem essa transição, os funcionários já o fizeram. Uma vez que as interações entre esses componentes e a sofisticação dos vetores de ataque aumentam, a segurança continua sendo um desafio para as empresas. As equipes de TI lutam para manter a visibilidade, o controle e a proteção dos dados corporativos.

Os recursos de controle de dados que protegem dados corporativos contra erros do usuário e impedem a perda de dados são etapas importantes para proteção dos recursos, ao mesmo tempo que permitem aos usuários serem produtivos.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?

O EMS (Enterprise Mobility + Security) permite que a TI obtenha mais visibilidade das atividades dos usuários, dispositivos e dados no local e na nuvem.  Com o EMS, a TI pode proteger dados corporativos contra erros do usuário com imposição e controles mais rígidos.  A TI será capaz de monitorar a detecção de riscos usando análises e relatórios avançados sobre usuários, tráfego de upload/download, padrões de uso e transações de aplicativos descobertos.

## <a name="recommended-solution"></a>Solução recomendada

Para atender aos requisitos desse cenário, o EMS usa o [Cloud App Security](https://technet.microsoft.com/library/mt489024.aspx) e a [Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection). Ao implementar essas tecnologias, as organizações poderão ter:

- Visibilidade completa do uso de aplicativos na nuvem pelos funcionários e da TI sombra
- Políticas de dados e controle em nível granular para proteção contínua de dados em aplicativos na nuvem
- Classificação e proteção persistentes de dados que garantem que os dados sejam protegidos o tempo todo, independentemente de onde estejam armazenados ou com quem são compartilhados
- Capacidade de compartilhar dados com segurança com pessoas dentro e fora da organização
- Controles intuitivos de classificação e proteção de dados
- Visibilidade e controle dos dados compartilhados para usuários e TI

O diagrama a seguir resume as funcionalidades envolvidas neste cenário e como eles são usados para proteger seus recursos:

![Gráfico mostrando como o Cloud App Security e a Proteção de Informações do Azure trabalham juntos para proteger dados no local e na nuvem.](./media/protect-data-user-mistake/protect-data-user-mistake-fig1-1.png)

Este é um breve vídeo que faz uma introdução rápida sobre como o Enterprise Mobility + Security (EMS) permite que a TI obtenha maior visibilidade e controle:

<iframe width="675" height="480" src="https://www.youtube.com/embed/LWlRVHp7sKQ" frameborder="0" allowfullscreen></iframe>


## <a name="how-to-implement-this-solution"></a>Como implementar esta solução

Siga estas etapas para implementar o [Cloud App Security](https://technet.microsoft.com/library/mt668458.aspx) e a [Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection):

- Etapa 1: Descobrir aplicativos na nuvem em uso e controlá-los com política
- Etapa 2: Proteger dados no local ou na nuvem

## <a name="how-to-protect-data-against-user-mistakes"></a>Como proteger dados contra erros do usuário

Os aplicativos em nuvem estão sendo usados pela maioria das empresas de hoje, e logo chegaremos a um tempo em que mais dados corporativos serão armazenados na nuvem do que no local. Muitas vezes, os usuários usarão aplicativos SaaS de seus dispositivos sem permissão ou conhecimento da empresa, o que causará um aumento no uso de TI sombra da nuvem. Essa conclusão vem de estudos que mostram que 80% dos funcionários admitiram usar aplicativos SaaS não aprovados para uso corporativo. O [Cloud App Security](https://technet.microsoft.com/library/mt657567.aspx) fornece uma visão geral detalhada de todos os aplicativos em nuvem que estão sendo usados na organização. Ele identifica todos os usuários e os endereços IP que acessam um aplicativo. Ele também faz uma avaliação de riscos para mais de 13.000 aplicativos de nuvem e fornece uma pontuação de risco automatizada para cada aplicativo com base em mais de 60 parâmetros. 

Siga a etapa 1 para descobrir os aplicativos em nuvem no seu ambiente e implementar políticas para controlá-los. A segunda etapa dessa solução implementará a [Proteção de Informações do Azure](https://docs.microsoft.com/en-us/information-protection/get-started/requirements) para proteger e classificar dados, o que pode reduzir erros dos usuários e o uso incorreto de dados.

### <a name="step-1-discover-cloud-apps-in-use-and-control-them-with-policy"></a>Etapa 1: Descobrir aplicativos na nuvem em uso e controlá-los com política

A primeira etapa para usar o Cloud App Security é [descobrir seus aplicativos](https://technet.microsoft.com/en-us/library/mt657567.aspx). Se você ignorar essa etapa, não haverá aplicativos a serem analisados e restringidos usando políticas. Se você não tiver iniciado o processo de descoberta, a opção Descobrir no painel do Cloud App Security mostrará a seguinte mensagem:

![Captura de tela mostrando a mensagem que o usuário ainda não carregou um log do Cloud Discovery.](./media/protect-data-user-mistake/protect-data-user-mistake-fig2-1.png)

Descobrir quais aplicativos estão em uso em toda a organização é a primeira etapa para garantir que dados corporativos confidenciais sejam protegidos. Assim que o processo de descoberta for finalizado, você poderá ver uma lista de aplicativos que foram descobertos no [painel do Cloud Discovery](https://technet.microsoft.com/en-us/library/mt727946.aspx).

![Captura de tela mostrando o painel do Cloud Discovery e uma lista de aplicativos que foram descobertos.](./media/protect-data-user-mistake/protect-data-user-mistake-fig3.png)

Cada aplicativo tem uma pontuação que representa a credibilidade e a confiabilidade dos aplicativos em nuvem. Ao acessar a classificação do aplicativo, você observará que há três categorias que são usadas para criar essa classificação: Geral, Segurança e Conformidade. Cada categoria tem determinados atributos que são testados durante o processo de descoberta. Se um atributo não for totalmente compatível, ele será mostrado como parcial, e você poderá acessar os detalhes desse atributo para entender por que ele está sendo mostrado como parcial.

![Captura de tela mostrando detalhes do atributo "Cabeçalhos de segurança do HTTP".](./media/protect-data-user-mistake/protect-data-user-mistake-fig4.png)

A próxima etapa é controlar o comportamento dos aplicativos que foram descobertos usando políticas. Esse recurso permite que a TI ajuste os aplicativos descobertos e o nível de risco associado à sua organização. Existem diferentes tipos de política; qual deles você deve criar primeiro depende do requisito de negócios da sua organização. Por padrão, a política de detecção de anomalias está habilitada, de modo que não é necessário configurar uma nova política para que ela funcione. Porém, é possível ajustar sobre quais tipos de anomalia você quer ser alertado na política padrão.

![Captura de tela mostrando como selecionar um tipo de política a ser criado.](./media/protect-data-user-mistake/protect-data-user-mistake-fig5.png)

Depois que a política estiver configurada, você poderá investigar possíveis violações em uma política que atualmente esteja em vigor. Nesse cenário específico, você quer verificar se há alguma informação de identificação pessoal compartilhada na nuvem. As informações sobre esse tipo de atividade estão disponíveis pela Política de Arquivo. A política no nível de arquivo que você vai procurar é a política de conformidade com a PII (Informações de Identificação Pessoal). A finalidade dessa política é identificar arquivos que contenham informações de identificação pessoal que são compartilhadas publicamente, bem como fornecer opções de correção e investigação.

![Captura de tela mostrando como investigar o tipo Política de Arquivo em busca de possíveis violações.](./media/protect-data-user-mistake/protect-data-user-mistake-fig6.png)

Nesse caso específico, há três correspondências para essa política, o que significa que há três arquivos que correspondem a essa política. É possível clicar em um para investigar o nome do arquivo e seu local.

### <a name="step-2-protect-data-on-premises-or-in-the-cloud"></a>Etapa 2: Proteger dados no local ou na nuvem

Antes de implementar essa solução, examine os requisitos para a [Proteção de Informações do Azure](https://docs.microsoft.com/en-us/information-protection/get-started/infoprotect-tutorial-step1).

A Proteção de Informações do Microsoft Azure ajuda você a classificar e rotular os dados no momento da criação. A Proteção (criptografia + autenticação + direitos de uso) pode ser então aplicada aos dados confidenciais. Os rótulos de classificação e a proteção são persistentes, acompanhando os dados para que eles possam ser identificados e protegidos o tempo todo, independentemente de onde são armazenados ou com quem são compartilhados. Ao planejar a implementação de rótulos e políticas de proteção de informações, use as seguintes diretrizes:



- Classifique os dados com base na confidencialidade
- Comece pelos dados mais confidenciais
- A TI pode definir regras automáticas; os usuários podem complementá-las
- Associe ações como marcas visuais e proteção

Embora a Proteção de Informações do Azure tenha rótulos padrão, você também pode personalizar e criar seus próprios rótulos ou sub-rótulos que os usuários veem na barra da Proteção de Informações.

> [!NOTE]
> Rótulos são metadados gravados em documentos. Os rótulos são em texto não criptografado para que outros sistemas, como um mecanismo de DLP, possam lê-los.

No exemplo a seguir, você pode ver sub-rótulos personalizados que foram criados sob o rótulo Segredo:

![Captura de tela mostrando os sub-rótulos personalizados que foram criados sob o rótulo "Segredo". ](./media/protect-data-user-mistake/protect-data-user-mistake-fig7.png)


Depois de definir como usará os rótulos (padrão ou personalizados), [configure um rótulo para aplicar a proteção do Rights Management](https://docs.microsoft.com/en-us/rights-management/information-protection/configure-policy-protection#to-configure-a-label-to-apply-rights-management-protection).

Com a Proteção de Informações do Azure, controles de proteção e classificação de dados são integrados ao Office e a outros aplicativos comuns. Essa integração oferece opções simples de um clique para proteger os dados com que os usuários estão trabalhando. No portal do Azure, um administrador pode aplicar padrões predefinidos, como "Números de cartão de crédito" ou "Números do seguro social dos EUA", como uma condição para classificação automática. Como alternativa, ele pode usar padrões de texto e expressões regulares para definir uma cadeia de caracteres ou um padrão personalizado.

Quando configura condições para um rótulo, você pode atribuir automaticamente um rótulo a um documento/email ou pode solicitar que os usuários selecionem o rótulo que você recomenda. Leia [Como configurar condições para classificação automática e recomendada da Proteção de Informações do Azure](https://docs.microsoft.com/en-us/rights-management/information-protection/configure-policy-classification) para obter mais informações sobre como fazer essa configuração.

> [!NOTE]
> Para saber mais sobre classificação e proteção de dados, leia [Secure data using classification, labeling and protection](https://docs.microsoft.com/en-us/enterprise-mobility-security/solutions/infoprotect-secure-classify-scenario) (Proteger dados usando classificação, rotulagem e proteção).

## <a name="next-steps"></a>Próximas etapas

O Microsoft Cloud App Security fornece uma solução abrangente para descobrir, monitorar, controlar e proteger os dados em aplicativos de nuvem. O Cloud App Security ajuda os administradores de TI a criptografar diretamente do console do Cloud App Security usando a Proteção de Informações do Azure. Por meio da integração com a Proteção de Informações do Azure, agora você pode aplicar proteção genérica a arquivos armazenados no SharePoint Online e no One Drive for Business se você vê uma necessidade. Para obter mais informações sobre a integração entre o Cloud App Security e a Proteção de Informações do Azure, leia [Integração da Proteção de informações do Azure](https://docs.microsoft.com/en-us/cloud-app-security/azip-integration).
