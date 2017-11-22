---
title: Proteger sites e arquivos do SharePoint Online seguros | Microsoft Docs
description: "Recomendações de configuração para proteger arquivos de sites de equipe do SharePoint Online no Office 365."
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
ms.openlocfilehash: 1bfa989d3929092c254972d3066246e1548ce198
ms.sourcegitcommit: 684c942047754e93378e271f5b1a659a9752f0ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="secure-sharepoint-online-sites-and-files"></a>Proteger sites e arquivos do SharePoint Online seguros

Este artigo fornece recomendações para configurar sites de equipe do SharePoint Online e proteção de arquivo que equilibra a segurança com facilidade de colaboração. Esse artigo define quatro configurações diferentes, começando com um site público dentro de sua organização com as políticas de compartilhamento abertas. Cada configuração adicional representa uma etapa significativa na proteção, mas a capacidade de acessar e colaborar com os recursos é reduzida ao conjunto de usuários relevantes. 

Use essas recomendações como um ponto de partida e ajuste as configurações para atender às necessidades da sua organização. 

As configurações nesse artigo se alinham às recomendações da Microsoft para três níveis de proteção de dados, identidades e dispositivos:

* Proteção de linha de base
* Proteção confidencial
* Proteção altamente confidencial

Para obter mais informações sobre essas camadas e recursos recomendados para cada camada, consulte os recursos a seguir. 

* [Proteção de dispositivo e identidade para o Office 365](https://technet.microsoft.com/library/28986107-e2fb-4116-bfdd-f66d751a7c16#BKMK_O365IDP)
* [Soluções de proteção de arquivo do Office 365](https://technet.microsoft.com/library/28986107-e2fb-4116-bfdd-f66d751a7c16#BKMK_O365fileprotect)

## <a name="capability-overview"></a>Visão geral da funcionalidade
As recomendações para sites de equipe do SharePoint Online traçam uma variedade de recursos do Office 365. Para sites altamente confidenciais, recomenda-se a Proteção de Informações do Azure. Ela está incluída no EMS (Enterprise Mobility + Security). 

Este diagrama mostra as configurações recomendadas para quatro sites de equipe do SharePoint Online.

 ![Configurações do SharePoint recomendadas](./media/secure-sharepoint-online-sites-and-files/capabilityoverview.png)

Conforme ilustrado:

* A proteção de linha de base inclui duas opções para sites de equipe do SharePoint Online — um site público e um site privado. Os sites públicos podem ser descobertos e acessados por qualquer pessoa na organização. Os sites privados podem ser descobertos e acessados apenas por membros do site. Essas configurações de site permitem o compartilhamento fora do grupo. 
* Os sites para proteção confidencial e altamente confidencial são sites privados com acesso limitado apenas a membros de grupos específicos.
* Os rótulos do Office 365 fornecem uma maneira de classificar os dados com um nível de proteção necessário. Cada um dos sites de equipe do SharePoint Online é configurado para aplicar rótulos automaticamente aos arquivos nas bibliotecas de documentos com um rótulo padrão para o site. Correspondentes às quatro configurações de site, os rótulos nesse exemplo são Público Interno, Privado, Confidencial e Altamente Confidencial. Os usuários podem alterar os rótulos, mas essa configuração garante que todos os arquivos de recebem um rótulo padrão.
* As políticas DLP (prevenção de perda de dados) são configuradas para os rótulos Confidenciais e Altamente Confidenciais do Office 365 para avisar ou impedir os usuários quando tentam enviar esses tipos de arquivos para fora da organização.
* Para sites configurados com a proteção altamente confidencial, a Proteção de Informações do Azure criptografa e concede permissões aos arquivos.

## <a name="tenant-wide-settings-for-sharepoint-online-and-onedrive-for-business"></a>Configurações para todo o locatário do SharePoint Online e OneDrive para Empresas
O SharePoint Online e OneDrive para Empresas incluem configurações para todo o locatário que afetam todos os sites e os usuários. Algumas dessas configurações também podem ser ajustadas no nível do site para serem mais restritivas (mas não menos). Esta seção discute as configurações para todo o locatário que afetam a segurança e a colaboração. 

### <a name="sharing"></a>Compartilhando
Para esta solução, recomendamos as seguintes configurações para todo o locatário:

* Mantenha a política de configuração padrão que permite todo o compartilhamento com todos os tipos de conta, incluindo o compartilhamento anônimo.
* Configure os links anônimos para expirar, se desejado.
* Altere o tipo de link padrão para o compartilhamento para Interno. Isso ajuda a impedir o vazamento acidental de dados fora da sua organização.

Embora possa parecer contraintuitivo permitir o compartilhamento externo, essa abordagem fornece mais controle sobre o compartilhamento de arquivo em comparação com enviar os arquivos por email. O SharePoint Online e o Outlook trabalham juntos para fornecer a colaboração segura nos arquivos. 

* Por padrão, o Outlook compartilha um link para um arquivo em vez de enviar o arquivo por email. 
* O SharePoint Online e OneDrive para Empresas tornam mais fácil compartilhar links para arquivos com colaboradores que estão dentro e fora da sua organização.

Você também tem controles para ajudar a controlar o compartilhamento externo. Por exemplo, você pode:

* Desabilitar um link de convidado anônimo.
* Revogar o acesso de usuário para um site.
* Ver quem tem acesso a um documento ou um site específico.
* Configurar os links de compartilhamento anônimos para expirarem (configuração de locatário).
* Limitar quem pode compartilhar fora da sua organização (configuração de locatário).

### <a name="use-external-sharing-together-with-data-loss-prevention-dlp"></a>Usar o compartilhamento externo junto com a DLP (prevenção de perda de dados)
Se você não permitir o compartilhamento externo, os usuários com uma empresa encontrarão métodos e ferramentas alternativas. A Microsoft recomenda que você combine o compartilhamento externo com políticas DLP para proteger os arquivos confidenciais e altamente confidenciais.

### <a name="device-access-settings"></a>Configurações de acesso de dispositivo
As configurações de acesso de dispositivo do SharePoint Online e do OneDrive para Empresas permitem que você determine se o acesso é limitado apenas ao navegador (não é possível baixar os arquivos) ou se o acesso está bloqueado. Essas configurações estão atualmente no Primeiro Lançamento e se aplicam a todo o locatário. Em breve a capacidade de configurar políticas de acesso do dispositivo no nível do site estará disponível. Para esta solução, é recomendável não usar configurações de acesso de dispositivo que se aplicam a todo o locatário.

Para usar configurações de acesso de dispositivo enquanto estão na primeira versão: [Configurar as opções dos programas Padrão ou Primeiro Lançamento no Office 365](https://support.office.com/article/Set-up-the-Standard-or-First-Release-options-in-Office-365-3B3ADFA4-1777-4FF0-B606-FB8732101F47).

### <a name="onedrive-for-business"></a>OneDrive for Business
Visite essas configurações para decidir se deseja alterar as configurações padrão para sites do OneDrive para Empresas. Atualmente, as configurações de acesso de compartilhamento e de dispositivo estão duplicadas do Centro de administração do SharePoint Online e se aplicam a ambos os ambientes.

## <a name="sharepoint-team-site-configuration"></a>Configuração de site de equipe do SharePoint
A tabela a seguir resume a configuração para cada um dos sites de equipe descritos anteriormente neste artigo. Use essas configurações como recomendações de ponto de partida e ajuste as configurações e os tipos de site para atender às necessidades da sua organização. Nem toda organização precisa de todos os tipos de site. Somente um pequeno número de organizações requer a proteção altamente confidencial.

| |**Proteção de linha de base nº 1**|**Proteção de linha de base nº 2**|**Proteção confidencial**|**Altamente confidencial**|
|:-----|:-----|:-----|:-----|:-----|
|Descrição|Abra a descoberta e a colaboração dentro da organização.|Grupo e site particulares com o compartilhamento permitido fora do grupo.|Site isolado, no qual os níveis de acesso são definidos pela associação em grupos específicos. O compartilhamento é permitido apenas para membros do site. A DLP avisa os usuários quando tenta enviar arquivos fora da organização.|Criptografia de arquivo + site isolado e permissões com a Proteção de Informações do Azure. A DLP impede que os usuários enviem arquivos fora da organização.|
|Site de equipe público ou privado|Público|Private|Private|Private|
|Quem tem acesso?|Todas as pessoas na organização, incluindo usuários convidados e usuários de B2B.|Membros do site somente. Outros usuários podem solicitar acesso.|Membros do site somente. Outros usuários podem solicitar acesso.|Somente membros. Outros usuários não podem solicitar acesso.|
|Controles de compartilhamento de nível de site|Compartilhamento permitido com qualquer pessoa. Configurações padrão.    |Compartilhamento permitido com qualquer pessoa. Configurações padrão.|Os membros não podem compartilhar o acesso ao site. <br>Os não membros podem solicitar acesso ao site, mas essas solicitações precisam ser atendidas por um administrador de site.|Os membros não podem compartilhar o acesso ao site. <br>Os não membros não podem solicitar acesso ao site ou conteúdo.|
|Controles de acesso de dispositivo de nível de site|Sem controles adicionais.|Sem controles adicionais.|Os controles de nível de site serão disponibilizados em breve, o que impede que os usuários baixem arquivos para dispositivos que não estão ingressados no domínio ou estão sem conformidade. Isso permite o acesso somente para navegador de todos os outros dispositivos.|Os controles de nível de site serão disponibilizados em breve, o que impede o download dos arquivos para dispositivos não ingressados no domínio ou sem conformidade.|
|Rótulos do Office 365|Público Interno|Private|Confidencial|Altamente Confidencial|
|Políticas DLP|||Avisar os usuários quando enviar arquivos que são rotulados como Confidencial para fora da organização. <br>Para bloquear o compartilhamento externo de tipos de dados confidenciais, como números de cartão de crédito ou outros dados pessoais, você pode configurar políticas DLP adicionais para esses tipos de dados (incluindo tipos de dados personalizados que você configurar).|Impedir que os usuários enviem arquivos rotulados como altamente confidenciais para fora da organização. Permitir que os usuários substituam isso fornecendo justificativa, incluindo com quem eles estão compartilhando o arquivo.|
|Azure Information Protection||||Usar a Proteção de Informações do Azure para automaticamente criptografar e conceder permissões aos arquivos. Essa proteção acompanha os arquivos caso eles sejam vazados. O Office 365 não pode ler arquivos criptografados com a Proteção de Informações do Azure. Além disso, as políticas DLP podem funcionar apenas com os metadados (incluindo rótulos), mas não com o conteúdo desses arquivos (como números de cartão de crédito em arquivos).|

Para as etapas de implantação dos quatro tipos diferentes de sites da equipe do SharePoint Online nesta solução, consulte [Implantar sites para três camadas de proteção](deploy-sites-for-three-tiers-of-protection.md).

Para obter instruções passo a passo e definir isso para demonstração, prova de conceito ou desenvolvimento/teste, consulte [Sites seguros do SharePoint Online em um ambiente de desenvolvimento/teste](secure-sharepoint-online-sites-dev-test.md).

## <a name="office-365-classification-and-labels"></a>Rótulos e classificação do Office 365
O uso dos rótulos do Office 365 é recomendado para ambientes com os dados confidenciais. Depois de configurar e publicar os rótulos do Office 365, você pode:

* Aplicar um rótulo padrão a uma biblioteca de documentos em um site de equipe do SharePoint Online, de forma que todos os documentos nessa biblioteca recebam o rótulo padrão. 
* Aplicar rótulos ao conteúdo automaticamente se ele corresponder a condições específicas.
* Criar políticas DLP que se baseiam nos rótulos do Office 365.
* Permitir que pessoas na sua organização apliquem um rótulo manualmente ao conteúdo no Outlook na Web, Outlook 2010 e posterior, OneDrive para Empresas, SharePoint Online e grupos do Office 365. Os usuários geralmente sabem melhor o tipo de conteúdo com o qual estão trabalhando, portanto eles podem classificá-lo e ter a política DLP apropriada aplicada.

 ![Rótulos do Office 365](./media/secure-sharepoint-online-sites-and-files/labels.png)
 
Conforme ilustrado, essa solução inclui a criação dos seguintes rótulos:

* Altamente Confidencial
* Confidencial
* Private
* Público Interno

Esses rótulos são mapeados para os sites recomendados nas ilustrações e gráficos anteriormente neste artigo. Esta solução recomenda a configuração de políticas DLP para ajudar a evitar vazamento de arquivos rotulados como Confidenciais e Altamente Confidenciais fora da organização.

Para as etapas de configuração de rótulos e políticas DLP do Office 365 nesta solução, consulte [Proteger os arquivos do SharePoint Online com rótulos e DLP do Office 365](protect-files-with-o365-labels-dlp.md).

Para obter instruções passo a passo e definir isso para demonstração, prova de conceito ou desenvolvimento/teste, consulte [Sites seguros do SharePoint Online em um ambiente de desenvolvimento/teste](secure-sharepoint-online-sites-dev-test.md).

## <a name="azure-information-protection"></a>Azure Information Protection
Use a Proteção de Informações do Azure para aplicar rótulos e proteções que seguem os arquivos onde quer que eles estejam. Para esta solução, recomendamos que você use uma política de Proteção de Informações do Azure e um sub-rótulo altamente confidencial para criptografar e conceder permissões a arquivos que precisam ser protegidos com o mais alto nível de segurança. 

Lembre-se de que quando a criptografia da Proteção de Informações do Azure é aplicada aos arquivos armazenados no Office 365, o serviço não pode processar o conteúdo desses arquivos. Coautoria, descoberta eletrônica, pesquisa, Delve e outros recursos de colaboração não funcionam. Políticas de DLP só funcionam com metadados (incluindo rótulos do Office 365), mas não com o conteúdo desses arquivos (como números de cartão de crédito em arquivos).

 ![Rótulos do Office 365](./media/secure-sharepoint-online-sites-and-files/azureinfoprotect.png)

Conforme ilustrado:

* Configure políticas e rótulos da Proteção de Informações do Azure no Portal do Microsoft Azure. É recomendável configurar um sub-rótulo de uma política em escopo.
* Os rótulos da Proteção de Informações do Azure aparecem como uma barra de ferramentas de **Proteção de informações** em aplicativos do Office. 

### <a name="adding-permissions-for-external-users"></a>Adicionando permissões para usuários externos
Há duas maneiras em que você pode conceder aos usuários externos o acesso aos arquivos protegidos com a Proteção de Informações do Azure. Em ambos os casos, os usuários externos devem ter uma conta do Azure AD. Se os usuários externos não forem membros de uma organização que usa o Azure AD, eles poderão obter uma conta do Azure AD como um indivíduo usando essa página de entrada: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

* **Adicionar usuários externos a um grupo do Azure AD que é usado para configurar a proteção para um rótulo**.
 Você precisará primeiro adicionar a conta como um usuário de B2B em seu diretório. Pode levar algumas horas para o [cache de associação de grupo pelo Azure Rights Management](https://docs.microsoft.com/information-protection/plan-design/prepare#group-membership-caching-by-azure-rights-management). Com esse método, as permissões são concedidas a todos os arquivos existentes protegidos com o rótulo (até mesmo arquivos protegidos antes de um usuário ser adicionado ao grupo Azure AD).

* **Adicionar usuários externos diretamente à proteção de rótulo**.
 Você pode adicionar todos os usuários de uma organização (por exemplo, Fabrikam.com), um grupo do Azure AD (por exemplo, um grupo de finanças dentro de uma organização) ou um usuário individual. Por exemplo, você pode adicionar uma equipe externa de agências reguladoras à proteção para um rótulo. Com esse método, as permissões são concedidas apenas para arquivos protegidos com o rótulo depois que a entidade externa é adicionada à proteção.

### <a name="deploying-and-using-azure-information-protection"></a>Implantando e usando a Proteção de Informações do Azure
Para as etapas de configuração de Proteção de Informações do Azure nesta solução, consulte [Proteger arquivos do SharePoint Online com a Proteção de Informações do Azure](protect-files-with-aip.md).

Para obter instruções passo a passo e definir isso para demonstração, prova de conceito ou desenvolvimento/teste, consulte [Sites seguros do SharePoint Online em um ambiente de desenvolvimento/teste](secure-sharepoint-online-sites-dev-test.md).

## <a name="next-steps"></a>Próximas etapas 

[Implantar sites para três camadas de proteção](deploy-sites-for-three-tiers-of-protection.md)
