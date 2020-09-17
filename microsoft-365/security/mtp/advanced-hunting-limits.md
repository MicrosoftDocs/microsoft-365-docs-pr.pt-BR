---
title: Limites de busca avançada na proteção contra ameaças da Microsoft
description: Entender vários limites de serviço que mantêm o serviço de busca avançada responsivo
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção contra ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, esquema, Kusto, limite de CPU, limite de consulta, recursos, resultados máximos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e3fbe29076d541df68dc39754960386fe935c7bc
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950901"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="8d26d-104">Limites de serviço de busca avançada</span><span class="sxs-lookup"><span data-stu-id="8d26d-104">Advanced hunting service limits</span></span>

<span data-ttu-id="8d26d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8d26d-105">**Applies to:**</span></span>
- <span data-ttu-id="8d26d-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d26d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8d26d-107">Para manter o serviço em execução e responsivo, a busca avançada define vários limites para consultas executadas manualmente e por [regras de detecção personalizadas](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="8d26d-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="8d26d-108">Consulte a tabela a seguir para entender esses limites.</span><span class="sxs-lookup"><span data-stu-id="8d26d-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="8d26d-109">Limite</span><span class="sxs-lookup"><span data-stu-id="8d26d-109">Limit</span></span> | <span data-ttu-id="8d26d-110">Size</span><span class="sxs-lookup"><span data-stu-id="8d26d-110">Size</span></span> | <span data-ttu-id="8d26d-111">Ciclo de atualização</span><span class="sxs-lookup"><span data-stu-id="8d26d-111">Refresh cycle</span></span> | <span data-ttu-id="8d26d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d26d-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="8d26d-113">Intervalo de dados</span><span class="sxs-lookup"><span data-stu-id="8d26d-113">Data range</span></span> | <span data-ttu-id="8d26d-114">30 dias</span><span class="sxs-lookup"><span data-stu-id="8d26d-114">30 days</span></span> | <span data-ttu-id="8d26d-115">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="8d26d-115">Every query</span></span> | <span data-ttu-id="8d26d-116">Cada consulta pode pesquisar dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="8d26d-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="8d26d-117">Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="8d26d-117">Result set</span></span> | <span data-ttu-id="8d26d-118">10.000 linhas</span><span class="sxs-lookup"><span data-stu-id="8d26d-118">10,000 rows</span></span> | <span data-ttu-id="8d26d-119">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="8d26d-119">Every query</span></span> | <span data-ttu-id="8d26d-120">Cada consulta pode retornar até 10.000 registros.</span><span class="sxs-lookup"><span data-stu-id="8d26d-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="8d26d-121">Timeout</span><span class="sxs-lookup"><span data-stu-id="8d26d-121">Timeout</span></span> | <span data-ttu-id="8d26d-122">10 minutos</span><span class="sxs-lookup"><span data-stu-id="8d26d-122">10 minutes</span></span> | <span data-ttu-id="8d26d-123">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="8d26d-123">Every query</span></span> | <span data-ttu-id="8d26d-124">Cada consulta pode ser executada por até 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="8d26d-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="8d26d-125">Se ele não for concluído dentro de 10 minutos, o serviço exibirá um erro.</span><span class="sxs-lookup"><span data-stu-id="8d26d-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="8d26d-126">Recursos de CPU</span><span class="sxs-lookup"><span data-stu-id="8d26d-126">CPU resources</span></span> | <span data-ttu-id="8d26d-127">Com base no tamanho do locatário</span><span class="sxs-lookup"><span data-stu-id="8d26d-127">Based on tenant size</span></span> | <span data-ttu-id="8d26d-128">-Na hora e, em seguida, a cada 15 minutos</span><span class="sxs-lookup"><span data-stu-id="8d26d-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="8d26d-129">– Diariamente às 12 da meia-noite</span><span class="sxs-lookup"><span data-stu-id="8d26d-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="8d26d-130">O serviço impõe o limite diário e de 15 minutos separadamente.</span><span class="sxs-lookup"><span data-stu-id="8d26d-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="8d26d-131">Para cada limite, o [portal exibe um erro](advanced-hunting-errors.md) sempre que uma consulta é executada e o locatário consome mais de 10% dos recursos alocados.</span><span class="sxs-lookup"><span data-stu-id="8d26d-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="8d26d-132">As consultas são bloqueadas se o locatário tiver alcançado 100% até o ciclo seguinte ou de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="8d26d-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="8d26d-133">Um conjunto separado de limites se aplica a consultas de busca avançada realizadas por meio da API.</span><span class="sxs-lookup"><span data-stu-id="8d26d-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="8d26d-134">Leia sobre APIs de busca avançada</span><span class="sxs-lookup"><span data-stu-id="8d26d-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="8d26d-135">Os clientes que executam várias consultas regularmente acompanham o consumo e [aplicam as práticas recomendadas de otimização](advanced-hunting-best-practices.md) para minimizar a interrupção resultante da excedeção desses limites.</span><span class="sxs-lookup"><span data-stu-id="8d26d-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d26d-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8d26d-136">Related topics</span></span>

- [<span data-ttu-id="8d26d-137">Práticas recomendadas de busca avançada</span><span class="sxs-lookup"><span data-stu-id="8d26d-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="8d26d-138">Manipular erros de busca avançada</span><span class="sxs-lookup"><span data-stu-id="8d26d-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="8d26d-139">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="8d26d-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8d26d-140">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="8d26d-140">Custom detections overview</span></span>](custom-detections-overview.md)
