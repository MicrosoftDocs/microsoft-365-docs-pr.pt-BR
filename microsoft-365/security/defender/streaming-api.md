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
ms.openlocfilehash: fad3dd64c9acf079bd8da778d417240c44031569
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772408"
---
# <a name="streaming-api"></a><span data-ttu-id="40e1e-104">Streaming API</span><span class="sxs-lookup"><span data-stu-id="40e1e-104">Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40e1e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="40e1e-105">**Applies to:**</span></span>
- [<span data-ttu-id="40e1e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40e1e-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="40e1e-107">Transmitir eventos de Busca Avançada para Hubs de Eventos e/ou conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="40e1e-107">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="40e1e-108">Microsoft 365 O Defender dá suporte ao streaming de todos os eventos disponíveis por meio da [Busca](../defender/advanced-hunting-overview.md) Avançada para [hubs](/azure/event-hubs/) de eventos e/ou conta de armazenamento do [Azure.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="40e1e-108">Microsoft 365 Defender supports streaming all the events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>



## <a name="in-this-section"></a><span data-ttu-id="40e1e-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="40e1e-109">In this section</span></span>

<span data-ttu-id="40e1e-110">Tópico</span><span class="sxs-lookup"><span data-stu-id="40e1e-110">Topic</span></span> | <span data-ttu-id="40e1e-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="40e1e-111">Description</span></span>
:---|:---
[<span data-ttu-id="40e1e-112">Transmitir eventos para hubs de eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="40e1e-112">Stream events to Azure Event Hubs</span></span>](streaming-api-event-hub.md)| <span data-ttu-id="40e1e-113">Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Microsoft 365 Defender para transmitir [a Busca Avançada](../defender/advanced-hunting-overview.md) para Hubs de Eventos.</span><span class="sxs-lookup"><span data-stu-id="40e1e-113">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](../defender/advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="40e1e-114">Transmitir eventos para sua conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="40e1e-114">Stream events to your Azure storage account</span></span>](streaming-api-storage.md)| <span data-ttu-id="40e1e-115">Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Microsoft 365 Defender para transmitir [a](advanced-hunting-overview.md) Busca Avançada para sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="40e1e-115">Learn about enabling the streaming API in your tenant and configure Microsoft 365 Defender to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="40e1e-116">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="40e1e-116">Related topics</span></span>
- [<span data-ttu-id="40e1e-117">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="40e1e-117">Overview of Advanced Hunting</span></span>](../defender/advanced-hunting-overview.md)
- [<span data-ttu-id="40e1e-118">Documentação dos Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="40e1e-118">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="40e1e-119">Documentação Armazenamento conta do Azure</span><span class="sxs-lookup"><span data-stu-id="40e1e-119">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)
