---
title: Proteger anexos de email da empresa
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: fc9c7d79-d2ca-4cb2-8456-c7a88cbbf6fd
author: karthikaraman
---

# Proteger emails e anexos contra vazamento de dados
[Proteção de documentos e emails corporativos](../Solutions/protect-corporate-email-documents.md) descreveu como você pode ter certeza de que apenas dispositivos em conformidade poderão acessar emails corporativos. No entanto, o conteúdo de email e anexos de email não são protegidos apenas protegendo o acesso. O conteúdo pode ser copiado, movido, salvo em um local diferente ou compartilhado com outro usuário. O EMS resolve esse problema usando as políticas MAM (gerenciamento de aplicativo móvel).

Aplicativos gerenciados são aplicativos implantados pelo administrador de TI que estão de acordo com os requisitos de segurança da empresa. Com esses aplicativos, a TI tem controle direto sobre implantação, gerenciamento contínuo, como inventário ou atualizações, e apagamento seletivo de aplicativos e seus dados associados. Além disso, por meio de um conjunto de políticas MAM (gerenciamento de aplicativo móvel), o Intune permite modificar a funcionalidade de aplicativos e restringir o compartilhamento de dados, como:

-   Bloquear copiar e colar ou impedir a transferência de dados de um aplicativo gerenciado para um aplicativo sem política MAM.

-   Impedir backup para armazenamento em nuvem particular, impedindo Salvar como, etc.

-   Proteger o acesso a aplicativo exigindo credenciais corporativas ou PIN/senha em um aplicativo protegido por MAM.

-   Configurar o aplicativo para abrir todos os links da Web dentro do navegador do Intune gerenciado.

-   Limpe seletivamente apenas os dados que estão associados ao aplicativo gerenciado. Quando um dispositivo é perdido, roubado ou deixa de ser gerenciado pela sua equipe de TI, um apagamento seletivo pode remover todos os dados corporativos dos aplicativos, deixando apenas dados pessoais do aplicativo. Isso é conhecido como várias identidades.

Com [Azure Rights Management Services](https://technet.microsoft.com/en-us/library/jj585026.aspx), você pode estender a proteção de email das seguintes maneiras:

-   Mensagens de email podem ser criptografadas para que somente os usuários certos possam ler ou exibir o conteúdo dentro ou fora da empresa.

-   Os usuários podem proteger mensagens de email e o destinatário pode ler e usar emails protegidos enviados a eles.

-   Um administrador pode definir regras para:

    -   Aplicar automaticamente as regras a um grupo específico de destinatários ou criar modelos para departamentos específicos.

    -   Detectar automaticamente e aplicar regras a mensagens de email com conteúdo confidencial. A regra pode ser baseada em remetente, destinatário, assunto da mensagem ou conteúdo.

    -   Detectar conteúdo confidencial e alertar o remetente para aplicar as regras de proteção antes de enviar o email.

## Componentes de aplicativo gerenciados

-   O **Microsoft Intune** é onde você configura as políticas, associa as políticas ao aplicativo ou usa a ferramenta de disposição de aplicativo para habilitar um aplicativo interno a usar políticas de gerenciamento de aplicativo móvel.

-   **O portal da empresa a** é um aplicativo executado nativamente em cada dispositivo ou baseado em navegador. A TI implanta os aplicativos gerenciados para usuários ou dispositivos, e os usuários finais podem instalar o aplicativo por meio do portal. As políticas associadas aos aplicativos são transportadas para o dispositivo com os aplicativos.

![Gráfico que mostra como as políticas para aplicativos gerenciados são tratadas por meio do portal da empresa e do Microsoft Intune](./media/ProtectEmail/CADataSheet-Diagram-Apps.png)

## A experiência de administração de TI:
Seu administrador de TI cria as políticas de gerenciamento de aplicativo móvel, associa a política ao aplicativo e a implanta para usuários ou dispositivos. Quando o aplicativo gerenciado é instalado no dispositivo, as restrições de aplicativo entram em vigor. Criar e implantar aplicativos gerenciados envolvem pouco ou nenhum esforço adicional:

-   Há aplicativos existentes que já têm o SDK do aplicativo que permite aplicar restrições ao aplicativo. Eles não exigem qualquer outro processamento, apenas adicionar um link que aponte para uma loja de aplicativos, como iTunes ou Google Play. Leia [este](https://technet.microsoft.com/en-us/library/dn708489.aspx) artigo para ver a lista de aplicativos gerenciados.

-   Se você quiser gerenciar aplicativos criados internamente, é possível reempacotar os aplicativos com a ferramenta de disposição de texto do aplicativo Microsoft Intune. A ferramenta reempacota o aplicativo, o que permite aplicar restrições ao aplicativo.

## A experiência do usuário final
Os usuários finais podem instalar aplicativos gerenciados e usá-los para fazer seu trabalho. Eles só poderão mover ou compartilhar dados entre aplicativos gerenciados. Qualquer tentativa de mover dados para fora do ecossistema do aplicativo gerenciado será bloqueada.

## Onde ir daqui
Agora que você sabe como [proteger emails e documentos corporativos](../Solutions/protect-corporate-email-documents.md), bem como anexos de email, é possível aprender a [implementar uma solução que proteja o email corporativo](../Solutions/implement-solution.md).


<!--HONumber=Apr16_HO2-->


