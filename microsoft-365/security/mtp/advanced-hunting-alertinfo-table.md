---
title: Tabela AlertInfo no esquema de busca avançada
description: Saiba mais sobre eventos de geração de alertas na tabela AlertInfo do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, gravidade, categoria, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS e Azure ATP
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
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929965"
---
# <a name="alertinfo"></a><span data-ttu-id="e999b-104">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="e999b-104">AlertInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e999b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e999b-105">**Applies to:**</span></span>
- <span data-ttu-id="e999b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e999b-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="e999b-107">A tabela no esquema de busca avançada contém informações sobre alertas do Microsoft Defender para Ponto de `AlertInfo` Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e999b-107">The `AlertInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="e999b-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="e999b-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="e999b-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e999b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e999b-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="e999b-110">Column name</span></span> | <span data-ttu-id="e999b-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e999b-111">Data type</span></span> | <span data-ttu-id="e999b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e999b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="e999b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e999b-113">datetime</span></span> | <span data-ttu-id="e999b-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="e999b-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="e999b-115">string</span><span class="sxs-lookup"><span data-stu-id="e999b-115">string</span></span> | <span data-ttu-id="e999b-116">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="e999b-116">Unique identifier for the alert</span></span> |
| `Title` | <span data-ttu-id="e999b-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e999b-117">string</span></span> | <span data-ttu-id="e999b-118">Título do alerta</span><span class="sxs-lookup"><span data-stu-id="e999b-118">Title of the alert</span></span> |
| `Category` | <span data-ttu-id="e999b-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e999b-119">string</span></span> | <span data-ttu-id="e999b-120">Tipo de atividade indicadora de ameaça ou violação identificada pelo alerta</span><span class="sxs-lookup"><span data-stu-id="e999b-120">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Severity` | <span data-ttu-id="e999b-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e999b-121">string</span></span> | <span data-ttu-id="e999b-122">Indica o impacto potencial (alto, médio ou baixo) do indicador de ameaça ou da atividade de violação identificados pelo alerta</span><span class="sxs-lookup"><span data-stu-id="e999b-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="e999b-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e999b-123">string</span></span> | <span data-ttu-id="e999b-124">Produto ou serviço que forneceu as informações de alerta</span><span class="sxs-lookup"><span data-stu-id="e999b-124">Product or service that provided the alert information</span></span> |
| `DetectionSource` | <span data-ttu-id="e999b-125">string</span><span class="sxs-lookup"><span data-stu-id="e999b-125">string</span></span> | <span data-ttu-id="e999b-126">Tecnologia ou sensor de detecção que identificou o componente ou a atividade notável</span><span class="sxs-lookup"><span data-stu-id="e999b-126">Detection technology or sensor that identified the notable component or activity</span></span> |
| `AttackTechniques` | <span data-ttu-id="e999b-127">string</span><span class="sxs-lookup"><span data-stu-id="e999b-127">string</span></span> | <span data-ttu-id="e999b-128">MITRE ATT&CK associadas à atividade que disparou o alerta</span><span class="sxs-lookup"><span data-stu-id="e999b-128">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e999b-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e999b-129">Related topics</span></span>
- [<span data-ttu-id="e999b-130">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="e999b-130">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e999b-131">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="e999b-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e999b-132">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="e999b-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e999b-133">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="e999b-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e999b-134">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="e999b-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e999b-135">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="e999b-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
