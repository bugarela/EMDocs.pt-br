---
# required metadata

title: Opções de gerenciamento de email
description:
keywords:
author: robmazz
manager: swadhwa
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: 9b89da63-039f-4831-b204-28c0681478fe

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opções de gerenciamento de email

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

O principal motivo para implementar uma solução de gerenciamento de dispositivos móveis normalmente é oferecer acesso gerenciado ao email corporativo em dispositivos móveis. Por exemplo, no MDM para Office 365, é possível criar uma [política de segurança](https://technet.microsoft.com/library/ms.o365.cc.newdevicepolicy.aspx) que fornece acesso gerenciado básico para caixas de correio de email hospedadas no Exchange Online ou acesso por meio de aplicativos do Office (no iOS e Android). Essa política impõe configurações básicas de conformidade de dispositivos móveis, como exigir uma senha de dispositivo e criptografia de dispositivo, antes que o dispositivo tenha permissão de se conectar a uma caixa de correio do usuário.

Você segue um processo semelhante para configurar as opções de gerenciamento de email no Intune, bem como em implantações híbridas do Intune e do ConfigMgr. A principal diferença é que você pode implementar opções mais avançadas de gerenciamento de email do que no MDM para o Office 365. Por exemplo, com o Intune autônomo, é possível configurar o acesso a email condicional para permitir o acesso a caixas de correio hospedadas no Exchange Online e no Exchange no Local, bem como configurar perfis de email personalizados. O Intune habilita esses recursos usando políticas de configuração e conformidade.  As implantações híbridas do Intune e do ConfigMgr também dão suporte ao acesso a email condicional, mas somente para caixas de correio hospedadas no Exchange Online.

No cenário mostrado abaixo na Figura 6, o usuário registrou seu dispositivo no Intune e agora está tentando acessar seu email corporativo usando o Office 365 ou o Exchange local. Com base nas configurações definidas pelo administrador de TI em sua empresa, o Intune executa um processo de verificação de política. Neste cenário, o acesso do usuário será concedido se o dispositivo for criptografado, uma senha for definida e o dispositivo não tiver sido desbloqueado nem modificado. Se um usuário tentar acessar o email corporativo e o dispositivo não estiver registrado ou não for compatível com base nas configurações definidas pelo administrador de TI, o usuário receberá um email explicando o motivo pelo qual o acesso foi bloqueado, junto com as etapas para resolver o problema. 

![Acesso condicional](./media/MDM_Figure_06.png)

**Acesso condicional**

Suas respostas às perguntas na Etapa 1 podem ajudar a determinar como você deseja que os dispositivos sejam gerenciados na solução de gerenciamento de dispositivos móveis. A lista abaixo relaciona as vantagens e desvantagens do gerenciamento de email para cada solução de MDM.

## Intune (autônomo)

**Vantagens**

- Dá suporte ao gerenciamento de email de todos os principais sistemas operacionais de dispositivos móveis (Android, iOS, Windows 10, Windows 8.x e Windows Phone)
- Pode aproveitar os aplicativos de email nativos do dispositivo móvel por meio da integração com o Exchange ActiveSync
- Integração com o Exchange Online por meio do conector de Serviço a Serviço, a fim de permitir o monitoramento e geração relatórios de plataforma cruzada entre o Intune e o Office 365
- Dá suporte à configuração de perfis de email para gerenciar configurações baseadas no Exchange ActiveSync em dispositivos móveis
- Acesso a email condicional para recursos

**Desvantagens**

- Não há suporte para perfis de email para dispositivos móveis baseados no Android

## MDM para o Office 365

**Vantagens**

- Permite o suporte do Exchange ActiveSync para senha, criptografia e conformidade do dispositivo com raiz
- Permite políticas de gerenciamento de dispositivos e exige o registro do dispositivo antes de obter acesso aos aplicativos do Office e do OneDrive para Empresas (iOS e Android)
- Acesso a email condicional para recursos

**Desvantagens**

- Não há suporte para algumas opções avançadas de gerenciamento de email 
- Não há suporte para a implantação de perfis de email (exceto iOS)

## Híbrido (Intune com ConfigMgr)

**Vantagens**

- Conector local do Intune para conectividade híbrida com o Exchange Online
- Integração com o Exchange ActiveSync (a configuração de política mais estrita será imposta)
- Perfis de email
- Acesso condicional para restringir o acesso a email ao Exchange Online
- Políticas de conformidade para definir as regras e as configurações que o dispositivo deve cumprir para obter acesso aos serviços
- As políticas de acesso condicional para cada serviço definem regras para grupos de segurança, grupos do Intune ou como os dispositivos não registrados são gerenciados

**Desvantagens**

- Acesso gerenciado ao email disponível apenas para caixas de correio hospedadas no Exchange Online, não para caixas de correio hospedadas no Exchange local
- A configuração do conector serviço a serviço não deve ser definida se você habilitar o acesso condicional para o Exchange Online e o Exchange local

Explore os detalhes sobre as opções de gerenciamento de configuração de email do dispositivo móvel examinando o seguinte:

- Intune: Como [habilitar perfis de email](/Intune/deployuse/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) e o [acesso a email condicional](/Intune/deployuse/restrict-access-to-email-and-o365-services-with-microsoft-intune)
- ConfigMgr: Como habilitar [perfis de email](https://technet.microsoft.com/library/dn554227.aspx) e o [acesso a email condicional](https://technet.microsoft.com/library/dn919655.aspx)
- MDM para Office 365: [Recursos de gerenciamento de dispositivos móveis](https://technet.microsoft.com/library/ms.o365.cc.devicepolicysupporteddevice.aspx)

<!--HONumber=Apr16_HO2-->


