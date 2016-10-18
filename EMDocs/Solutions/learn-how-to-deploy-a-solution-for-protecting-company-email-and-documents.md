---
title: "Saiba como implantar uma solução para proteger documentos e email da empresa"
description: "Determine e implante a melhor solução para sua empresa para impor o acesso condicional."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 2e10af43-3138-45c0-b2f7-14a1d2bfb237
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d1211e3ef25b73679c851bce7f5eca872520f023
ms.openlocfilehash: 346338c40e83164d63476cf8e08117a5687903b3


---

# Saiba como implantar uma solução para proteger documentos e email da empresa
Cada vez mais, as empresas estão permitindo que os funcionários aumentem sua produtividade acessando emails, documentos e recursos da empresa por meio de seus dispositivos móveis. No entanto, a quantidade de dados confidenciais armazenados em documentos e emails corporativos apresenta um risco de segurança significativo para as empresas.

Este guia é voltado para você, profissional de TI, para ajudá-lo a determinar e implantar a melhor solução para sua empresa aplicar o acesso condicional em uma das configurações descritas abaixo. Isso permitirá que os funcionários usem seus dispositivos móveis para acessar emails corporativos enquanto os dados da empresa permanecem protegidos.

Esta seção discute como implantar uma solução para proteger emails e documentos da empresa. Para obter detalhes sobre a arquitetura dessas soluções, consulte [Diretrizes de arquitetura para proteger emails e documentos da empresa](architecture-guidance-for-protecting-company-email-and-documents.md).

> [!TIP]
> Obtenha uma cópia baixável deste tópico completo na [Galeria do TechNet](https://gallery.technet.microsoft.com/Deploying-Enterprise-16499404).

## Introdução
Proteger os dados da empresa é extremamente importante e é uma tarefa de cada vez mais desafiadora, conforme mais funcionários usam seus dispositivos móveis para acessar recursos da empresa, incluindo emails e anexos de email. Como administrador de TI, você deseja garantir que os dados da empresa permaneçam protegidos mesmo quando os dispositivos móveis não estiverem no local físico da empresa.

O Microsoft EMS (Enterprise Mobility + Security) resolve esse desafio, oferecendo proteção abrangente dos emails e documentos corporativos em quatro camadas – identidade, dispositivos, aplicativos e dados. Entre outros recursos, o EMS garante que os funcionários possam acessar emails corporativos somente de dispositivos gerenciados pelo Microsoft Intune e em conformidade com as políticas de TI.

Proteção de email corporativo envolve dois objetivos principais:

-   **Permitir que somente dispositivos compatíveis acessem o email da empresa:** uma etapa importante para proteger dados corporativos é restringir o acesso a dispositivos que não usem uma senha forte, não estejam desbloqueado ou não estejam criptografados.  O Microsoft Intune oferece a capacidade de definir as condições que os usuários devem cumprir para obter acesso aos recursos da empresa. Isso é conhecido como acesso condicional.

-   **Proteger o conteúdo e os anexos do email:** enquanto o acesso condicional permite que você garanta que somente dispositivos compatíveis sejam capazes de acessar o email, ainda há a questão de proteger o conteúdo e os anexos do email.  O conteúdo pode ser copiado, movido, salvo em um local diferente ou compartilhado com outro usuário.  O EMS resolve esse problema usando as políticas de gerenciamento de aplicativos móveis.

    Aplicativos gerenciados são aplicativos que têm políticas de gerenciamento de aplicativo móvel aplicadas que os tornam compatíveis com os requisitos de segurança da sua empresa. Com esses aplicativos, você tem controle direto sobre implantação, gerenciamento contínuo, como inventário ou atualizações, e apagamento seletivo de aplicativos e seus dados associados. Além disso, por meio de um conjunto de políticas de gerenciamento (MAM) do aplicativo móvel, o Intune permite modificar a funcionalidade de aplicativos e restringir o compartilhamento de dados. Para obter mais detalhes de como essa solução funciona, incluindo detalhes da arquitetura, consulte [Proteger documentos e email corporativos](architecture-guidance-for-protecting-company-email-and-documents.md).

    > [!NOTE]
    > Você pode criar e implantar um perfil de email e definir uma política de conformidade que especifica que os perfis de email sejam gerenciados pelo Intune (recomendado). Isso lhe dá a capacidade de apagar emails de dispositivos desativados e garante que, para o iOS, anexos só possam ser abertos em aplicativos gerenciados pelo Intune. Consulte [Etapa 5: Criar políticas de conformidade e implantá-las nos usuários.](conditional-access-intune-configmgr-exchange.md) para obter mais informações.

### Soluções abordadas neste artigo
Esta seção fornece uma visão geral de cada solução: Configuration Manager com a implementação do Intune, Intune sozinho, gerenciamento de aplicativos móveis e Proteção de Informações do Azure.

-   **Gerenciar o acesso ao email usando o acesso condicional:** você pode usar uma combinação do Configuration Manager com o Intune ou usar apenas o Intune por si só, juntamente com o Exchange Online ou o Exchange Server local, para gerenciar e garantir o acesso condicional em todos os tipos de PCs e dispositivos móveis, independentemente de sua localização. Aplicar o acesso condicional nesse tipo de ambiente permite que o usuário possa ser mais produtivo, enquanto os dados da empresa são mantidos em segurança.

-   **Proteger anexos e dados de email usando a solução MAM:** você pode aplicar políticas de MAM (gerenciamento de aplicativos móveis) no Intune para modificar a funcionalidade dos aplicativos implantados em sua empresa. Por exemplo, você pode restringir as operações de recortar, copiar e colar em um aplicativo gerenciado, ou configurar um aplicativo para abrir todos os links da web dentro do navegador gerenciado. Isso garante que esses aplicativos estejam de acordo com as políticas de conformidade e segurança da empresa.

-   **Proteção de Informações do Azure para políticas de prevenção contra perda de dados:** a Proteção de Informações do Azure (antigo Azure RMS) usa políticas de criptografia, identidade e autorização para ajudar a proteger seus arquivos e emails em vários dispositivos, como telefones, tablets e PCs. As informações podem ser protegidas em sua empresa e fora dela, porque a proteção permanece com os dados, mesmo quando eles saem dos limites da empresa.

### Avaliando sua implementação desejada
Com todas as opções diferentes de design e configuração para gerenciar dispositivos móveis, é difícil determinar qual combinação melhor atende às necessidades da sua empresa. O [Guia de considerações de design do Gerenciamento de dispositivo móvel](mdm-design-considerations-guide.md) ajuda você a entender os requisitos de design de gerenciamento de dispositivo móvel e detalha uma série de etapas e tarefas que você pode seguir para criar a solução mais adequada às necessidades de negócios e tecnologia da sua empresa.

### Experiência de alto nível do usuário final
Após a solução ser implementada, os usuários finais só poderão acessar o email da empresa em dispositivos gerenciados **e** compatíveis. Quando eles tiverem a capacidade de acessar o email nos dispositivos, os dados da empresa ficarão protegidos e contidos no ecossistema do aplicativo, e ficarão disponíveis apenas para os usuários pretendidos. O acesso pode ser revogado a qualquer momento se o dispositivo for incompatível.

Especificamente, as políticas de acesso condicional definidas no Intune garantem que os dispositivos possam acessar o email somente se forem compatíveis com as políticas de conformidade que você definir. Ações como copiar e colar ou salvar em serviços pessoais de armazenamento na nuvem podem ser restringidas usando políticas de gerenciamento de aplicativos móveis. A Proteção de Informações do Azure pode ser usada para garantir que os dados confidenciais de emails, bem como os anexos encaminhados, somente possam ser lidos pelos destinatários pretendidos. A experiência do usuário final é descrita com mais detalhes em [Experiência do usuário final de acesso condicional](end-user-experience-conditional-access.md).

### Onde ir daqui
Agora que você leu todo este tópico, pode aprender mais sobre como implantar uma solução específica para proteger documentos e emails da empresa, dependendo de seu ambiente:

- [Usar o acesso condicional com o Microsoft Intune](conditional-access-intune.md)
- [Usar o acesso condicional com o Microsoft Intune e o Configuration Manager](conditional-access-intune-configmgr.md)



<!--HONumber=Oct16_HO1-->


