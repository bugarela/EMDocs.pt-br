---
title: Controle de acesso aos recursos
description: "Este artigo fornece um conjunto de considerações de design para controle de acesso que devem ser usadas em um cenário de gerenciamento de dispositivo móvel."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5967876b-3c08-4498-a0a6-0225b562d35f
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 782f6dac4a366312ce0a6d04735262908df6fe72


---

# <a name="access-control-to-resources"></a>Controle de acesso aos recursos

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

As organizações que já usam o Active Directory para autenticar e autorizar os usuários já gerenciam o controle de acesso a recursos específicos usando grupos no Active Directory para segmentar e controlar o acesso aos recursos.  

Para gerenciar o controle de recursos específicos, primeiro você autentica e autoriza o acesso do usuário e, em seguida, valida o tipo de controle que o usuário tem sobre o recurso de destino. Na figura abaixo, isso é mostrado para o usuário João que está acessando a pasta

![Fluxo de autenticação](./media/MDM_Figure_13.png)

## <a name="basic-authentication-and-authorization-flow"></a>Fluxo básico de autenticação e autorização

A ACL (Lista de Controle de Acesso) tradicional é bastante limitada e não leva em consideração outros aspectos do estado do usuário, como onde ele está localizado ao tentar acessar este recurso. Se a sua organização precisar incluir mais variáveis antes de conceder acesso a um recurso, você poderá usar o [Controle de Acesso Dinâmico](https://technet.microsoft.com/library/dn408191.aspx), originalmente disponível no Windows Server 2012. O Windows 10 oferece suporte ao atestado de integridade, que ajuda a equipe de TI a controlar o estado de integridade do dispositivo antes de fornecer acesso aos dados. Serviço de atestado de integridade remoto executa uma série de verificações sobre as medidas. Ele valida os pontos de dados relacionados à segurança, incluindo o estado de inicialização (Inicialização Segura, Modo de Depuração etc.) e o estado dos componentes que gerenciam a segurança (BitLocker, o Device Guard etc.). Em seguida, transmite o estado de integridade do dispositivo enviando um blob criptografado de integridade de volta ao dispositivo. Leia [Controlar a integridade de dispositivos baseados no Windows 10](https://technet.microsoft.com/library/mt592023.aspx) para saber mais.

Os administradores do Intune podem exibir o status do Atestado de Integridade do Dispositivo do Windows 10 no [console de Administração do Intune](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune). O atestado de integridade do dispositivo permite que o administrador garanta que os computadores cliente têm configurações confiáveis de BIOS, TPM e software de inicialização. Para dar suporte ao atestado de integridade do dispositivo, os dispositivos do cliente devem estar executando o Windows 10 com o TPM 2 habilitado.

Com muitas empresas atuando como provedores de nuvem de maneira independente usando tecnologias que permitem que elas tenham uma nuvem privada, outra opção é usar o RBAC (Controle de Acesso Baseado em Função). [O Azure AD permite que a TI use RBAC](http://azure.microsoft.com/documentation/articles/role-based-access-control-configure/) para controlar o acesso aos recursos. E como o Azure AD pode ser integrado ao seu Active Directory local, você pode usá-los juntos para determinar como os usuários acessam os recursos.

Um recurso também pode ser um aplicativo, o que significa que, para implementar o controle de acesso a recursos, sua solução de MDM também deve ter a capacidade de controlar como os aplicativos são instalados e acessados. [As políticas de gerenciamento de aplicativos móveis no Intune](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) permitem que você modifique a funcionalidade dos aplicativos implantados para ajudar a ter certeza de que eles atendem às políticas de conformidade e segurança de sua empresa.

Use a tabela abaixo como referência para ajudar a escolher a opção de MDM que melhor atende aos requisitos de controle de acesso de sua organização.

## <a name="intune-standalone"></a>Intune (autônomo)

**Vantagens**

- Controle de acesso (instalação e gerenciamento) de aplicativos
- Acesso condicional com o serviço de atestado de integridade

**Desvantagens**

- A falta de integração com a atual plataforma de MDM local introduzirá uma interface de gerenciamento adicional para você usar
- Algumas políticas podem não estar disponíveis para algumas plataformas móveis

## <a name="mdm-for-office-365"></a>MDM para o Office 365

**Vantagens**

- Controle de acesso para email, Office Mobile, aplicativos do Office e OneDrive for Business

**Desvantagens**

- Permite apenas um pequeno subconjunto de controle de acesso aos recursos
- A falta de integração com a atual plataforma de MDM local introduzirá uma interface de gerenciamento adicional para você usar
- Algumas políticas podem não estar disponíveis para algumas plataformas móveis

## <a name="hybrid-intune-with-configmgr"></a>Híbrido (Intune com ConfigMgr)

**Vantagens**

- Controle de acesso (instalação e gerenciamento) de aplicativos
- Acesso condicional com o serviço de atestado de integridade

**Desvantagens**

- O serviço de nuvem do Azure AD não está incluído na compra da assinatura do Intune

## <a name="enterprise-mobility-security"></a>Enterprise Mobility + Security

**Vantagens**

- Controle de acesso (instalação e gerenciamento) de aplicativos
- Utiliza o Azure AD Premium para fornecer controle de acesso baseado em RBAC
- Acesso condicional com o serviço de atestado de integridade

**Desvantagens**

- Se a organização não tiver uma infraestrutura local do ConfigMgr atual, será necessário planejar, instalar e configurar essa plataforma antes da integração



<!--HONumber=Nov16_HO4-->


