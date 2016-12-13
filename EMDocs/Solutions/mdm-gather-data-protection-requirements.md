---
title: "Reunir os requisitos de proteção de dados"
description: "Este artigo fornece um conjunto de requisitos comuns que devem ser usados para proteção de dados em um cenário de gerenciamento de dispositivo móvel."
keywords: 
author: YuriDio
ms.author: yurid
manager: swadhwa
ms.date: 11/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 98f7bd00-4be7-478e-82ea-6046813f1556
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5adb7f68efacdfa20d78c3cf5853fa374793140a
ms.openlocfilehash: 9cf26f4ead50e00580fc5abe1983ba88ee4c8ce9


---

# <a name="gather-your-data-protection-requirements"></a>Reunir os requisitos de proteção de dados

>[!NOTE]
>Este tópico faz parte de um guia de considerações sobre design mais amplo. Se você quiser começar do início do guia, confira o [tópico principal](mdm-design-considerations-guide.md). Para obter uma cópia baixável deste guia inteiro, visite a [Galeria do TechNet](https://gallery.technet.microsoft.com/Mobile-Device-Management-7d401582).

Para ajudar a definir os requisitos de proteção de dados de sua organização em relação aos dispositivos móveis, é útil pensar primeiro sobre os requisitos de proteção de dados que a sua organização já tem em vigor. Por exemplo, talvez sua empresa precise cumprir regulamentos específicos, ou talvez você já tenha uma política sobre a proteção de dados.

Anote esses requisitos de alto nível primeiro para ter uma base para fazer perguntas mais granulares que ajudarão a levá-lo a projetar melhores decisões sobre design para a sua solução de MDM.  Ao definir esses requisitos, considere o seguinte:

- Criptografia de dados em repouso: como mostra a Figura 8, os dados da empresa serão armazenados no dispositivo móvel do usuário. Considere se o seguinte é importante para a sua empresa:
    - A solução de MDM dá suporte à criptografia de todo o disco e cartões SD do dispositivo móvel?
        - Se sim, para quais sistemas operacionais?
    - A solução de MDM dá suporte à criptografia de dados do aplicativo?
        - Se sim, para quais sistemas operacionais?
        - Se sim, para quais aplicativos?
- Criptografia de dados em trânsito: independentemente de quem possui os dados, em algum momento durante a comunicação de dados, os dados estarão em trânsito entre o dispositivo móvel e um servidor da empresa (ou um serviço Web). Você deve entender quais recursos a solução de MDM tem para proteger os dados em trânsito. Considere se o seguinte é importante para a sua empresa:
    - A solução de MDM dá suporte à criptografia de dados em trânsito?
        - Se sim, para quais sistemas operacionais?
        - Se sim, quais recursos estão disponíveis?
    - Quais são as opções oferecidas pela solução de MDM para proteger os dados em trânsito?
- Diferenciação de dados: também é importante entender se os dados de sua empresa devem ser tratados de modo diferente dos dados do usuário. Diferenciação, separação ou isolamento são alguns termos que podem ser usados para descrever essa funcionalidade. Ao projetar sua solução de MDM, considere:
    - A solução de MDM dá suporte à separação de dados?
        - Em caso afirmativo, é possível apagar os dados de sua empresa e ao mesmo tempo preservar os dados do usuário do dispositivo móvel?
    - A capacidade de separação de dados de MDM garante que apenas aplicativos confiáveis possam acessar dados localizados no dispositivo móvel?
    - As soluções de MDM oferecem suporte à separação de dados de acordo com a identidade do usuário?
    - A solução de MDM dá suporte à conteinerização?
        - Nesse caso, é possível criptografar dados localizados em um contêiner específico?
- Proteção de dispositivos móveis: já que pode haver diferentes plataformas de dispositivos móveis usadas em sua organização, você deve entender quais recursos de proteção estão disponíveis em cada plataforma de dispositivo móvel. Cada plataforma de dispositivo móvel pode controlar e proteger dispositivos usando métodos diferentes e em diferentes níveis de granularidade. Se um conjunto de dispositivos móveis tiver um conjunto mais granular de configuração que os outros, você precisará de um conjunto comum de opções para proteger os dispositivos, ao mesmo tempo que usa políticas personalizadas para aumentar a segurança de cada plataforma de dispositivo móvel com suporte de sua organização.

A lista abaixo inclui opções comuns que devem ter o suporte da solução de MDM para proteger os dispositivos móveis:

- É necessário uma senha para desbloquear dispositivos móveis
- Exigindo um tipo de senha – o número mínimo de caracteres e tipos de caracteres
- Comprimento mínimo da senha
- Número de falhas de entrada repetidas a serem permitidas antes do apagamento do dispositivo móvel
- Minutos de inatividade antes que a tela se apague
- Lembrando o histórico de senha – impedindo a reutilização de senhas anteriores
- Expiração da senha (dias)
- É necessária a criptografia no dispositivo móvel
- É necessária a criptografia em cartões de memória
- Permitindo o retorno ocioso sem uma senha

>[!TIP]
> No Windows Phone 8.1, a política Permitir retorno ocioso sem senha pode ser configurada usando o [Protocolo de gerenciamento de dispositivos empresariais do Windows Phone 8.1](http://download.microsoft.com/download/C/A/0/CA091018-1A43-4063-B70B-20B9901F4D10/Windows Phone 8.1 MDM Protocol.pdf).



<!--HONumber=Nov16_HO4-->


