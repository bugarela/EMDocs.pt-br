---
title: "Função da Proteção de Informações do Azure na segurança dos dados | Microsoft Docs"
description: "Este artigo descreve a função da Proteção de Informações do Azure na manutenção da segurança dos dados da sua organização."
author: yuridio
ms.author: yurid
manager: mbaldwin
ms.date: 05/18/2017
ms.topic: solution
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 2f906e2e-3d99-40e6-b5cc-8d903fcda444
ms.reviewer: v-craic
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: bf2418b68e40b60508447fc5400f4acfc5c6b1b3
ms.openlocfilehash: 17f2a0b6991d05af2a6f000af48e9fc085221a4d
ms.contentlocale: pt-br
ms.lasthandoff: 02/14/2017


---

# <a name="the-role-of-azure-information-protection-in-securing-data"></a>A função da Proteção de Informações do Azure na segurança dos dados

A [AIP (Proteção de Informações do Azure)](/information-protection/understand-explore/what-is-information-protection) fornece aos clientes a capacidade de classificar, rotular e proteger seus dados usando criptografia. A Proteção de Informações do Azure permite que os administradores de TI:

- Classifiquem automaticamente emails e documentos com base em regras predefinidas
- Adicionem marcadores ao conteúdo, como cabeçalhos, rodapés e marcas-d'água personalizados
- Protejam arquivos confidenciais da empresa com o Rights Management, o qual permite que eles:
    - Sempre usem chaves RSA de 2.048 bits para criptografia de chave pública e SHA-256 para operações de assinatura.
    - Criptografem os arquivos para um conjunto específico de destinatários dentro e fora da organização
    - Apliquem um conjunto específico de direitos para restringir a usabilidade do arquivo    
    - Descriptografem o conteúdo com base na identidade e na autorização do usuário na política de direitos

Essas funcionalidades permitem que as empresas tenham maior controle de ponta a ponta dos seus dados. Nesse contexto, a Proteção de Informações do Azure desempenha uma função importante na segurança dos dados da empresa.

> [!IMPORTANT]
> Para obter mais informações sobre como funciona a Proteção de Informações do Azure, leia [Como funciona o Azure RMS? De modo subjacente](/information-protection/understand-explore/how-does-it-work).

## <a name="the-state-of-enterprise-protection-today"></a>O estado atual da proteção corporativa

Atualmente, muitas empresas não contam com nenhuma tecnologia de proteção, com o compartilhamento de documentos e de emails sendo feito em texto não criptografado e sem que os guardiões dos dados tenham clareza de quais usuários têm acesso ao conteúdo com privilégios. As tecnologias de proteção como a SMIME são complicadas e as ACLs não são necessariamente transportadas com documentos e emails.

![Sem proteção para documentos](./media/azure-information-protection-securing-data/aip-securing-data-fig1.png)

Em um ambiente amplamente desprotegido, a Proteção de Informações do Azure fornece uma medida de segurança que não estava disponível antes. Além disso, embora a segurança seja um assunto em constante evolução e nenhuma organização nunca poderá declarar ter 100% de proteção, a Proteção de Informações do Azure, quando implantada corretamente, aumenta a superfície de segurança de uma organização.

## <a name="security-principles-for-sharing-content"></a>Princípios de segurança para o compartilhamento de conteúdo

Ao usar a Proteção de Informações do Azure na organização, os administradores de TI têm controle total sobre o dispositivo cliente e sobre o gerenciamento de identidades do usuário, resultando na plataforma de confiança correta para compartilhamento na organização. Por natureza, o envio de informações para fora da organização é menos confiável. Ao pensar na abordagem para a proteção de informações, há alguns princípios que ditam a necessidade da realização de uma avaliação de riscos. Ao executar essa avaliação de risco, considere os seguintes pontos:

- O destinatário tem acesso físico a um dispositivo não gerenciado e, portanto, tem controle sobre tudo o que acontece no dispositivo.
- O destinatário é autenticado com um grau de confiança relacionado a não representação.

Em uma situação na qual o administrador de TI não controla o dispositivo nem a identidade, a TI não consegue controlar o que acontece com as informações protegidas. Assim que um usuário é autenticado e abre as informações protegidas, o controle dessas informações deixa de ser da TI. Nesse momento em diante, você confia que o destinatário respeitará as políticas aplicadas ao conteúdo.

Não é possível deter totalmente um destinatário externo mal-intencionado com acesso autorizado ao conteúdo protegido. A Proteção de Informações do Azure ajuda a estabelecer limites éticos e, com o uso de aplicativos habilitados, a manter as pessoas honestas em relação a como acessam o documento. A Proteção de Informações do Azure ajuda quando há uma relação de confiança implícita nos limites definidos do acesso concedido com base na identidade.

No entanto, é mais simples detectar e reduzir o acesso futuro. O recurso de Rastreamento de Documentos do serviço de Proteção de Informações do Azure pode acompanhar o acesso e a organização pode tomar medidas revogando o acesso ao documento específico ou o acesso do usuário.

Se o conteúdo for confidencial e a organização não puder confiar no destinatário, será essencial que o conteúdo conte com segurança adicional. A recomendação é que a balança pese para o lado da segurança e que controles de acesso sejam aplicados ao documento.

## <a name="identity-based-security"></a>Segurança baseada em identidade

As seções a seguir explorarão três cenários principais de ataques em conteúdo protegido e como uma combinação de controles de ambiente e a Proteção de Informações do Azure pode ser usada para reduzir o acesso mal-intencionado ao conteúdo.

### <a name="attacks-by-unauthorized-users"></a>Ataques de usuários não autorizados

A base da proteção na Proteção de Informações do Azure é que o acesso ao conteúdo protegido seja baseado em identidade autenticada e em autorização. Isso significa que, com a Proteção de Informações do Azure, *não ter autenticação* nem *autorização* significa *não ter acesso*. Esse é o motivo principal para implantar a Proteção de Informações do Azure, uma vez que ela permite que as empresas saiam do estado de acesso irrestrito e alcancem o estado em que o acesso às informações é baseado na autenticação e na autorização do usuário.

Ao usar as funcionalidades da Proteção de Informações do Azure, as empresas poderão compartimentalizar as informações. Por exemplo: mantendo as informações confidenciais do departamento de RH (recursos humanos) isoladas no próprio departamento e mantendo o uso dos dados do departamento de finanças restritos ao departamento de finanças. O acesso fornecido pela Proteção de Informações do Azure é *baseado em identidade em vez de ser baseado em nada*.

O diagrama abaixo mostra um exemplo de um usuário (Bob) que envia um documento a Tom. Nesse caso, Bob é do departamento de finanças e Tom, do departamento de vendas. Sem Tom não receber os direitos, ele não terá acesso ao documento.

![Sem acesso](./media/azure-information-protection-securing-data/aip-securing-data-fig2.png)

A principal vantagem nesse cenário é que a Proteção de Informações do Azure pode deter ataques de usuários não autorizados. Para obter mais informações sobre os controles criptográficos na Proteção de Informações do Azure, leia [Cryptographic controls used by Azure RMS: Algorithms and key lengths](/information-protection/understand-explore/how-does-it-work) (Controles criptográficos usados pelo Azure RMS: algoritmos e comprimentos de chave).

### <a name="access-by-malicious-programs-on-behalf-of-users"></a>Acesso por programas mal-intencionados em nome dos usuários

Normalmente, o acesso por programas mal-intencionados em nome de um usuário é algo que ocorre sem o conhecimento do usuário. Cavalos de Troia, vírus e outros tipos de malware são exemplos clássicos de programas mal-intencionados que podem agir em nome do usuário. Se esses programas puderem representar a identidade do usuário ou aproveitar os privilégios do usuário para executar uma ação, eles poderão usar o [SDK da Proteção de Informações do Azure](/information-protection/develop/developers-guide) para descriptografar o conteúdo em nome de um usuário que nem saberá o que está acontecendo. Uma vez que essa ação ocorre no contexto do usuário, não há uma forma simples para evitar esses ataques.

![Programas mal-intencionados](./media/azure-information-protection-securing-data/aip-securing-data-fig3.png)

O objetivo aqui é aprimorar a segurança da identidade do usuário, o que ajudará a reduzir a capacidade dos aplicativos invasores de sequestrarem a identidade do usuário. O Azure Active Directory fornece várias soluções que podem ajudar a proteger a identidade do usuário, por exemplo, o uso da autenticação de dois fatores. Além disso, como parte do Azure Activity Directory Identity Protection, são fornecidas funcionalidades que devem ser exploradas para manter a segurança da identidade do usuário.

A proteção de identidades não está no escopo da Proteção de Informações do Azure, sendo de responsabilidade do administrador.

> [!IMPORTANT]
> É importante também se concentrar em um ambiente “gerenciado” para remover a presença de programas mal-intencionados. Isso será abordado no próximo cenário.

### <a name="malicious-users-with-authorization"></a>Usuários mal-intencionados com autorização

O acesso de um usuário mal-intencionado é, em sua essência, um comprometimento da relação de confiança. O habilitador nesse cenário precisa ser um programa criado para escalonar privilégios do usuário, uma vez que, diferentemente do cenário anterior, o usuário fornece voluntariamente as credenciais para a quebra da relação de confiança.

![Usuários mal-intencionados](./media/azure-information-protection-securing-data/aip-securing-data-fig4.png)

A Proteção de Informações do Azure foi projetada para tornar os aplicativos localizados no dispositivo cliente responsáveis pela imposição dos direitos associados ao documento. De toda forma, o elo mais fraco na segurança de conteúdo protegido hoje está no dispositivo cliente, no qual o conteúdo é visível para o usuário final em texto não criptografado. Os aplicativos cliente, como o Microsoft Office, respeitam os direitos corretamente e, com isso, um usuário mal-intencionado não consegue usá-los para escalonar privilégios. No entanto, com o SDK da Proteção de Informações do Azure, um invasor motivado pode criar aplicativos que não respeitam os direitos e essa é a essência de um *programa mal-intencionado*.

O foco desse cenário é proteger o dispositivo e os aplicativos cliente, para que os aplicativos invasores não possam ser usados. Algumas medidas que podem ser tomadas pelo administrador de TI estão listadas abaixo:

- Usar o [Windows AppLocker](https://technet.microsoft.com/library/dd759117(v=ws.11).aspx) para ajudar a assegurar que programas indesejados não possam ser executados
- Usar o [Intune](https://docs.microsoft.com/intune/) e o [System Center Configuration Manager](https://docs.microsoft.com/sccm/) para ajudar a assegurar que o dispositivo é “íntegro”
- Verificar se o antivírus no dispositivo está atualizado
- Usar aplicativos que dão suporte aos [Agentes de Identidade da Microsoft](https://technet.microsoft.com/library/ms166045(v=sql.105).aspx) para autenticação e [SSO](https://azure.microsoft.com/resources/videos/overview-of-single-sign-on/)

Uma vantagem importante desse cenário é que a proteção de computadores e aplicativos cliente é uma parte importante da relação de confiança que serve de base para a Proteção de Informações do Azure.

## <a name="summary"></a>Resumo

A segurança completa é muito mais que uma tecnologia. Em uma variedade de meios interdependentes, um administrador de TI pode reduzir a superfície de ataque ao conteúdo protegido no mundo real.

- **Proteção de Informações do Azure**: impede o acesso não autorizado ao conteúdo
- **Microsoft Intune, System Center Configuration Manager e outros produtos de gerenciamento de dispositivo**: proporcionam um ambiente controlado e gerenciado livre de aplicativos mal-intencionados
- **Windows AppLocker**: proporciona um ambiente controlado e gerenciado livre de aplicativos mal-intencionados
- **Azure AD Identity Protection**: aprimora a relação de confiança na identidade do usuário
- **Acesso Condicional do EMS**: aprimora a relação de confiança no dispositivo e na identidade

## <a name="additional-resources"></a>Recursos adicionais

Os cenários a seguir mostrarão mais detalhes sobre como a Proteção de Informações do Azure pode ajudar você a proteger os seus dados:

- [Proteger dados usando classificação, rotulação e proteção](infoprotect-secure-classify-scenario.md)
- [Compartilhar dados confidenciais interna e externamente](share-sensitive-data.md)
- [Acompanhar o uso de dados compartilhados e responder a violações de dados](infoprotect-track-usage-scenario.md)

