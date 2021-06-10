---
title: Cotas de busca avançadas e parâmetros de uso no Microsoft 365 Defender
description: Entenda várias cotas e parâmetros de uso (limites de serviço) que mantêm o serviço de busca avançado responsivo
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, esquema, kusto, limite de CPU, limite de consulta, recursos, resultados máximos, cota, parâmetros, alocação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245595"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="3c54c-104">Cotas de busca avançadas e parâmetros de uso</span><span class="sxs-lookup"><span data-stu-id="3c54c-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3c54c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3c54c-105">**Applies to:**</span></span>
- <span data-ttu-id="3c54c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c54c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3c54c-107">Para manter o serviço performant e responsivo, a busca avançada define várias cotas e parâmetros de uso (também conhecidos como "limites de serviço").</span><span class="sxs-lookup"><span data-stu-id="3c54c-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="3c54c-108">Essas cotas e parâmetros se aplicam separadamente às consultas executados manualmente e às consultas que são executados usando regras [de detecção personalizadas.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="3c54c-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="3c54c-109">Os clientes que executarem várias consultas regularmente devem estar atentos a esses limites e aplicar práticas recomendadas de otimização [para](advanced-hunting-best-practices.md) minimizar interrupções.</span><span class="sxs-lookup"><span data-stu-id="3c54c-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="3c54c-110">Consulte a tabela a seguir para entender cotas e parâmetros de uso existentes.</span><span class="sxs-lookup"><span data-stu-id="3c54c-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="3c54c-111">Cota ou parâmetro</span><span class="sxs-lookup"><span data-stu-id="3c54c-111">Quota or parameter</span></span> | <span data-ttu-id="3c54c-112">Size</span><span class="sxs-lookup"><span data-stu-id="3c54c-112">Size</span></span> | <span data-ttu-id="3c54c-113">Ciclo de atualização</span><span class="sxs-lookup"><span data-stu-id="3c54c-113">Refresh cycle</span></span> | <span data-ttu-id="3c54c-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="3c54c-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="3c54c-115">Intervalo de dados</span><span class="sxs-lookup"><span data-stu-id="3c54c-115">Data range</span></span> | <span data-ttu-id="3c54c-116">30 dias</span><span class="sxs-lookup"><span data-stu-id="3c54c-116">30 days</span></span> | <span data-ttu-id="3c54c-117">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="3c54c-117">Every query</span></span> | <span data-ttu-id="3c54c-118">Cada consulta pode procurar dados de até os últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="3c54c-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="3c54c-119">Conjunto de resultados</span><span class="sxs-lookup"><span data-stu-id="3c54c-119">Result set</span></span> | <span data-ttu-id="3c54c-120">10.000 linhas</span><span class="sxs-lookup"><span data-stu-id="3c54c-120">10,000 rows</span></span> | <span data-ttu-id="3c54c-121">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="3c54c-121">Every query</span></span> | <span data-ttu-id="3c54c-122">Cada consulta pode retornar até 10.000 registros.</span><span class="sxs-lookup"><span data-stu-id="3c54c-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="3c54c-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="3c54c-123">Timeout</span></span> | <span data-ttu-id="3c54c-124">10 minutos</span><span class="sxs-lookup"><span data-stu-id="3c54c-124">10 minutes</span></span> | <span data-ttu-id="3c54c-125">Cada consulta</span><span class="sxs-lookup"><span data-stu-id="3c54c-125">Every query</span></span> | <span data-ttu-id="3c54c-126">Cada consulta pode ser executado por até 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="3c54c-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="3c54c-127">Se ele não for concluído em 10 minutos, o serviço exibirá um erro.</span><span class="sxs-lookup"><span data-stu-id="3c54c-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="3c54c-128">Recursos da CPU</span><span class="sxs-lookup"><span data-stu-id="3c54c-128">CPU resources</span></span> | <span data-ttu-id="3c54c-129">Com base no tamanho do locatário</span><span class="sxs-lookup"><span data-stu-id="3c54c-129">Based on tenant size</span></span> | <span data-ttu-id="3c54c-130">A cada 15 minutos</span><span class="sxs-lookup"><span data-stu-id="3c54c-130">Every 15 minutes</span></span> | <span data-ttu-id="3c54c-131">O [portal exibe um erro sempre](advanced-hunting-errors.md) que uma consulta é executado e o locatário consumiu mais de 10% dos recursos alocados.</span><span class="sxs-lookup"><span data-stu-id="3c54c-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="3c54c-132">As consultas serão bloqueadas se o locatário tiver atingido 100% até após o próximo ciclo de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="3c54c-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="3c54c-133">Um conjunto separado de cotas e parâmetros se aplicam a consultas de busca avançadas realizadas por meio da API.</span><span class="sxs-lookup"><span data-stu-id="3c54c-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="3c54c-134">Ler sobre APIs de busca avançada</span><span class="sxs-lookup"><span data-stu-id="3c54c-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="3c54c-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3c54c-135">Related topics</span></span>

- [<span data-ttu-id="3c54c-136">Práticas recomendadas de busca avançada</span><span class="sxs-lookup"><span data-stu-id="3c54c-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3c54c-137">Manipular erros avançados de busca</span><span class="sxs-lookup"><span data-stu-id="3c54c-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="3c54c-138">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="3c54c-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3c54c-139">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="3c54c-139">Custom detections overview</span></span>](custom-detections-overview.md)