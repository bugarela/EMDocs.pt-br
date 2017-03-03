---
title: Diretrizes de arquitetura para proteger documentos e email da empresa
description: "Forneça proteção de dados para sua empresa enquanto garante que a experiência do usuário final seja simples e não afete a produtividade."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc9c7d79-d2ca-4cb2-8456-c7a88cbbf6fd
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: 43594d947f3fa081a777eee6081c83b35621a9bf


---

# <a name="architecture-guidance-for-protecting-company-email-and-documents"></a>Diretrizes de arquitetura para proteger documentos e email da empresa
Este tópico começa com uma visão geral de como você pode fornecer proteção de dados para sua empresa enquanto garante que a experiência do usuário final seja simples e não afete a produtividade. Em seguida, nos concentraremos especificamente em como você pode ajudar a fornecer acesso seguro ao seu email corporativo e ajudar a proteger dados da empresa e anexos de email usando a solução Microsoft Enterprise Mobility + Security.

Esta seção discute a arquitetura para proteger emails e documentos da empresa. Consulte [Saiba mais sobre como implantar uma solução para proteger emails e documentos da empresa](learn-how-to-deploy-a-solution-for-protecting-company-email-and-documents.md) para obter orientações sobre como implantar uma solução.

> [!TIP]
> Obtenha uma cópia baixável deste tópico completo na [Galeria do TechNet](https://gallery.technet.microsoft.com/Managing-Access-and-Help-b7a05d0d/file/140056/1/Managing%20Access%20and%20Help%20Protect%20Corporate%20Email%20Data%20on%20Mobile%20Devices.pdf).

Os funcionários querem poder usar seus próprios dispositivos para acessar recursos da empresa e as ferramentas de produtividade. A TI precisa garantir que os funcionários tenham essa capacidade, mas que os dados confidenciais da empresa estejam protegidos. BYOD, ou [Traga seu próprio dispositivo](byod-design-considerations-guide.md), representa um desafio específico porque precisa haver uma separação dos dados pessoais e de trabalho em dispositivos pessoais e impedir o compartilhamento intencional ou não de dados da empresa.

**Estudos mostraram que:**

-   37% da força de trabalho do mundo é móvel

-   53% do total de aberturas de email ocorreu em um celular ou tablet no T3 de 2014

-   61% dos trabalhadores combinam tarefas pessoais e de trabalho em seus dispositivos

Considere o seguinte:

-   Email costuma ser o aplicativo mais usado em qualquer dispositivo.

-   Conteúdo de email e anexos de email podem ser copiados, compartilhados ou movidos para outros locais fora do alcance do departamento de TI, o que pode comprometer a segurança da sua empresa.

Uma vez que os usuários finais querem fazer trabalho para a empresa usando seus próprios dispositivos pessoais e que o email é o aplicativo acessado com mais frequência, a primeira etapa para sua TI é certificar-se de que os usuários finais possam acessar o email corporativo em seus dispositivos com a garantia de que os dados confidenciais no email não sejam comprometidos.

## <a name="overview"></a>Visão geral
A Microsoft oferece o EMS (Enterprise Mobility + Security), uma solução abrangente para gerenciamento de dispositivos móveis, identidade, gerenciamento de aplicativos e proteção de dados. O EMS fornece um modelo de segurança em camadas que permite ao departamento de TI gerenciar o acesso a email, dados e aplicativos corporativos de praticamente qualquer dispositivo.

O EMS é composto pelos seguintes serviços de nuvem:

![Gráfico que mostra os serviços de nuvem que fazem parte do EMS: Microsoft Azure AD Premium, Microsoft Intune e Proteção de Informações do Microsoft Azure](./media/ProtectEmail/Enterprise-Mobility-Suite.png)

Usando o EMS, os dados são protegidos dentro e fora da sua rede corporativa:

-   Os funcionários têm acesso ao email corporativo, aplicativos de trabalho e dados da empresa no dispositivo de sua escolha, sem se preocupar com informações confidenciais da empresa.

-   Dados da empresa são protegidos em todos os níveis: usuário, dispositivo, aplicativo e, finalmente, no nível dos dados em si.

-   Seu administrador de TI pode assegurar que dados corporativos sejam acessados apenas por usuários confiáveis nos dispositivos gerenciados e compatíveis e no contexto de aplicativos gerenciados.

Aplicativos gerenciados pelo Intune incluem aplicativos móveis do Office, que são essenciais para essa solução. Com aplicativos móveis do Office, você pode ajudar a maximizar a produtividade dos funcionários, impedindo a perda de dados. Por exemplo, seu administrador de TI pode definir políticas que impeçam a cópia de dados da empresa para armazenamento em nuvem particular como o Dropbox.

Quando os funcionários se movem ou alteram trabalhos, ou perdem o dispositivo, o EMS fornece a opção de apagar remota e seletivamente os dados corporativos do dispositivo. Isso pode ser feito pelo usuário final ou pelo administrador de TI.

## <a name="how-ems-can-help-protect-your-data"></a>Como o EMS pode ajudar a proteger seus dados
O modelo de segurança de quatro camadas para identidade, dispositivos, aplicativos e dados é focado em garantir que os recursos da empresa sejam acessados pelo usuário pretendido, em um dispositivo que atenda a um conjunto de políticas de conformidade configurado por você e dentro dos limites dos aplicativos gerenciados.

![Gráfico mostrando o modelo de segurança em quatro camadas para identidade, dispositivos, aplicativos e dados](./media/ProtectEmail/Protecting_your_data.png)

Proteger seus dados começa com o estabelecimento e validação da identidade do usuário. *Azure AD/*, uma ferramenta de gerenciamento de identidades e acesso de nível empresarial, fornece logon único, autenticação multifator, senhas de autoatendimento e muito mais. Ele fornece a funcionalidade para a **camada de identidade** do modelo de segurança.

Compilando na linha de base de identidade, o administrador de TI pode usar *Microsoft Intune* para certificar-se de que os dispositivos móveis sejam registrados e gerenciados e estejam em conformidade com as políticas da empresa. Esta é a **camada do dispositivo**.

A terceira camada é a **camada de gerenciamento de aplicativo** com o ecossistema de aplicativos gerenciados pelo Intune. Esse ecossistema, enquanto permite aos usuários serem produtivos e usarem as ferramentas de que precisam e conhecem, como o Office, também permite que a TI mantenha os dados confidenciais dentro do ecossistema de aplicativos gerenciados.

A *Proteção de Informações do Azure (antigo Azure RMS)* conclui o modelo de segurança, protegendo os dados no nível de arquivo. As políticas de segurança aplicadas aos dados viajam com os dados, ajudam a manter os dados protegidos em trânsito e em repouso, independentemente do dispositivo usado para acesso. Essa é a **camada de dados** do modelo de segurança.

## <a name="where-to-go-from-here"></a>Onde ir daqui
- [Assista](https://www.youtube.com/watch?v=ltcZvm4VOFU) a este vídeo para aprender como inscrever-se para uma conta de avaliação e começar.

- Leia o [Guia de considerações de design de gerenciamento de dispositivo móvel](mdm-design-considerations-guide.md) para entender melhor os requisitos de design do gerenciamento de dispositivo móvel.

- [Saiba mais sobre como implantar uma solução para proteger emails e documentos da empresa](learn-how-to-deploy-a-solution-for-protecting-company-email-and-documents.md).

Além disso, se você quiser saber mais sobre o EMS e Azure Active Directory, poderá obter mais informações de qualquer um dos seguintes artigos:
- [Arquitetura do EMS](https://azure.microsoft.com/documentation/infographics/enterprise-mobility/)

- [O que é o Active Directory do Azure](/active-directory/active-directory-whatis)

- [Como o Active Directory do Azure dá suporte a Office 365, Microsoft Intune e outros serviços da Microsoft?](/active-directory/active-directory-administer#what-is-an-azure-ad-tenant)

- [Como o Active Directory do Azure ajuda a gerenciar identidades](/active-directory/active-directory-administer)

- [O que é a Proteção de Informações do Azure?](/information-protection/understand-explore/what-is-azure-rms)

- [Como os aplicativos dão suporte à Proteção de Informações do Azure](/information-protection/understand-explore/applications-support)



<!--HONumber=Jan17_HO2-->


