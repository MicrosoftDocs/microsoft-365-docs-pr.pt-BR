---
title: Tabela AlertEvents no esquema de busca avançada
description: Aprenda sobre os eventos de geração de alerta na tabela AlertEvents do esquema de busca avançada
keywords: caça avançada, caça de ameaças, caça de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, alertevents, alerta, gravidade, categoria
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
ms.openlocfilehash: 4d83b659a98c56cc59e88f9777aa73ca2e25b745
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910715"
---
# <a name="alertevents"></a><span data-ttu-id="f9447-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="f9447-104">AlertEvents</span></span>

<span data-ttu-id="f9447-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f9447-105">**Applies to:**</span></span>
- <span data-ttu-id="f9447-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f9447-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="f9447-107">A tabela `AlertEvents` no esquema [busca avançada](advanced-hunting-overview.md) tem informações sobre os alertas do Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="f9447-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="f9447-108">Use esta referência para criar consultas que retornam informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="f9447-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f9447-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f9447-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f9447-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="f9447-110">Column name</span></span> | <span data-ttu-id="f9447-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f9447-111">Data type</span></span> | <span data-ttu-id="f9447-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f9447-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="f9447-113">string</span><span class="sxs-lookup"><span data-stu-id="f9447-113">string</span></span> | <span data-ttu-id="f9447-114">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="f9447-114">Unique identifier for the bucket.</span></span> |
| `EventTime` | <span data-ttu-id="f9447-115">datetime</span><span class="sxs-lookup"><span data-stu-id="f9447-115">dateTime</span></span> | <span data-ttu-id="f9447-116">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="f9447-116">Date and time the report was recorded.</span></span> |
| `MachineId` | <span data-ttu-id="f9447-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9447-117">string</span></span> | <span data-ttu-id="f9447-118">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="f9447-118">Unique identifier for the machine in the service</span></span> |
| `ComputerName` | <span data-ttu-id="f9447-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9447-119">string</span></span> | <span data-ttu-id="f9447-120">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="f9447-120">Fully qualified domain name (FQDN) of the pool</span></span> |
| `Severity` | <span data-ttu-id="f9447-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9447-121">string</span></span> | <span data-ttu-id="f9447-122">Indica o impacto potencial (alto, médio ou baixo) do indicador de ameaça ou da atividade de violação identificados pelo alerta</span><span class="sxs-lookup"><span data-stu-id="f9447-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="f9447-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9447-123">string</span></span> | <span data-ttu-id="f9447-124">Tipo de atividade indicadora de ameaça ou violação identificada pelo alerta</span><span class="sxs-lookup"><span data-stu-id="f9447-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="f9447-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9447-125">string</span></span> | <span data-ttu-id="f9447-126">Título do alerta</span><span class="sxs-lookup"><span data-stu-id="f9447-126">Title of the alert.</span></span> |
| `FileName` | <span data-ttu-id="f9447-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9447-127">string</span></span> | <span data-ttu-id="f9447-128">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="f9447-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="f9447-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9447-129">string</span></span> | <span data-ttu-id="f9447-130">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="f9447-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="f9447-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9447-131">string</span></span> | <span data-ttu-id="f9447-132">URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à</span><span class="sxs-lookup"><span data-stu-id="f9447-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="f9447-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9447-133">string</span></span> | <span data-ttu-id="f9447-134">Endereço IP que estava sendo conectado ao</span><span class="sxs-lookup"><span data-stu-id="f9447-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="f9447-135">long</span><span class="sxs-lookup"><span data-stu-id="f9447-135">long</span></span> | <span data-ttu-id="f9447-136">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="f9447-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f9447-137">Para identificar os eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas ComputerName e EventTime</span><span class="sxs-lookup"><span data-stu-id="f9447-137">To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns</span></span> |
| `Table` | <span data-ttu-id="f9447-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f9447-138">string</span></span> | <span data-ttu-id="f9447-139">Tabela que contém os detalhes do evento</span><span class="sxs-lookup"><span data-stu-id="f9447-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f9447-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f9447-140">Related topics</span></span>
- [<span data-ttu-id="f9447-141">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="f9447-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f9447-142">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="f9447-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f9447-143">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="f9447-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f9447-144">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="f9447-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f9447-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="f9447-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f9447-146">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="f9447-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
