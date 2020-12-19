---
title: APIs com suporte do Microsoft 365 Defender
description: APIs com suporte do Microsoft 365 Defender
keywords: MTP, APIs, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719317"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="073bd-104">APIs com suporte do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="073bd-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="073bd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="073bd-105">**Applies to:**</span></span>
- <span data-ttu-id="073bd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="073bd-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="073bd-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="073bd-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="073bd-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="073bd-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="073bd-109">Lista de APIs disponíveis</span><span class="sxs-lookup"><span data-stu-id="073bd-109">List of available APIs</span></span>

<span data-ttu-id="073bd-110">Artigo</span><span class="sxs-lookup"><span data-stu-id="073bd-110">Article</span></span> | <span data-ttu-id="073bd-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="073bd-111">Description</span></span>
-|-
[<span data-ttu-id="073bd-112">API de Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="073bd-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="073bd-113">Executar consultas de busca avançadas.</span><span class="sxs-lookup"><span data-stu-id="073bd-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="073bd-114">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="073bd-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="073bd-115">Incidentes de lista e atualização, juntamente com outras tarefas práticas.</span><span class="sxs-lookup"><span data-stu-id="073bd-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="073bd-116">URIs de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="073bd-116">Endpoint URIs</span></span>

<span data-ttu-id="073bd-117">O URI de base para ambas as APIs principais é: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="073bd-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="073bd-118">Para melhorar o desempenho, use um servidor mais próximo da sua localização geográfica:</span><span class="sxs-lookup"><span data-stu-id="073bd-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="073bd-119">Estados Unidos: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="073bd-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="073bd-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="073bd-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="073bd-121">O Reino Unido: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="073bd-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="073bd-122">Tokens podem ser adquiridos acessando https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="073bd-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="073bd-123">Todas as APIs ao longo do `/api` caminho usam o protocolo [OData](https://docs.microsoft.com/odata/overview) ; por exemplo, https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="073bd-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="073bd-124">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="073bd-124">Related articles</span></span>

- [<span data-ttu-id="073bd-125">Visão geral das APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="073bd-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="073bd-126">Acessar as APIs de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="073bd-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="073bd-127">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="073bd-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="073bd-128">Entender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="073bd-128">Understand error codes</span></span>](api-error-codes.md)
