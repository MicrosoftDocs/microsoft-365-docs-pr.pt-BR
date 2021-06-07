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
ms.openlocfilehash: 3e6d4df1c2c0f4934de1e8a54e8c1676aae230e3
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771616"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="459f9-104">API de Streaming de Dados Brutos</span><span class="sxs-lookup"><span data-stu-id="459f9-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="459f9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="459f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="459f9-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="459f9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="459f9-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="459f9-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="459f9-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="459f9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="459f9-109">Transmitir eventos de Busca Avançada para Hubs de Eventos e/ou conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="459f9-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="459f9-110">O Defender for Endpoint oferece suporte [](advanced-hunting-overview.md) ao streaming de todos os eventos disponíveis por meio da Busca Avançada para [hubs](/azure/event-hubs/) de eventos e/ou conta de armazenamento do [Azure.](/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="459f9-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="459f9-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="459f9-111">In this section</span></span>

<span data-ttu-id="459f9-112">Tópico</span><span class="sxs-lookup"><span data-stu-id="459f9-112">Topic</span></span> | <span data-ttu-id="459f9-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="459f9-113">Description</span></span>
:---|:---
[<span data-ttu-id="459f9-114">Transmitir eventos do Microsoft Defender para Ponto de Extremidade para Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="459f9-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="459f9-115">Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Defender for Endpoint para transmitir [a Busca Avançada](advanced-hunting-overview.md) para Hubs de Eventos.</span><span class="sxs-lookup"><span data-stu-id="459f9-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="459f9-116">Stream Defender for Endpoint events to your Azure storage account</span><span class="sxs-lookup"><span data-stu-id="459f9-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="459f9-117">Saiba mais sobre a habilitação da API de streaming em seu locatário e configurar o Defender for Endpoint para transmitir [a Busca](advanced-hunting-overview.md) Avançada para sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="459f9-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="459f9-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="459f9-118">Related topics</span></span>
- [<span data-ttu-id="459f9-119">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="459f9-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="459f9-120">Documentação dos Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="459f9-120">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="459f9-121">Documentação Armazenamento conta do Azure</span><span class="sxs-lookup"><span data-stu-id="459f9-121">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)