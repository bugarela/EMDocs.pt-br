---
title: Compartilhar dados confidenciais interna e externamente | Microsoft Docs
description: "Um cenário que descreve como o Enterprise Mobility + Security pode ser usado para compartilhar dados confidenciais interna e externamente aproveitando os recursos da Proteção de Informações do Microsoft Azure."
author: yuridio
ms.author: yurid
manager: swadhwa
ms.date: 01/23/2017
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: a996fbf8-ece4-40bc-b866-d4606c230027
ms.reviewer: v-craic
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5d9a4bd18660a573b2dd76c0263b89ecf5ae4610
ms.openlocfilehash: 3d84bbe6d252976e1a3152f65003787e37d408c8


---

# <a name="share-sensitive-data-internally-and-externally"></a>Compartilhar dados confidenciais interna e externamente

Embora muitas violações de dados se devam a ataques cibernéticos, os especialistas concordam que muitas resultam do erro humano, que são os momentos de deslize que ocorrem quando os funcionários inadvertidamente vazam dados corporativos confidenciais. Com os protocolos certos de prevenção contra perda de dados e informações de segurança estabelecidos, quase todos esses tipos de violação podem ser evitados.

O compartilhamento de dados é algo inevitável para as empresas e os usuários e, embora isso seja necessário, ele também cria um dos maiores desafios do setor, que é: como permitir o compartilhamento de dados entre diferentes dispositivos e, ao mesmo tempo, reduzir o vazamento de dados compartilhados com outras pessoas? O panorama de ameaças é ainda mais amplo quando você precisa compartilhar dados confidenciais com fontes externas, como parceiros, clientes e outros participantes.

![Diagrama](./media/share-sensitive-data/share-sensitive-data-fig1.png)

Nesse contexto, um cenário comum nas empresas é ter projetos em que elas precisam permitir que os funcionários colaborem internamente entre silos de dados e externamente com fornecedores terceirizados e, ao mesmo tempo, alinhar protocolos de segurança com os negócios, bem como influenciar o comportamento do usuário final nos processos de proteção e classificação de dados.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?

O EMS (Enterprise Mobility + Security) é a única solução de nuvem abrangente que protege nativamente dados corporativos no próprio dispositivo e além dele, com quatro camadas de proteção de identidades, dispositivos, aplicativos e dados. O EMS ajuda a resolver um dos principais desafios do mundo concentrado em dispositivos móveis e na nuvem – como entregar emails seguros para funcionários em trânsito. Com o EMS, você permitirá que seus funcionários colaborem com segurança dentro e fora da sua organização. O EMS permite que os administradores de TI aproveitem o modelo de política do [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms) para uso de email. Os direitos de uso são anexados à mensagem em si para que a proteção ocorra online e offline, bem como dentro e fora do firewall da organização.

## <a name="recommended-solution"></a>Solução recomendada

Ao integrar o Azure Rights Management ao Rights Management no Exchange Online, o EMS permite às organizações proteger dados que saem da organização por email. Você pode implementar essa solução em Servidores Exchange no local e no Exchange Online (Office 365). Tanto o Gerenciamento de Direitos de Informação quanto a [Criptografia de Mensagens do Office 365](https://technet.microsoft.com/library/dn569285.aspx) se baseiam em política e foram criados para trabalhar com o mecanismo de regra de transporte do Exchange. Isso significa que o Microsoft Azure Rights Management permite configurar com facilidade restrições complexas de política, com apenas uma única ação.

Alguns dos recursos disponíveis com essas soluções são descritos abaixo:

- Ajuda a proteger emails contra acesso não autorizado aplicando diferentes opções de IRM às suas mensagens de email.
- Ajuda a manter suas informações em segurança, online ou offline, pois seus arquivos são protegidos, sejam eles exibidos usando o Office Online, sejam baixados em um computador local.
- A integração perfeita a todos os documentos do Office ajuda a proteger a propriedade intelectual da organização.
- Aplicação de modelos personalizados com base nas necessidades de negócios, além de uso dos modelos padrão dos Rights Management Services.


## <a name="how-to-implement-this-solution"></a>Como implementar esta solução

Para configurar o Exchange Online para suportar o Azure RMS, é necessário configurar o gerenciamento de direitos de informação (IRM) para o Exchange Online. Siga estas etapas para implementar essa solução:

1. Integração ao Exchange:
    - Exchange Online: habilitar o Exchange Online para usar o Azure RMS
    - Exchange no local: implantar o conector do Azure Rights Management
2. Enviar um documento do Office protegido usando o Exchange

## <a name="how-to-share-sensitive-data-internally-and-externally"></a>Como compartilhar dados confidenciais interna e externamente

As empresas precisam permitir que os funcionários colaborem internamente entre silos de dados e externamente com fornecedores terceirizados e, ao mesmo tempo, alinhar protocolos de segurança com os negócios, bem como influenciar o comportamento do usuário final nos processos de proteção e classificação de dados. O compartilhamento de dados torna-se uma parte essencial do processo que precisa ser permitido pelas organizações; ao mesmo tempo, elas precisam reduzir a probabilidade de comprometimento da integridade e privacidade dos dados.

### <a name="step-1-integration-with-exchange"></a>Etapa 1: Integração ao Exchange

A proteção do Rights Management é aplicada aos emails com um modelo de política do Azure Rights Management em uma mensagem de email. A primeira etapa para permitir essa integração varia de acordo com a localização do Exchange: na nuvem (Exchange Online) ou no local.

#### <a name="enable-rights-management-integration-with-exchange-online"></a>Habilitar a integração do Rights Management ao Exchange Online

Para configurar o Exchange Online para suportar o Azure RMS, é necessário configurar o gerenciamento de direitos de informação (IRM) para o Exchange Online. No artigo [Office 365: Configuração de clientes e serviços online](https://docs.microsoft.com/rights-management/deploy-use/configure-office365), siga as etapas da seção [Exchange Online: configuração do IRM](https://docs.microsoft.com/rights-management/deploy-use/configure-office365#exchange-online-irm-configuration) para configurar o Exchange Online para IRM.

A última etapa deve ser o teste final para validar a configuração, e você deverá ver um resultado semelhante ao mostrado na seguinte tela:

![PowerShell](./media/share-sensitive-data/share-sensitive-data-fig2.png)

#### <a name="enable-rights-management-integration-with-exchange-on-premises"></a>Habilitar a integração do Rights Management ao Exchange no local

Para configurar a integração do Rights Management ao Exchange no local, é preciso configurar o conector Microsoft RMS (Rights Management). Esse conector permitirá que os servidores Exchange existentes no local usem a respectiva funcionalidade IRM (Gerenciamento de Direitos de Informação) com o Azure RMS (Rights Management Service). Você pode usar este conector em um cenário híbrido, mesmo se alguns dos seus usuários estiverem se conectando a serviços online.

Examine os [pré-requisitos para instalar o Conector RMS](https://docs.microsoft.com/rights-management/deploy-use/deploy-rms-connector#prerequisites-for-the-rms-connector) e siga as cinco etapas disponíveis no artigo [Instalação e configuração do conector do Azure Rights Management](https://docs.microsoft.com/rights-management/deploy-use/install-configure-rms-connector).

### <a name="step-2-send-a-protected-document-using-exchange"></a>Etapa 2: Enviar um documento protegido usando o Exchange

Siga a Etapa 3 do cenário [Secure data using classification and labeling](infoprotect-secure-classify-scenario.md) (Proteger dados usando classificação e rotulagem) para instalar o aplicativo RMS Sharing. Se precisar dar suporte a diferentes tipos de cliente, leia o artigo [Aplicativo de compartilhamento do Rights Management: Instalação e configuração para clientes](https://docs.microsoft.com/rights-management/deploy-use/configure-sharing-app) para obter mais detalhes sobre como instalar o aplicativo RMS Sharing.

Se quiser compartilhar um documento do Office diretamente do Word, por exemplo, você poderá usar o ícone Compartilhamento Protegido na faixa de opções, conforme mostrado na imagem que se segue:

![ShareProtect](./media/share-sensitive-data/share-sensitive-data-fig3.png)

Depois de clicar nessa opção, você deverá ver a caixa de diálogo de compartilhamento protegido com mais detalhes sobre como deseja compartilhar esse documento, conforme mostrado na imagem a seguir:

![Compartilhar](./media/share-sensitive-data/share-sensitive-data-fig4.png)

Na parte superior dessa janela, é preciso digitar o email do usuário de destino e selecionar o tipo de acesso que quer fornecer a esse usuário. Na parte inferior dessa janela, também é possível controlar a data de validade do documento e habilitar a opção para receber um email toda vez que alguém tentar abrir esse documento. Após o término das seleções apropriadas, clique em Enviar, e o Outlook será aberto com uma nova mensagem, conforme mostrado na tela a seguir:

![Email](./media/share-sensitive-data/share-sensitive-data-fig5.png)

> [!IMPORTANT]
> Assista à apresentação [Collaborate securely using Azure Information Protection](https://myignite.microsoft.com/videos/49947) (Colaborar com segurança usando a Proteção de Informações do Azure) no Microsoft Ignite para obter mais informações sobre esse cenário.



<!--HONumber=Jan17_HO4-->


