---
title: Cotas de busca avançada e parâmetros de uso no Microsoft 365 Defender
description: Compreender várias cotas e parâmetros de uso (limites de serviço) que mantêm o serviço de busca avançada responsivo
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, esquema, kusto, limite de CPU, limite de consulta, recursos, resultados máximos, cota, parâmetros, alocação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929785"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="243f7-104">Cotas de busca avançada e parâmetros de uso</span><span class="sxs-lookup"><span data-stu-id="243f7-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="243f7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="243f7-105">**Applies to:**</span></span>
- <span data-ttu-id="243f7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="243f7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="243f7-107">Para manter o desempenho e a capacidade de resposta do serviço, a busca avançada define várias cotas e parâmetros de uso (também conhecidos como "limites de serviço").</span><span class="sxs-lookup"><span data-stu-id="243f7-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="243f7-108">Essas cotas e parâmetros se aplicam às consultas são executados manualmente e por regras [de detecção personalizadas.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="243f7-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="243f7-109">Os clientes que executarem várias consultas regularmente devem controlar o consumo e aplicar as práticas recomendadas de [otimização](advanced-hunting-best-practices.md) para minimizar as interrupções.</span><span class="sxs-lookup"><span data-stu-id="243f7-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="243f7-110">Consulte a tabela a seguir para entender as cotas e os parâmetros de uso existentes.</span><span class="sxs-lookup"><span data-stu-id="243f7-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="243f7-111">Cota ou parâmetro</span><span class="sxs-lookup"><span data-stu-id="243f7-111">Quota or parameter</span></span> | <span data-ttu-id="243f7-112">Size</span><span class="sxs-lookup"><span data-stu-id="243f7-112">Size</span></span> | <span data-ttu-id="243f7-113">Ciclo de atualização</span><span class="sxs-lookup"><span data-stu-id="243f7-113">Refresh cycle</span></span> | <span data-ttu-id="243f7-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="243f7-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="243f7-115">Intervalo de dados</span><span class="sxs-lookup"><span data-stu-id="243f7-115">Data range</span></span> | <span data-ttu-id="243f7-116">30 dias</span><span class="sxs-lookup"><span data-stu-id="243f7-116">30 days</span></span> | <span data-ttu-id="243f7-117">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="243f7-117">Every query</span></span> | <span data-ttu-id="243f7-118">Cada consulta pode procurar dados de até os últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="243f7-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="243f7-119">Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="243f7-119">Result set</span></span> | <span data-ttu-id="243f7-120">10.000 linhas</span><span class="sxs-lookup"><span data-stu-id="243f7-120">10,000 rows</span></span> | <span data-ttu-id="243f7-121">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="243f7-121">Every query</span></span> | <span data-ttu-id="243f7-122">Cada consulta pode retornar até 10.000 registros.</span><span class="sxs-lookup"><span data-stu-id="243f7-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="243f7-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="243f7-123">Timeout</span></span> | <span data-ttu-id="243f7-124">10 minutos</span><span class="sxs-lookup"><span data-stu-id="243f7-124">10 minutes</span></span> | <span data-ttu-id="243f7-125">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="243f7-125">Every query</span></span> | <span data-ttu-id="243f7-126">Cada consulta pode ser executado por até 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="243f7-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="243f7-127">Se ele não for concluído dentro de 10 minutos, o serviço exibirá um erro.</span><span class="sxs-lookup"><span data-stu-id="243f7-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="243f7-128">Recursos da CPU</span><span class="sxs-lookup"><span data-stu-id="243f7-128">CPU resources</span></span> | <span data-ttu-id="243f7-129">Com base no tamanho do locatário</span><span class="sxs-lookup"><span data-stu-id="243f7-129">Based on tenant size</span></span> | <span data-ttu-id="243f7-130">- Na hora e a cada 15 minutos</span><span class="sxs-lookup"><span data-stu-id="243f7-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="243f7-131">- Diariamente às 12h</span><span class="sxs-lookup"><span data-stu-id="243f7-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="243f7-132">O serviço impõe a cota diária e de 15 minutos separadamente.</span><span class="sxs-lookup"><span data-stu-id="243f7-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="243f7-133">Para cada cota, o [portal exibe](advanced-hunting-errors.md) um erro sempre que uma consulta é executado e o locatário consumiu mais de 10% dos recursos alocados.</span><span class="sxs-lookup"><span data-stu-id="243f7-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="243f7-134">As consultas são bloqueadas se o locatário tiver atingido 100% até o próximo ciclo diário ou de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="243f7-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="243f7-135">Um conjunto separado de cotas e parâmetros se aplica a consultas de busca avançada executadas por meio da API.</span><span class="sxs-lookup"><span data-stu-id="243f7-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="243f7-136">Leia sobre APIs de busca avançada</span><span class="sxs-lookup"><span data-stu-id="243f7-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="243f7-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="243f7-137">Related topics</span></span>

- [<span data-ttu-id="243f7-138">Práticas recomendadas de busca avançada</span><span class="sxs-lookup"><span data-stu-id="243f7-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="243f7-139">Lidar com erros de busca avançada</span><span class="sxs-lookup"><span data-stu-id="243f7-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="243f7-140">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="243f7-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="243f7-141">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="243f7-141">Custom detections overview</span></span>](custom-detections-overview.md)