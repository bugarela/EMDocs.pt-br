---
# required metadata

title: Identificar requisitos de conectividade de SaaS
description:
keywords:
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 6afbce4c-7500-4387-a19c-dff52c152097

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Identificar requisitos de conectividade de SaaS

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

A forma como você conecta sua infraestrutura local afetará a forma como a identidade de usuário e de dispositivo será gerenciada com todas as soluções de MDM: Intune, MDM para Office 365 e implantações híbridas do Intune e do ConfigMgr. Tanto o Intune quanto o MDM para Office 365 aproveitam a arquitetura de serviços de diretório fornecida pelos Serviços do Azure Active Directory. Essa integração com o Azure oferece bastante flexibilidade quando você estiver projetando o suporte de gerenciamento de identidades em sua solução de gerenciamento de dispositivos móveis.

Conforme mostra as listas abaixo, a conexão dos serviços de diretório locais ao Azure é o principal requisito para habilitar o logon único e o gerenciamento de contas de diretório unificado. O logon único torna muito mais fácil para seus usuários se conectarem aos recursos da empresa que estão locais e na nuvem. Ter um único local para gerenciar contas facilita o trabalho dos administradores. Para o acesso móvel, sincronizar atributos e credenciais de conta de diretório entre o Azure e os serviços locais de diretório permite que os usuários se autentiquem em seus dispositivos móveis para acessar os recursos que são gerenciados pelo MDM para Office 365 ou Intune.

![Visão geral do gerenciamento integrado de identidades](./media/MDM_Figure_15.png)

**Visão geral do gerenciamento integrado de identidades**

Dependendo de como você respondeu às perguntas na Tarefa 2, você precisa conseguir determinar como a solução de SaaS precisa se conectar à sua plataforma de gerenciamento local de clientes de sua solução de gerenciamento de dispositivos móveis. As listas abaixo ajudarão você a entender as vantagens e desvantagens de conectar sua infraestrutura local a uma solução de SaaS.

## Intune (autônomo)

**Vantagens**

- Totalmente integrado ao Azure Active Directory para gerenciar a identidade e autenticação do usuário e do dispositivo
- Dá suporte ao autogerenciamento de credenciais de usuário e a experiências de logon único que podem aproveitar as credenciais existentes de conta local
- Dá suporte a logon único para milhares de aplicativos SaaS pré-integrados
- Dá suporte à segurança de acesso ao aplicativo com a imposição da MFA (autenticação multifator baseada em regras) para aplicativos locais e na nuvem

**Desvantagens**

- Recursos e funcionalidades avançados de conectividade de serviços de diretório exigem o emparelhamento com o Azure Active Directory Premium

## MDM para o Office 365

**Vantagens**

- Integrado aos locatários do Office 365, que usam a estrutura do Azure Active Directory para gerenciar a identidade e autenticação de usuário e dispositivo
- Os serviços locais de diretório podem ser conectados como parte da conexão dos serviços ao Office 365
- Dá suporte ao autogerenciamento e a experiências de logon único que podem aproveitar as credenciais existentes de conta local
- Oferece suporte à autorização de multifator para inscrições de dispositivos usando o serviço do Azure MFA

**Desvantagens**

- Não dá suporte à integração do gerenciamento de aplicativos móveis com outras soluções ou aplicativos de SaaS

## Híbrido (Intune com ConfigMgr)

**Vantagens**

- Todas as vantagens do Intune autônomo, além das seguintes:
 - Integração direta com serviços locais de diretório por meio da infraestrutura do ConfigMgr

**Desvantagens**

- Para as organizações que não tenham uma infraestrutura do ConfigMgr atual configurada, será necessário planejá-la, instalá-la e configurá-la antes da integração com o Intune
- Exige requisitos de implantação local adicional e alterações de configuração para as organizações com o ConfigMgr.

<!--HONumber=Jun16_HO1-->


