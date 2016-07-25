---
title: Usar acesso condicional com o Exchange Online, Microsoft Intune e Configuration Manager
description: "Use o Gerenciador de Configuração, o Exchange Online e o Intune para gerenciar o acesso ao email e proteger dados de email em dispositivos móveis."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 06921361-9475-46e6-9368-3cc44c84b22f
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7c389de59d0ca6b33fbd4d872cb77236930d55bf
ms.openlocfilehash: e87f189128279a2f12da202dd0b9022a967fc5c2


---

# Implantar o Exchange Online com o Microsoft Intune e o Configuration Manager
Agora que você leu as [diretrizes de arquitetura para proteger emails e documentos da empresa](architecture-guidance-for-protecting-company-email-and-documents.md), está pronto para prosseguir com a implantação de uma solução.

Se já estiver usando o System Center Configuration Manager e o Exchange Online, você pode incorporar o Intune para gerenciar o acesso ao email e proteger os dados de email em dispositivos móveis. O processo de alto nível para implementar esta solução é o seguinte:

-   Crie políticas de conformidade que definem as regras e configurações às quais um dispositivo deve obedecer para ser considerado compatível pelas políticas de acesso condicional.

-   Comece impondo o acesso condicional.

-   Outra opção é configurar o conector do Exchange Server para Exchange Online. Este conector é necessário apenas para fins de relatório. Ele não é necessário para habilitar o acesso condicional.

## Fluxo de controle de acesso condicional para o Exchange Online
Este diagrama mostra o fluxo de controle para clientes que tentam acessar o email no Exchange Online. A e B podem ser realizados antes da imposição de acesso condicional.

![Diagrama de fluxo de controle de acesso condicional no Configuration Manager com o Intune e o Exchange Online](./media/ProtectEmail/Hybrid-Exchange-Online-CA-architecture.png)

-   Microsoft Intune: gerencia a conformidade e políticas de acesso condicional para o dispositivo

-   Active Directory do Microsoft Azure: autentica o usuário e fornece o status de conformidade do dispositivo

-   Configuration Manager: gerencia o registro do dispositivo e fornece relatórios, se habilitado

-   Exchange Online: impõe o acesso ao email com base no estado do dispositivo

## Antes de começar
Verifique se seu ambiente inclui esses requisitos para implementação dessa solução.

-   Instale e atribua os serviços do Exchange a um [certificado digital válido ](https://technet.microsoft.com/library/dd351044.aspx) adquirido de uma autoridade de certificação pública confiável.

-   Verifique se você está executando o System Center 2012 R2 Configuration Manager SP1 com atualização cumulativa 1 ou posterior.

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

## Etapas de Implantação
Siga estas etapas para implantar a solução do Exchange Online:

### Etapa 1: criar políticas de conformidade e implantá-las para os usuários.
As políticas de conformidade definem regras e configurações com que um dispositivo deve manter a conformidade para ser considerado compatível pelas políticas de acesso condicional. Siga as etapas em [Políticas de conformidade no Configuration Manager](https://technet.microsoft.com/en-us/library/mt131417.aspx) para criar políticas de conformidade.

Se você desejar poder remover todos os email corporativo de um dispositivo iOS depois que ele não fizer mais parte da sua empresa, será necessário criar e implantar um perfil de email e, em seguida, definir a política de conformidade que especifica que perfis de email são gerenciados pelo Intune. Você deve implantar o perfil de email para o mesmo conjunto de usuários-alvos desta política de conformidade.

![Captura de tela que mostra a página "Regras" do Assistente para Criar Política de Conformidade, onde é possível especificar que um perfil de email deve ser gerenciado pelo Intune](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

Se você especificar essa política de conformidade, um usuário que já tenha configurado a conta de email deverá removê-la manualmente e, em seguida, o Intune a adicionará novamente por meio do processo de registro descrito em [Experiência de usuário final do acesso condicional](end-user-experience-conditional-access.md).

Depois que a política de conformidade for criada, selecione o nome da política de conformidade na lista e clique em **Implantar**.

### Etapa 2: configurar a política de acesso condicional.
Decida primeiro como e quando você deseja impor o acesso condicional e os funcionários que serão afetados. Em seguida, siga as etapas em [Acesso Condicional para Email do Exchange no Configuration Manager](https://technet.microsoft.com/en-us/library/mt131421.aspx) para habilitar a política de acesso condicional para o Exchange Online.

> [!NOTE]
> A política de acesso condicional deve ser configurada no console do Intune. As etapas começam acessando o console do Intune por meio do Configuration Manager. Se solicitado, faça logon usando as mesmas credenciais que foram usadas para configurar o conector entre o Intune e o Configuration Manager.

### Etapa 3: (*opcional*) instalar e configurar um conector do Exchange Server.
O Configuration Manager dá suporte apenas a um conector em uma organização do Exchange.

> [!IMPORTANT]
> Antes de instalar o conector do Exchange Server, verifique se o Configuration Manager dá suporte à versão do Microsoft Exchange que você está usando. Para obter mais informações, consulte [Configurações com suporte no Configuration Manager](https://technet.microsoft.com/en-us/library/gg682077.aspx).

Siga as etapas em [como gerenciar dispositivos móveis usando o Configuration Manager e o Exchange](https://technet.microsoft.com/en-us/library/gg682001.aspx) para instalar e configurar o conector do Exchange Server.

## Etapas de Verificação
Se você configurou o conector do Exchange Server opcional para esta solução, poderá usar a Ferramenta de Log de Rastreamento do Configuration Manager para abrir o arquivo EasDisc.log (localizado na pasta Microsoft Configuration Manager/Logs em que você instalou o Configuration Manager). Procure no arquivo de log por "Exchange Connector" para encontrar informações sobre se o Exchange Connector está em execução e quantos dispositivos estão conectados.

![Captura de tela que mostra o arquivo EasDisc.log aberto na Ferramenta de Log de Rastreamento do Configuration Manager](./media/ProtectEmail/Hybrid-Onprem-Eas-DiscLog-Sample.PNG)

A Ferramenta de Log de Rastreamento do Configuration Manager está incluída no [Kit de Ferramentas do System Center 2012 R2 Configuration Manager](https://www.microsoft.com/en-us/download/details.aspx?id=50012).

## Relatórios
Se tiver configurado o conector do Exchange Server opcional, você poderá usar o conector console do Configuration Manager para exibir informações específicas sobre os dispositivos que foram descobertos pelo Exchange Connector. Para os dispositivos nos quais o acesso condicional é imposto, você pode exibir o status atual de cada dispositivo, a última vez que o dispositivo esteve conectado ao Exchange Server e assim por diante.

No console do Configuration Manager, clique em **Ativos e Conformidade** e em **Dispositivos**. Você pode exibir o status atual de cada dispositivo (Em quarentena ou Permitido) na coluna **Estado de Acesso ao Exchange** . Adicione esta coluna se ela ainda não for exibida clicando na área de barra de título da coluna. Você também pode exibir o último momento de sincronização bem-sucedida para cada dispositivo, conforme relatado pelo Exchange, adicionando a coluna **Momento da última sincronização bem-sucedida com o Exchange Server** .

![Captura de tela que mostra uma lista de dispositivos no console do Configuration Manager](./media/ProtectEmail/Hybrid-Onprem-Verify-Devices-State.png)

Se você estiver executando o SSRS (SQL Server Reporting Services), você pode exibir um relatório de acesso condicional que mostra o estado de conformidade dos dispositivos, se houver um conector do Exchange instalado e em execução, além do estado de acesso do EAS. Ele também fornecerá informações sobre o registro do Active Directory, ativação de EAS, bem como sobre o proprietário do dispositivo.

![Captura de tela que mostra o exemplo de um relatório do SQL Server Reporting Services](./media/ProtectEmail/Hybrid-Reports-CA.png)

Para exibir relatórios do SSRS, você deve ter uma função de relatórios instalada no servidor primário:

1.  No Configuration Manager, clique em **Administração &gt; Configuração da Hierarquia &gt; Configuração do Site &gt; Funções de Servidores e Sistema de Site**.

2.  Selecione um servidor e clique em **Adicionar Função de Sistema de Site** para abrir o assistente Adicionar Função de Sistema de Site.

3.  Na página de Seleção de Função do Sistema, marque a caixa de seleção **Ponto do Reporting Services** . O ponto do Reporting Services exibe relatórios relacionados ao gerenciamento de clientes.

4.  Clique em **Avançar**.

O exemplo a seguir mostra o status da implantação da política de configuração:

![Captura de tela que mostra o status de implantação da política de configuração](./media/ProtectEmail/Hybrid-Reports-Deployment-Status.png)

### Latência
Dispositivos que usam autenticação moderna têm acesso condicional aplicado imediatamente. Para dispositivos que se conectam por meio do protocolo EAS, pode haver um tempo de atraso de até seis horas para que acesso condicional seja imposto, com base na configuração padrão. Durante esse período, um dispositivo pode ser considerado compatível.

## Onde ir daqui
Depois de implantar uma solução para proteger email corporativo e dados de email em dispositivos móveis, você poderá aprender mais sobre a [experiência de acesso condicional do usuário final](end-user-experience-conditional-access.md). Isso ajudará a preparar você para problemas que possam surgir quando os usuários finais registrarem seus dispositivos específicos.



<!--HONumber=Jul16_HO3-->


