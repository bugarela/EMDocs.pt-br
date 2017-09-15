---
title: Microsoft 365 Enterprise | Microsoft Docs
description: "Fornece uma visão geral e descreve os serviços do Microsoft 365 Enterprise."
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/15/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 14f22a558e2e437f1491033eb33858b377eeca9d
ms.sourcegitcommit: d8588b191a4f9daea73698426dd632e7997140dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2017
---
# <a name="microsoft-365-enterprise-overview"></a>Visão geral do Microsoft 365 Enterprise
O Microsoft 365 Enterprise foi desenvolvido para organizações de grande porte e integra-se ao Office 365 Enterprise, ao Windows 10 Enterprise e ao Enterprise Mobility + Security (EMS) a fim de permitir que todos sejam criativos e trabalhem juntos, de forma segura. O Microsoft 365 Enterprise inclui uma edição corporativa do Windows 10 e aplicativos do Office por meio do Office 365 ProPlus.

O Windows 10 e o Office 365 ProPlus fornecem novas versões de recursos para as empresas em março e setembro, por meio do Canal Semestral. Uma versão de recurso do Canal Semestral tem suporte durante 18 meses. O Microsoft Intune e o System Center Configuration Manager fornecem recursos para implantar e atualizar o Windows 10 e o Office 365 ProPlus.

Esta seção oferece uma visão geral dos serviços do EMS e do Office 365 incluídos no Microsoft 365 Enterprise e também apresenta os conceitos básicos necessários para entender como usá-lo para suas necessidades organizacionais. Esses serviços oferecem funcionalidades que permitem que os administradores de empresa da nuvem da Microsoft não só protejam as identidades e os dispositivos dos funcionários da empresa, como também controlem o acesso aos próprios dados da empresa; tanto em trânsito quanto em repouso.

|Serviço|Descrição|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|O Azure AD oferece um pacote completo de funcionalidades de gerenciamento de identidade, incluindo autenticação multifator, registro de dispositivos, gerenciamento de senha de autoatendimento, gerenciamento de grupo de autoatendimento, controle de acesso baseado em função, monitoramento de uso do aplicativo, alerta e monitoramento avançados de segurança e de auditoria.|
|[Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|Esse serviço permite que você detecte possíveis vulnerabilidades que afetam as identidades da sua organização e configure respostas automatizadas por meio de políticas de acesso condicional para risco do usuário e risco de conexão baixo, médio e alto.|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|Esse serviço permite que as organizações minimizem o número de pessoas que têm acesso persistente a operações privilegiadas. Para isso, o Azure AD Privileged Identity Management apresenta o conceito de um administrador qualificado. Os administradores qualificados devem ser usuários que precisam de acesso privilegiado de vez em quando, mas não todos os dias. A função ficará inativa até o usuário precisar de acesso. Depois de concluir um processo de ativação, ele se tornará um administrador ativo durante um período de tempo predeterminado.|
|[Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| A Proteção de Informações do Azure é uma solução baseada em nuvem, fornecida como parte da oferta do EMS E5, que ajuda uma organização a classificar, rotular e proteger seus documentos e emails. Isso pode ser feito automaticamente por administradores que definem regras e condições, manualmente pelos usuários, ou uma combinação na qual os usuários recebem as recomendações. Você utiliza rótulos da Proteção de Informações do Azure para aplicar classificação a documentos e emails. Quando você faz isso, a classificação fica identificável sempre, independentemente de onde os dados são armazenados ou com quem eles são compartilhados. <br><br>As configurações da política de Proteção de Informações do Azure são protegidas pelo [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms). De forma semelhante à maneira como os rótulos são aplicados, a proteção aplicada usando o Rights Management permanece com os documentos e emails, independentemente do local — dentro ou fora de sua organização, redes, servidores de arquivos e aplicativos.|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|O Intune é um serviço de EMM (gerenciamento de mobilidade empresarial) baseado em nuvem que ajuda a habilitar sua força de trabalho a ser produtiva enquanto mantém dados corporativos protegidos. O Intune integra-se completamente ao Azure AD para oferecer controle de acesso e de identidade e é usado para gerenciamento de dispositivos e de aplicativos. As funcionalidades do [Gerenciamento de dispositivo do Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) são usadas para configurar e proteger os dispositivos do seu usuário, incluindo computadores Windows. <br><br>As funcionalidades do gerenciamento de dispositivo do Intune dão suporte ao registro [BYOD (Traga seu próprio dispositivo)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod), que permite que os usuários registrem seus celulares, tablets ou computadores, e ao registro [COD (Dispositivo de propriedade corporativa)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices) que habilita cenários de gerenciamento como registro automático, dispositivos compartilhados ou configurações de requisito de registro pré-autorizado. Para ter mais segurança, ainda é possível exigir que a MFA registre um dispositivo. Depois de registrado no gerenciamento, o Intune poderá configurar os recursos e as configurações do dispositivo para habilitar o acesso seguro aos recursos da empresa.|


Estas são as versões mais recentes do Windows 10, Office 365 ProPlus, Microsoft Intune e System Center Configuration Manager:

|     |**Canal Semestral (Direcionado)**|**Canal Semestral**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update (em breve)|Versão 1703|
|**Office 365 ProPlus**|Versão 1708|Versão 1705|
|**Intune**|N/D|Versão 1708|
|**System Center Configuration Manager**|Versão do Technical Preview 1708|Versão 1706<sup>*</sup>|

<sup>*</sup> A atualização 1706 do branch atual do System Center Configuration Manager está disponível como uma atualização no console para sites instalados anteriormente que executam a versão 1606, 1610 ou 1702.

> [!NOTE]
> Os serviços do Microsoft Azure também são atualizados regularmente, mas não são conhecidos por um número de versão. Para ver as atualizações mais recentes, e as próximas, para os serviços do Azure, consulte o [roteiro da plataforma de nuvem](https://www.microsoft.com/cloud-platform/roadmap).

Para saber mais sobre os recursos disponíveis nessas versões, consulte os seguintes artigos:
- [Novidades no Windows 10](https://docs.microsoft.com/windows/whats-new/)
- [Informações de versão do Windows 10](https://technet.microsoft.com/windows/release-info)
- [Histórico de atualizações do Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Versões de canal de atualização de cliente do Office 365](https://technet.microsoft.com/office/mt465751)
- [Novidades do Microsoft Intune](https://docs.microsoft.com/intune/whats-new)
- [Novidades no System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions)
- [Funcionalidades no Technical Preview 1708 do System Center Configuration Manager](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="security-best-practices-and-recommendations"></a>Recomendações e melhores práticas de segurança
Embora não haja uma única melhor recomendação para todos os ambientes de clientes, o artigo [Políticas de segurança e configurações recomendadas](microsoft-365-policies-configurations.md) apresenta conceitos importantes de melhores práticas para serem compreendidos. Este artigo também descreve as recomendações gerais da Microsoft sobre como aplicar a política e a configuração na nuvem da Microsoft para garantir que os seus colaboradores estejam protegidos e também sejam produtivos.


## <a name="deploy-windows-10-and-office-365-proplus"></a>Implantar o Windows 10 e o Office 365 ProPlus
Saiba como implantar o Windows 10 e o Office 365 ProPlus e integrar ao Microsoft Azure Active Directory (Azure AD) ou no Active Directory Domain Services (AD DS). Implante o Windows 10, o Office 365 ProPlus e seus outros aplicativos de linha de negócios em novos dispositivos, ou atualize os dispositivos existentes para Windows 10 usando o Intune, o System Center Configuration Manager e a Política de Grupo para gerenciar dispositivos.

Para obter mais informações, consulte os artigos a seguir.
- [Considerações sobre a implantação do Windows 10](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations)
- [Guia de implantação do Office 365 ProPlus](https://support.office.com/article/f99f8cd0-e648-4834-8f45-f5637351899d)
- [Guia de práticas recomendadas para implantação do Office 365 ProPlus na empresa](https://support.office.com/article/31a384ca-650c-4265-b76c-a87b414fd8b8)
- [Implantar aplicativos do Office 365 ProPlus em dispositivos Windows 10 usando o Intune](https://docs.microsoft.com/intune/apps-add-office365)

Para obter assistência de implantação com o Microsoft 365 [entre em contato com o FastTrack](https://fasttrack.microsoft.com/microsoft365).

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>Gerenciar atualizações para Windows 10 e Office 365 ProPlus
Os links a seguir mostram como obter o máximo de controle sobre a qualidade e as atualizações de recurso para Windows 10 e Office 365 ProPlus. Aprenda a controlar com eficiência o uso de largura de banda e a manter o Windows e o Office atualizados com os recursos e atualizações de segurança mais recentes.

Para obter mais informações, consulte os artigos a seguir.
- [Visão geral do Windows como serviço](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Visão geral dos canais de atualização do Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
- [Gerenciar atualizações de software com o Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [Implantar as atualizações do Windows 10 usando o System Center Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [Gerenciar o Office 365 ProPlus com o Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup> A Microsoft incentiva as organizações que estão usando o Configuration Manager para gerenciamento de atualizações do Windows a continuar fazendo isso para computadores cliente com Windows 10.

## <a name="next-steps"></a>Próximas etapas
[Saiba mais sobre os serviços do Microsoft 365 Enterprise](services-overview.md)

[Página do produto do Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)

[Roteiro da plataforma de nuvem](https://www.microsoft.com/cloud-platform/roadmap)

