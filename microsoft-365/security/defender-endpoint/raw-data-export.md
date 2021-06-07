---
title: Transmitir evento do Microsoft Defender para Ponto de Extremidade
description: Saiba como configurar o Microsoft Defender para o Ponto de Extremidade para transmitir eventos de Busca Avançada para Hubs de Eventos ou conta de armazenamento do Azure
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
ms.custom: api
ms.openlocfilehash: c8403dee11070dcf0825fad2502d8d21d54933fd
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782748"
---
# <a name="raw-data-streaming-api"></a>API de Streaming de Dados Brutos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Transmitir eventos de Busca Avançada para Hubs de Eventos e/ou conta de armazenamento do Azure.


O Microsoft Defender para Ponto de Extremidade oferece suporte a eventos de streaming disponíveis por meio da [Busca](../defender/advanced-hunting-overview.md) Avançada para [hubs](/azure/event-hubs/) de eventos e/ou conta de armazenamento do [Azure.](/azure/storage/common/storage-account-overview)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>Nesta seção

Tópico | Descrição
:---|:---
[Transmitir eventos do Microsoft Defender para Ponto de Extremidade para Hubs de Eventos do Azure](raw-data-export-event-hub.md)| Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Defender for Endpoint para transmitir [a Busca Avançada](advanced-hunting-overview.md) para Hubs de Eventos.
[Stream Defender for Endpoint events to your Azure storage account](raw-data-export-storage.md)| Saiba mais sobre a habilitação da API de streaming em seu locatário e configurar o Defender for Endpoint para transmitir [a Busca](advanced-hunting-overview.md) Avançada para sua conta de armazenamento do Azure.


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da Busca Avançada](advanced-hunting-overview.md)
- [Documentação dos Hubs de Eventos do Azure](/azure/event-hubs/)
- [Documentação Armazenamento conta do Azure](/azure/storage/common/storage-account-overview)