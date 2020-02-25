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
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9f341705d8247183b7e8a5271231c82faf8b386a
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235090"
---
# <a name="alertevents"></a><span data-ttu-id="8db6d-104">AlertEvents</span><span class="sxs-lookup"><span data-stu-id="8db6d-104">AlertEvents</span></span>

<span data-ttu-id="8db6d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8db6d-105">**Applies to:**</span></span>
- <span data-ttu-id="8db6d-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8db6d-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="8db6d-107">A tabela `AlertEvents` no esquema [busca avançada](advanced-hunting-overview.md) tem informações sobre os alertas do Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="8db6d-107">The `AlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about Microsoft Defender ATP alerts.</span></span> <span data-ttu-id="8db6d-108">Use esta referência para criar consultas que retornam informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="8db6d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="8db6d-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="8db6d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="8db6d-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="8db6d-110">Column name</span></span> | <span data-ttu-id="8db6d-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="8db6d-111">Data type</span></span> | <span data-ttu-id="8db6d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="8db6d-112">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="8db6d-113">string</span><span class="sxs-lookup"><span data-stu-id="8db6d-113">string</span></span> | <span data-ttu-id="8db6d-114">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="8db6d-114">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="8db6d-115">datetime</span><span class="sxs-lookup"><span data-stu-id="8db6d-115">datetime</span></span> | <span data-ttu-id="8db6d-116">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="8db6d-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="8db6d-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8db6d-117">string</span></span> | <span data-ttu-id="8db6d-118">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="8db6d-118">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="8db6d-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8db6d-119">string</span></span> | <span data-ttu-id="8db6d-120">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="8db6d-120">Fully qualified domain name (FQDN) of the machine</span></span> |
| `Severity` | <span data-ttu-id="8db6d-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8db6d-121">string</span></span> | <span data-ttu-id="8db6d-122">Indica o impacto potencial (alto, médio ou baixo) do indicador de ameaça ou da atividade de violação identificados pelo alerta</span><span class="sxs-lookup"><span data-stu-id="8db6d-122">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="8db6d-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8db6d-123">string</span></span> | <span data-ttu-id="8db6d-124">Tipo de atividade indicadora de ameaça ou violação identificada pelo alerta</span><span class="sxs-lookup"><span data-stu-id="8db6d-124">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="8db6d-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8db6d-125">string</span></span> | <span data-ttu-id="8db6d-126">Título do alerta</span><span class="sxs-lookup"><span data-stu-id="8db6d-126">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="8db6d-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8db6d-127">string</span></span> | <span data-ttu-id="8db6d-128">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="8db6d-128">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="8db6d-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8db6d-129">string</span></span> | <span data-ttu-id="8db6d-130">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="8db6d-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="8db6d-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8db6d-131">string</span></span> | <span data-ttu-id="8db6d-132">URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à</span><span class="sxs-lookup"><span data-stu-id="8db6d-132">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="8db6d-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8db6d-133">string</span></span> | <span data-ttu-id="8db6d-134">Endereço IP que estava sendo conectado ao</span><span class="sxs-lookup"><span data-stu-id="8db6d-134">IP address that was being connected to</span></span> |
| `ReportId` | <span data-ttu-id="8db6d-135">long</span><span class="sxs-lookup"><span data-stu-id="8db6d-135">long</span></span> | <span data-ttu-id="8db6d-136">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="8db6d-136">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="8db6d-137">Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp</span><span class="sxs-lookup"><span data-stu-id="8db6d-137">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `Table` | <span data-ttu-id="8db6d-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8db6d-138">string</span></span> | <span data-ttu-id="8db6d-139">Tabela que contém os detalhes do evento</span><span class="sxs-lookup"><span data-stu-id="8db6d-139">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="8db6d-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8db6d-140">Related topics</span></span>
- [<span data-ttu-id="8db6d-141">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="8db6d-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8db6d-142">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="8db6d-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8db6d-143">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="8db6d-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="8db6d-144">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="8db6d-144">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="8db6d-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="8db6d-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8db6d-146">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="8db6d-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
