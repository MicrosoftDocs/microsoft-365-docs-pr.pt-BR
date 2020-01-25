---
title: Tabela AlertEvents no esquema de busca avançada
description: Aprenda sobre os eventos de geração de alerta na tabela AlertEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, alertevents, alerta, severidade, categoria
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: f72658e552bcb7ce351eafa43ad950c0bc11cb69
ms.sourcegitcommit: e872676ec98036a50d3a0cb5071109ea5f5a7ae5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2020
ms.locfileid: "41515822"
---
# <a name="alertevents"></a><span data-ttu-id="06ad8-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="06ad8-104">AlertEvents</span></span>

<span data-ttu-id="06ad8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="06ad8-105">**Applies to:**</span></span>
- <span data-ttu-id="06ad8-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="06ad8-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="06ad8-107">A tabela `AlertEvents` no esquema [busca avançada](advanced-hunting-overview.md) tem informações sobre os alertas do Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="06ad8-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="06ad8-108">Use esta referência para criar consultas que retornam informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="06ad8-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="06ad8-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="06ad8-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="06ad8-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="06ad8-110">Column name</span></span> | <span data-ttu-id="06ad8-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="06ad8-111">Data type</span></span> | <span data-ttu-id="06ad8-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="06ad8-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="06ad8-113">string</span><span class="sxs-lookup"><span data-stu-id="06ad8-113">string</span></span> | <span data-ttu-id="06ad8-114">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="06ad8-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="06ad8-115">datetime</span><span class="sxs-lookup"><span data-stu-id="06ad8-115">datetime</span></span> | <span data-ttu-id="06ad8-116">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="06ad8-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="06ad8-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06ad8-117">string</span></span> | <span data-ttu-id="06ad8-118">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="06ad8-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="06ad8-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06ad8-119">string</span></span> | <span data-ttu-id="06ad8-120">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="06ad8-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="06ad8-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06ad8-121">string</span></span> | <span data-ttu-id="06ad8-122">Indica o impacto potencial (alto, médio ou baixo) do indicador de ameaça ou da atividade de violação identificados pelo alerta</span><span class="sxs-lookup"><span data-stu-id="06ad8-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="06ad8-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06ad8-123">string</span></span> | <span data-ttu-id="06ad8-124">Tipo de atividade indicadora de ameaça ou violação identificada pelo alerta</span><span class="sxs-lookup"><span data-stu-id="06ad8-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="06ad8-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06ad8-125">string</span></span> | <span data-ttu-id="06ad8-126">Título do alerta</span><span class="sxs-lookup"><span data-stu-id="06ad8-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="06ad8-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06ad8-127">string</span></span> | <span data-ttu-id="06ad8-128">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="06ad8-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="06ad8-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06ad8-129">string</span></span> | <span data-ttu-id="06ad8-130">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="06ad8-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="06ad8-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06ad8-131">string</span></span> | <span data-ttu-id="06ad8-132">URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à</span><span class="sxs-lookup"><span data-stu-id="06ad8-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="06ad8-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06ad8-133">string</span></span> | <span data-ttu-id="06ad8-134">Endereço IP que estava sendo conectado ao</span><span class="sxs-lookup"><span data-stu-id="06ad8-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="06ad8-135">long</span><span class="sxs-lookup"><span data-stu-id="06ad8-135">long</span></span> | <span data-ttu-id="06ad8-136">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="06ad8-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="06ad8-137">Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp</span><span class="sxs-lookup"><span data-stu-id="06ad8-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="06ad8-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06ad8-138">string</span></span> | <span data-ttu-id="06ad8-139">Tabela que contém os detalhes do evento</span><span class="sxs-lookup"><span data-stu-id="06ad8-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="06ad8-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="06ad8-140">Related topics</span></span>
- [<span data-ttu-id="06ad8-141">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="06ad8-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="06ad8-142">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="06ad8-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="06ad8-143">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="06ad8-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="06ad8-144">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="06ad8-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="06ad8-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="06ad8-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="06ad8-146">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="06ad8-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
