---
title: "Proteger arquivos com a Proteção de Informações do Azure | Microsoft Docs"
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
ms.date: 08/28/2017
ms.author: josephd
ms.openlocfilehash: 34758e152a483a2bada03aeb4c4b5ee3327fb469
ms.sourcegitcommit: 5b34af60e3aac19d618f1c6297da91e2c050a374
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="protect-files-with--azure-information-protection"></a>Proteger arquivos com a Proteção de Informações do Azure

## <a name="introduction"></a>Introdução

Use as etapas neste artigo para configurar a AIP (Proteção de Informações do Azure) para fornecer a criptografia e as permissões para arquivos em um site de equipe do SharePoint Online altamente confidencial. 

A proteção de criptografia e permissões viaja com um arquivo, mesmo quando ele é baixado do site. Para obter mais informações sobre sites de equipe do SharePoint Online altamente confidenciais, consulte [Arquivos e sites do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md).

## <a name="configure-azure-information-protection"></a>Configurar a Proteção de Informações do Azure

Primeiro, siga as instruções em [Ativar o Azure RMS com o centro de administração do Office 365 para sua assinatura do Office 365](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).

Em seguida, configure o rótulo **AIP Altamente Confidencial** com proteção e permissões para o site de equipe do SharePoint Online altamente confidencial seguindo estas etapas:

1. Entre no **Portal do Office 365** com uma conta que tenha a função de Administrador de Segurança ou Administrador da Empresa. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
2. Em uma guia separada no navegador, vá até o Portal do Azure ([https://portal.azure.com](https://portal.azure.com/)).
3. No painel de lista, clique em **Mais serviços**, digite **informações** e clique em **Proteção de Informações do Azure**.
4. Na folha **Proteção de Informações do Azure – Política global**, sob a lista de rótulos, clique em **Altamente Confidencial**.
5. Na folha **Rótulo: Altamente Confidencial**, em **Definir permissões para documentos e emails contendo esse rótulo**, clique em **Proteger**.
6. Na seção **Proteção**, clique em **Azure RMS**.
7. Na folha **Proteção**, em **Configurações de proteção**, clique em **+ Adicionar permissões**.
8. Na folha **Adicionar permissões**, em **Especificar usuários e grupos**, clique em **+ Procurar no diretório**.
9. No painel **Usuários e Grupos do AAD**, selecione o grupo de acesso de membros do site para seu site de equipe do SharePoint Online altamente confidencial e clique em **Selecionar**.
10. Em **Escolher permissões da predefinição**, desmarque as caixas de seleção **Imprimir, copiar e extrair conteúdo** e **Encaminhar**.
11. Clique em **OK** duas vezes.
12. Na folha **Rótulo: Altamente Confidencial**, clique em **Salvar**.
13. Na folha **Proteção de Informações do Azure – Política global**, clique em **Publicar**.

Abaixo está a configuração resultante para seu site de equipe do SharePoint Online altamente confidencial.

 ![Altamente Confidencial](./media/protect-files-with-aip/hc_w_aip.png)

Agora você está pronto para começar a criar documentos e protegê-los com a Proteção de Informações do Azure e o rótulo Altamente Confidencial.

Você deve [instalar o cliente da Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/install-client-app) em seu dispositivo ou computador baseado no Windows. Você pode criar scripts e automatizar a instalação, ou os usuários podem instalar o cliente manualmente. 

Para obter mais informações, consulte os seguintes recursos:

* [O lado do cliente da Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/use-client)
* [Instalando o cliente da Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
* [Página de download para a instalação manual](https://www.microsoft.com/download/details.aspx?id=53018)

Uma vez instalado, os usuários executam e entram de um aplicativo do Office (como o Microsoft Word) com sua conta do Office 365. Uma nova barra de ferramentas **Confidencialidade** permite que você selecione o rótulo **Altamente Confidencial**. 

Certifique-se de que os usuários conheçam o site de equipe do SharePoint Online para armazenar seus arquivos altamente confidenciais.

>[!Note]
>Se você tiver vários sites de equipe do SharePoint Online altamente confidenciais, deverá criar vários rótulos da Proteção de Informações do Azure com as configurações acima, com as permissões para cada rótulo definido para o grupo de acesso de membros de um site de equipe do SharePoint Online específico.
>

## <a name="next-steps"></a>Próximas etapas
[Diretrizes de segurança da Microsoft para campanhas políticas, organizações sem fins lucrativos e outras organizações ágeis](https://technet.microsoft.com/library/mt493213.aspx)

[Proteger sites e arquivos do SharePoint Online seguros](secure-sharepoint-online-sites-and-files.md)

[Criar sites de equipe em um ambiente de desenvolvimento e teste de campanha política](secure-sharepoint-online-sites-dev-test.md)

[Adoção da nuvem e soluções híbridas](https://technet.microsoft.com/library/dn262744.aspx)






