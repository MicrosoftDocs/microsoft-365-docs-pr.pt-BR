---
title: APIs do Microsoft 365 defender com suporte
description: APIs do Microsoft 365 defender com suporte
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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844955"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="73ad4-104">APIs do Microsoft 365 defender com suporte</span><span class="sxs-lookup"><span data-stu-id="73ad4-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="73ad4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="73ad4-105">**Applies to:**</span></span>
- <span data-ttu-id="73ad4-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="73ad4-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="73ad4-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="73ad4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="73ad4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="73ad4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="73ad4-109">URIs de ponto de extremidade:</span><span class="sxs-lookup"><span data-stu-id="73ad4-109">End Point URIs:</span></span>

- <span data-ttu-id="73ad4-110">O URI da base de serviço é: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="73ad4-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="73ad4-111">Para melhorar o desempenho, você pode usar o servidor mais próximo do local geográfico:</span><span class="sxs-lookup"><span data-stu-id="73ad4-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="73ad4-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="73ad4-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="73ad4-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="73ad4-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="73ad4-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="73ad4-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="73ad4-115">O recurso para aquisição de token deve ser: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="73ad4-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="73ad4-116">Todas as APIs em ```/api``` Path são APIs OData.</span><span class="sxs-lookup"><span data-stu-id="73ad4-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="73ad4-117">exemplo. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="73ad4-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="73ad4-118">Lista de APIs disponíveis:</span><span class="sxs-lookup"><span data-stu-id="73ad4-118">List of available APIs:</span></span>

<span data-ttu-id="73ad4-119">Tópico</span><span class="sxs-lookup"><span data-stu-id="73ad4-119">Topic</span></span> | <span data-ttu-id="73ad4-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="73ad4-120">Description</span></span>
:---|:---
[<span data-ttu-id="73ad4-121">API de Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="73ad4-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="73ad4-122">Executar consultas de busca avançada da API.</span><span class="sxs-lookup"><span data-stu-id="73ad4-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="73ad4-123">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="73ad4-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="73ad4-124">Executar chamadas de API relacionadas a incidentes, como: listar incidentes, atualizar incidente e mais.</span><span class="sxs-lookup"><span data-stu-id="73ad4-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
