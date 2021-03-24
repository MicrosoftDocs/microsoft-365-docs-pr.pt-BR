---
title: Limites avançados de busca no Microsoft Defender ATP
description: Compreender vários limites de serviço que mantêm o serviço de busca avançado responsivo
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, wdatp, pesquisa, consulta, telemetria, esquema, kusto, limite de CPU, limite de consulta, recursos, resultados máximos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054331"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="adbdf-104">Limites avançados do serviço de busca</span><span class="sxs-lookup"><span data-stu-id="adbdf-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="adbdf-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="adbdf-105">**Applies to:**</span></span>
- [<span data-ttu-id="adbdf-106">Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="adbdf-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="adbdf-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="adbdf-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="adbdf-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="adbdf-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="adbdf-109">Para manter o serviço performant e responsivo, a busca avançada define vários limites para consultas executados manualmente e por regras [de detecção personalizadas.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="adbdf-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="adbdf-110">Consulte a tabela a seguir para entender esses limites.</span><span class="sxs-lookup"><span data-stu-id="adbdf-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="adbdf-111">Limite</span><span class="sxs-lookup"><span data-stu-id="adbdf-111">Limit</span></span> | <span data-ttu-id="adbdf-112">Size</span><span class="sxs-lookup"><span data-stu-id="adbdf-112">Size</span></span> | <span data-ttu-id="adbdf-113">Ciclo de atualização</span><span class="sxs-lookup"><span data-stu-id="adbdf-113">Refresh cycle</span></span> | <span data-ttu-id="adbdf-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="adbdf-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="adbdf-115">Intervalo de dados</span><span class="sxs-lookup"><span data-stu-id="adbdf-115">Data range</span></span> | <span data-ttu-id="adbdf-116">30 dias</span><span class="sxs-lookup"><span data-stu-id="adbdf-116">30 days</span></span> | <span data-ttu-id="adbdf-117">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="adbdf-117">Every query</span></span> | <span data-ttu-id="adbdf-118">Cada consulta pode procurar dados de até os últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="adbdf-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="adbdf-119">Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="adbdf-119">Result set</span></span> | <span data-ttu-id="adbdf-120">10.000 linhas</span><span class="sxs-lookup"><span data-stu-id="adbdf-120">10,000 rows</span></span> | <span data-ttu-id="adbdf-121">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="adbdf-121">Every query</span></span> | <span data-ttu-id="adbdf-122">Cada consulta pode retornar até 10.000 registros.</span><span class="sxs-lookup"><span data-stu-id="adbdf-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="adbdf-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="adbdf-123">Timeout</span></span> | <span data-ttu-id="adbdf-124">10 minutos</span><span class="sxs-lookup"><span data-stu-id="adbdf-124">10 minutes</span></span> | <span data-ttu-id="adbdf-125">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="adbdf-125">Every query</span></span> | <span data-ttu-id="adbdf-126">Cada consulta pode ser executado por até 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="adbdf-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="adbdf-127">Se ele não for concluído em 10 minutos, o serviço exibirá um erro.</span><span class="sxs-lookup"><span data-stu-id="adbdf-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="adbdf-128">Recursos da CPU</span><span class="sxs-lookup"><span data-stu-id="adbdf-128">CPU resources</span></span> | <span data-ttu-id="adbdf-129">Com base no tamanho do locatário</span><span class="sxs-lookup"><span data-stu-id="adbdf-129">Based on tenant size</span></span> | <span data-ttu-id="adbdf-130">- Na hora e, em seguida, a cada 15 minutos</span><span class="sxs-lookup"><span data-stu-id="adbdf-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="adbdf-131">- Diariamente à meia-noite</span><span class="sxs-lookup"><span data-stu-id="adbdf-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="adbdf-132">O serviço impõe o limite diário e de 15 minutos separadamente.</span><span class="sxs-lookup"><span data-stu-id="adbdf-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="adbdf-133">Para cada limite, o [portal exibe](advanced-hunting-errors.md) um erro sempre que uma consulta é executado e o locatário consumiu mais de 10% dos recursos alocados.</span><span class="sxs-lookup"><span data-stu-id="adbdf-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="adbdf-134">As consultas serão bloqueadas se o locatário tiver atingido 100% até após o próximo ciclo diário ou de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="adbdf-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="adbdf-135">Um conjunto separado de limites se aplica a consultas de busca avançadas realizadas por meio da API.</span><span class="sxs-lookup"><span data-stu-id="adbdf-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="adbdf-136">Ler sobre APIs de busca avançada</span><span class="sxs-lookup"><span data-stu-id="adbdf-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="adbdf-137">Os clientes que executarem várias consultas [](advanced-hunting-best-practices.md) regularmente devem controlar o consumo e aplicar práticas recomendadas de otimização para minimizar a interrupção resultante de exceder esses limites.</span><span class="sxs-lookup"><span data-stu-id="adbdf-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="adbdf-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="adbdf-138">Related topics</span></span>

- [<span data-ttu-id="adbdf-139">Práticas recomendadas de busca avançada</span><span class="sxs-lookup"><span data-stu-id="adbdf-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="adbdf-140">Manipular erros avançados de busca</span><span class="sxs-lookup"><span data-stu-id="adbdf-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="adbdf-141">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="adbdf-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="adbdf-142">Regras de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="adbdf-142">Custom detections rules</span></span>](custom-detection-rules.md)
