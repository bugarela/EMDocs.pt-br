---
title: Detectar ataques antes que causem danos | Microsoft Docs
description: "Um cenário que descreve como o Enterprise Mobility + Security pode ser usado para proteger dados corporativos contra ataques antes que causem danos, aproveitando a Análise avançada de ameaças , o Cloud App Security e o Active Directory Premium."
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 01/23/2017
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: de0a7e70-008b-45c1-bba8-f033b1f62194
ms.reviewer: v-craic
ms.suite: ems
ms.custom: advanced-threat-analytics, cloud-app-security
ms.openlocfilehash: 420df3bfcc0fca07bf4f7b068f4d49015ace048f
ms.sourcegitcommit: 0541e4aa400a818551469fe9df8929c25c2dd918
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/25/2017
---
# <a name="detect-attacks-before-they-cause-damage"></a>Detectar ataques antes que causem danos
Uma postura de segurança forte requer um sistema de detecção avançado em vigor para identificar ameaças antes que causem maiores danos. As organizações podem aproveitar facilmente a inteligência de segurança da Microsoft para detectar atividades suspeitas no local e na nuvem.

Um sistema de detecção de alta segurança deve revelar atividades suspeitas e identificar ameaças com visibilidade profunda e análise de comportamento contínua. Isso permite que a TI tome medidas imediatas contra ataques detectados e simplifique a recuperação com suporte robusto.


## <a name="how-can-enterprise-mobility--security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?
O Microsoft Enterprise Mobility + Security permite que a TI identifique invasores na organização usando análise comportamental inovadora e tecnologias de detecção de anomalias, no local e na nuvem.  Ele poderá ajudar a TI a detectar ataques maliciosos conhecidos e vulnerabilidades de segurança em seus sistemas.

## <a name="recommended-solution"></a>Solução recomendada
Para atender aos requisitos deste cenário, o EMS usa [Análise avançada de ameaças](https://docs.microsoft.com/en-us/advanced-threat-analytics/), [Cloud App Security](https://docs.microsoft.com/en-us/cloud-app-security/what-is-cloud-app-security) e [Azure Active Directory Premium](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-get-started-premium). Implementando essas tecnologias, as organizações poderão:

- Detectar ou identificar comportamento anormal usando análise comportamental inovadora e tecnologias de detecção de anomalias, aproveitando o aprendizado de máquina
- Detectar ataques mal-intencionados conhecidos (por exemplo, Pass the Hash, Pass the Ticket) e vulnerabilidades de segurança conhecidas
- Concentrar-se rapidamente no que é importante e em informações de ataque relevantes
- Identificar anomalias e violações de política que podem indicar uma violação de segurança

O diagrama a seguir resume as funcionalidades envolvidas neste cenário e como eles são usados para proteger seus recursos:

![Gráfico mostrando os recursos de cada solução de produto e como funcionam para proteger contra ataques.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig1.png)

# <a name="how-to-detect-attacks-before-they-cause-damage"></a>Como detectar ataques antes que causem danos
Tradicionalmente, os investimentos em segurança se concentravam apenas na proteção. No entanto, hoje em dia, é imperativo também ter boa detecção e resposta. As organizações de TI devem se concentrar em uma abordagem que busca proteger, detectar e responder a ameaças.

![Gráfico mostrando o processo contínuo de proteção, detecção e resposta a ameaças.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig2.png)

A TI deve analisar como proteger adequadamente identidade, dados, aplicativos, dispositivos e infraestrutura – no local ou na nuvem.  Isso exige uma abordagem de segurança que considera todos os seus pontos de extremidade, dos sensores ao datacenter. No passado, os administradores de TI contavam com as assinaturas de malware para reconhecer ameaças.

Ferramentas de segurança de TI tradicionais fornecem proteção limitada contra ataques sofisticados de segurança cibernética quando as credenciais do usuário são roubadas. Instalação inicial, criação de regras e ajuste são trabalhosos e podem levar anos. Todos os dias, você recebe vários relatórios cheios de falsos positivos. Na maioria das vezes, você não tem os recursos para analisar essas informações e mesmo se pudesse, talvez ainda não tenha as respostas, já que essas ferramentas foram projetadas para proteger o perímetro, interrompendo principalmente o acesso de invasores. Os complexos ataques de segurança cibernética atuais exigem uma abordagem diferente.

Para atenuar ameaças atuais nesse novo panorama de ataques de segurança cibernética, a TI precisa de soluções de detecção de ameaça inovadoras que aproveitem as funções analíticas comportamentais e as tecnologias de aprendizagem para reconhecer rapidamente novas ameaças.  Ao aproveitar o ATA e o Cloud App Security para detectar ataques locais e na nuvem, a TI pode responder rapidamente a incidentes antes que causem danos maiores no ambiente.

Leia o [Planejamento de capacidade do ATA](https://docs.microsoft.com/en-us/advanced-threat-analytics/plan-design/ata-capacity-planning) antes de implementá-lo no local e também os [pré-requisitos do ATA](https://docs.microsoft.com/en-us/advanced-threat-analytics/plan-design/ata-prerequisites), para considerações gerais antes de instalá-lo. Use a [lista de verificação de pré-instalação](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/preinstall-ata) para validar se a infraestrutura está pronta para receber o ATA. Depois de concluir essa fase de planejamento e validação, você estará pronto para [implantar o ATA](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/install-ata-step1). Quando o ATA é implantado no seu ambiente, a configuração é mínima e ele imediatamente começará a aprender sobre seu ambiente e a disparar alertas, se encontrar ataques mal-intencionados conhecidos. Siga a etapa 1 para usar o [ATA](https://docs.microsoft.com/en-us/advanced-threat-analytics/understand-explore/what-is-ata) a fim de identificar atividades suspeitas no local.

Para detectar ameaças em aplicativos na nuvem, esse cenário usa o [Cloud App Security](https://docs.microsoft.com/en-us/cloud-app-security/what-is-cloud-app-security). Certifique-se de seguir as [instruções gerais de instalação](https://docs.microsoft.com/en-us/cloud-app-security/general-setup) para configurar o Cloud App Security e usar a opção [Cloud Discovery](https://docs.microsoft.com/en-us/cloud-app-security/set-up-cloud-discovery) para analisar os logs de tráfego no catálogo de aplicativos de nuvem do Cloud App Security. Siga a etapa 2 para usar o Cloud App Security para detectar ameaças e violações de conformidade.

## <a name="how-to-implement-this-solution"></a>Como implementar esta solução
Siga estas etapas para implementar [Análise avançada de ameaças](https://docs.microsoft.com/en-us/advanced-threat-analytics/) e o [Cloud App Security](https://docs.microsoft.com/en-us/cloud-app-security/what-is-cloud-app-security):

- Etapa 1: Use o ATA (Análise Avançada de Ameaças) para detectar atividade suspeita no local
- Etapa 2: Use o Cloud App Security para detectar ameaças e violações de conformidade em aplicativos na nuvem  

### <a name="step-1-using-ata-to-detect-suspicious-activity"></a>Etapa 1: Usando o ATA para detectar atividades suspeitas
Os relatórios constantes de ferramentas de segurança tradicionais e sua análise para localizar alertas relevantes e importantes pode ser sobrepujante. Em vez disso, o ATA fornece relatórios semelhantes a feeds de mídia social fáceis de consumir e simples de detalhar, ajudando a TI a se concentrar no que é mais importante. Apresentar essa quantidade de dados como uma linha do tempo fornece a capacidade de perspectiva e insight sobre quem está acessando o quê, quando estão acessando e como estão acessando os dados.

Quando você abre o [a linha do tempo de ataques](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/working-with-suspicious-activities) no ATA, vê um relatório abrangente com atividades suspeitas mostrando o [entidades](https://docs.microsoft.com/en-us/advanced-threat-analytics/plan-design/ata-architecture) envolvidas nessa atividade e quais são as recomendações:

![Captura de tela da linha do tempo do ataque com um relatório de atividades suspeitas.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig3.png)

Neste exemplo, há exemplo indicando suspeita de roubo de identidade, usando ataques pass-the-ticket. Você também tem uma lista de recomendações que pode ser usada para etapas de correção iniciais. Neste exemplo, o ATA forneceu um alerta quando o tíquete Kerberos do administrador foi roubado do servidor SHAREDADMIN-SRV para EXTVENDOR-TS e usou o acesso DC01. Você pode ir além em seu processo de investigação clicando em qualquer objeto nesse evento. Por exemplo, ao clicar no servidor Host da Sessão da Área de Trabalho Remota (EXTVENDOR-TS) do fornecedor externo, você terá acesso a todas as [atividades suspeitas](https://docs.microsoft.com/en-us/advanced-threat-analytics/deploy-use/working-with-suspicious-activities) nas quais esse servidor esteve envolvido.

O ATA usa o aprendizado de máquina em seus mecanismos de determinação e detecção para estabelecer um entendimento dos padrões de comportamento normal de usuários e entidades, e é esse recurso exclusivo que nos permite fornecer alertas oportunos e precisos em uma grande variedade de vetores de ataque.


### <a name="step-2-using-cloud-app-security-to-detect-threats-and-policy-violations-for-cloud-apps"></a>Etapa 2: Usando o Cloud App Security para detectar ameaças e violações à política em aplicativos na nuvem

Cada vez mais as empresas estão adotando aplicativos SaaS, não apenas para reduzir custos, mas também para revelar vantagens competitivas, como tempo de lançamento no mercado e melhor colaboração. Mesmo que sua empresa não use aplicativos na nuvem, seus funcionários provavelmente usam. De acordo com a pesquisa, mais de 80 por cento dos funcionários admitem usar aplicativos SaaS não aprovados em seus trabalhos.

Com essa transição rápida para aplicativos na nuvem, sabemos que você pode se preocupar sobre como armazenar dados corporativos na nuvem e como torná-lo acessível a usuários em qualquer lugar sem visibilidade, auditoria ou controles abrangentes. Soluções de segurança herdadas não foram projetadas para proteger dados em aplicativos SaaS. Soluções de segurança de rede tradicionais, como firewalls e IPS, não oferecem visibilidade das transações que são exclusivas de cada aplicativo e tráfego externo, incluindo como os dados são usados e armazenados. Controles clássicos não fornecem proteção para aplicativos de nuvem, já que monitoram apenas um pequeno subconjunto de tráfego de nuvem e têm compreensão limitada de atividades no nível de aplicativo.

Então, como manter a visibilidade, o controle e a proteção de seus aplicativos na nuvem? Temos a solução:

O Microsoft Cloud App Security é um serviço abrangente que fornece maior visibilidade, controles abrangentes e proteção aprimorada para seus aplicativos em nuvem. O Cloud App Security foi projetado para ajudá-lo a estender a visibilidade, a auditoria e os controle que você tem no local para seus aplicativos na nuvem.

O Cloud App Security fornece não só visibilidade e controle, mas também poderosa proteção contra ameaças para seus aplicativos de nuvem, aprimorado com vasta inteligência e pesquisa de ameaças da Microsoft. Você pode identificar incidentes de uso e segurança de alto risco e detectar comportamentos anormais do usuário para impedir ameaças.

Quando você acessa o painel do Cloud App Security, tem uma visão abrangente do estado de segurança dos aplicativos na nuvem, incluindo uma seção dedicada a alertas:

![Captura de tela do painel do Cloud App Security, incluindo alertas abertos.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig6.png)

Você pode clicar no menu Alertas para acessar a [central de alertas](https://docs.microsoft.com/en-us/cloud-app-security/monitor-alerts). A central de alertas reúne alertas de várias categorias, incluindo detecção de ameaças, contas privilegiadas e violações de conformidade.

![Captura de tela da central de alertas mostrando uma lista de cada alerta.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig5.png)

A central de alertas reúne todos os sinalizadores vermelhos identificados pelo Cloud App Security, incluindo detecção de ameaças e anomalias, violações de conformidade e contas privilegiadas. A heurística de aprendizagem avançada de máquina avançada do Cloud App Security aprende como cada usuário interage com cada aplicativo na nuvem e por meio de análise comportamental, avalia o risco em cada transação.

Ao investigar um alerta, clique no nome do alerta para obter mais informações sobre ele. No exemplo a seguir, o alerta se refere a uma correspondência na [política de arquivo](https://docs.microsoft.com/en-us/cloud-app-security/data-protection-policies) de *arquivos confidenciais compartilhados publicamente*, que é considerado de alta prioridade, já que pode levar a vazamento de dados.   

![Captura de tela de detalhes específicos de um dos alertas.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig7.png)

O exemplo anterior baseou-se em violação de política, mas o Cloud App Security também é capaz de [detectar anomalias](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy#anomaly-detection-policy-reference). O Cloud App Security tem um período inicial de assimilação de 7 dias, durante o qual ele não sinaliza nenhum novo usuários, atividade, dispositivos ou locais como anormais. Depois disso, cada sessão é comparada à atividade – quando os usuários estavam ativos, endereços IP, dispositivos, etc. – detectados ao longo do mês anterior e uma pontuação de risco é atribuída a essas atividades. A descrição para este tipo de alerta é chamada de Detecção de anomalias geral e quando você clicar nele, verá uma tela semelhante à seguinte:

![Captura de tela mostrando anomalias detectadas pelo Cloud App Security.](./media/detect-attacks-before-damage/detect-attacks-before-damage-fig8.png)

Nessa página, você pode ver que o usuário disparou o alerta, o endereço IP, a associação a um grupo do usuário e mais informações sobre o comportamento suspeito. Você pode exibir mais detalhes sobre essa atividade, que inclui tentativas de logon com falha, o local de origem do logon e o aplicativo usado para realizar a tentativa de logon.
