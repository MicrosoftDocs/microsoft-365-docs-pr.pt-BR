---
title: Tabela AlertInfo no esquema de busca avançado
description: Saiba mais sobre eventos de geração de alertas na tabela AlertInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, gravidade, categoria, MITRE, ATT&CK, Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security, MCAS e Microsoft Defender for Identity
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
ms.openlocfilehash: 69c9201dbc3458cd4ad09a72f2ea0d7ea3bb2d2a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933692"
---
# <a name="alertinfo"></a><span data-ttu-id="dbb2d-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="dbb2d-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="dbb2d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="dbb2d-105">**Applies to:**</span></span>
- <span data-ttu-id="dbb2d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbb2d-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="dbb2d-107">A tabela no esquema de busca avançada contém informações sobre alertas do Microsoft Defender para Ponto de `AlertInfo` Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="dbb2d-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="dbb2d-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="dbb2d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="dbb2d-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="dbb2d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="dbb2d-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="dbb2d-110">Column name</span></span> | <span data-ttu-id="dbb2d-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="dbb2d-111">Data type</span></span> | <span data-ttu-id="dbb2d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="dbb2d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="dbb2d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="dbb2d-113">datetime</span></span> | <span data-ttu-id="dbb2d-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="dbb2d-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="dbb2d-115">string</span><span class="sxs-lookup"><span data-stu-id="dbb2d-115">string</span></span> | <span data-ttu-id="dbb2d-116">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="dbb2d-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="dbb2d-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="dbb2d-117">string</span></span> | <span data-ttu-id="dbb2d-118">Título do alerta</span><span class="sxs-lookup"><span data-stu-id="dbb2d-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="dbb2d-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="dbb2d-119">string</span></span> | <span data-ttu-id="dbb2d-120">Tipo de atividade indicadora de ameaça ou violação identificada pelo alerta</span><span class="sxs-lookup"><span data-stu-id="dbb2d-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="dbb2d-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="dbb2d-121">string</span></span> | <span data-ttu-id="dbb2d-122">Indica o impacto potencial (alto, médio ou baixo) do indicador de ameaça ou da atividade de violação identificados pelo alerta</span><span class="sxs-lookup"><span data-stu-id="dbb2d-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="dbb2d-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="dbb2d-123">string</span></span> | <span data-ttu-id="dbb2d-124">Produto ou serviço que forneceu as informações de alerta</span><span class="sxs-lookup"><span data-stu-id="dbb2d-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="dbb2d-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="dbb2d-125">string</span></span> | <span data-ttu-id="dbb2d-126">Tecnologia de detecção ou sensor que identificou o componente ou atividade notável</span><span class="sxs-lookup"><span data-stu-id="dbb2d-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="dbb2d-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="dbb2d-127">string</span></span> | <span data-ttu-id="dbb2d-128">MITRE ATT&técnicas de CK associadas à atividade que disparou o alerta</span><span class="sxs-lookup"><span data-stu-id="dbb2d-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="dbb2d-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="dbb2d-129">Related topics</span></span>
- [<span data-ttu-id="dbb2d-130">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="dbb2d-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="dbb2d-131">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="dbb2d-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="dbb2d-132">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="dbb2d-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="dbb2d-133">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="dbb2d-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="dbb2d-134">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="dbb2d-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="dbb2d-135">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="dbb2d-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
