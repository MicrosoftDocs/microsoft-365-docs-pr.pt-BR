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
# <a name="raw-data-streaming-api"></a><span data-ttu-id="b7d1d-104">API de Streaming de Dados Brutos</span><span class="sxs-lookup"><span data-stu-id="b7d1d-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7d1d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b7d1d-105">**Applies to:**</span></span>
- [<span data-ttu-id="b7d1d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b7d1d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="b7d1d-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b7d1d-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b7d1d-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="b7d1d-109">Transmitir eventos de Busca Avançada para Hubs de Eventos e/ou conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>


<span data-ttu-id="b7d1d-110">O Microsoft Defender para Ponto de Extremidade oferece suporte a eventos de streaming disponíveis por meio da [Busca](../defender/advanced-hunting-overview.md) Avançada para [hubs](/azure/event-hubs/) de eventos e/ou conta de armazenamento do [Azure.](/azure/storage/common/storage-account-overview)</span><span class="sxs-lookup"><span data-stu-id="b7d1d-110">Microsoft Defender for Endpoint supports streaming events available through [Advanced Hunting](../defender/advanced-hunting-overview.md) to an [Event Hubs](/azure/event-hubs/) and/or [Azure storage account](/azure/storage/common/storage-account-overview).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="b7d1d-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b7d1d-111">In this section</span></span>

<span data-ttu-id="b7d1d-112">Tópico</span><span class="sxs-lookup"><span data-stu-id="b7d1d-112">Topic</span></span> | <span data-ttu-id="b7d1d-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="b7d1d-113">Description</span></span>
:---|:---
[<span data-ttu-id="b7d1d-114">Transmitir eventos do Microsoft Defender para Ponto de Extremidade para Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="b7d1d-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="b7d1d-115">Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Defender for Endpoint para transmitir [a Busca Avançada](advanced-hunting-overview.md) para Hubs de Eventos.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="b7d1d-116">Stream Defender for Endpoint events to your Azure storage account</span><span class="sxs-lookup"><span data-stu-id="b7d1d-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="b7d1d-117">Saiba mais sobre a habilitação da API de streaming em seu locatário e configurar o Defender for Endpoint para transmitir [a Busca](advanced-hunting-overview.md) Avançada para sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b7d1d-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b7d1d-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b7d1d-118">Related topics</span></span>
- [<span data-ttu-id="b7d1d-119">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="b7d1d-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b7d1d-120">Documentação dos Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="b7d1d-120">Azure Event Hubs documentation</span></span>](/azure/event-hubs/)
- [<span data-ttu-id="b7d1d-121">Documentação Armazenamento conta do Azure</span><span class="sxs-lookup"><span data-stu-id="b7d1d-121">Azure Storage Account documentation</span></span>](/azure/storage/common/storage-account-overview)