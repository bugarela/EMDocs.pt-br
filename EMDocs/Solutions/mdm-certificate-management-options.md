---
# required metadata

title: Opções de gerenciamento de certificados
description:
keywords:
author: andredm7
manager: swadhwa
ms.date: 05/31/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: c3d350b5-4437-4f3d-907f-57ce6a819a74

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: 
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Opções de gerenciamento de certificados

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

O uso de gerenciamento de certificados digitais e de perfis de certificado tem o suporte de cenários de implantação do [Intune](/Intune/deployuse/secure-resource-access-with-certificate-profiles) autônomo e do [Intune e do ConfigMgr](https://technet.microsoft.com/library/dn261202.aspx) híbridos. Esses recursos permitem que você implante certificados raiz confiáveis em dispositivos móveis, bem como perfis baseados no protocolo SCEP que instruem os dispositivos móveis a obter certificados adicionais de um servidor NDES em sua organização.

Como o SCEP tem o suporte nativo do iOS, Windows 10 e 8.1, Windows Phone 10 e 8.1 e também tem suporte por meio do aplicativo Portal de Empresa do Microsoft Intune para Android, o uso desse protocolo de registro oferece a vantagem de gerar a chave privada diretamente no dispositivo móvel. A chave privada nunca é gerada, armazenada em cache ou armazenada pelo ConfigMgr ou Intune, o que ajuda a manter o dispositivo móvel seguro.

A figura abaixo mostra como o Intune e o ConfigMgr usam o NDES para fornecer o provisionamento seguro de certificados em dispositivos móveis usando o SCEP:

![Provisionamento seguro de certificados](./media/MDM_Figure_07.png)

**Provisionamento seguro de certificados**

1. Uma política que inclui as propriedades do certificado para o registro do SCEP é criada no serviço do Intune.
2. O Intune converte a política em um protocolo de gerenciamento de dispositivos móveis de plataforma (como OMA-DM para Windows 10 e Windows 8.1) e a envia para o dispositivo
3. O dispositivo móvel recebe a política de e inicia uma solicitação de registro por meio do NDES
4. O NDES encaminha a solicitação para o ConfigMgr
5. O ConfigMgr compara os atributos de solicitação da solicitação do SCEP para uma correspondência de autenticação e envia a confirmação de volta ao NDES.
6. O NDES envia uma solicitação de emissão de certificado à AC e envia o certificado para a função NDES.
7. A função do NDES envia o certificado para o dispositivo.

Dependendo de como você respondeu às perguntas na Tarefa 3, você precisa conseguir determinar como deseja que os certificados sejam gerenciados na solução de gerenciamento de dispositivos móveis. Atualmente, o MDM for Office 365 não oferece suporte ao gerenciamento de perfis de certificado para dispositivos móveis. 

A lista abaixo ajudará você a entender as vantagens e desvantagens do gerenciamento de perfis de certificados para um cenário de implantação do Intune e do Intune com ConfigMgr híbrido:

## Intune (autônomo)

**Vantagens**

- Dá suporte aos perfis de certificado em todos os principais sistemas operacionais de dispositivos móveis (Android, iOS, Windows 10, Windows 8.x e Windows Phone)
- A plataforma dá suporte ao protocolo SCEP
- Os perfis de certificado podem configurar automaticamente dispositivos móveis para que os recursos da empresa possam ser acessados sem a necessidade de instalar certificados manualmente nem usar um processo de segurança não aprovado
- Os certificados podem ser revogados automaticamente quando o dispositivo for desativado do gerenciamento, apagado seletivamente ou bloqueado da hierarquia de gerenciamento

**Desvantagens**

- Para usar perfis de certificado, deve existir alguma infraestrutura local. Você deve integrar a seguinte infraestrutura local com o Intune:
 - Um servidor que executa o Serviço de Registro de Dispositivo de Rede
 - Uma Autoridade de Certificação Corporativa
 - O conector de NDES do Intune, que é instalado no servidor que executa o NDES

## MDM para o Office 365

- Não há suporte para perfis de certificado no MDM para Office 365.

## Híbrido (Intune com ConfigMgr)

**Vantagens**

- Todas as vantagens do Intune autônomo, além das seguintes:
 - Também dá suporte ao gerenciamento de certificados para dispositivos não móveis

**Desvantagens**

- Para usar perfis de certificado, deve existir alguma infraestrutura local. 
- Você deve integrar a seguinte infraestrutura local com o Intune:
 - Um servidor que executa o Serviço de Registro de Dispositivo de Rede
 - Uma Autoridade de Certificação Corporativa
 - O conector de NDES do Intune, que é instalado no servidor que executa o NDES

Para obter mais detalhes sobre as opções de gerenciamento de certificados de dispositivo móvel, leia como [habilitar perfis de certificado](/Intune/deployuse/secure-resource-access-with-certificate-profiles) no Intune e compare esses requisitos e procedimentos com a [habilitação de perfis de certificado](https://technet.microsoft.com/library/dn261202.aspx) no System Center 2012 R2 Configuration Manager.

<!--HONumber=Jun16_HO1-->


