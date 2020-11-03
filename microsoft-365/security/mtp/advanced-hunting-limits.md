---
title: Cotas de busca avançada e parâmetros de uso no Microsoft 365 defender
description: Entenda vários parâmetros de uso e cotas (limites de serviço) que mantêm o serviço de busca avançada responsivo
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Search, Query, telemetria, Schema, Kusto, limite de CPU, limite de consulta, recursos, resultados máximos, cota, parâmetros, alocação
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847363"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="01708-104">Cotas de busca avançada e parâmetros de uso</span><span class="sxs-lookup"><span data-stu-id="01708-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01708-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="01708-105">**Applies to:**</span></span>
- <span data-ttu-id="01708-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="01708-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="01708-107">Para manter o serviço em desempenho e resposta, a busca avançada define várias cotas e parâmetros de uso (também conhecidos como "limites de serviço").</span><span class="sxs-lookup"><span data-stu-id="01708-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="01708-108">Essas cotas e parâmetros se aplicam às consultas executadas manualmente e por [regras de detecção personalizadas](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="01708-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="01708-109">Os clientes que executam várias consultas regularmente acompanham o consumo e [aplicam práticas recomendadas de otimização](advanced-hunting-best-practices.md) para minimizar as interrupções.</span><span class="sxs-lookup"><span data-stu-id="01708-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="01708-110">Consulte a tabela a seguir para entender as cotas e os parâmetros de uso existentes.</span><span class="sxs-lookup"><span data-stu-id="01708-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="01708-111">Cota ou parâmetro</span><span class="sxs-lookup"><span data-stu-id="01708-111">Quota or parameter</span></span> | <span data-ttu-id="01708-112">Size</span><span class="sxs-lookup"><span data-stu-id="01708-112">Size</span></span> | <span data-ttu-id="01708-113">Ciclo de atualização</span><span class="sxs-lookup"><span data-stu-id="01708-113">Refresh cycle</span></span> | <span data-ttu-id="01708-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="01708-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="01708-115">Intervalo de dados</span><span class="sxs-lookup"><span data-stu-id="01708-115">Data range</span></span> | <span data-ttu-id="01708-116">30 dias</span><span class="sxs-lookup"><span data-stu-id="01708-116">30 days</span></span> | <span data-ttu-id="01708-117">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="01708-117">Every query</span></span> | <span data-ttu-id="01708-118">Cada consulta pode pesquisar dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="01708-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="01708-119">Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="01708-119">Result set</span></span> | <span data-ttu-id="01708-120">10.000 linhas</span><span class="sxs-lookup"><span data-stu-id="01708-120">10,000 rows</span></span> | <span data-ttu-id="01708-121">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="01708-121">Every query</span></span> | <span data-ttu-id="01708-122">Cada consulta pode retornar até 10.000 registros.</span><span class="sxs-lookup"><span data-stu-id="01708-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="01708-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="01708-123">Timeout</span></span> | <span data-ttu-id="01708-124">10 minutos</span><span class="sxs-lookup"><span data-stu-id="01708-124">10 minutes</span></span> | <span data-ttu-id="01708-125">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="01708-125">Every query</span></span> | <span data-ttu-id="01708-126">Cada consulta pode ser executada por até 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="01708-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="01708-127">Se ele não for concluído dentro de 10 minutos, o serviço exibirá um erro.</span><span class="sxs-lookup"><span data-stu-id="01708-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="01708-128">Recursos de CPU</span><span class="sxs-lookup"><span data-stu-id="01708-128">CPU resources</span></span> | <span data-ttu-id="01708-129">Com base no tamanho do locatário</span><span class="sxs-lookup"><span data-stu-id="01708-129">Based on tenant size</span></span> | <span data-ttu-id="01708-130">-Na hora e, em seguida, a cada 15 minutos</span><span class="sxs-lookup"><span data-stu-id="01708-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="01708-131">– Diariamente às 12 da meia-noite</span><span class="sxs-lookup"><span data-stu-id="01708-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="01708-132">O serviço impõe a cota diária e de 15 minutos separadamente.</span><span class="sxs-lookup"><span data-stu-id="01708-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="01708-133">Para cada cota, o [portal exibe um erro](advanced-hunting-errors.md) sempre que uma consulta é executada e o locatário consome mais de 10% dos recursos alocados.</span><span class="sxs-lookup"><span data-stu-id="01708-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="01708-134">As consultas são bloqueadas se o locatário tiver alcançado 100% até o ciclo seguinte ou de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="01708-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="01708-135">Um conjunto separado de cotas e parâmetros se aplica a consultas de busca avançada realizadas por meio da API.</span><span class="sxs-lookup"><span data-stu-id="01708-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="01708-136">Leia sobre APIs de busca avançada</span><span class="sxs-lookup"><span data-stu-id="01708-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="01708-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="01708-137">Related topics</span></span>

- [<span data-ttu-id="01708-138">Práticas recomendadas de busca avançada</span><span class="sxs-lookup"><span data-stu-id="01708-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="01708-139">Manipular erros de busca avançada</span><span class="sxs-lookup"><span data-stu-id="01708-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="01708-140">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="01708-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="01708-141">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="01708-141">Custom detections overview</span></span>](custom-detections-overview.md)