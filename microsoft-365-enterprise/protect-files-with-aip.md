---
title: "Proteger arquivos do SharePoint Online com a Proteção de Informações do Azure | Microsoft Docs"
description: "Aplique a Proteção de Informações do Azure para proteger arquivos em um site de equipe do SharePoint Online altamente confidencial."
services: active-directory
keywords: Office 365, Windows 10, Enterprise Mobility and Security, Microsoft 365 Enterprise
documentationcenter: 
author: JoeDavies-MSFT
manager: laurawi
ms.assetid: 
ms.prod: microsoft-365-enterprise
ms.service: 
ms.workload: 
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 11/15/2017
ms.author: josephd
ms.openlocfilehash: ec88a40392e8bc530a40c35a1d8dadd1be8eb4f3
ms.sourcegitcommit: 684c942047754e93378e271f5b1a659a9752f0ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="protect-files-with--azure-information-protection"></a>Proteger arquivos com a Proteção de Informações do Azure

## <a name="introduction"></a>Introdução

Use as etapas neste artigo para configurar a AIP (Proteção de Informações do Azure) para fornecer a criptografia e as permissões para arquivos em um site de equipe do SharePoint Online altamente confidencial. 

A proteção de criptografia e permissões viaja com um arquivo, mesmo quando ele é baixado do site. Para obter mais informações sobre sites de equipe do SharePoint Online altamente confidenciais, consulte [Arquivos e sites do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md).

> [!NOTE]
> Quando a criptografia da Proteção de Informações do Azure é aplicada aos arquivos armazenados no Office 365, o serviço não pode processar o conteúdo desses arquivos. Coautoria, descoberta eletrônica, pesquisa, Delve e outros recursos de colaboração não funcionam. Políticas DLP só funcionam com metadados (incluindo rótulos do Office 365), mas não com o conteúdo desses arquivos (como números de cartão de crédito em arquivos).

## <a name="configure-azure-information-protection"></a>Configurar a Proteção de Informações do Azure

Primeiro, siga as instruções em [Ativar o Azure RMS com o centro de administração do Office 365 para sua assinatura do Office 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).

Em seguida, configure a Proteção de Informações do Azure com uma nova política e sub-rótulo em escopo para proteção e permissões do site de equipe altamente confidencial do SharePoint Online, seguindo estas etapas:

1. Entre no **Portal do Office 365** com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Em uma guia separada no navegador, vá até o Portal do Azure ([https://portal.azure.com](https://portal.azure.com/)).
3. Se esta é a primeira vez que configura a Proteção de Informações do Azure, consulte [estas instruções](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).
4. No painel de lista, clique em **Mais serviços**, digite **informações** e clique em **Proteção de Informações do Azure**.
5. Na folha **Proteção de Informações do Azure**, clique em **Políticas no escopo > + Adicionar uma nova política**.
6. Digite um nome para a nova política no **Nome da política** e uma descrição em **Descrição**.
7. Clique em **Selecionar quais usuários ou grupos obtêm esta política > Usuário/ Grupos**, e selecione o grupo de acesso dos membros do site para o site da equipe do SharePoint Online altamente confidencial.
8. Clique em **Selecionar > OK**.
9. Para o rótulo **Altamente Confidencial**, clique nas reticências (...) e, em seguida, clique em **Adicionar um sub-rótulo**.
10. Digite um nome para o subrótulo em **Nome** e uma descrição do rótulo em **Descrição**.
11. Em **Definir permissões para documentos e emails que contenham este rótulo**, clique em **Proteger**.
12. Na seção **Proteção**, clique em **Azure (chave de nuvem)**.
13. Na folha **Proteção**, em **Configurações de proteção**, clique em **+ Adicionar permissões**.
14. Na folha **Adicionar permissões**, em **Especificar usuários e grupos**, clique em **+ Procurar no diretório**.
15. No painel **Usuários e Grupos do AAD**, selecione o grupo de acesso de membros do site para seu site de equipe do SharePoint Online altamente confidencial e clique em **Selecionar**.
16. Em **Escolher permissões da predefinição**, desmarque as caixas de seleção **Imprimir, copiar e extrair conteúdo** e **Encaminhar**.
17. Clique em **OK** duas vezes.
18. Na folha **Sub-rótulo**, configure as marcações visuais conforme necessário e clique em**Salvar**.
19. Feche a nova folha de política em escopo.
20. Na folha **Proteção de Informações do Azure – Políticas em escopo**, clique em **Publicar** e depois em **Sim**.

Aqui está a configuração resultante para seu site de equipe do SharePoint Online altamente confidencial.

 ![Altamente Confidencial](./media/protect-files-with-aip/hc_w_aip.png)

Agora você está pronto para começar a criar documentos e protegê-los com a Proteção de Informações do Azure e seu novo rótulo.

Você deve [instalar o cliente da Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/install-client-app) em seu dispositivo ou computador baseado no Windows. Você pode criar scripts e automatizar a instalação, ou os usuários podem instalar o cliente manualmente. 

Para obter mais informações, consulte os seguintes recursos:

* [O lado do cliente da Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/use-client)
* [Instalando o cliente da Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
* [Página de download para a instalação manual](https://www.microsoft.com/download/details.aspx?id=53018)

Uma vez instalado, os usuários executam e entram de um aplicativo do Office (como o Microsoft Word) com sua conta do Office 365. Uma nova barra **Proteção de Informações** permite que você selecione o rótulo. 

Verifique se todos os usuários conhecem o site de equipe do SharePoint Online e qual rótulo usar para proteger seus arquivos altamente confidenciais.

>[!Note]
>Se houver vários sites de equipe do SharePoint Online altamente confidenciais, crie várias políticas de escopo de Proteção de Informações do Azure com sub-rótulos com as configurações acima, com as permissões para cada sub-rótulo definidas para o grupo de acesso de membros do site, de um site específico de equipe do SharePoint Online.
>

## <a name="next-steps"></a>Próximas etapas

[Adoção da nuvem e soluções híbridas](https://technet.microsoft.com/library/dn262744.aspx)
