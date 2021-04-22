---
title: Tabela DeviceAlertEvents no esquema de busca avançado
description: Saiba mais sobre eventos de geração de alertas na tabela DeviceAlertEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, microsoft defender para ponto de extremidade, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, DeviceAlertEvents, alerta, gravidade, categoria
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/22/2020
ms.technology: mde
ms.openlocfilehash: f4f6ecdc57d8602f49fb389c741c5e01dc1b41b5
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939643"
---
# <a name="devicealertevents"></a><span data-ttu-id="021cd-104">DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="021cd-104">DeviceAlertEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="021cd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="021cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="021cd-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="021cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="021cd-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="021cd-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="021cd-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="021cd-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="021cd-109">A `DeviceAlertEvents` tabela no esquema de busca [avançado](advanced-hunting-overview.md) contém informações sobre alertas no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="021cd-109">The `DeviceAlertEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about alerts in Microsoft Defender Security Center.</span></span> <span data-ttu-id="021cd-110">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="021cd-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="021cd-111">Para obter informações sobre outras tabelas no esquema de busca avançado, consulte [a referência avançada do esquema de busca](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="021cd-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="021cd-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="021cd-112">Column name</span></span> | <span data-ttu-id="021cd-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="021cd-113">Data type</span></span> | <span data-ttu-id="021cd-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="021cd-114">Description</span></span> |
|-------------|-----------|-------------|
| `AlertId` | <span data-ttu-id="021cd-115">string</span><span class="sxs-lookup"><span data-stu-id="021cd-115">string</span></span> | <span data-ttu-id="021cd-116">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="021cd-116">Unique identifier for the alert</span></span> |
| `Timestamp` | <span data-ttu-id="021cd-117">datetime</span><span class="sxs-lookup"><span data-stu-id="021cd-117">datetime</span></span> | <span data-ttu-id="021cd-118">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="021cd-118">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="021cd-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-119">string</span></span> | <span data-ttu-id="021cd-120">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="021cd-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="021cd-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-121">string</span></span> | <span data-ttu-id="021cd-122">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="021cd-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `Severity` | <span data-ttu-id="021cd-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-123">string</span></span> | <span data-ttu-id="021cd-124">Indica o impacto potencial (alto, médio ou baixo) do indicador de ameaça ou da atividade de violação identificados pelo alerta</span><span class="sxs-lookup"><span data-stu-id="021cd-124">Indicates the potential impact (high, medium, or low) of the threat indicator or breach activity identified by the alert</span></span> |
| `Category` | <span data-ttu-id="021cd-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-125">string</span></span> | <span data-ttu-id="021cd-126">Tipo de atividade indicadora de ameaça ou violação identificada pelo alerta</span><span class="sxs-lookup"><span data-stu-id="021cd-126">Type of threat indicator or breach activity identified by the alert</span></span> |
| `Title` | <span data-ttu-id="021cd-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-127">string</span></span> | <span data-ttu-id="021cd-128">Título do alerta</span><span class="sxs-lookup"><span data-stu-id="021cd-128">Title of the alert</span></span> |
| `FileName` | <span data-ttu-id="021cd-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-129">string</span></span> | <span data-ttu-id="021cd-130">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="021cd-130">Name of the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="021cd-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-131">string</span></span> | <span data-ttu-id="021cd-132">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="021cd-132">SHA-1 of the file that the recorded action was applied to</span></span> |
| `RemoteUrl` | <span data-ttu-id="021cd-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-133">string</span></span> | <span data-ttu-id="021cd-134">URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à</span><span class="sxs-lookup"><span data-stu-id="021cd-134">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `RemoteIP` | <span data-ttu-id="021cd-135">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-135">string</span></span> | <span data-ttu-id="021cd-136">Endereço IP que estava sendo conectado ao</span><span class="sxs-lookup"><span data-stu-id="021cd-136">IP address that was being connected to</span></span> |
| `AttackTechniques` | <span data-ttu-id="021cd-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-137">string</span></span> | <span data-ttu-id="021cd-138">MITRE ATT&técnicas de CK associadas à atividade que disparou o alerta</span><span class="sxs-lookup"><span data-stu-id="021cd-138">MITRE ATT&CK techniques associated with the activity that triggered the alert</span></span> |
| `ReportId` | <span data-ttu-id="021cd-139">long</span><span class="sxs-lookup"><span data-stu-id="021cd-139">long</span></span> | <span data-ttu-id="021cd-140">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="021cd-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="021cd-141">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com `DeviceName` as `Timestamp` colunas e</span><span class="sxs-lookup"><span data-stu-id="021cd-141">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `Table` | <span data-ttu-id="021cd-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="021cd-142">string</span></span> | <span data-ttu-id="021cd-143">Tabela que contém os detalhes do evento</span><span class="sxs-lookup"><span data-stu-id="021cd-143">Table that contains the details of the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="021cd-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="021cd-144">Related topics</span></span>
- [<span data-ttu-id="021cd-145">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="021cd-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="021cd-146">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="021cd-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="021cd-147">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="021cd-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
