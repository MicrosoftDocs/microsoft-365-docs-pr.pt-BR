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
ms.openlocfilehash: 971cc757dcbd0a190917d2a5f11eb7f68b758008
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778192"
---
# <a name="streaming-api"></a><span data-ttu-id="89c31-104">Streaming API</span><span class="sxs-lookup"><span data-stu-id="89c31-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89c31-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="89c31-105">**Applies to:**</span></span>
- [<span data-ttu-id="89c31-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89c31-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="89c31-107">Transmitir eventos de Busca Avançada para Hubs de Eventos e/ou conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="89c31-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="89c31-108">Microsoft 365 O Defender dá suporte ao streaming de todos os eventos disponíveis por meio da [Busca](../defender/advanced-hunting-overview.md) Avançada para [hubs](/azure/event-hubs/) de eventos e/ou conta de armazenamento do [Azure.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="89c31-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="89c31-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="89c31-109">In this section</span></span>

<span data-ttu-id="89c31-110">Tópico</span><span class="sxs-lookup"><span data-stu-id="89c31-110">Topic</span></span> | <span data-ttu-id="89c31-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="89c31-111">Description</span></span>
:---|:---
[<span data-ttu-id="89c31-112">Transmitir eventos para hubs de eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="89c31-112">Stream events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="89c31-113">Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Microsoft 365 Defender para transmitir [a Busca Avançada](../defender/advanced-hunting-overview.md) para Hubs de Eventos.</span><span class="sxs-lookup"><span data-stu-id="89c31-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="89c31-114">Transmitir eventos para sua conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="89c31-114">Stream events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="89c31-115">Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Microsoft 365 Defender para transmitir [a](../defender/advanced-hunting-overview.md) Busca Avançada para sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="89c31-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="89c31-116">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="89c31-116">Related topics</span></span>
- [<span data-ttu-id="89c31-117">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="89c31-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="89c31-118">Documentação dos Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="89c31-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="89c31-119">Documentação Armazenamento conta do Azure</span><span class="sxs-lookup"><span data-stu-id="89c31-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
