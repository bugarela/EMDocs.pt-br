---
# required metadata

title: Opções de gerenciamento de dispositivo
description:
keywords:
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: a25f7407-92a0-4588-b5f7-a7bad9cdd070

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opções de gerenciamento de dispositivo

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

O gerenciamento de dispositivos móveis com o Intune e o ConfigMgr gira em torno das políticas de gerenciamento. As políticas definem grupos de configurações para dispositivos móveis e podem ser criadas por meio de modelos ou personalizadas para dispositivos, usuários ou grupos específicos. A prática recomendada de gerenciamento é criar políticas de gerenciamento antes que os dispositivos móveis sejam registrados na solução de gerenciamento. Isso assegura que os dispositivos sejam gerenciados imediatamente de acordo com as políticas e os processos definidos em sua estratégia de TI. Ambas as soluções permitem configurar os seguintes tipos de política:

- Políticas de configuração: as políticas de configuração são usadas para definir as configurações organizacionais gerais para cada dispositivo móvel registrado. Isso pode incluir a senha do dispositivo, aplicativo, política de nuvem e configurações de criptografia, mas pode incluir **[muitas outras configurações de dispositivo](https://technet.microsoft.com/library/dn743712.aspx)** para diferentes áreas de gerenciamento. Além disso, as políticas de configuração são aplicadas e configuradas de modo diferente para diferentes tipos de sistemas operacionais de dispositivos móveis usando perfis de registro de dispositivo.

>[!TIP]
>Durante a criação de diferentes políticas para diferentes tipos de dispositivos, usuários ou grupos, é fácil ter configurações de política conflitantes aplicadas ao mesmo dispositivo. Certifique-se de que entendeu **[como as configurações de políticas conflitantes são aplicadas](https://technet.microsoft.com/library/dn743712.aspx)**.

- **Políticas de conformidade:** as políticas de conformidade impõem os requisitos de sua organização para dispositivos móveis para que eles tenham acesso (ou o acesso negado) aos recursos ou serviços da empresa. Isso também pode incluir configurações de senha e criptografia do dispositivo, além de determinar se o dispositivo móvel foi modificado (“desbloqueado”). Assim como ocorre com as políticas de configuração, as opções de política de conformidade do Intune e do [ConfigMgr](https://technet.microsoft.com/library/dn376523.aspx) também variam de acordo com o tipo de sistema operacional do dispositivo móvel. Se você estiver criando políticas de conformidade no ConfigMgr, é importante observar que uma maior granularidade pode ser configurada como parte de um processo de várias partes:

 1. Criando [itens de configuração](https://technet.microsoft.com/library/gg712331.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT)
 2. Criando [linhas de base de configuração](https://technet.microsoft.com/library/gg712268.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT)
 3. Implantando as [linhas de base de configuração](https://technet.microsoft.com/library/hh219289.aspx?WT.mc_id=Blog_EntMob_Showcase_PCIT) em coleções de usuário ou dispositivo do ConfigMgr

- **Políticas de acesso condicional:** as políticas de acesso condicional definem como o acesso a email é gerenciado e podem ser usadas separadamente ou em conjunto com as políticas de conformidade. As conexões com seu serviço do Exchange Server local ou do Exchange Online devem ser configuradas no [Intune](/Intune/deployuse/restrict-access-to-email-and-o365-services-with-microsoft-intune) ou no [ConfigMgr](https://technet.microsoft.com/library/dn919655.aspx) antes que as políticas de acesso condicional possam ser implantadas. O acesso condicional também pode ser configurado para serviços do Office 365 e do SharePoint Online.

Suas respostas às perguntas na Etapa 1 podem ajudá-lo a determinar como você deseja que os dispositivos sejam registrados na solução de gerenciamento de dispositivos móveis. A lista abaixo ajudará você a entender as vantagens e desvantagens de cada cenário de gerenciamento.

## Intune (autônomo)

**Vantagens**

- Dá suporte ao controle de política simplificado para gerenciar usuários e dispositivos, agora separado por plataforma de dispositivo.
- Dá suporte às plataformas Android, iOS, Windows 10 https://technet.microsoft.com/library/mt147406.aspx, Windows 8.x e Windows Phone, bem como suporte para o Exchange ActiveSync.
- Fornece um console de administração e gerenciamento simples baseado na web, que é acessível de qualquer local
- Dá suporte a políticas baseadas em grupo, facilitando o gerenciamento de grandes números e tipos diversificados de dispositivos móveis
- Dá suporte a recursos e funcionalidades avançados de conformidade do dispositivo móvel, incluindo a detecção da raiz e jailbreak do dispositivo
- Permite o apagamento seletivo ou a redefinição completa de fábrica para todos os dispositivos móveis
- Inclui um portal da Empresa personalizável, que permite a distribuição segura e gerenciada de aplicativos móveis internos e de terceiros
- Implantar certificados em dispositivos móveis
- Permite que as organizações previnam funções de recortar/copiar/colar em aplicativos móveis
- Dá suporte à imposição do uso de navegadores gerenciados
- Dá suporte ao uso de números de IMEI do dispositivo para identificar e marcar dispositivos de propriedade corporativa a fim de separar as atribuições de política dos dispositivos pessoais

**Desvantagens**

- Requisitos e custos de licenciamento adicionais para os dispositivos de registro de contas de usuário no serviço do Intune

## MDM para o Office 365

**Vantagens**

- Console de administração e gerenciamento integrado baseado na Web nos locatários do Office 365
- Dá suporte a políticas baseadas em grupo, facilitando o gerenciamento de grandes números e tipos diversificados de dispositivos móveis
- Dá suporte a recursos e funcionalidades avançados de conformidade do dispositivo móvel, incluindo a detecção da raiz e jailbreak do dispositivo
- Permite o apagamento seletivo ou a redefinição completa de fábrica para todos os dispositivos móveis

**Desvantagens**

- Não há suporte para os recursos de gerenciamento avançado de dispositivos móveis, incluindo:
 - Provisionando e gerenciando perfis de certificados, email, VPN e sem fio
 - Registrando e gerenciando coleções de dispositivos
- Não há suporte para alguns recursos e funcionalidades de gerenciamento de aplicativos móveis:
 - Implantando aplicativos de linha de negócios em dispositivos móveis
 - Habilitando o acesso seguro a dados para aplicativos móveis do Office
 - Estendendo os dados corporativos com segurança à aplicativos de linha de negócios para dispositivos móveis
 - Navegadores gerenciados ou outros aplicativos de exibição de conteúdo

## Híbrido (Intune com ConfigMgr)

**Vantagens**

- Todas as vantagens do Intune autônomo, além das seguintes:
 - Fornece um único painel de exibição com efeito de transparência para gerenciar o estado corporativo, incluindo a flexibilidade para administração baseada em função e scripts (por meio do PowerShell)

**Desvantagens**

- Exige configuração adicional para conectar o Intune à infraestrutura local do ConfigMgr
- Para as organizações que não têm uma infraestrutura do ConfigMgr atual configurada, será necessário planejá-la, instalá-la e configurá-la antes da integração com o Intune
- Atualmente, não há suporte para perfis de VPN e de email para dispositivos com Android
- Atualmente, não há suporte para o suporte ao navegador gerenciado

<!--HONumber=Jun16_HO1-->


