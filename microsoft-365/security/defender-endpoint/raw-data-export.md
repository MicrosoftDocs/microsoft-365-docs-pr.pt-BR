---
title: Transmitir evento do Microsoft Defender para Ponto de Extremidade
description: Saiba como configurar o Microsoft Defender ATP para transmitir eventos de Busca Avançada para Hubs de Eventos ou conta de armazenamento do Azure
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
ms.openlocfilehash: 22f4e4c974b60e291273eb9bebfa34583f4e2fb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053295"
---
# <a name="raw-data-streaming-api"></a>API de Streaming de Dados Brutos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a>Transmitir eventos de Busca Avançada para Hubs de Eventos e/ou conta de armazenamento do Azure.

O Defender for Endpoint oferece suporte [](advanced-hunting-overview.md) ao streaming de todos os eventos disponíveis por meio da Busca Avançada para [hubs](https://docs.microsoft.com/azure/event-hubs/) de eventos e/ou conta de armazenamento do [Azure.](https://docs.microsoft.com/azure/event-hubs/)

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a>Nesta seção

Tópico | Descrição
:---|:---
[Transmitir eventos do Microsoft Defender para Ponto de Extremidade para Hubs de Eventos do Azure](raw-data-export-event-hub.md)| Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Defender for Endpoint para transmitir [a Busca Avançada](advanced-hunting-overview.md) para Hubs de Eventos.
[Stream Defender for Endpoint events to your Azure storage account](raw-data-export-storage.md)| Saiba mais sobre a habilitação da API de streaming em seu locatário e configurar o Defender for Endpoint para transmitir [a Busca](advanced-hunting-overview.md) Avançada para sua conta de armazenamento do Azure.


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da Busca Avançada](advanced-hunting-overview.md)
- [Documentação dos Hubs de Eventos do Azure](https://docs.microsoft.com/azure/event-hubs/)
- [Documentação da Conta de Armazenamento do Azure](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
