---
title: "Proteção de email e documentos da empresa"
description: "Permitir que apenas dispositivos compatíveis acessem email da sua empresa e protejam o conteúdo e anexos de email."
keywords: 
author: craigcaseyMSFT
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 78d8368e-1bfe-4ac4-991d-467321a76ed7
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 55a3dbe32e3b5e10e21a6d99bc101ec76fc51f5e
ms.openlocfilehash: cc6844a9329cafd14d7902ec1d677c5bea685b86


---

# Proteção de emails e documentos corporativos
Proteção de email corporativo envolve dois objetivos principais:

-   Permitir somente a dispositivos compatíveis acessar o email da empresa

-   Proteção do conteúdo de email e anexos

## Permitir somente a dispositivos compatíveis acessar o email da empresa
Uma etapa importante para proteger dados corporativos é restringir o acesso a dispositivos que não usem uma senha forte, não estejam desbloqueado ou não estejam criptografados. O Microsoft Intune oferece a capacidade de definir as condições que os usuários devem cumprir para obter acesso aos recursos da empresa. Isso é conhecido como acesso condicional.

Acesso condicional é determinado por dois tipos de políticas que podem ser definidas no Intune:

**Políticas de conformidade** determinam a conformidade de um dispositivo. Elas avaliam as configurações e as condições, como:

-   **PINs e senhas**: sua TI pode criar regras para exigir senhas antes de desbloquear um dispositivo, como complexidade da senha, expiração de senha e outras configurações de senha.

-   **Criptografia**: sua TI pode restringir o acesso a dispositivos criptografados.

-   **O dispositivo não está desbloqueado ou enraizado**: o Intune pode detectar se um dispositivo registrado está desbloqueado, e sua TI pode definir a política para bloquear o acesso a esses dispositivos.

**Políticas de acesso condicional** são configuradas para um serviço específico como o Exchange Online ou no SharePoint Online. Para cada serviço, você pode definir a quais grupos de usuários essas políticas devem ser aplicadas. Por exemplo, você pode garantir que todos no departamento financeiro possam acessar apenas email de dispositivos registrados e compatíveis.

## Experiência de alto nível do usuário final
Após a solução ser implementada, os usuários finais só poderão acessar o email da empresa em dispositivos gerenciados e compatíveis. Quando eles tiverem a capacidade de acessar o email nos dispositivos, os dados da empresa ficarão protegidos e contidos no ecossistema do aplicativo, e ficarão disponíveis apenas para os usuários pretendidos. O acesso pode ser revogado a qualquer momento se o dispositivo for incompatível.

Especificamente, as políticas de acesso condicional definidas no Intune garantem que os dispositivos possam acessar o email somente se forem compatíveis com as políticas de conformidade que você definir. Ações como copiar e colar ou salvar em serviços pessoais de armazenamento na nuvem podem ser restringidas usando políticas de gerenciamento de aplicativos móveis. O Serviço de gerenciamento de direitos do Azure pode ser usado para garantir que os dados confidenciais de emails, bem como os anexos encaminhados, somente possam ser lidos pelos destinatários pretendidos. A experiência do usuário final é descrita com mais detalhes em [Experiência do usuário final de acesso condicional](end-user-experience-conditional-access.md).


Assista a [este](https://www.youtube.com/watch?feature=player_embedded&v=lYx3YIezccg) vídeo de quatro minutos para ver como acesso condicional afeta os usuários finais.

## Por que a arquitetura é importante
Os diferentes componentes do EMS e o Office 365 são criados e projetados para execução na nuvem. Isso traz todos os benefícios que a nuvem oferece: escalabilidade, flexibilidade e facilidade de gerenciamento.

Uma vez que diferentes empresas têm requisitos diferentes, o EMS foi projetado para integrar-se com a infraestrutura local existente, como o Active Directory, o Exchange Server ou o System Center Configuration Manager. Isso permite que você use as credenciais já estabelecidas em sua para seus recursos locais e na nuvem.

As seções a seguir descrevem a arquitetura conforme projetada para ser executada na nuvem e falam brevemente sobre a opção local.

### Fluxo de acesso de email
Dependendo do tipo de aplicativo de email que você usa para acessar o Exchange online, o caminho para estabelecer acesso seguro ao email pode ser ligeiramente diferente. No entanto, os componentes principais: AD do Azure (Active Directory do Azure), Office 365/Exchange Online e Microsoft Intune são os mesmos. A experiência de TI e a experiência do usuário final também são semelhantes. O EMS atualmente dá suporte a aplicativos de email nativos e ao aplicativo Microsoft Outlook para iOS e Android.

### Fluxo de controle de acesso para aplicativos de email nativos
Os clientes do Exchange ActiveSync (EAS) que estiverem tentando acessar email no Exchange Online serão avaliados para as seguintes propriedades:

-   O dispositivo é gerenciado pelo Intune?

-   O dispositivo está registrado com o Active Directory do Azure?

-   O dispositivo é compatível?

-   A ID EAS do cliente está mapeada para um dispositivo registrado?

Para obter um estado compatível, o dispositivo em que o cliente EAS está em execução precisa:

-   Registrar com o Intune

-   Registre-se com o [Azure Active Directory](https://msdn.microsoft.com/6a14cb1f-a058-4453-8ede-d9f4a66a7073.aspx) para

-   Estar em conformidade com as políticas de dispositivo definidas por seu administrador de TI.

Na maioria das plataformas, o registro de dispositivo do Active Directory do Azure ocorre automaticamente durante o registro. Os estados de dispositivo são gravados pelo Intune no Active Directory do Azure e então lidos pelo Exchange Online na próxima vez que o cliente EAS tenta obter email. Se o dispositivo não estiver registrado, o usuário receberá uma mensagem na caixa de entrada com instruções sobre como registrar (também conhecido como registro). Se o dispositivo não for compatível, o usuário receberá um email diferente que o redireciona para o portal da Web do Intune em que ele poderá obter mais informações sobre o problema de conformidade e como corrigi-lo.

O**Azure AD**autentica o usuário e o dispositivo Microsoft Intune gerencia a conformidade e as políticas de acesso condicional, enquanto o **Exchange Online** gerencia o acesso ao email com base no estado do dispositivo.

![Gráfico que mostra o fluxo de controle de acesso para aplicativos de email nativos em dispositivos com Android e iOS](./media/ProtectEmail/Access-Control-Flow-For-Native-Email-Apps.png)

### Fluxo de controle de acesso para aplicativos do Outlook
Semelhante ao cliente EAS, o aplicativo de email do Outlook que estiver tentando acessar o email no Exchange Online será avaliado para as seguintes propriedades:

-   O dispositivo é gerenciado pelo Intune?

-   O dispositivo está registrado com o Active Directory do Azure?

-   O dispositivo é compatível?

A conformidade do dispositivo é estabelecida quase da mesma forma, conforme descrito no fluxo de controle de acesso de cliente do EAS. No entanto, para aplicativos do Outlook, o fluxo entre os componentes é levemente diferente. Quando o aplicativo Outlook tenta obter o email, ele é redirecionado ao Azure AD. O Azure AD emite um token de segurança se o dispositivo for avaliado com sucesso como estando registrado e em conformidade. O token de segurança então é usado para obter email corporativo do Exchange Online. A sincronização de email, na verdade, é orientada por meio do serviço de nuvem do Outlook, que obtém um token de acesso do serviço EAS em nome do usuário para concluir a autenticação e entrega o email.

![Gráfico que mostra o fluxo de controle de acesso do aplicativo do Outlook](./media/ProtectEmail/Access-Control-Flow-For-Outlook-App.png)

## A experiência de administração de TI:
Não há necessidade de uma configuração de infraestrutura complexa para o Azure AD ou o Exchange para que isso aconteça. Seus administradores de TI:

-   Configure e implante as políticas de conformidade usadas para avaliar o status de conformidade do dispositivo.

-   Configurar a política de acesso condicional do Exchange Online e especificar quais grupos de segurança do AD do Azure serão afetados por ela ou estão isentos dela.

-   Escolha permitir ou bloquear dispositivos que não são capazes de se registrar no Intune. A lista de sistemas operacionais com suporte para dispositivos móveis é apresentada mais adiante.

Pode ser necessária uma etapa de configuração opcional. O relatório usado para gerenciar e monitorar o status e o acesso ao dispositivo requer a configuração do conector de serviços do Microsoft Intune.

## A experiência do usuário final:
Quando o usuário tenta acessar email no dispositivo pela primeira vez ou sincronizar posteriormente, o status de conformidade e de registro do dispositivo é verificado. O processo de registrar ou corrigir problemas de conformidade é uma experiência guiada. São mostradas ao usuário final as etapas necessárias para registrar o dispositivo e torná-lo compatível sem necessidade de chamar o suporte técnico da TI:

-   **Se o dispositivo não estiver registrado**, a página de logon mostrará o acesso negado e solicitará o registro. No registro, o dispositivo é registrado automaticamente no Active Directory do Azure. O Intune verifica o dispositivo para fins de conformidade e apresenta as etapas de solução para resolver quaisquer problemas de não conformidade. Depois que o dispositivo estiver em conformidade, o Intune define o status de conformidade do dispositivo com o Active Directory do Azure.

-   **Se o dispositivo estiver registrado, mas não estiver em conformidade**, um link com etapas para corrigir os problemas é enviado ao dispositivo. Quando o usuário final corrige o problema (por exemplo, definir senha, criptografia), o Intune que gerencia as políticas de conformidade atualiza o status de conformidade do dispositivo no Azure AD.

Quando o dispositivo é avaliado como registro e em conformidade, a sincronização de email deve acontecer dentro de alguns minutos.

## Onde ir daqui
Agora que você sabe como proteger emails e documentos corporativos, pode ler sobre como [proteger anexos de email](protect-email-attachments.md). Ou, se você estiver pronto, saiba mais sobre [como implementar uma solução para proteger seu email corporativo](implement-solution.md).



<!--HONumber=Aug16_HO1-->


