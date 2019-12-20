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
ms.openlocfilehash: ee14dcc1c2ae0a2bc6fa3c094d757441515f00de
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807010"
---
# <a name="alertevents"></a><span data-ttu-id="b1b57-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="b1b57-104">AlertEvents</span></span>

<span data-ttu-id="b1b57-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b1b57-105">**Applies to:**</span></span>
- <span data-ttu-id="b1b57-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1b57-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b1b57-107">A tabela `AlertEvents` no esquema [busca avançada](advanced-hunting-overview.md) tem informações sobre os alertas do Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="b1b57-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="b1b57-108">Use esta referência para criar consultas que retornam informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="b1b57-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b1b57-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b1b57-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b1b57-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="b1b57-110">Column name</span></span> | <span data-ttu-id="b1b57-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b1b57-111">Data type</span></span> | <span data-ttu-id="b1b57-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b1b57-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="b1b57-113">string</span><span class="sxs-lookup"><span data-stu-id="b1b57-113">string</span></span> | <span data-ttu-id="b1b57-114">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="b1b57-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="b1b57-115">datetime</span><span class="sxs-lookup"><span data-stu-id="b1b57-115">datetime</span></span> | <span data-ttu-id="b1b57-116">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="b1b57-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b1b57-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1b57-117">string</span></span> | <span data-ttu-id="b1b57-118">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="b1b57-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b1b57-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1b57-119">string</span></span> | <span data-ttu-id="b1b57-120">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="b1b57-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="b1b57-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1b57-121">string</span></span> | <span data-ttu-id="b1b57-122">Indica o impacto potencial (alto, médio ou baixo) do indicador de ameaça ou da atividade de violação identificados pelo alerta</span><span class="sxs-lookup"><span data-stu-id="b1b57-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="b1b57-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1b57-123">string</span></span> | <span data-ttu-id="b1b57-124">Tipo de atividade indicadora de ameaça ou violação identificada pelo alerta</span><span class="sxs-lookup"><span data-stu-id="b1b57-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="b1b57-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1b57-125">string</span></span> | <span data-ttu-id="b1b57-126">Título do alerta</span><span class="sxs-lookup"><span data-stu-id="b1b57-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="b1b57-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1b57-127">string</span></span> | <span data-ttu-id="b1b57-128">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="b1b57-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="b1b57-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1b57-129">string</span></span> | <span data-ttu-id="b1b57-130">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="b1b57-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="b1b57-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1b57-131">string</span></span> | <span data-ttu-id="b1b57-132">URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à</span><span class="sxs-lookup"><span data-stu-id="b1b57-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="b1b57-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1b57-133">string</span></span> | <span data-ttu-id="b1b57-134">Endereço IP que estava sendo conectado ao</span><span class="sxs-lookup"><span data-stu-id="b1b57-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="b1b57-135">long</span><span class="sxs-lookup"><span data-stu-id="b1b57-135">long</span></span> | <span data-ttu-id="b1b57-136">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="b1b57-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b1b57-137">Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp</span><span class="sxs-lookup"><span data-stu-id="b1b57-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="b1b57-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1b57-138">string</span></span> | <span data-ttu-id="b1b57-139">Tabela que contém os detalhes do evento</span><span class="sxs-lookup"><span data-stu-id="b1b57-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b1b57-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b1b57-140">Related topics</span></span>
- [<span data-ttu-id="b1b57-141">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="b1b57-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b1b57-142">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b1b57-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b1b57-143">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="b1b57-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b1b57-144">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="b1b57-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b1b57-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="b1b57-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b1b57-146">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="b1b57-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
