---
title: "Começar a usar o Enterprise Mobility + Security | Microsoft Docs"
description: 
keywords: 
author: jeffgilb
manager: swadhwa
ms.date: 6/7/2017
ms.topic: solution
ms.prod: 
ms.service: active-directory
ms.technology: 
ms.assetid: 1df56825-c0d1-48ac-a294-5ebd1667bc38
ms.reviewer: mhamerof
ms.suite: ems
ms.custom: advanced-threat-analytics,cloud-app-security,information-protection,microsoft-identity-manager,microsoft-intune,rights-management
experimental: true
experiment_id: jeffgilb-length-20161110
ms.translationtype: Human Translation
ms.sourcegitcommit: ed952bd866758978ed4348c70da826eb519b4733
ms.openlocfilehash: 78b0119b52ca1459fd644d093bf7f364b80e8ce1
ms.contentlocale: pt-br
ms.lasthandoff: 12/08/2016


---
# <a name="start-using-enterprise-mobility--security"></a>Começar a usar o Enterprise Mobility + Security

Organizações que estão passando pelo processo de transformação digital precisam se proteger contra novas ameaças e desafios, enquanto o setor de TI lida com demandas contínuas de aumentar a eficiência e fazer mais com menos. Além disso, em um mundo que prioriza soluções móveis e em nuvem, os usuários esperam ser produtivos em qualquer lugar, usando qualquer dispositivo. Com o EMS, você tem soluções holísticas para ajudá-lo a:

- **Controlar a identidade e o acesso na nuvem**. De forma central, gerencie identidades e proteja o logon único em dispositivos, no seu datacenter e na nuvem.
- **Obter segurança baseada em identidade**. Proteção abrangente e inteligente contra os ataques avançados dos dias atuais.
- **Gerenciar dispositivos e aplicativos móveis**. Gerencie com segurança aplicativos e dados no iOS, no Android e no Windows, de um único lugar.
- **Proteger informações**. De forma inteligente, proteja seus dados corporativos e habilite a colaboração segura.

Continue lendo para saber mais sobre como o EMS capacita o setor de TI a fornecer produtividade com segurança e sem limites, do jeito que as pessoas adoram. Esses cenários de exemplo ajudarão você a começar a usar o EMS enquanto faz a transição do local para a nuvem, aproveitar a segurança e a proteção na nuvem e, por fim, fornecer um serviço de TI completo da nuvem.

## <a name="transition-from-on-premises-to-the-cloud"></a>Transição do local para a nuvem
O EMS é composto por muitos serviços e funcionalidades que você pode usar dependendo das necessidades da sua empresa e conforme se familiarizar mais com tais recursos.

### <a name="establish-azure-ad-identity"></a>Estabelecer a identidade do Azure AD
Tudo começa com identidade de nuvem, de modo que a primeira coisa que você precisará fazer para começar é estabelecer a presença de sua organização no [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/). Você pode fazer isso completamente na nuvem ou pode [sincronizar seus objetos atuais do Windows Server Active Directory com o Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) para aproveitar seus investimentos atuais em gerenciamento de identidade local.

### <a name="protect-your-organization-at-the-front-door"></a>Proteger a sua organização na porta de entrada
As soluções tradicionais de segurança costumavam ser o suficiente para proteger seus negócios. Mas isso foi antes do crescimento do setor de mobilidade, que criou um cenário mais amplo de ataques, e da transição para a nuvem, que torna mais complexas as interações de funcionários com outros usuários, dispositivos, aplicativos e dados. Agora, para realmente proteger seus negócios, você precisa [adotar uma abordagem de segurança mais holística e inovadora](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-front-door), que possa proteger, detectar e responder a ameaças de todos os tipos, seja localmente ou na nuvem.

### <a name="start-managing-devices"></a>Começar a gerenciar dispositivos
Garantir que os dados corporativos estejam protegidos e os custos administrativos sejam baixos, enquanto também gerencia a complexidade dos dispositivos na empresa, pode ser um desafio para a TI tradicional. Com o EMS, é mais fácil dar suporte a vários cenários diferentes de gerenciamento de dispositivos, que vão do CYOD (escolha seu dispositivo), com dispositivos empresariais, ao BYOD (traga seu próprio dispositivo), com dispositivos pessoais usados no trabalho.

- **Emita dispositivos de propriedade corporativa**. O Intune oferece soluções de gerenciamento e provisionamento em massa para ajudá-lo a [emitir dispositivos de propriedade corporativa](https://docs.microsoft.com/intune/deploy-use/manage-corporate-owned-devices) em sua organização que estejam integrados com as principais plataformas de gerenciamento de dispositivos corporativos no mercado atualmente, incluindo o Programa de Registro de Dispositivos da Apple e a plataforma de segurança móvel do Samsung KNOX.
- **Habilite uma solução de dispositivos compartilhados de uso limitado**. Os funcionários estão cada vez mais fazendo uso de tecnologias móveis. Seja para processar uma venda ou para verificar o inventário instantaneamente, tablets que talvez executem apenas um aplicativo de linha de negócios normalmente são fornecidos para os funcionários em modo de uso limitado. O Intune permite que você provisione, proteja e gerencie centralmente em massa esses tablets iOS e Android compartilhados que podem ser configurados para funcionar nesse modo de uso limitado.
- **Habilite um programa de BYOD em sua organização**. O BYOD continua a crescer em termos de popularidade entre organizações como um meio para reduzir as despesas de hardware ou aumentar as opções de produtividade móvel para os funcionários. Conforme se afastam do modelo tradicional para os dispositivos corporativos, as empresas precisam [decidir como implementar um programa de BYOD](https://docs.microsoft.com/enterprise-mobility-security/solutions/byod-design-considerations-guide) para permitir que os funcionários usem seus dispositivos pessoais para algumas tarefas de trabalho.
- **Alinhe uma estratégia de implantação e gerenciamento do Windows 10 s necessidades de negócios, do usuário final e do setor de TI**. O Windows 10 oferece novos recursos, cenários e ferramentas de implantação baseados em tecnologias introduzidas no Windows 7 e no Windows 8.1, ao mesmo tempo em que apresenta novos conceitos do Windows como serviço para manter o sistema operacional atualizado. Em conjunto, essas alterações exigem que você [repense o processo de implantação tradicional](https://technet.microsoft.com/itpro/windows/plan/windows-10-deployment-considerations). Após implantar o Windows 10, você também precisará [determinar a melhor forma de gerenciar computadores Windows 10](https://docs.microsoft.com/intune/get-started/choose-how-to-manage-devices) usando o Intune para atender às suas necessidades de negócios e de produtividade do usuário final. Você tem duas opções: registrar o computador Windows 10 como um dispositivo móvel ou instalar o cliente de software do Intune para gerenciar o dispositivo como um computador.

### <a name="manage-and-protect-company-data"></a>Gerenciar e proteger dados da empresa
Atualmente, a maioria dos profissionais que trabalham com informações o fazem de maneira móvel e ser produtivo em dispositivos móveis e fundamental para sermos competitivos. Esses funcionários precisam de acesso contínuo a todos os aplicativos e dados corporativos, a qualquer momento e onde estiverem e o EMS facilita fazer isso, seja localmente ou na nuvem.
- **Proteja dados da empresa locais**. A maioria das estratégias de mobilidade empresarial começam com um plano para habilitar o acesso seguro a email para funcionários que têm dispositivos móveis na Internet, mas você também precisa ser capaz de [acessar de forma segura dados locais da empresa](https://docs.microsoft.com/enterprise-mobility-security/solutions/conditional-access-intune-exchange) que estão sendo acessados por dispositivos móveis. Por exemplo, muitas organizações ainda têm servidores de aplicativos e dados locais, como o Microsoft Exchange, hospedados em sua rede corporativa.
- **Proteja dados da empresa no Office 365**. [Proteger dados corporativos no Office 365 (emails, documentos, mensagens instantâneas etc)](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-office365-data-with-intune) não poderia ser mais fácil para você ou mais simples para os usuários. O Office 365 e o EMS fornecem uma solução de acesso condicional integrada de maneira única, que garante que nenhum usuário, aplicativo ou dispositivo possa acessar dados do Office 365 a menos que atendam aos requisitos de conformidade da empresa (autenticação multifator executada, registrado no Intune, usando o aplicativo gerenciado, versão do sistema operacional com suporte, PIN do dispositivo, perfil de risco do usuário baixo etc.).
- **Proteja o acesso ao Office 365 e proteja dados em dispositivos não gerenciados**. Uma prática de implantação comum do Office 365 é exigir que os dispositivos sejam registrados no gerenciamento, mas nem sempre isso é necessário. Se o usuário simplesmente precisar acessar documentos e o email corporativo, o que normalmente é o caso para dispositivos pessoais, você pode simplesmente usar os aplicativos móveis do Office ([aos quais você aplicou políticas de restrição de aplicativos](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)) e ignorar completamente o registro do dispositivo.

## <a name="leverage-cloud-security-and-protection"></a>Aproveitar a proteção e a segurança de nuvem
O EMS fornece uma solução de segurança baseada em identidades que oferece uma abordagem holística para os desafios de segurança nesta era que prioriza dispositivos móveis e a nuvem. Com o EMS, você pode não apenas proteger dados organizacionais compartilhados, mas também identificar violações de segurança antes que elas possam causar danos.

### <a name="securely-share-data"></a>Compartilhar dados com segurança
Atualmente, o compartilhamento de informações acontece em vários dispositivos e entre fronteiras organizacionais. As empresas enfrentam o desafio de identificar quais dados precisam de proteção e quais não precisam. Para lidar com esse desafio, você pode [classificar, rotular e proteger dados confidenciais](https://docs.microsoft.com/enterprise-mobility-security/solutions/infoprotect-secure-classify-scenario) com o [Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) para garantir que dados corporativos críticos não sejam comprometidos, enquanto habilita os usuários a compartilharem com segurança o que é importante para eles fazerem seu trabalho.

### <a name="identify-and-protect-against-threats"></a>Identificar e proteger contra ameaças
<!-- Detect advanced threats on-premises and in the cloud (ATA, Azure AD, Cloud App Security) -->
Conforme mais organizações passam a adotar a postura de presumir que há violações, o EMS ajuda a identificar invasores em sua organização usando inovadoras tecnologias de análise comportamental e detecção de anomalias – localmente com o [Microsoft Advanced Threat Analytics](http://www.microsoft.com/ata) e na nuvem com o [Azure Active Directory](http://www.microsoft.com/identity) e o [Cloud App Security](http://www.microsoft.com/cloudappsecurity). Nossa inteligência de ameaças é aprimorada com o Microsoft Intelligent Security Graph, baseado em vastos conjuntos de dados e em aprendizado de máquina na nuvem.

## <a name="full-service-it-from-the-cloud"></a>Serviço completo de TI na nuvem
Conforme as organizações concluem sua transformação digital, o serviço completo de TI na nuvem se tornará costumeiro. Empresas com implementações de nuvem maduras tirarão proveito dos recursos fornecidos pelo EMS para habilitar cenários de proteção de dados e identidade de ponta a ponta e de longo prazo.

### <a name="identity-management-from-hire-to-retire"></a>Gerenciamento de identidades da contratação à aposentadoria
A Microsoft vem protegendo identidades baseadas em nuvem por mais de uma década, e com o Azure Active Directory, a Microsoft está disponibilizando esses mesmos sistemas de proteção para clientes corporativos, a fim de garantir a responsabilidade do usuário e do administrador com melhor segurança e governança.
- **Milhares de aplicativos, uma identidade**. O Azure AD é uma solução de gerenciamento de acesso e identidade na nuvem capaz de fornecer às organizações acesso a tudo de que precisam, de qualquer lugar. O Azure AD (Azure Active Directory) torna os usuários mais produtivos [fornecendo a eles uma identidade comum para aplicativos de SaaS (software como serviço)](https://docs.microsoft.com/enterprise-mobility-security/solutions/thousands-apps-one-identity) que acessam recursos na nuvem e locais.
- **Habilite negócios sem fronteiras**. As organizações precisam [capacitar seus funcionários a acessarem todos os seus dados e aplicativos de qualquer dispositivo e de qualquer lugar](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-business-without-borders). Os usuários precisam colaborar entre si e com parceiros, bem como se conectar com clientes.
- **Gerencie o acesso em escala**. O Azure AD fornece um conjunto de ferramentas para automatizar o [gerenciamento avançado de ciclo de vida do usuário](https://docs.microsoft.com/enterprise-mobility-security/solutions/manage-access-at-scale) aproveitando regras de associação de grupo dinâmicas e recursos de gerenciamento de aplicativos.
- **Proteção habilitada para a nuvem**. O Azure AD Identity Protection é um serviço de segurança que proporciona uma [exibição consolidada dos eventos de risco e de possíveis vulnerabilidades](https://docs.microsoft.com/enterprise-mobility-security/solutions/cloud-powered-protection) que afetam as identidades da organização.

### <a name="protect-shared-files-and-saas-apps-with-policies-and-tracking"></a>Proteger arquivos compartilhados e aplicativos SaaS com políticas e acompanhamento
O EMS integra perfeitamente a proteção avançada de dados da empresa ao ritmo dos seus negócios para facilitar a proteção de informações da empresa contra perdas de dados acidentais ou propositais.
- **Compartilhe dados confidenciais interna e externamente**. Embora muitas violações de dados se devam a ataques cibernéticos, os especialistas concordam que muitas resultam do erro humano, que são os momentos de deslize que ocorrem quando os funcionários inadvertidamente vazam dados corporativos confidenciais. [Com os protocolos certos de prevenção contra perda de dados e de informações de segurança estabelecidos](https://docs.microsoft.com/enterprise-mobility-security/solutions/share-sensitive-data), quase todos esses tipos de violação podem ser evitados.
- **Acompanhe o uso de dados compartilhados e responda a violações de dados**. A [Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) é uma solução baseada em nuvem que ajuda uma organização a classificar, rotular e proteger seus documentos e emails. Isso pode ser feito automaticamente por administradores que definem regras e condições, manualmente pelos usuários, ou uma combinação na qual os usuários recebem as recomendações.
- **Gerencie os dados da sua maneira com opções flexíveis de implantação e gerenciamento de chaves**. Em vez da Microsoft gerenciar sua chave de locatário (o padrão), talvez você queira [gerenciar sua própria chave de locatário da Proteção de Informações do Azure](https://docs.microsoft.com/en-us/information-protection/plan-design/plan-implement-tenant-key) para cumprir os regulamentos que se aplicam à sua organização. Gerenciar a sua chave de locatário também é chamado de trazer sua própria chave, ou BYOK.
- **Aprove e gerencie aplicativos SaaS para funcionários**. Use o [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para aprovar/cancelar a aprovação de aplicativos, impor a DLP (prevenção de perda de dados), controlar permissões e compartilhamento e gerar relatórios e alertas personalizados.
- **Proteja seus dados contra erros do usuário**. Podemos fornecer uma visibilidade profunda das atividades de dados e dos usuários, para que você possa [proteger sua empresa quando os usuários tomam más decisões](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-data-user-mistake) quando trabalham com os dados importantes da empresa. O Microsoft Cloud App Security fornece visibilidade e controles para aplicativos de nuvem, incluindo o Office 365. Com a Proteção de Informações do Azure, reunimos a classificação e a rotulação com a proteção de dados persistentes para habilitar o compartilhamento de arquivos seguro, interna e externamente.


### <a name="learn-more"></a>Saiba mais

[Visite a página do Microsoft Enterprise Mobility + Security](http://go.microsoft.com/fwlink/?LinkId=816837)

[Saiba mais sobre o Enterprise Mobility + Security](learn-about-ems.md)

[Experimente o EMS gratuitamente](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-security-trial)

