---
# required metadata

title: Autenticação e autorização
description:
keywords:
author: YuriDio
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 31b98333-5a3d-49ba-a25e-66447df68035

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Autenticação e autorização

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Antes que você possa proteger adequadamente os dados de sua empresa, é necessário identificar quem são seus usuários e, em seguida, você poderá verificar que eles estão autorizados a acessar o recurso solicitado. As organizações que já têm serviços locais do Active Directory devem aproveitá-los para autenticar e autorizar usuários móveis. Todas as soluções de gerenciamento de dispositivos móveis da Microsoft podem usar uma infraestrutura atual do Active Directory para fazer isso. 

Outro ponto de decisão para a autenticação e autorização é o local onde estarão os serviços de diretório. Embora a maioria das organizações tenha serviços locais do Active Directory, algumas organizações podem querer estender seus serviços locais de diretório com um serviço de diretório baseado em nuvem, como o [Azure AD](http://azure.microsoft.com/documentation/articles/active-directory-whatis/) 

O ConfigMgr permite a integração com o [Microsoft Passport for Work](https://technet.microsoft.com/library/mt488797.aspx), que é um método de entrada alternativo que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual em dispositivos que executam o Windows 10. Para um cenário híbrido, a integração dos dois diretórios é uma boa alternativa para aproveitar os recursos do Azure AD, como os seguintes:

- **Gerenciamento de grupos de autoatendimento**: permite que os usuários criem grupos, solicitem o acesso a outros grupos, mantenham suas associações de grupo e deleguem a propriedade do grupo para que outras pessoas possam aprovar solicitações.
- **SLA empresarial de 99,9%**:  a Microsoft garante pelo menos 99,9% de disponibilidade no serviço do Azure Active Directory Premium.
- **Redefinição de senha com write-back**: a redefinição de senha de autoatendimento pode fazer write-back para diretórios locais.

Leia mais sobre as diferentes opções e recursos no [Azure Active Directory](https://msdn.microsoft.com/library/azure/dn532272.aspx).
Exigir dois tipos de autenticação (autenticação multifator ou MFA) é outra estratégia a ser incluído ao planejar uma solução de gerenciamento de dispositivo móvel. O Intune pode [integrar serviços de diretório à MFA (autenticação multifator)](https://technet.microsoft.com/library/dn889751.aspx), o que adiciona outra camada de segurança ao processo de autenticação. 

Se sua organização tiver uma infraestrutura de TI local que inclui um domínio do Active Directory com ADFS (Serviços de Federação do Active Directory), você poderá configurar a MFA em seu servidor de federação e habilitar a MFA para registro no Intune. Se você configurar a MFA no servidor de federação, mas não habilitar a MFA para registro no Intune, os usuários precisarão usar a MFA sempre que acessarem os recursos corporativos de algum dispositivo. 

Você também pode usar a MFA do Azure AD para exigir a MFA sempre que os usuários acessarem os recursos corporativos, habilitados de acordo com o usuário. A MFA do Azure AD é um serviço de nuvem que não exige qualquer infraestrutura de TI local.

Use a tabela abaixo como referência para ajudá-lo a escolher a opção de MDM que melhor atende aos requisitos de autenticação e autorização de sua organização.

## Intune (autônomo)

**Vantagens**

- Pode usar os serviços de diretório local, como o Active Directory para autenticação
- Pode usar os serviços de diretório baseado em nuvem, como o Azure AD para autenticação
- Pode ser integrado à autenticação multifator

**Desvantagens**

- O serviço de nuvem do Azure AD não está incluído na compra de uma assinatura do Intune

## MDM para o Office 365

**Vantagens**

- Pode usar o diretório local, como o Active Directory para autenticação
- Pode usar o diretório baseado em nuvem, como o Azure AD para autenticação
- Pode ser integrado à autenticação multifator
- Pode aproveitar o Centro de Conformidade para usar o modelo de permissões RBAC (Controle de acesso baseado em função)

**Desvantagens**

- O serviço de nuvem do Azure AD não está incluído na compra de uma assinatura do Office 365

## Híbrido (Intune com ConfigMgr)

**Vantagens**

- Pode usar o diretório local, como o Active Directory para autenticação
- Pode usar o diretório baseado em nuvem, como o Azure AD para autenticação

**Desvantagens**

- O serviço de nuvem do Azure AD não está incluído na compra de uma assinatura do Intune

## Enterprise Mobility Suite

**Vantagens**

- Utiliza o Azure AD Premium para fornecer controle de acesso
- A licença do Azure AD Premium já está incluída com o EMS
- Não requer serviços locais de diretório
- Pode sincronizar com os serviços locais do Active Directory
- A MFA é disponível de modo nativo com o EMS

**Desvantagens**

- Não disponível para clientes que não estão adotando uma solução baseada em nuvem



<!--HONumber=Apr16_HO2-->


