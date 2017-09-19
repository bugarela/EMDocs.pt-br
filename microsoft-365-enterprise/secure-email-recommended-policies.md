---
title: "Políticas recomendadas para email seguro – Microsoft 365 Enterprise | Microsoft Docs"
description: "Descreve as políticas para as recomendações da Microsoft sobre como aplicar configurações e políticas de email."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 6c8ad1b7a297c28e52cfc5412fe40d3001d2efa3
ms.sourcegitcommit: d8588b191a4f9daea73698426dd632e7997140dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2017
---
# <a name="policy-recommendations-for-securing-email"></a>Recomendações de política para proteger o email

Este artigo descreve as políticas recomendadas para ajudar a proteger o email organizacional e os clientes de email que dão suporte à Autenticação Moderna e ao Acesso Condicional. Essas recomendações são um complemento à [identidade comum e às recomendações da política de acesso](identity-access-policies.md).

As seguintes recomendações se baseiam em três diferentes camadas de segurança e proteção para seu email que podem ser aplicadas com base na granularidade de suas necessidades: **linha de base**, **confidencial** e **altamente controlada**. Você pode aprender mais sobre esses níveis de segurança e os sistemas operacionais de cliente recomendada, referenciados por essas recomendações na [introdução de configurações e políticas de segurança recomendadas](microsoft-365-policies-configurations.md).

>[!NOTE]
>Todos os grupos de segurança criados como parte dessas recomendações devem ser criados com recursos do Office habilitados. Isso é especificamente importante para a implantação do AIP ao proteger documentos no SharePoint.
>
>![Recursos do Office habilitados para grupos de segurança](./media/security-group.png)
>

## <a name="baseline"></a>Linha de base
Para criar uma nova política de acesso condicional, faça logon no Portal do Microsoft Azure com suas credenciais de administrador. Navegue até **Azure Active Directory > Segurança > Acesso condicional**.

Você pode adicionar uma nova política (+Adicionar), conforme mostrado na captura de tela a seguir:

![Política de AC de linha de base](./media/secure-email/baseline-ca-policy.png)

As tabelas a seguir descrevem as configurações apropriadas necessárias para expressar as políticas necessárias para cada nível de proteção.

### <a name="medium-and-above-risk-requires-mfa"></a>O risco médio e superior requer a MFA

A tabela a seguir descreve as configurações de política de acesso condicional a serem implementadas para esta política.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Atribuições**|Usuários e grupos|Incluir|Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto.|
|||Excluir|Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)|Associação modificada de forma temporária, conforme o necessário|
||Aplicativos em nuvem|Incluir|Selecionar aplicativos – selecione Office 365 Exchange Online||
||Condições|Configurado|Sim|Configure específicos para suas necessidades e ambiente|
||Risco de entrada|Nível de risco|Alto, médio|Marque ambos|
|**Controles de acesso**|Conceder|Conceder acesso|verdadeiro|Selecionada|
|||Exigir MFA|verdadeiro|Verificar|
|||Exigir dispositivos em conformidade|Falso||
|||Exigir dispositivos ingressados no domínio|Falso||
|||Exigir todos os controles selecionados|verdadeiro|Selecionada|
|**Habilitar política**|||Ativado|Implantar política de acesso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio

Para criar uma nova Política de Acesso Condicional do Intune para Exchange Online, faça logon no [Portal de Gerenciamento da Microsoft (http://manage.microsoft.com)](http://manage.microsoft.com/) com suas credenciais de administrador e navegue até **Política > Acesso Condicional > Política do Exchange Online**.

![Política do Exchange Online](./media/secure-email/exchange-online-policy.png)

Você deve definir uma política de acesso condicional especificamente para o Exchange Online no Portal de Gerenciamento do Intune para exigir um dispositivo em conformidade ou ingressado no domínio.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Acesso ao aplicativo**|Outlook e outros aplicativos que usam autenticação moderna|Todas as plataformas|verdadeiro|Selecionada|
|||O Windows deve atender aos seguintes requisitos|O dispositivo deve estar ingressado no domínio ou estar em conformidade|Selecionado (Lista)|
|||Plataforma selecionada|Falso||
||Outlook Web Access (OWA)|Bloquear dispositivos sem conformidade na mesma plataforma que o Outlook|verdadeiro|Verificar|
||Aplicativos do Exchange ActiveSync que usam autenticação básica|Bloquear dispositivos incompatíveis em plataformas com suporte pelo Microsoft Intune|verdadeiro|Verificar|
|||Bloquear todos os outros dispositivos em plataformas sem suporte pelo Microsoft Intune|verdadeiro|Verificar|
|**Implantação de política**|Grupos de destino|Selecione os grupos do Active Directory a serem atingidos por essa política|||
|||todos os usuários|Falso||
|||Grupos de segurança selecionados|verdadeiro|Selecionada|
|||Modificar|Selecione grupos de segurança específicos que contém os usuários de destino||
||Grupos isentos|Selecione os grupos do Active Directory a serem isentados desta política (substitui membros da lista de Grupos de Destino)|||
|||Nenhum usuário isento|verdadeiro|Selecionada|
|||Grupos de segurança selecionados|Falso|||

### <a name="mobile-application-management-conditional-access-for-exchange-online"></a>Acesso condicional para gerenciamento de aplicativos móveis para o Exchange Online

Você deve definir uma política de acesso condicional especificamente para o Exchange Online no Portal de Gerenciamento do Intune para gerenciar aplicativos móveis.

Para gerenciar aplicativos móveis, faça logon no Portal do Microsoft Azure com suas credenciais de administrador e, em seguida, navegue até **Proteção de Aplicativo do Intune > Configurações > Acesso Condicional > Exchange Online**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Acesso ao aplicativo**|Aplicativos permitidos|Habilitar acesso ao aplicativo|Permitir os aplicativos que dão suporte a políticas de aplicativo do Intune|Selecionado (lista) – isso resulta em uma lista de combinações de aplicativos/plataforma com suporte pelas políticas de aplicativo do Intune|
|**Acesso do usuário**|Aplicativos permitidos|Grupos de usuários com restrições|Adicionar grupos de usuários – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto|
|||Grupos de usuários isentos|Grupos de segurança de exceção|||

#### <a name="apply-to"></a>Aplicar a

Depois que o projeto foi concluído, essas políticas devem aplicadas a todos os usuários em sua organização.

## <a name="sensitive"></a>Confidencial

### <a name="low-and-above-risk-requires-mfa"></a>O risco baixo e superior requer a MFA
A tabela a seguir descreve as configurações de política de acesso condicional a serem implementadas para políticas de risco baixo e superior.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Atribuições**|Usuários e grupos|Incluir|Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto|
|||Excluir|Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)|Associação modificada de forma temporária, conforme o necessário|
||Aplicativos em nuvem|Incluir|Selecionar aplicativos – selecione Office 365 Exchange Online||
||Condições|Configurado|Sim|Configure específicos para suas necessidades e ambiente|
||Risco de entrada|Configurado|Sim|Configure específicos para suas necessidades e ambiente|
|||Nível de risco|Baixo, médio, alto|Marque todos os três|
|**Controles de acesso**|Conceder|Conceder acesso|verdadeiro|Selecionada|
|||Exigir MFA|verdadeiro|Verificar|
|||Exigir dispositivos em conformidade|Falso||
|||Exigir dispositivo ingressado no domínio|Falso||
|||Exigir todos os controles selecionados|verdadeiro|Selecionada|
|**Habilitar política**|||Ativado|Implantar política de acesso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio
(Consulte as instruções de linha de base)

### <a name="mobile-application-management-conditional-access-for-exchange-online"></a>Acesso condicional para gerenciamento de aplicativos móveis para o Exchange Online

(Consulte as instruções de linha de base)

#### <a name="apply-to"></a>Aplicar a

Depois que o projeto piloto foi concluído, essas políticas devem ser aplicadas aos usuários em sua organização que exigem acesso ao email considerado confidencial.

## <a name="highly-regulated"></a>Altamente controlada
### <a name="mfa-required"></a>MFA necessária

A tabela a seguir descreve as configurações de política de acesso condicional a serem implementadas para a política altamente controlada.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Atribuições**|Usuários e grupos|Incluir|Selecionar usuários e grupos – selecione grupos de segurança específicos que contém os usuários de destino|Inicie com o grupo de segurança, incluindo usuários piloto|
|||Excluir|Grupo de segurança de exceção, contas de serviço (identidades de aplicativo)|Associação modificada de forma temporária, conforme o necessário|
||Aplicativos em nuvem|Incluir|Selecionar aplicativos – selecione Office 365 Exchange Online||
|**Controles de acesso**|Conceder|Conceder acesso|verdadeiro|Selecionada|
|||Exigir MFA|verdadeiro|Verificar|
|||Exigir dispositivos em conformidade|Falso|Verificar|
|||Exigir dispositivo ingressado no domínio|Falso||
|||Exigir todos os controles selecionados|verdadeiro|Selecionada|
|**Habilitar política**|||Ativado|Implantar política de acesso condicional|

### <a name="require-a-compliant-or-domain-joined-device"></a>Exigir um dispositivo em conformidade ou ingressado no domínio
(Consulte as instruções de linha de base)
### <a name="mobile-application-management-conditional-access-for-exchange-online"></a>Acesso condicional para gerenciamento de aplicativos móveis para o Exchange Online
(Consulte as instruções de linha de base)
#### <a name="apply-to"></a>Aplicar a
Depois que o projeto piloto foi concluído, essas políticas devem ser aplicadas aos usuários em sua organização que exigem acesso ao email considerado altamente controlado.

### <a name="high-risk-users-policy"></a>Política de usuários de alto risco
Para garantir que todas as contas de usuários de alto risco comprometidas sejam forçadas a executar uma alteração de senha ao entrar, você deve aplicar a política a seguir.

Faça logon no [Portal do Microsoft Azure (http://portal.azure.com)](http://portal.azure.com/) com suas credenciais de administrador e, em seguida, navegue até **Azure AD Identity Protection > Política de Risco do Usuário**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Atribuições**|Usuários|Incluir|todos os usuários|Selecionada|
|||Excluir|Nenhum||
||Condições|Risco do usuário|Alta|Selecionada|
|**Controles**|Acessar|Permitir acesso|verdadeiro|Selecionada|
||Acessar|Requer a alteração de senha|verdadeiro|Verificar|
|**Examinar**|N/D|N/D|N/D|N/D|
|**Impor a política**|||Ativado|Inicia a imposição de política|


## <a name="additional-configurations"></a>Configurações adicionais
Além das políticas acima, você deve definir as seguintes configurações de aplicativo móvel e gerenciamento de dispositivo abordadas nesta seção.

### <a name="intune-mobile-application-management"></a>Gerenciamento de aplicativos móveis do Intune

Para garantir que o email está protegido pelas recomendações de política indicadas anteriormente para cada camada de proteção de dados e segurança, você deve criar políticas de proteção de aplicativo do Intune de dentro do Portal do Azure.

Para criar uma nova política de proteção de aplicativo, faça logon no Portal do Microsoft Azure com suas credenciais de administrador e, em seguida, navegue até **Proteção de Aplicativo do Intune > Configurações > Política de aplicativo**.

Adicione uma nova política (+Adicionar), conforme mostrado na captura de tela a seguir:

![Gerenciamento de aplicativos móveis do Intune](./media/secure-email/intune-mobile-app-mgmt.png)

>[!NOTE]
>Há pequenas diferenças nas opções de política de proteção de aplicativo entre o iOS e o Android. A política abaixo é especificamente para Android.
>

As tabelas a seguir descrevem as configurações de política de proteção de aplicativo do Intune recomendadas:

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Geral**|Email|Nome|Política de email seguro para Android|Insira um nome de política|
|||Descrição||Digite o texto que descreve a política|
|||Plataforma|Android|Há pequenas diferenças nas opções de política de proteção de aplicativo entre o iOS e o Android, essa política é especificamente para Android|
|**Apps**|Aplicativos|Aplicativos|Outlook|Selecionado (lista)|
|**Configurações**|Realocação de dados|Impedir backup do Android|Sim|No iOS isso especificamente indicará o iTunes e o iCloud|
||||Permitir que o aplicativo transfira dados para outros aplicativos|Aplicativos gerenciados por política||
|||Permitir que o aplicativo receba dados para outros aplicativos|Aplicativos gerenciados por política||
|||Impedir "Salvar como"|Sim||
|||Restringir recortar, copiar e colar com outros aplicativos|Aplicativos gerenciados por política||
|||Restringir a exibição de conteúdo da Web no Managed Browser|Não||
|||Criptografar dados do aplicativo|Sim|No iOS, selecione a opção: Quando o dispositivo está bloqueado|
|||Desabilitar a sincronização de contatos|Não||
||Acessar|Solicitar PIN para acesso|Sim||
|||Número de tentativas antes da redefinição do PIN|3||
|||Permitir PIN simples|Não||
|||Tamanho do PIN|6||
|||Permitir a impressão digital em vez do PIN|Sim||
|||Exigir credenciais corporativas para acesso|Não||
|||Bloquear a execução de aplicativos gerenciados em dispositivos com jailbreak ou root|Sim||
|||Verificar novamente o requisito de acesso após (minutos)|30||
|||Período de cortesia offline|720||
|||Intervalo offline (dias) antes do apagamento dos dados do aplicativo|90||
|||Bloquear captura de tela e Assistente do Android|Não|No iOS isso não é uma opção disponível|

Ao concluir, lembre-se de clicar em "Criar". Repita as etapas acima e substitua a plataforma selecionada (menu suspenso) por iOS. Isso cria duas políticas de aplicativo, portanto, após criar a política, atribua grupos à política e implante-a.

### <a name="intune-mobile-device-management"></a>Gerenciamento de dispositivo móvel do Intune
Crie as seguintes políticas de configuração e conformidade fazendo logon na [Portal de Gerenciamento da Microsoft (http://manage.microsoft.com)](https://manage.microsoft.com/) com suas credenciais de administrador.

#### <a name="ios-email-profile"></a>Perfil de email do iOS
No [Portal de gerenciamento do Intune (https://manage.microsoft.com)](https://manage.microsoft.com/) crie as seguintes políticas de configuração em **Política > Políticas de Configuração > Adicionar > iOS > Perfil de Email (iOS 8 e posterior)**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Perfil de email**|Exchange Active Sync|Host (#)|Outlook.office365.com||
|||Nome da Conta (#)|SecureEmailAccount|Escolha do administrador|
|||Nome de usuário|Nome UPN|Selecionado – lista suspensa|
|||Endereço de email|Endereço SMTP primário|Selecionado – lista suspensa|
|||Método de autenticação|Nome de usuário e senha|Selecionado – lista suspensa|
|||Usar S/MIME|Falso||
||Configurações de sincronização|Número de dias de email para sincronizar|Duas semanas|Selecionado – lista suspensa|
|||Usar SSL|verdadeiro|Verificar|
|||Permitir que as mensagens sejam movidos para outras contas de email|Falso||
|||Permitir que o email seja enviado de aplicativos de terceiros|verdadeiro||
|||Sincronizar os endereços de email usados recentemente|verdadeiro|Verificar|

#### <a name="ios-app-sharing-profile"></a>Perfil de compartilhamento de aplicativo do iOS
No [Portal de gerenciamento do Intune (https://manage.microsoft.com)](https://manage.microsoft.com/) crie as seguintes políticas de configuração em **Política > Políticas de Configuração > Adicionar > iOS > Configuração Geral (iOS 8.0 e posterior)**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Security**|Tudo|Tudo|Não configurado||
|**Nuvem**|Tudo|Tudo|Não configurado||
|**Aplicativos**|Navegador|Tudo|Não configurado||
||Aplicativos|Permitir instalação de aplicativos|Não configurado||
|||Exigir uma senha para acessar a loja de aplicativo|Não configurado||
|||Todas as compras no aplicativo|Não configurado||
|||Permitir documentos gerenciados em outros aplicativos gerenciados (iOS 8.0 e posterior)|Não|Selecionado – lista suspensa|
|||Permitir documentos não gerenciados em outros aplicativos gerenciados|Não configurado||
|||Permitir videoconferência|Não configurado||
|||Permitir que o usuário confie em novos autores de aplicativos empresariais|Não configurado||
||Jogos|Tudo|Não configurado||
||Conteúdo de mídia|Tudo|Não configurado|||

#### <a name="android-email-profile"></a>Perfil de email do Android
No [Portal de gerenciamento do Intune (https://manage.microsoft.com)](https://manage.microsoft.com/) crie as seguintes políticas de configuração em **Política > Políticas de Configuração > Adicionar > iOS > Perfil de Email (Samsung KNOX Standard 4.0 e posterior)**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Perfil de email**|Exchange Active Sync|Host (#)| Outlook.office365.com|
|||Nome da Conta (#)|SecureEmailAccount|Escolha do administrador|
|||Nome de usuário|Nome UPN|Selecionado – lista suspensa|
|||Endereço de email|Endereço SMTP primário|Selecionado – lista suspensa|
|||Método de autenticação|Nome de usuário e senha|Selecionado – lista suspensa|
|||Usar S/MIME|Falso||
||Configurações de sincronização|Número de dias de email para sincronizar|Duas semanas|Selecionado – lista suspensa|
|||Agenda de sincronização|Não configurado|Selecionado – lista suspensa|
|||Usar SSL|verdadeiro|Verificar|
|||Tipo de conteúdo para sincronizar|||
|||Email|verdadeiro|Verificar (bloqueado)|
|||Contatos|verdadeiro|Verificar|
|||Calendário|verdadeiro|Verificar|
|||Tarefas|verdadeiro|Verificar|
|||Anotações|verdadeiro|Verificar|

#### <a name="android-for-work-email-profile"></a>Perfil de email do Android for Work
No [Portal de gerenciamento do Intune (https://manage.microsoft.com)](https://manage.microsoft.com/) crie as seguintes políticas de configuração em **Política > Políticas de Configuração > Adicionar > iOS > Perfil de Email (Android for Work – Gmail)**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Perfil de email**|Exchange Active Sync|Host(#)| Outlook.office365.com|
|||Nome da Conta(#)|SecureEmailAccount|Escolha do administrador|
|||Nome de usuário|Nome UPN|Selecionado – lista suspensa|
|||Endereço de email|Endereço SMTP primário|Selecionado – lista suspensa|
|||Método de autenticação|Nome de usuário e senha|Selecionado – lista suspensa|
||Configurações de sincronização|Número de dias de email para sincronizar|Duas semanas|Selecionado – lista suspensa|
|||Usar SSL|verdadeiro|Verificar|

#### <a name="android-for-work-app-sharing-profile"></a>Perfil de compartilhamento de aplicativo do Android for Work
No [Portal de gerenciamento do Intune (https://manage.microsoft.com)](https://manage.microsoft.com/) crie as seguintes políticas de configuração em **Política > Políticas de Configuração > Adicionar > iOS > Configuração Geral (Android for Work)**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Security**|Senha|Comprimento mínimo da senha|Não configurado||
|||Número de falhas de conexão repetidas antes da remoção do perfil de trabalho|Não configurado||
|||Minutos de inatividade antes da tela do dispositivo ser bloqueada|Não configurado||
|||Expiração da senha (dias)|Não configurado||
|||Lembrar de histórico de senha|Não configurado||
|||Exigir uma senha para desbloquear o dispositivo móvel|Não configurado||
|||Permitir desbloqueio por impressão digital (Android 6.0+)|Não configurado||
|||Permitir o Smart Lock e outros agentes de confiança (Android 6.0+)|Não configurado||
||Configurações de perfil de trabalho|Permitir o compartilhamento de dados entre perfis de trabalho e pessoais|Aplicativos do perfil de trabalho podem manipular solicitações de compartilhamento no perfil pessoal|Selecionado – lista suspensa|
|||Ocultar notificações de perfil de trabalho quanto o dispositivo estiver bloqueado (Android 6.0+)|Não configurado||
|||Definir política de permissão do aplicativo padrão (Android 6.0+)|Não configurado|||

#### <a name="device-compliance-policy"></a>Política de conformidade do dispositivo
No [Portal de gerenciamento do Intune (https://manage.microsoft.com)](https://manage.microsoft.com/) crie as seguintes políticas de configuração em **Política > Política de Conformidade > Adicionar**.

|Categories|Tipo|Propriedades|Valores|Anotações|
|:---------|:---|:---------|:-----|:----|
|**Segurança do sistema**|Senha|Exigir uma senha para desbloquear os dispositivos móveis (...)|Sim|Selecionado – lista suspensa|
|||Permitir senhas simples (...)|Não|Selecionado – lista suspensa|
|||Comprimento mínimo da senha (...)|6|Selecionado – lista|
||Configurações de senha avançadas|Tudo|Não configurado||
||Criptografia|Exigir criptografia no dispositivo móvel (...)|Sim|Selecionado – lista suspensa|
||Perfis de email|A conta de email deve ser gerenciada pelo Intune (iOS 8.0+)|Sim| Selecionado – lista suspensa|
|||Selecionar (#)||Necessário selecionar a política de configuração de email do iOS: política de Email do iOS (consulte as políticas de configuração acima)|
|**Integridade do dispositivo**|Atestado de integridade do dispositivo Windows|Exigir que os dispositivos sejam relatados como íntegros (Windows 10 Desktop e Mobile e posterior)|Sim||
||Configurações de segurança de dispositivo|Tudo|Não configurado||
||Proteção contra ameaças ao dispositivo|Tudo|Não configurado||
||Jailbreak|O dispositivo não pode estar com jailbreak ou com raiz (iOS 8.0+, Android 4.0+)|Sim||
|**Propriedades do dispositivo**|Versão do sistema operacional|Tudo|Não configurado|||

Para todas as políticas acima para serem consideradas implantadas, elas devem ser direcionadas para grupos de usuários. Você pode fazer isso criando a política (ao Salvar) ou posteriormente selecionando Gerenciar Implantação na seção Política (no mesmo nível de Adicionar).

## <a name="remediating-medium-or-high-risk-access-events"></a>Correção de eventos de acesso de risco médio ou alto
Se um usuário relata que agora deve executar a MFA quando isso não era exigido anteriormente, o suporte pode examinar seu status de uma perspectiva de risco.  

Os usuários dentro da organização com uma função de Administrador Global ou Administrador de Segurança podem usar o Azure AD Identity Protection para examinar os eventos de risco que contribuíram para a pontuação de risco calculada. Se eles identificarem alguns eventos que foram marcados como suspeitos, mas que foram confirmados com sendo válidos (como um logon de um local desconhecido quando um funcionário está em férias), o administrador poderá resolver o evento para que ele não contribua mais para a pontuação de risco.

## <a name="next-steps"></a>Próximas etapas

[Saiba mais sobre as recomendações de política para proteger arquivos e sites do SharePoint](sharepoint-file-access-policies.md)
