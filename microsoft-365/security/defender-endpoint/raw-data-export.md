---
title: Transmitir Microsoft 365 eventos do Defender
description: Saiba como configurar o Microsoft 365 Defender para transmitir eventos de Busca Avançada para Hubs de Eventos ou conta de armazenamento do Azure
keywords: exportação de dados brutos, API de streaming, API, hubs de eventos, armazenamento do Azure, conta de armazenamento, Busca Avançada, compartilhamento de dados brutos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0c25ec8bc88a2714fb2f02ef8641c3eae700efe0
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730685"
---
# <a name="streaming-api"></a>Streaming API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Transmitir eventos de Busca Avançada para Hubs de Eventos e/ou conta de armazenamento do Azure.

Microsoft 365 O Defender dá suporte ao streaming de todos os eventos disponíveis por meio da [Busca](../defender/advanced-hunting-overview.md) Avançada para [hubs](/azure/event-hubs/) de eventos e/ou conta de armazenamento do [Azure.](/azure/event-hubs/)



## <a name="in-this-section"></a>Nesta seção

Tópico | Descrição
:---|:---
[Transmitir eventos para hubs de eventos do Azure](raw-data-export-event-hub.md)| Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Microsoft 365 Defender para transmitir [a Busca Avançada](../defender/advanced-hunting-overview.md) para Hubs de Eventos.
[Transmitir eventos para sua conta de armazenamento do Azure](raw-data-export-storage.md)| Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Microsoft 365 Defender para transmitir [a](../defender/advanced-hunting-overview.md) Busca Avançada para sua conta de armazenamento do Azure.


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da Busca Avançada](../defender/advanced-hunting-overview.md)
- [Documentação dos Hubs de Eventos do Azure](/azure/event-hubs/)
- [Documentação Armazenamento conta do Azure](/azure/storage/common/storage-account-overview)
