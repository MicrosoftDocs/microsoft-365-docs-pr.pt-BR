---
title: Tabela AlertInfo no esquema de busca avançada
description: Saiba mais sobre eventos de geração de alerta na tabela AlertInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Search, Query, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, gravidade, categoria, MITRE, ATT&CK, Microsoft defender ATP, MDATP, Office 365 ATP, Microsoft Cloud app Security, MCAS
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
ms.openlocfilehash: 36e76ae097dc31c6d7eb7eeff18dd2128ff0cc5c
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649482"
---
# <a name="alertinfo"></a><span data-ttu-id="f9f10-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="f9f10-104">AlertInfo</span></span>

<span data-ttu-id="f9f10-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f9f10-105">**Applies to:**</span></span>
- <span data-ttu-id="f9f10-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f9f10-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="f9f10-107">A `AlertInfo` tabela no esquema de [caça avançada](advanced-hunting-overview.md) contém informações sobre os alertas do Microsoft defender ATP, Office 365 ATP, Microsoft Cloud app Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="f9f10-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="f9f10-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="f9f10-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f9f10-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f9f10-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f9f10-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="f9f10-110">Column name</span></span> | <span data-ttu-id="f9f10-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f9f10-111">Data type</span></span> | <span data-ttu-id="f9f10-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f9f10-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f9f10-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f9f10-113">datetime</span></span> | <span data-ttu-id="f9f10-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="f9f10-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="f9f10-115">string</span><span class="sxs-lookup"><span data-stu-id="f9f10-115">string</span></span> | <span data-ttu-id="f9f10-116">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="f9f10-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="f9f10-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9f10-117">string</span></span> | <span data-ttu-id="f9f10-118">Título do alerta</span><span class="sxs-lookup"><span data-stu-id="f9f10-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="f9f10-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9f10-119">string</span></span> | <span data-ttu-id="f9f10-120">Tipo de atividade indicadora de ameaça ou violação identificada pelo alerta</span><span class="sxs-lookup"><span data-stu-id="f9f10-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="f9f10-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9f10-121">string</span></span> | <span data-ttu-id="f9f10-122">Indica o impacto potencial (alto, médio ou baixo) do indicador de ameaça ou da atividade de violação identificados pelo alerta</span><span class="sxs-lookup"><span data-stu-id="f9f10-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="f9f10-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9f10-123">string</span></span> | <span data-ttu-id="f9f10-124">Produto ou serviço que forneceu as informações de alerta</span><span class="sxs-lookup"><span data-stu-id="f9f10-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="f9f10-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9f10-125">string</span></span> | <span data-ttu-id="f9f10-126">Tecnologia de detecção ou sensor que identificou o componente ou atividade notável</span><span class="sxs-lookup"><span data-stu-id="f9f10-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="f9f10-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9f10-127">string</span></span> | <span data-ttu-id="f9f10-128">MITRE ATT&as técnicas de Enck associadas à atividade que disparou o alerta</span><span class="sxs-lookup"><span data-stu-id="f9f10-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f9f10-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f9f10-129">Related topics</span></span>
- [<span data-ttu-id="f9f10-130">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="f9f10-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f9f10-131">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="f9f10-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f9f10-132">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="f9f10-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f9f10-133">Procurar por dispositivos, emails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="f9f10-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f9f10-134">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="f9f10-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f9f10-135">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="f9f10-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
