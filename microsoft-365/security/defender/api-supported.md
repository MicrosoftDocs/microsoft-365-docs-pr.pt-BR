---
title: APIs com suporte do Microsoft 365 Defender
description: APIs com suporte do Microsoft 365 Defender
keywords: MTP, APIs, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b2239b960106d756cbd29504af05af77a553067d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052548"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="6efc9-104">APIs com suporte do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6efc9-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6efc9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6efc9-105">**Applies to:**</span></span>
- <span data-ttu-id="6efc9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6efc9-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6efc9-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="6efc9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6efc9-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="6efc9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="6efc9-109">Lista de APIs disponíveis</span><span class="sxs-lookup"><span data-stu-id="6efc9-109">List of available APIs</span></span>

<span data-ttu-id="6efc9-110">Artigo</span><span class="sxs-lookup"><span data-stu-id="6efc9-110">Article</span></span> | <span data-ttu-id="6efc9-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="6efc9-111">Description</span></span>
-|-
[<span data-ttu-id="6efc9-112">API de Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="6efc9-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="6efc9-113">Execute consultas de Busca Avançada.</span><span class="sxs-lookup"><span data-stu-id="6efc9-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="6efc9-114">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="6efc9-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="6efc9-115">Listar e atualizar incidentes, juntamente com outras tarefas práticas.</span><span class="sxs-lookup"><span data-stu-id="6efc9-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="6efc9-116">URIs de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="6efc9-116">Endpoint URIs</span></span>

<span data-ttu-id="6efc9-117">O URI base para ambas as APIs principais é: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="6efc9-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="6efc9-118">Para melhorar o desempenho, use um servidor mais próximo de sua localização geográfica:</span><span class="sxs-lookup"><span data-stu-id="6efc9-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="6efc9-119">Estados Unidos: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6efc9-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="6efc9-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6efc9-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="6efc9-121">Reino Unido: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6efc9-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="6efc9-122">Tokens podem ser adquiridos acessando https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="6efc9-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="6efc9-123">Todas as APIs ao longo `/api` do caminho usam o Protocolo [OData;](/odata/overview) por exemplo, https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="6efc9-123">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6efc9-124">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="6efc9-124">Related articles</span></span>

- [<span data-ttu-id="6efc9-125">Visão geral das APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6efc9-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="6efc9-126">Acessar as APIs da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6efc9-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="6efc9-127">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="6efc9-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="6efc9-128">Compreender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="6efc9-128">Understand error codes</span></span>](api-error-codes.md)