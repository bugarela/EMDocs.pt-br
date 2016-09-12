---
title: Acesso condicional- Exchange local, Intune, Configuration Manager
description: "Use o Gerenciador de Configuração, o Exchange Server local e o Intune para gerenciar o acesso ao email e proteger dados de email em dispositivos móveis."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56b6cd2d-3dea-468b-9f1c-92717c9ec5f5
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: faa30f461ff9a1a14d150bd85d86d37cd298570c
ms.openlocfilehash: 1fbda5ec4bf589dc888d4b63a6b5da659e8d1c17


---

# Implantar o Exchange Server local com o Microsoft Intune e o Configuration Manager
Agora que você leu as [diretrizes de arquitetura para proteger emails e documentos da empresa](architecture-guidance-for-protecting-company-email-and-documents.md), está pronto para prosseguir com a implantação de uma solução.

Se já estiver usando o System Center Configuration Manager e o Exchange em sua infraestrutura local, você pode incorporar o Intune para gerenciar o acesso ao email e proteger os dados de email em dispositivos móveis. O processo de alto nível para implementar esta solução é o seguinte:

-   Configure o Intune Exchange Connector local por meio do console do Configuration Manager, o que permitirá que o Configuration Manager se comunique com o Exchange Server que hospeda as caixas de correio dos dispositivos móveis.

-   Execute uma sincronização completa do Exchange Server Connector para descobrir os usuários e todos as EASIDs (IDs do Exchange ActiveSync) de todos os dispositivos móveis que estão se conectando ao servidor do Exchange local.

-   Crie coleções de usuários para grupos de usuários que serão alvo ou ficarão isentos da política de acesso condicional. Em seguida, crie políticas de conformidade que definem as regras e configurações às quais um dispositivo deve obedecer para ser considerado compatível pelas políticas de acesso condicional.

-   Comece impondo o acesso condicional.

## Fluxo de controle de acesso condicional para o Exchange Server local
Este diagrama mostra o fluxo de controle para clientes que tentam acessar o email no Exchange local.

![Diagrama de fluxo de controle de acesso condicional do fluxo de controle no Configuration Manager com o Intune e o Exchange Server local](./media/ProtectEmail/Hybrid-on-prem-CA-architecture.png)

-   Microsoft Intune: gerencia a conformidade e políticas de acesso condicional para o dispositivo

-   Active Directory do Microsoft Azure: autentica o usuário e fornece o status de conformidade do dispositivo

-   Configuration Manager: gerencia o registro do dispositivo e fornece relatórios

-   Exchange local: impõe o acesso ao email com base no estado do dispositivo

## Antes de começar
Verifique se seu ambiente inclui esses requisitos para implementação dessa solução.

> [!NOTE]
> Se você já tiver configurado o Configuration Manager para gerenciar dispositivos móveis por meio do serviço do Intune, prossiga para a [Etapas de implantação](#deployment-steps).

-   Verifique se você atende aos [requisitos de hardware para o conector local](/intune/get-started/network-infrastructure-requirements-for-microsoft-intune).

-   Verifique se você está executando o System Center 2012 R2 Configuration Manager SP1 com atualização cumulativa 1 ou posterior.

-   Verifique se o [ponto de extremidade do EWS (Serviços Web do Exchange) ](https://technet.microsoft.com/library/hh529912.aspx)está configurado corretamente para descoberta. Se necessário, entre em contato com a equipe de suporte do Configuration Manager para conseguir uma ferramenta que pode ajudar a identificar problemas de conexão do EWS. O EWS permite aos desenvolvedores interagir com as caixas de correio e conteúdo do Exchange usando HTTP padrão.

-   Instale e atribua os serviços do Exchange a um [certificado digital válido ](https://technet.microsoft.com/library/dd351044.aspx) adquirido de uma autoridade de certificação pública confiável.

-   Configure uma conta (administração local ou de domínio) com permissões para executar os seguintes cmdlets do Exchange Server:

    Clear-ActiveSyncDevice

    Get-ActiveSyncDevice

    Get-ActiveSyncDeviceAccessRule

    Get-ActiveSyncDeviceStatistics

    Get-ActiveSyncMailboxPolicy

    Get-ActiveSyncOrganizationSettings

    Get-ExchangeServer

    Get-Recipient

    Set-ADServerSettings

    Set-ActiveSyncDeviceAccessRule

    Set-ActiveSyncMailboxPolicy

    Set-CASMailbox

    New-ActiveSyncDeviceAccessRule

    New-ActiveSyncMailboxPolicy

    Remove-ActiveSyncDevice

> [!IMPORTANT]
> Ao tentar instalar ou usar o conector do Exchange Server sem os cmdlets necessários, você verá um erro registrado com a mensagem: _Falha ao invocar o cmdlet &lt;cmdlet&gt; no arquivo EasDisc.log no computador do servidor do site_.

## Etapas de Implantação
Siga estas etapas para implantar a solução do Exchange local:

### Etapa 1: verificar se a função do Conector do Intune está instalada.
Certifique-se de que a função do Conector do Intune esteja instalada para que o Configuration Manager possa interagir com o Intune. Consulte [Gerenciar Dispositivos Móveis com o Configuration Manager e o Intune](https://technet.microsoft.com/library/JJ884158.aspx) para obter mais informações.

### Etapa 2: instalar e configurar um conector do Exchange Server.
O Configuration Manager dá suporte apenas a um conector em uma organização do Exchange.

> [!IMPORTANT]
> Antes de instalar o conector do Exchange Server, verifique se o Configuration Manager dá suporte à versão do Microsoft Exchange que você está usando. Para obter mais informações, consulte [Configurações com suporte no Configuration Manager](https://technet.microsoft.com/library/gg682077.aspx).

Siga as etapas em [Como gerenciar dispositivos móveis usando o Configuration Manager e o Exchange](https://technet.microsoft.com/library/gg682001.aspx) para instalar e configurar o conector do Exchange Server.

### Etapa 3: executar uma sincronização completa para descobrir os usuários.

1.  No console do Configuration Manager, clique em **Administração**, expanda **Configuração de Hierarquia**e selecione **Conectores do Exchange Server**.

2.  Selecione o Conector do Exchange Server que você instalou na etapa 2.

3.  Clique em **Sincronizar Agora**.

    ![Captura de tela que mostra onde executar uma sincronização completa no console do Configuration Manager](./media/ProtectEmail/Hybrid-Onprem-Run-FullSync.png)

Essa sincronização completa pode levar várias horas para ser concluída, dependendo do número de dispositivos. Uma sincronização completa será executado uma vez a cada 24 horas por padrão. Uma sincronização delta descobre as conexões de dispositivo desde a sincronização completa anterior e ocorre em intervalos definidos durante a instalação do Conector do Exchange Server. Isso garante que os novos usuários e novos usuários do Exchange sejam descobertos rapidamente para que o acesso condicional possa ser aplicado.

Usando a Ferramenta de Log de Rastreamento do Configuration Manager, você pode abrir o arquivo EasDisc.log (localizado na pasta **Microsoft Configuration Manager/Logs** em que você instalou o Configuration Manager) para verificar se o conector está em execução e consultando as conexões de dispositivo. Após a sincronização completa ser concluída, ela fará um inventário todas as EASIDs (IDs do Exchange ActiveSync) de dispositivos móveis que estão se conectando ao Exchange local.

### Etapa 4: criar coleções de usuários.
Determine os grupos de usuários do Intune aos quais a política de acesso condicional será aplicada. Em seguida, crie coleções de usuários para grupos de usuários que serão alvo ou ficarão isentos da política de acesso condicional. Você especificará esses grupos ao importo acesso condicional posteriormente.

Siga as etapas em [Como criar coleções no Configuration Manager](https://technet.microsoft.com/library/gg712295.aspx) para criar coleções de usuários.

### Etapa 5: criar políticas de conformidade e implantá-las para os usuários.
As políticas de conformidade definem regras e configurações com que um dispositivo deve manter a conformidade para ser considerado compatível pelas políticas de acesso condicional. Siga as etapas em [Políticas de conformidade no Configuration Manager](https://technet.microsoft.com/library/mt131417.aspx) para criar políticas de conformidade.

Se você desejar poder remover todos os email corporativo de um dispositivo iOS depois que ele não fizer mais parte da sua empresa, será necessário criar e implantar um perfil de email e, em seguida, definir a política de conformidade que especifica que perfis de email são gerenciados pelo Intune. Você deve implantar o perfil de email para o mesmo conjunto de usuários-alvos desta política de conformidade.

![Captura de tela que mostra a página "Regras" do Assistente para Criar Política de Conformidade, onde é possível especificar que um perfil de email deve ser gerenciado pelo Intune](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

Se você especificar essa política de conformidade, um usuário que já tenha configurado a conta de email deverá removê-la manualmente e, em seguida, o Intune a adicionará novamente por meio do processo de registro descrito em [Experiência de usuário final do acesso condicional](end-user-experience-conditional-access.md).

Depois que a política de conformidade for criada, selecione o nome da política de conformidade na lista e clique em **Implantar**.

### Etapa 6: configurar a política de acesso condicional.
Decida primeiro como e quando você deseja impor o acesso condicional e os funcionários que serão afetados. Em seguida, siga as etapas em [Acesso Condicional para Email do Exchange no Configuration Manager](https://technet.microsoft.com/library/mt131421.aspx) para configurar a política de acesso condicional para o Exchange local.

### Etapa 7: monitorar registros e impor o acesso condicional.
Se você já tiver um número significativo de usuários registrados e compatíveis no Intune, comece a impor o acesso condicional disponibilizando-o para aproximadamente 500 usuários por dia. Isso levará cerca de quatro a cinco meses para 70.000 usuários e permite tratar problemas que podem surgir sem restringir o acesso ao email para muitos usuários ao mesmo tempo.

Se você não tiver um grande número de usuários já registrados no Intune, o acesso condicional fornecerá a eles uma experiência guiada para o registro, conforme descrito em [Experiência de acesso condicional do usuário final](end-user-experience-conditional-access.md).

## Etapas de Verificação
Usando a Ferramenta de Log de Rastreamento do Configuration Manager, abra o arquivo EasDisc.log (localizado na pasta Microsoft Configuration Manager/Logs em que você instalou o Configuration Manager). Procure no arquivo de log por "Exchange Connector" para encontrar informações sobre se o Exchange Connector está em execução e quantos dispositivos estão conectados.

![Captura de tela que mostra o arquivo EasDisc.log aberto na Ferramenta de Log de Rastreamento do Configuration Manager](./media/ProtectEmail/Hybrid-Onprem-Eas-DiscLog-Sample.PNG)

A Ferramenta de Log de Rastreamento do Configuration Manager está incluída no [Kit de Ferramentas do System Center 2012 R2 Configuration Manager](http://www.microsoft.com/download/details.aspx?id=50012).

## Relatórios
Você pode usar o console do Configuration Manager para exibir informações específicas sobre os dispositivos que foram descobertos pelo Exchange Connector. Para os dispositivos nos quais o acesso condicional é imposto, você pode exibir o status atual de cada dispositivo, a última vez que o dispositivo esteve conectado ao Exchange Server e assim por diante.

No console do Configuration Manager, clique em **Ativos e Conformidade** e em **Dispositivos**. Você pode exibir o status atual de cada dispositivo (Bloqueado ou Permitido) na coluna **Estado de Acesso ao Exchange** . Adicione esta coluna se ela ainda não for exibida clicando na área de barra de título da coluna. Você também pode exibir o último momento de sincronização bem-sucedida para cada dispositivo, conforme relatado pelo Exchange, adicionando a coluna **Momento da última sincronização bem-sucedida com o Exchange Server** .

![Captura de tela que mostra uma lista de dispositivos no console do Configuration Manager](./media/ProtectEmail/Hybrid-Onprem-Verify-Devices-State.png)

Se você estiver executando o SSRS (SQL Server Reporting Services), você pode exibir um relatório de acesso condicional que mostra o estado de conformidade dos dispositivos, se houver um conector do Exchange instalado e em execução, além do estado de acesso do EAS. Ele também fornecerá informações sobre o registro do Active Directory, ativação de EAS, bem como sobre o proprietário do dispositivo.

![Captura de tela que mostra o exemplo de um relatório do SQL Server Reporting Services](./media/ProtectEmail/Hybrid-Reports-CA.png)

Para exibir relatórios do SSRS, você deve ter uma função de relatórios instalada no servidor primário:

1.  No Configuration Manager, clique em **Administração**, **Configuração de Hierarquia**, **Configuração do Site**e em **Servidores e Funções de Sistema de Site**.

2.  Selecione um servidor e clique em **Adicionar Função de Sistema de Site** para abrir o assistente Adicionar Função de Sistema de Site.

3.  Na página de Seleção de Função do Sistema, marque a caixa de seleção **Ponto do Reporting Services** . O ponto do Reporting Services exibe relatórios relacionados ao gerenciamento de clientes.

4.  Clique em **Avançar**.

O exemplo a seguir mostra o status da implantação da política de configuração:

![Captura de tela que mostra o status de implantação da política de configuração](./media/ProtectEmail/Hybrid-Reports-Deployment-Status.png)

### Latência
Um dispositivo é bloqueado assim que é descoberto pelo conector do Exchange. A latência de bloqueio depende de intervalos configurados para sincronização Completa e sincronização delta e o tempo entre esses intervalos quando o dispositivo se conecta ao servidor do Exchange. Por padrão, uma sincronização Completa ocorre a cada 24 horas enquanto uma sincronização delta a cada 240 minutos. Durante esse período de latência, um dispositivo pode ser considerado compatível.

## Onde ir daqui
Depois de implantar uma solução para proteger email corporativo e dados de email em dispositivos móveis, você poderá aprender mais sobre a [experiência de acesso condicional do usuário final](end-user-experience-conditional-access.md). Isso ajudará a preparar você para problemas que possam surgir quando os usuários finais registrarem seus dispositivos específicos.



<!--HONumber=Sep16_HO1-->


