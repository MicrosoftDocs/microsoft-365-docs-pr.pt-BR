---
title: Sinalizadores de eventos de linha do tempo do dispositivo do Microsoft Defender for Endpoint
description: Usar os sinalizadores de eventos de linha do tempo do dispositivo do Microsoft Defender para Endpoint para
keywords: Linha do tempo do dispositivo Defender para Ponto de Extremidade, sinalizadores de eventos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165148"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="44bd1-104">Sinalizadores de eventos de linha do tempo do dispositivo do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="44bd1-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="44bd1-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="44bd1-105">**Applies to:**</span></span>
- [<span data-ttu-id="44bd1-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="44bd1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="44bd1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44bd1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="44bd1-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="44bd1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="44bd1-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="44bd1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="44bd1-110">Sinalizadores de evento na linha do tempo do dispositivo Defender para Ponto de Extremidade ajudam você a filtrar e organizar eventos específicos quando você está investigando possíveis ataques.</span><span class="sxs-lookup"><span data-stu-id="44bd1-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="44bd1-111">A linha do tempo do dispositivo Defender para Ponto de Extremidade fornece uma exibição cronológica dos eventos e alertas associados observados em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44bd1-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="44bd1-112">Esta lista de eventos fornece visibilidade total sobre quaisquer eventos, arquivos e endereços IP observados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44bd1-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="44bd1-113">Às vezes, a lista pode ser longa.</span><span class="sxs-lookup"><span data-stu-id="44bd1-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="44bd1-114">Os sinalizadores de eventos da linha do tempo do dispositivo ajudam você a rastrear eventos que podem estar relacionados.</span><span class="sxs-lookup"><span data-stu-id="44bd1-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="44bd1-115">Depois de passar por uma linha do tempo do dispositivo, você pode classificar, filtrar e exportar os eventos específicos sinalizados.</span><span class="sxs-lookup"><span data-stu-id="44bd1-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="44bd1-116">Ao navegar pela linha do tempo do dispositivo, você pode pesquisar e filtrar eventos específicos.</span><span class="sxs-lookup"><span data-stu-id="44bd1-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="44bd1-117">Você pode definir sinalizadores de evento por:</span><span class="sxs-lookup"><span data-stu-id="44bd1-117">You can set event flags by:</span></span> 

- <span data-ttu-id="44bd1-118">Realçando os eventos mais importantes</span><span class="sxs-lookup"><span data-stu-id="44bd1-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="44bd1-119">Marcando eventos que exigem imersão profunda</span><span class="sxs-lookup"><span data-stu-id="44bd1-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="44bd1-120">Criando uma linha do tempo de violação limpa</span><span class="sxs-lookup"><span data-stu-id="44bd1-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="44bd1-121">Sinalizar um evento</span><span class="sxs-lookup"><span data-stu-id="44bd1-121">Flag an event</span></span>
1. <span data-ttu-id="44bd1-122">Encontre o evento que você deseja sinalizar</span><span class="sxs-lookup"><span data-stu-id="44bd1-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="44bd1-123">Clique no ícone de sinalizador na coluna Sinalizador.</span><span class="sxs-lookup"><span data-stu-id="44bd1-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="44bd1-124">![Imagem do sinalizador de linha do tempo do dispositivo](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="44bd1-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="44bd1-125">Exibir eventos sinalizados</span><span class="sxs-lookup"><span data-stu-id="44bd1-125">View flagged events</span></span>  
1. <span data-ttu-id="44bd1-126">Na seção **Filtros da Linha do Tempo,** habilita **eventos sinalizados**.</span><span class="sxs-lookup"><span data-stu-id="44bd1-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="44bd1-127">Clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="44bd1-127">Click **Apply**.</span></span> <span data-ttu-id="44bd1-128">Somente eventos sinalizados são exibidos.</span><span class="sxs-lookup"><span data-stu-id="44bd1-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="44bd1-129">Você pode aplicar filtros adicionais clicando na barra de tempo.</span><span class="sxs-lookup"><span data-stu-id="44bd1-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="44bd1-130">Isso só mostrará eventos antes do evento sinalizado.</span><span class="sxs-lookup"><span data-stu-id="44bd1-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="44bd1-131">![Imagem do sinalizador de linha do tempo do dispositivo com filtro em](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="44bd1-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
