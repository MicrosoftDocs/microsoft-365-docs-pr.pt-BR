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
ms.openlocfilehash: f6a45629d610ea3cc3ca7d517021a215b72b1439
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688748"
---
# <a name="raw-data-streaming-api"></a><span data-ttu-id="3a553-104">API de Streaming de Dados Brutos</span><span class="sxs-lookup"><span data-stu-id="3a553-104">Raw Data Streaming API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3a553-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3a553-105">**Applies to:**</span></span>
- [<span data-ttu-id="3a553-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3a553-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="3a553-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="3a553-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3a553-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="3a553-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="stream-advanced-hunting-events-to-event-hubs-andor-azure-storage-account"></a><span data-ttu-id="3a553-109">Transmitir eventos de Busca Avançada para Hubs de Eventos e/ou conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="3a553-109">Stream Advanced Hunting events to Event Hubs and/or Azure storage account.</span></span>

<span data-ttu-id="3a553-110">O Defender for Endpoint oferece suporte [](advanced-hunting-overview.md) ao streaming de todos os eventos disponíveis por meio da Busca Avançada para [hubs](https://docs.microsoft.com/azure/event-hubs/) de eventos e/ou conta de armazenamento do [Azure.](https://docs.microsoft.com/azure/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="3a553-110">Defender for Endpoint supports streaming all the events available through [Advanced Hunting](advanced-hunting-overview.md) to an [Event Hubs](https://docs.microsoft.com/azure/event-hubs/) and/or [Azure storage account](https://docs.microsoft.com/azure/event-hubs/).</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4ga]


## <a name="in-this-section"></a><span data-ttu-id="3a553-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3a553-111">In this section</span></span>

<span data-ttu-id="3a553-112">Tópico</span><span class="sxs-lookup"><span data-stu-id="3a553-112">Topic</span></span> | <span data-ttu-id="3a553-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="3a553-113">Description</span></span>
:---|:---
[<span data-ttu-id="3a553-114">Transmitir eventos do Microsoft Defender para Ponto de Extremidade para Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="3a553-114">Stream Microsoft Defender for Endpoint events to Azure Event Hubs</span></span>](raw-data-export-event-hub.md)| <span data-ttu-id="3a553-115">Saiba mais sobre a habilitação da API de streaming em seu locatário e configure o Defender for Endpoint para transmitir [a Busca Avançada](advanced-hunting-overview.md) para Hubs de Eventos.</span><span class="sxs-lookup"><span data-stu-id="3a553-115">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to Event Hubs.</span></span>
[<span data-ttu-id="3a553-116">Stream Defender for Endpoint events to your Azure storage account</span><span class="sxs-lookup"><span data-stu-id="3a553-116">Stream Defender for Endpoint events to your Azure storage account</span></span>](raw-data-export-storage.md)| <span data-ttu-id="3a553-117">Saiba mais sobre a habilitação da API de streaming em seu locatário e configurar o Defender for Endpoint para transmitir [a Busca](advanced-hunting-overview.md) Avançada para sua conta de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="3a553-117">Learn about enabling the streaming API in your tenant and configure Defender for Endpoint to stream [Advanced Hunting](advanced-hunting-overview.md) to your Azure storage account.</span></span>


## <a name="related-topics"></a><span data-ttu-id="3a553-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3a553-118">Related topics</span></span>
- [<span data-ttu-id="3a553-119">Visão geral da Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="3a553-119">Overview of Advanced Hunting</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3a553-120">Documentação dos Hubs de Eventos do Azure</span><span class="sxs-lookup"><span data-stu-id="3a553-120">Azure Event Hubs documentation</span></span>](https://docs.microsoft.com/azure/event-hubs/)
- [<span data-ttu-id="3a553-121">Documentação da Conta de Armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="3a553-121">Azure Storage Account documentation</span></span>](https://docs.microsoft.com/azure/storage/common/storage-account-overview)
