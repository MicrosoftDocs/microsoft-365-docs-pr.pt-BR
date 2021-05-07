---
title: Use rótulos de confidencialidade como condições em políticas DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: saiba mais sobre os serviços e os tipos de item que você pode usar rótulos de confidencialidade como condições em políticas DLP
ms.openlocfilehash: 19bd80de225f703b5c280163e94826498fa097bd
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876290"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a>Use rótulos de confidencialidade como condições em políticas DLP

Você pode usar os [rótulos de confidencialidade](sensitivity-labels.md) como uma condição nas políticas DLP para esse local:

- Mensagens de email do Exchange Online
- SharePoint Online
- Sites do OneDrive for Business
- Dispositivos do Windows 10

Os rótulos de confidencialidade aparecem como uma opção na lista **Conteúdo contém**.

> [!div class="mx-imgBorder"]
> ![rótulo de confidencialidade como condição](../media/dlp-sensitivity-label-as-a-condition.png)

> [!IMPORTANT]
> Como condição, os **Rótulos de Confidencialidade** não estarão disponíveis se você tiver selecionado o **chat do Teams e as mensagens do canal** como um local para aplicar a política DLP.


## <a name="supported-items-scenarios-and-policy-tips"></a>Itens com suporte, cenários e dicas de política

Você pode usar rótulos de confidencialidade como condições nestes itens e nestes cenários.

### <a name="supported-items"></a>Itens com suporte

|Serviço  |Tipo de item  |Disponível para a dica de política  |Aplicável  |
|---------|---------|---------|---------|
|Exchange    |mensagem de email         |sim         |sim         |
|Exchange    |anexos de email         |não *         |sim *         |
|SharePoint Online     |itens no SharePoint Online         |sim         |sim         |
|OneDrive for Business     |itens         |sim         |sim         |
|Teams     |Teams e mensagens de canal         |não se aplica         |não se aplica         |
|Teams     |anexos         |sim **         |sim **         |
|Dispositivos Windows 10     |itens         |sim         |sim         |
|MCAS (visualização) |itens         |sim         |sim         |

\* A detecção de DLP e a aplicação de rótulos de confidencialidade em emails e anexos são suportados em trânsito. As dicas de política DLP de rotulagem de confidencialidade não são anexos de email.

\** Anexos enviados no Teams em chats individuais ou canais são carregados automaticamente para o OneDrive for Business e para o SharePoint. Portanto, se o SharePoint Online ou OneDrive for Business estiverem incluídos como locais na sua política de DLP, os anexos enviados pelo Teams serão incluídos automaticamente no escopo dessa condição. O Teams como local não precisa ser selecionado na política de DLP.

### <a name="supported-scenarios"></a>Cenários com suporte

- O administrador de DLP poderá ver uma lista de todos os rótulos de confidencialidade no locatário quando eles optarem por incluir um ou mais rótulos de confidencialidade como uma condição.

- Como condição, o uso de rótulos de confidencialidade tem suporte em todas as cargas de trabalho, como indicado na matriz de suporte acima.

- As dicas de política DLP continuarão a ser mostradas entre cargas de trabalho (exceto o Outlook Win32) para políticas DLP que contêm rótulos de confidencialidade como uma condição.

- Os rótulos de confidencialidade também serão exibidos como parte do email do relatório de incidentes se uma política DLP com rótulos de confidencialidade for correspondida.

- Os detalhes dos rótulos de confidencialidade também serão mostrados na regra de correspondência do log de auditoria da DLP para obter uma correspondência à política DLP que contenha o rótulos de confidencialidade como uma condição.


### <a name="support-policy-tips"></a>Dicas de política com suporte


|Carga de trabalho  |Dicas de política com suporte/sem suporte  |
|---------|---------|
|OWA |    com suporte     |
|Outlook Win 32    |  sem suporte.       |
|SharePoint   |   com suporte      |
|OneDrive for Business    |    com suporte     |
|dispositivos de ponto de extremidade   |  sem suporte.       |
