---
title: "Opções de gerenciamento de aplicativos"
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 1f77eba2-8e27-4e08-b2f2-e71e3d776cf4
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 73c37109735567642ff1dc11f9729e3ab3affd3b
ms.openlocfilehash: 2d8c4371a06ab1e006083f91f814028573b46141


---

# Opções de gerenciamento de aplicativos

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

As políticas de MAM (gerenciamento de aplicativo móvel) ajudam a evitar que seus dados corporativos vazem dos aplicativos ou serviços do consumidor em dispositivos móveis. Normalmente, essas políticas seriam aplicadas apenas no dispositivo registrado em uma solução de gerenciamento de dispositivo móvel. Agora, o Intune expandiu seus recursos de MAM a fim de incluir dispositivos gerenciados por outras soluções de gerenciamento de dispositivos móveis e dispositivos que não são registrados em qualquer sistema de gerenciamento de dispositivo.

Conforme mostra a figura abaixo, se você já tiver uma solução de MDM ativa, o recurso MAM do Intune poderá ajudar a gerenciar e a proteger os aplicativos do Office e os dados do Office 365, sem a necessidade de cancelar o registro dos dispositivos de funcionários e registrá-los novamente no MDM do Intune, em um cenário de coexistência ou migração:

![Visão geral da separação do gerenciamento de aplicativos para dispositivos móveis usando políticas de MAM do Intune](./media/Intune_without_enrollment.png)

**Visão geral da separação do gerenciamento de aplicativos para dispositivos móveis usando políticas de MAM do Intune**

Os recursos de MAM do Intune não são uma substituição para soluções completas de MDM. O protocolo MDM é necessário para cenários de gerenciamento abrangente de dispositivos, como VPN, Wi-Fi, gerenciamento de certificados, implantação de aplicativos e definição de configurações de segurança no nível do dispositivo.

Para implantações híbridas com o ConfigMgr e o Intune, é possível usar políticas de gerenciamento de aplicativo móvel para proteger aplicativos em dispositivos que não são gerenciados pelo Intune. Usando essa nova funcionalidade, você pode aplicar políticas de gerenciamento de aplicativo móvel para aplicativos conectados aos serviços do Office 365. Isso não tem suporte em aplicativos que se conectam ao Exchange ou SharePoint local. Para usar esse recurso, você deve usar o Versão Prévia do Portal do Azure.

Dependendo de como você respondeu às perguntas na Etapa 1, você deverá ser capaz de determinar como você quer gerenciar os dispositivos na solução de gerenciamento de dispositivos móveis. A lista abaixo mostra as vantagens e desvantagens de cada opção de gerenciamento de aplicativo.

## Intune (autônomo)

**Vantagens**

- Oferece suporte ao gerenciamento de aplicativos em dispositivos registrados no Intune, em dispositivos registrados em outras soluções de gerenciamento ou em dispositivos não registrados em qualquer solução de gerenciamento
- Isola os dados da empresa dos dados pessoais do consumidor dentro de aplicativos habilitados para o Intune. Isso inclui aplicativos do Office Mobile, aplicativos de terceiros que adotaram o SDK do Intune ou aplicativos de linha de negócios abrangidos pelo Intune
- Compartilhamento de dados da empresa com ações de recortar/copiar/colar em aplicativos corporativos, evitando o compartilhamento de dados da empresa em aplicativos pessoais
- Políticas de prevenção de perda de dados importantes, como PIN por aplicativo, controles de salvar como e compartilhamento de dados gerenciados entre aplicativos.
- Suporte para esses recursos no Microsoft Word, Excel, PowerPoint, Outlook, OneNote e OneDrive for Business
- Gerencie aplicativos iOS comprados por meio do Programa de Compra por Volume para Empresas da Apple
- Com suporte em dispositivos Android e iOS

**Desvantagens**

- Não tem suporte em dispositivos com Windows Phone.

## MDM para o Office 365

- Atualmente não há suporte

## Híbrido (Intune com ConfigMgr)

**Vantagens**

- Todas as vantagens do Intune autônomo

**Desvantagens**

- Exige configuração adicional para conectar o Intune à infraestrutura local do ConfigMgr
- Para as organizações que não tenham uma infraestrutura do ConfigMgr atual configurada, será necessário planejá-la, instalá-la e configurá-la antes da integração com o Intune

Explore os detalhes sobre as opções de gerenciamento de aplicativos móveis revisando o seguinte para o Intune e o ConfigMgr: Configurar e implantar políticas de gerenciamento de aplicativos móveis no console do Microsoft Intune. Além disso, não deixe de conferir a lista de aplicativos da Microsoft que podem ser usados com as políticas de MAM do Intune, bem como a lista crescente de aplicativos parceiros compatíveis com o Intune.


<!--HONumber=Jul16_HO3-->


