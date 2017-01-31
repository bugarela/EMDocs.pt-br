---
title: "Proteger dados usando classificação, rotulação e proteção | Microsoft Docs"
description: "Um cenário que descreve como o Enterprise Mobility + Security pode ser usado para classificar, rotular e proteger dados tirando proveito dos recursos da Proteção de Informações do Microsoft Azure."
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 01/23/17
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 65409d5c-4f1b-4026-86e9-e65e1c4fe2b4
ms.reviewer: v-craic
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5d9a4bd18660a573b2dd76c0263b89ecf5ae4610
ms.openlocfilehash: 88359b6542ce8524095af2b7ce1df4674b655b82


---

# <a name="secure-data-using-classification-labeling-and-protection"></a>Proteger dados usando classificação, rotulação e proteção

Atualmente, o compartilhamento de informações acontece em vários dispositivos e entre fronteiras organizacionais.  É fundamental garantir que dados corporativos críticos não sejam comprometidos nesse processo, enquanto permite que os usuários possam compartilhar com segurança o que é importante para que possam executar seus trabalhos. Com as tendências como a terceirização, você precisa compartilhar dados confidenciais da empresa com contratados e fornecedores. Como nem todos os conteúdos precisam da mesma proteção, as empresas enfrentam o desafio de identificar quais dados precisam de proteção e quais não precisam.

Continue lendo para saber mais sobre como o Enterprise Mobility + Security ajuda a lidar com esse cenário.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?

O EMS (Enterprise Mobility + Security) é a única solução de nuvem abrangente que protege dados corporativos no próprio dispositivo e além dele, com quatro camadas de proteção de identidades, dispositivos, aplicativos e dados. O EMS ajuda a resolver um dos principais desafios do mundo concentrado em dispositivos móveis e na nuvem – como fornecer dados seguros para funcionários em trânsito. Com o EMS, você permitirá que seus funcionários colaborem com segurança dentro e fora da sua organização. O EMS permite que os administradores de TI tirem proveito da Proteção de Informações do Azure para ajudar a proteger dados corporativos no nível do arquivo. Usando essa capacidade, eles podem ter certeza de que os dados estarão sempre protegidos, independentemente de onde estão armazenados, com quem são compartilhados e se estão em repouso ou em trânsito.

## <a name="recommended-solution"></a>Solução recomendada

A Proteção de Informações do Azure permite que as organizações classifiquem, rotulem e protejam dados no momento da criação ou modificação. Com a Proteção de Informações do Azure, os usuários podem:

- classificar dados com base na confidencialidade e adicionar rótulos — manual ou automaticamente
- proteger dados usando criptografia, autenticação e direitos de uso
- Possibilitar uma experiência intuitiva e não intrusiva para os usuários finais

A organização também tem acesso a relatórios e monitoramento detalhado para que possam ver o que está acontecendo com os dados compartilhados e gerenciá-los melhor. O diagrama a seguir resume o ciclo de vida da proteção de informações:

![Ciclo de vida da proteção de informações](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig1.png)

Assista a este breve vídeo para obter uma introdução rápida sobre como a Proteção de Informações do Azure torna mais simples classificar, rotular e proteger informações, mesmo quando elas trafegam fora da sua organização.

<iframe src="https://channel9.msdn.com/Shows/Mechanics/An-Introduction-to-Microsoft-Azure-Information-Protection/player" width="560" height="315" allowFullScreen frameBorder="0"></iframe>

## <a name="how-to-implement-this-solution"></a>Como implementar esta solução

Siga estas etapas para implementar a classificação, identificação e proteção de dados usando a Proteção de Informações do Azure:

- Etapa 1: Preparar-se para a proteção e a classificação de dados
- Etapa 2: Configurar políticas e rótulos de proteção de informações
- Etapa 3: Implementar a classificação automática baseada no conteúdo
- Etapa 4: Configurar condições para classificação automática e recomendada

## <a name="how-to-secure-data-using-classification-labeling-and-protection-with-azure-information-protection"></a>Como proteger dados usando a classificação, a rotulagem e a proteção com a Proteção de Informações do Azure

As empresas precisam identificar quais dados precisam de proteção e quais não precisam do mesmo nível de proteção. As etapas a seguir orientarão você pelas principais tarefas que devem ser executadas para possibilitar que a IT implemente a Proteção de Informações do Azure.

### <a name="step-1-preparing-for-document-protection-and-content-classification"></a>Etapa 1: Preparar-se para a proteção de documentos e a classificação de conteúdo

Antes de implementar essa solução, examine o [requisitos para a Proteção de Informações do Azure](/information-protection/get-started/requirements.md) e garantir que o Azure Rights Management esteja ativado. Se estiver ativado, você verá a tela a seguir no Portal do Azure:

![Portal do Azure](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig2.png)

Quando ativa o Azure Rights Management, você pode proteger dados importantes usando aplicativos e serviços que têm suporte da solução de proteção de informações. Você também pode gerenciar e monitorar arquivos protegidos e emails que sua organização possui. Você precisa ativar o Azure Rights Management antes que possa usar os recursos de gerenciamento de direitos no Office, SharePoint e Exchange e proteger arquivos confidenciais.

### <a name="step-2-configure-information-protection-policies-and-labels"></a>Etapa 2: Configurar políticas e rótulos de proteção de informações

Ao planejar a implementação de rótulos e políticas de proteção de informações, use as seguintes diretrizes:

- Classifique os dados com base na confidencialidade
- Comece pelos dados mais confidenciais
- A TI pode definir regras automáticas; os usuários podem complementá-las
- Associe ações como marcas visuais e proteção

O diagrama a seguir tem um exemplo de como isso poderia ser implementado:

![Classificação](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig3.png)

Embora a Proteção de Informações do Azure tenha rótulos padrão, você também pode [personalizar](/information-protection/deploy-use/configure-policy-new-label.md) e criar seus próprios rótulos ou rótulos secundários que os usuários veem na barra da Proteção de Informações.

> [!IMPORTANT]
> Rótulos são metadados gravados em documentos. Os rótulos são em texto não criptografado para que outros sistemas, como um mecanismo de DLP, possam lê-los.

No exemplo a seguir, você pode ver rótulos secundários personalizados que foram criados sob o rótulos **Segredo**:

![Rótulo](./media/infoprotect-secure-classify-scenario/infoprotect-secure-classify-scenario-fig4.png)

Depois de definir como usará os rótulos (padrão ou personalizados), [configure um rótulo para aplicar a proteção do Rights Management](/information-protection/deploy-use/configure-policy-new-label.md).

### <a name="step-3-implement-content-based-automatic-classification"></a>Etapa 3: Implementar a classificação automática baseada no conteúdo

Com a Proteção de Informações do Azure, controles de proteção e classificação de dados são integrados ao Office e a outros aplicativos comuns. Essa integração oferece opções simples de um clique para proteger os dados com que os usuários estão trabalhando. No portal do Azure, você pode aplicar padrões predefinidos, como "Números de cartão de crédito" ou "Número do seguro social dos EUA", como uma condição para classificação automática. Como alternativa, você pode usar padrões de texto e expressões regulares para definir uma cadeia de caracteres ou padrão personalizado.

Quando configura condições para um rótulo, você pode atribuir automaticamente um rótulo a um documento/email ou pode solicitar que os usuários selecionem o rótulo que você recomenda. Leia [Como configurar condições para classificação automática e recomendada da Proteção de Informações do Azure](/information-protection/deploy-use/configure-policy-classification.md) para obter mais informações sobre como fazer essa configuração.


### <a name="step-4-configure-conditions-for-automatic-and-recommended-classification"></a>Etapa 4: Configurar condições para classificação automática e recomendada

As políticas podem ser definidas por administradores de TI para aplicar automaticamente a classificação e a proteção aos dados. As políticas também podem ser baseadas no conteúdo com que você está trabalhando e podem ser configuradas para solicitar aos usuários a classificação sugerida. A lista de condições internas são:

- Código SWIFT
- Número do Cartão de Crédito
- Número do banco ABA
- SSN (Número do Seguro Social dos EUA)
- IBAN (Número de Conta Bancária Internacional)

Leia [Informações sobre as condições internas](/information-protection/deploy-use/configure-policy-classification.md#information-about-the-built-in-conditions) para obter mais detalhes sobre esse tipo de implementação.



<!--HONumber=Jan17_HO4-->


