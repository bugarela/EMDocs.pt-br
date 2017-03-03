---
title: "Acompanhar o uso de dados compartilhados e responder a violações de dados | Microsoft Docs"
description: "Um cenário que descreve como o Enterprise Mobility + Security pode ser usado para controlar o uso de dados compartilhados e responder a violações de dados, aproveitando os recursos do Azure Rights Management."
author: yuridio
manager: swadhwa
ms.date: 02/23/2017
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c7e6e01a-5796-4bd7-a0c5-847ecfc08a1e
ms.reviewer: v-craic
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5d9a4bd18660a573b2dd76c0263b89ecf5ae4610
ms.openlocfilehash: cca39a029b31f619a49b605ed28ab73a58e5c73b



---

# <a name="track-usage-of-shared-data-and-respond-to-data-abuse"></a>Acompanhar o uso de dados compartilhados e responder a violações de dados

Ter visibilidade e controle sobre os dados compartilhados é essencial para acompanhar o uso ou violações de dados. Hoje em dia, o compartilhamento de dados é mais amplo e as organizações precisam compartilhar dados fora de seu domínio para atender às necessidades de negócios.

Nesse contexto, é um cenário comum para os usuários não só compartilhar documentos, mas também monitorar quem está acessando esses documentos e revogar o acesso quando necessário. Os administradores de TI querem ter uma experiência semelhante à que têm atualmente ao compartilhar dados com um grupo de usuários autorizados – querem manter o controle e tomar as medidas apropriadas quanto ao uso ou a violações de dados. Continue lendo para saber mais sobre como o Enterprise Mobility + Security ajuda a lidar com esse cenário.

## <a name="how-can-enterprise-mobility--security-help-you"></a>Como o Enterprise Mobility + Security pode ajudar você?
O EMS (Enterprise Mobility + Security) é a única solução de nuvem abrangente que protege dados corporativos no próprio dispositivo e além dele, com quatro camadas de proteção de identidades, dispositivos, aplicativos e dados. O EMS ajuda você a resolver um dos principais desafios em um mundo que prioriza a mobilidade e a nuvem – como compartilhar dados enquanto mantém o controle e toma medidas para responder rapidamente a algum problema. Com o EMS, você permitirá que seus funcionários colaborem com segurança dentro e fora da sua organização. O EMS permite que proprietários e administradores de documentos acompanhem atividades realizadas em arquivos confidenciais que eles compartilharam com outras pessoas. Eles podem exibir atividades como destinatários que abriram o documento ou usuários não autorizados que têm acesso negado aos arquivos. Os usuários também podem exibir as regiões geográficas de onde os arquivos foram acessados. Com um único clique, os usuários também podem revogar o acesso a um arquivo compartilhado.

### <a name="recommended-solution"></a>Solução recomendada
Integrando o Azure Rights Management, você pode controlar como as pessoas estão usando seus documentos protegidos. Se necessário, você também pode revogar acesso a estes documentos quando quiser parar de compartilhá-los. Essa capacidade está disponível para aplicativos do Office (Word, Excel, Outlook e PowerPoint), usando o grupo de RMS, a opção de Compartilhamento Protegido e Acompanhar Uso. Para sistemas Windows, você também pode usar o Explorador de Arquivos e, para todos os outros dispositivos com suporte, é possível acompanhar o uso usando o navegador da Web. O acompanhamento e a revogação fazem parte da fase de monitorar e responder do ciclo de vida do documento, conforme mostrado no diagrama a seguir:

![Gráfico mostrando o ciclo de vida do documento no Azure Rights Management.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig1.png)

Assista a este breve vídeo para obter uma introdução rápida de como a Proteção de Informações do Azure facilita o acompanhamento do uso do documento.

<iframe width="675" height="480" src="https://sec.ch9.ms/ch9/76ac/35499c0a-859c-4a3e-9a5c-fa4e5d0e76ac/AzureRMSDocumentTrackingandRevocation_high.mp4 " frameborder="0" allowfullscreen></iframe>

#### <a name="how-to-implement-this-solution"></a>Como implementar esta solução
Acompanhar o uso de dados compartilhados não é uma capacidade que você precisa configurar se já tiver usado as etapas do cenário [Compartilhar dados confidenciais internamente](https://docs.microsoft.com/enterprise-mobility-security/solutions/share-sensitive-data) e externamente para configurar o Azure Rights Management e o aplicativo cliente. Agora, basta escolher como você deseja acompanhar seus documentos. As opções disponíveis são:

1. Acompanhar o uso usando o Office
- Acompanhar o uso usando o navegador
- Revogar o acesso ao documento compartilhado

### <a name="how-to-track-usage-of-shared-data-and-respond-to-data-abuse"></a>Como acompanhar o uso de dados compartilhados e responder a violações de dados
Nas seções a seguir, você tem as opções disponíveis para acompanhar o uso de dados compartilhados de acordo com um cenário específico.

#### <a name="scenario-1-track-usage-using-microsoft-office"></a>Cenário 1: Acompanhar o uso usando o Microsoft Office
Para usuários que estão tentando para obter mais informações sobre o uso de documentos que foram protegidos com aplicativos do Office (Word, Excel e PowerPoint), eles podem usar o grupo do RMS, selecionar a opção **Compartilhamento Protegido** e, em seguida, clicar em **Acompanhar o Uso**, conforme mostrado na imagem a seguir:

![Gráfico mostrando como um usuário pode definir a opção "Acompanhar o Uso" em aplicativos do Office.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig2.png)

Leia [Track and revoke your documents when you use the RMS sharing application](https://docs.microsoft.com/information-protection/rms-client/sharing-app-track-revoke) (Rastrear e revogar seus documentos ao usar o aplicativo de compartilhamento do RMS) para obter mais informações sobre o recurso.

#### <a name="scenario-2-track-usage-using-browser"></a>Cenário 2: Acompanhar o uso usando o navegador
Em algumas circunstâncias, talvez você não tenha um aplicativo do Office instalado no dispositivo, mas ainda precisa monitorar o uso de documentos. De um [navegador com suporte](https://docs.microsoft.com/rights-management/rms-client/sharing-app-track-revoke), vá até o [site de acompanhamento de documentos](http://go.microsoft.com/fwlink/?LinkId=529562), entre com suas credenciais e, quando selecionar o documento que deseja acompanhar, você deverá ver as estatísticas de uso conforme mostrado na seguinte imagem:

![Gráfico mostrando as estatísticas de uso geral do documento em um navegador da Web.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig3.png)

Nessa tela, você pode ver o número exibições e o número de acessos negados no número de meses que o arquivo foi compartilhado. Embora cada bloco tenha um resumo mostrando os usuários que acessaram o arquivo, você pode obter mais informações quando clica no bloco. Para o exemplo na tela anterior, o seguinte resultado é mostrado ao selecionar o acesso negado:

![Gráfico mostrando as estatísticas de acesso negado de um documento em um navegador da Web.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig4.png)

#### <a name="scenario-3-revoke-access-to-shared-document"></a>Cenário 3: Revogar o acesso ao documento compartilhado

Ao monitorar o documento, o uso é uma etapa importante para entender o comportamento do usuário e o maior valor é fornecido quando você pode tomar medidas com base no que encontra enquanto monitora o documento. Por exemplo, após ler o relatório de uso você identificou que um usuário válido teve p acesso negado ao tentar acessar o documento. Neste ponto, você deve tomar uma medida corretiva para corrigir o problema.

Também há cenários em que você responde a um incidente de segurança. Por exemplo, foi identificado que um dos documentos que foi compartilhado amplamente contém informações confidenciais da empresa e o RH solicitou que o setor de TI revogasse o acesso a esse documento. Quando você [revoga um documento](https://docs.microsoft.com/rights-management/rms-client/sharing-app-track-revoke), o documento que você compartilhou não é excluído, mas usuários autorizados já não serão capazes de abri-lo. Para revogar o acesso, basta clicar em **Revogar Acesso**, localizado na página de acompanhamento do uso e você verá um formulário semelhante ao seguinte:

![Gráfico mostrando o formulário Revogar Acesso que permite revogar o acesso a um documento.](./media/infoprotect-track-usage-scenario/infoprotect-track-usage-scenario-fig5.png)

É possível habilitar a opção de notificar os destinatários de que o acesso ao documento foi revogado e você pode incluir uma mensagem com a explicação de por que o documento foi revogado.



<!--HONumber=Jan17_HO4-->


