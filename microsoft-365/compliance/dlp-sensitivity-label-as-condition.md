---
title: Usar rótulos de confidencialidade como condições em políticas DLP (visualização)
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
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235709"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a>Usar rótulos de confidencialidade como condições em políticas DLP (visualização)

Você pode usar os [rótulos de confidencialidade](sensitivity-labels.md) como uma condição nas políticas DLP para esse local:

- Mensagens de email do Exchange Online
- SharePoint Online
- Sites do OneDrive for Business
- Dispositivos do Windows 10

Os rótulos de confidencialidade aparecem como uma opção na lista **Conteúdo contém**.

![rótulo de confidencialidade como uma condição](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a>Itens com suporte, cenários e dicas de política

Você pode usar rótulos de confidencialidade como condições nestes itens e nestes cenários.

### <a name="supported-items"></a>Itens com suporte

|serviço  |tipo de item  |disponível para a dica de política  |aplicável  |
|---------|---------|---------|---------|
|Exchange    |mensagem de email         |sim         |sim         |
|Exchange    |anexos de email         |não *         |não *         |
|SharePoint Online     |itens no SharePoint Online         |sim         |sim         |
|OneDrive for Business     |itens         |sim         |sim         |
|Teams     |Teams e mensagens de canal         |não se aplica         |não se aplica         |
|Teams     |anexos         |sim **         |sim **         |
|Dispositivos do Windows 10 (visualização)     |itens         |sim         |sim         |
|MCAS (visualização) |itens         |sim         |sim         |

\* A detecção de DLP de rótulos de confidencialidade em emails possui suporte. A detecção de DLP de anexos de email rotulados como confidenciais não.

\** Anexos enviados no Teams em chats individuais ou canais são carregados automaticamente para o One Drive for Business e para o SharePoint. Portanto, se o SharePoint Online ou One Drive for Business estiverem incluídos como locais na sua política de DLP, os anexos enviados pelo Teams serão incluídos automaticamente no escopo dessa condição. O Teams como local não precisa ser selecionado na política de DLP.

### <a name="supported-scenarios"></a>Cenários com suporte

- O administrador de DLP poderá ver uma lista de todos os rótulos de confidencialidade no locatário quando eles optarem por incluir um ou mais rótulos de confidencialidade como uma condição.
- O uso de rótulos de confidencialidade como uma condição tem suporte em todas as cargas de trabalho, como indicado na matriz de suporte acima
- As dicas de política DLP continuarão a ser mostradas entre cargas de trabalho (exceto o Outlook Win32) para políticas DLP que contêm rótulos de confidencialidade como uma condição.
- Os rótulos de confidencialidade também serão exibidos como parte do email do relatório de incidentes se uma política DLP com rótulos de confidencialidade for correspondida.
- Os detalhes dos rótulos de confidencialidade também serão mostrados na regra de correspondência do log de auditoria da DLP para obter uma correspondência à política DLP que contenha o rótulos de confidencialidade como uma condição.


### <a name="support-policy-tips"></a>Dicas de política com suporte


|carga de trabalho  |dicas de política com suporte/sem suporte  |
|---------|---------|
|OWA |    com suporte     |
|Outlook Win 32    |  sem suporte.       |
|SharePoint   |   com suporte      |
|OneDrive for Business    |    com suporte     |
|dispositivos de ponto de extremidade   |  sem suporte.       |
