---
# required metadata

title: Opções de provisionamento de dispositivo
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 991cd722-089c-4e8c-80b9-b82e405cc891

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opções de provisionamento de dispositivo

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Quando um usuário pode usar e registrar seus próprios dispositivos, isso aumenta os requisitos para o usuário e a equipe de TI, além de afetar várias áreas. Por exemplo, a figura abaixo mostra uma visão geral do processo de registro para uma organização usando o Intune e o ConfigMgr. Este exemplo descreve as considerações sobre certificado, aplicativo Web e sincronização que você precisará levar em conta ao planejar sua solução:

![Visão geral do processo de registro para dispositivos móveis usando o Intune e o ConfigMgr híbridos](./media/MDM_Figure_04.png)

**Visão geral do processo de registro para dispositivos móveis usando o Intune e o ConfigMgr híbridos**

1. Com o <token>Com o Windows Server 2012 R2, um novo conceito conhecido como registro de dispositivo foi introduzido.  Os usuários podem registrar seus dispositivos para logon único e acessar os dados corporativos usando o Ingresso no Local de Trabalho.  Como parte desse processo de registro, um certificado é instalado no dispositivo. Em troca de registrar seu dispositivo e torná-lo conhecido para a solução de gerenciamento de dispositivos, o usuário obtém acesso aos recursos corporativos que anteriormente não estavam disponíveis fora de seus PCs ingressados em domínio.
2. Os usuários podem registrar dispositivos que configuram o dispositivo para o gerenciamento com o Intune [usando o Portal da Empresa](/Intune/deployuse/enroll-devices-in-microsoft-intune) e, em seguida, aproveitar o Portal da Empresa do Microsoft Intune para acessar facilmente os aplicativos e dados corporativos, e poder gerenciar seus próprios dispositivos, executando tarefas como apagamento remoto caso sejam perdidos, roubados ou substituídos.
3. É possível publicar o acesso aos recursos corporativos com a funcionalidade interna disponível no Windows Server 2012 R2 chamada [Proxy de Aplicativo Web](https://technet.microsoft.com/library/dn584107.aspx), com base no reconhecimento de dispositivo (ou seja, se é foi registrado) e a identidade dos usuários. Se você estiver usando o Enterprise Mobility Suite, também poderá publicar aplicativos usando o Proxy de Aplicativo do Azure AD. A autenticação multifator pode ser usada por meio da [Autenticação Ativa do Azure](https://azure.microsoft.com/documentation/articles/multi-factor-authentication-get-started-cloud/).
4. Para fornecer aos administradores uma visão unificada de todo o ambiente, os dados do Intune são sincronizados com o ConfigMgr, que fornece o gerenciamento unificado localmente e na nuvem.
5. Como parte do processo de registro, um novo objeto de dispositivo é criado no Active Directory.  Esse objeto de dispositivo estabelece um vínculo entre o usuário e seu dispositivo, tornando-o conhecido para a solução de gerenciamento de dispositivos e permitindo que o dispositivo seja autenticado de maneira efetiva em uma autenticação de dois fatores contínua.

Dependendo de como você respondeu às perguntas na Etapa 1, você precisa determinar como deseja que os dispositivos sejam gerenciados na solução de gerenciamento de dispositivos móveis. A lista abaixo mostra as vantagens e desvantagens de cada opção de provisionamento.

## Intune (autônomo)

**Vantagens**

- Dá suporte ao registro e ao provisionamento de todos os principais sistemas operacionais de dispositivos móveis (Android, iOS, Windows 10, Windows 8.x e Windows Phone)
- Um serviço baseado em nuvem, os dispositivos móveis podem ser registrados em qualquer local com acesso à Internet
- Os dispositivos podem ser registrados por meio de um Portal da Empresa centralizado e personalizável
- Opções avançadas de provisionamento de dispositivos para dispositivos móveis

**Desvantagens**

- Interface de gerenciamento adicional para o provisionamento de dispositivos móveis (somente) se for usada uma plataforma de gerenciamento local para dispositivos não móveis
- Políticas separadas de segurança e de conformidade do dispositivo para o serviço baseado em nuvem e a plataforma de gerenciamento local 

## MDM para o Office 365

**Vantagens**

- Integrado aos locatários do Office 365, fornecendo um único console de gerenciamento para dispositivos móveis e serviços de locatário do Office 365 (Exchange Online, SharePoint Online e Skype for Business).
- Dá suporte ao registro e ao provisionamento de todos os principais sistemas operacionais de dispositivos móveis (Android, iOS, Windows 10, Windows 8.1 e Windows Phone)
- Opções básicas de provisionamento de dispositivos para dispositivos móveis

**Desvantagens**

- Interface de gerenciamento adicional para o provisionamento de dispositivos móveis (somente) se for usada uma plataforma de gerenciamento local para dispositivos não móveis
- Políticas separadas de segurança e de conformidade do dispositivo para o serviço baseado em nuvem e a plataforma de gerenciamento local
- Opções menos avançadas de provisionamento de dispositivos

## Híbrido (Intune com ConfigMgr)

**Vantagens**

- Integração nativa entre o Intune (serviço de gerenciamento de dispositivo baseado em nuvem) com o System Center 2012 Configuration Manager e o System Center 2012 R2 Configuration Manager (plataformas locais de gerenciamento de dispositivo)
- Dá suporte ao registro e ao provisionamento de todos os principais sistemas operacionais de dispositivos móveis (Android, iOS e Windows Phone) e inclui o provisionamento de todos os principais sistemas operacionais de dispositivos não móveis
- Dá suporte a opções avançadas de provisionamento de dispositivos para dispositivos móveis por meio da conectividade do Intune

**Desvantagens**

- Para as organizações que não tenham uma infraestrutura do ConfigMgr atual configurada, será necessário planejá-la, instalá-la e configurá-la antes da integração com o Intune
- Exige configuração adicional para conectar o Intune à infraestrutura local do ConfigMgr

Para obter mais detalhes sobre as opções de registro e provisionamento de dispositivos móveis, lembre-se de examinar como [habilitar registros de dispositivo móvel](/Intune/deployuse/enroll-devices-in-microsoft-intune) no Intune e comparar esses requisitos e procedimentos com a [habilitação de registros de dispositivo móvel](https://technet.microsoft.com/library/jj884158.aspx) no ConfigMgr e no MDM para Office 365.

<!--HONumber=Apr16_HO2-->


