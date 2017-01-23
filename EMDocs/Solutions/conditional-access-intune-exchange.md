---
title: Use o acesso condicional com o Intune e Exchange Server locais
description: "Implante o Exchange local com a solução do Intune."
keywords: 
author: craigcaseyMSFT
ms.author: v-craic
manager: swadhwa
ms.date: 01/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2a64e898-4c60-48bf-ae14-b05e091e0533
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0be1ad609016303572b67676c03f544d88fb5576
ms.openlocfilehash: 71c6868c62fa50c44663f00aadb8dd9215b3337e


---

# <a name="deploy-exchange-on-premises-with-intune"></a>Implantar o Exchange local com o Intune

Agora que você leu as [diretrizes de arquitetura para proteger emails e documentos da empresa](architecture-guidance-for-protecting-company-email-and-documents.md), está pronto para prosseguir com a implantação de uma solução.

Para o Intune gerenciar dispositivos móveis diretamente, os usuários precisarão registrar os dispositivos no Intune.

## <a name="deployment-steps"></a>Etapas de Implantação
Siga estas etapas para implantar a solução Exchange local com Intune:

### <a name="step-1-install-and-configure-the-microsoft-intune-on-premises-exchange-server-connector"></a>Etapa 1: Instalar e configurar o conector do Exchange Server do Microsoft Intune local.

É possível habilitar o gerenciamento do Exchange ActiveSync para os dispositivos móveis que os usuários não registraram usando o Exchange Connector. O Exchange Connector conecta você à sua implantação do Exchange e permite gerenciar dispositivos móveis por meio do console do Intune.

Siga as etapas em [Configurar o conector local do Microsoft Intune para um Exchange local ou hospedado](/intune/deploy-use/intune-on-premises-exchange-connector) a fim de baixar, instalar e configurar o Microsoft Intune Exchange Connector.

> [!IMPORTANT]
> É possível configurar somente uma conexão do Exchange por conta do Intune. Se você tentar configurar uma conexão adicional, ela substituirá a conexão original.

### <a name="step-2-create-compliance-policies-and-deploy-to-users"></a>Etapa 2: Criar políticas de conformidade e implantá-las para os usuários.
As políticas de conformidade definem regras e configurações com que um dispositivo deve manter a conformidade para ser considerado compatível pelas políticas de acesso condicional. Siga as etapas em [Criar uma política de conformidade no Microsoft Intune](/intune/deploy-use/create-a-device-compliance-policy-in-microsoft-intune) para criar e implantar políticas de conformidade.

Se você desejar poder remover todos os email corporativo de um dispositivo iOS depois que ele não fizer mais parte da sua empresa, será necessário criar e implantar um perfil de email e, em seguida, definir a política de conformidade que especifica que perfis de email são gerenciados pelo Intune. Você deve implantar o perfil de email para o mesmo conjunto de usuários-alvos desta política de conformidade.
![Captura de tela que mostra a página "Regras" do Assistente para Criar Política de Conformidade, onde é possível especificar que um perfil de email deve ser gerenciado pelo Intune](./media/ProtectEmail/Hybrid-Onprem-ExchSrvr-Wizard6.PNG)

Se você especificar essa política de conformidade, um usuário que já tenha configurado a conta de email deverá removê-la manualmente e, em seguida, o Intune a adicionará novamente por meio do processo de registro descrito em [Experiência de usuário final do acesso condicional](end-user-experience-conditional-access.md).

> [!IMPORTANT]
> Se você habilitar a política de acesso condicional do Exchange sem ter antes implantado uma política de conformidade, todos os dispositivos de destino terão o acesso permitido.

### <a name="step-3-identify-users-who-will-be-impacted-by-conditional-access-policy"></a>Etapa 3: Identificar usuários que serão afetados pela política de acesso condicional.
Depois que o conector do Exchange Server for configurado com êxito, ele começará a realizar o inventário dos dispositivos que ainda não estão registrados no Intune, mas estão se conectando aos recursos do Exchange da sua organização usando o Exchange Active Sync.  

Siga as instruções em [Avaliar o efeito da política de acesso condicional](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access) para identificar os usuários que serão afetados pela política de acesso condicional.


### <a name="step-4-configure-user-groups-for-the-conditional-access-policy"></a>Etapa 4: Configurar grupos de usuários para a política de acesso condicional.
Você direciona políticas de acesso condicional a diferentes grupos de usuários de acordo com os tipos de política. Esses grupos contêm os usuários que serão afetados ou que ficarão isentos da política. Quando um usuário é afetado por uma política, cada dispositivo que ele usa deve ser compatível para que possa acessar o email.

Para saber mais, consulte [Configurar grupos de usuários para a política de acesso condicional](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access).

### <a name="step-5-configure-conditional-access-policy"></a>Etapa 5: Configurar política de acesso condicional.
As políticas de acesso condicional usam o fluxo a seguir para um ambiente do Exchange local a fim de avaliar se devem permitir ou bloquear os dispositivos.

![Fluxograma que mostra como as políticas de acesso condicional do Exchange Server local avaliam se permitem ou bloqueiam dispositivos](./media/ProtectEmail/conditional-access-8-2.png)

Siga as informações fornecidas em [Configurar uma política de acesso condicional](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune#configure-conditional-access) para definir a política de acesso condicional.

## <a name="reporting"></a>Relatórios

### <a name="monitor-the-compliance-and-conditional-access-policies"></a>Monitorar a conformidade e políticas de acesso condicional
Para exibir dispositivos que foram bloqueados no Exchange:

No painel do Intune, clique no bloco **Dispositivos Bloqueados no Exchange** para mostrar o número de dispositivos bloqueados e links para mais informações.
![Captura de tela que mostra o bloco "Dispositivos Bloqueados no Exchange" no painel do Intune](./media/ProtectEmail/intune-sa-6blocked-devices.PNG)

## <a name="where-to-go-from-here"></a>Onde ir daqui
Depois de implantar uma solução para proteger email corporativo e dados de email em dispositivos móveis, você poderá aprender mais sobre a [experiência de acesso condicional do usuário final](end-user-experience-conditional-access.md). Isso ajudará a preparar você para problemas que possam surgir quando os usuários finais registrarem seus dispositivos específicos.



<!--HONumber=Jan17_HO2-->


