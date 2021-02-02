---
title: Alterações de nomeação no esquema de busca avançada do Microsoft 365 Defender
description: Acompanhar e revisar as tabelas e colunas de alterações de nomeação no esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, dados, alterações de nomeação, renomear, Proteção contra Ameaças da Microsoft
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
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066864"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="2eebd-104">Esquema de busca avançada - Alterações de nomeação</span><span class="sxs-lookup"><span data-stu-id="2eebd-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2eebd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2eebd-105">**Applies to:**</span></span>
- <span data-ttu-id="2eebd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2eebd-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2eebd-107">O [esquema de busca avançada é](advanced-hunting-schema-tables.md) atualizado regularmente para adicionar novas tabelas e colunas.</span><span class="sxs-lookup"><span data-stu-id="2eebd-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="2eebd-108">Em alguns casos, os nomes de colunas existentes são renomeados ou substituídos para melhorar a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="2eebd-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="2eebd-109">Consulte este artigo para revisar as alterações de nomeação que podem afetar suas consultas.</span><span class="sxs-lookup"><span data-stu-id="2eebd-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="2eebd-110">As alterações de nomeação são aplicadas automaticamente às consultas salvas no centro de segurança, incluindo consultas usadas por regras de detecção personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2eebd-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="2eebd-111">Você não precisa atualizar essas consultas manualmente.</span><span class="sxs-lookup"><span data-stu-id="2eebd-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="2eebd-112">No entanto, você precisará atualizar as seguintes consultas:</span><span class="sxs-lookup"><span data-stu-id="2eebd-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="2eebd-113">Consultas que são executados usando a API</span><span class="sxs-lookup"><span data-stu-id="2eebd-113">Queries that are run using the API</span></span>
- <span data-ttu-id="2eebd-114">Consultas salvas em outro lugar fora da central de segurança</span><span class="sxs-lookup"><span data-stu-id="2eebd-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="2eebd-115">Dezembro de 2020</span><span class="sxs-lookup"><span data-stu-id="2eebd-115">December 2020</span></span>

| <span data-ttu-id="2eebd-116">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="2eebd-116">Table name</span></span> | <span data-ttu-id="2eebd-117">Nome da coluna original</span><span class="sxs-lookup"><span data-stu-id="2eebd-117">Original column name</span></span> | <span data-ttu-id="2eebd-118">Novo nome de coluna</span><span class="sxs-lookup"><span data-stu-id="2eebd-118">New column name</span></span> | <span data-ttu-id="2eebd-119">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="2eebd-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="2eebd-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="2eebd-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="2eebd-121">Comentários dos clientes</span><span class="sxs-lookup"><span data-stu-id="2eebd-121">Customer feedback</span></span> |
| [<span data-ttu-id="2eebd-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="2eebd-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="2eebd-123">Comentários dos clientes</span><span class="sxs-lookup"><span data-stu-id="2eebd-123">Customer feedback</span></span> |
| [<span data-ttu-id="2eebd-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="2eebd-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="2eebd-125">Comentários dos clientes</span><span class="sxs-lookup"><span data-stu-id="2eebd-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="2eebd-126">Janeiro de 2021</span><span class="sxs-lookup"><span data-stu-id="2eebd-126">January 2021</span></span>

| <span data-ttu-id="2eebd-127">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="2eebd-127">Column name</span></span> | <span data-ttu-id="2eebd-128">Nome do valor original</span><span class="sxs-lookup"><span data-stu-id="2eebd-128">Original value name</span></span> | <span data-ttu-id="2eebd-129">Nome do novo valor</span><span class="sxs-lookup"><span data-stu-id="2eebd-129">New value name</span></span> | <span data-ttu-id="2eebd-130">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="2eebd-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="2eebd-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="2eebd-131">MCAS</span></span> |    <span data-ttu-id="2eebd-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2eebd-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="2eebd-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="2eebd-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="2eebd-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="2eebd-135">EDR</span><span class="sxs-lookup"><span data-stu-id="2eebd-135">EDR</span></span>| <span data-ttu-id="2eebd-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="2eebd-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="2eebd-137">WindowsDefenderAv</span></span> | <span data-ttu-id="2eebd-138">Antivírus</span><span class="sxs-lookup"><span data-stu-id="2eebd-138">Antivirus</span></span> | <span data-ttu-id="2eebd-139">Renomear</span><span class="sxs-lookup"><span data-stu-id="2eebd-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="2eebd-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="2eebd-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="2eebd-141">SmartScreen</span></span> | <span data-ttu-id="2eebd-142">Renomear</span><span class="sxs-lookup"><span data-stu-id="2eebd-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="2eebd-143">CustomerTI</span></span> |  <span data-ttu-id="2eebd-144">TI personalizada</span><span class="sxs-lookup"><span data-stu-id="2eebd-144">Custom TI</span></span> | <span data-ttu-id="2eebd-145">Renomear</span><span class="sxs-lookup"><span data-stu-id="2eebd-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="2eebd-146">OfficeATP</span></span> | <span data-ttu-id="2eebd-147">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2eebd-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="2eebd-148">Renomear</span><span class="sxs-lookup"><span data-stu-id="2eebd-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-149">MTP</span><span class="sxs-lookup"><span data-stu-id="2eebd-149">MTP</span></span>   | <span data-ttu-id="2eebd-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2eebd-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="2eebd-151">Renomear</span><span class="sxs-lookup"><span data-stu-id="2eebd-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="2eebd-152">AzureATP</span></span> |    <span data-ttu-id="2eebd-153">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="2eebd-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="2eebd-154">Renomear</span><span class="sxs-lookup"><span data-stu-id="2eebd-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="2eebd-155">CustomDetection</span></span>   | <span data-ttu-id="2eebd-156">Detecção personalizada</span><span class="sxs-lookup"><span data-stu-id="2eebd-156">Custom detection</span></span> | <span data-ttu-id="2eebd-157">Renomear</span><span class="sxs-lookup"><span data-stu-id="2eebd-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="2eebd-158">AutomatedInvestigation</span></span> |<span data-ttu-id="2eebd-159">Investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="2eebd-159">Automated investigation</span></span> | <span data-ttu-id="2eebd-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="2eebd-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="2eebd-161">ThreatExperts</span></span> | <span data-ttu-id="2eebd-162">Especialistas em ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2eebd-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="2eebd-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="2eebd-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="2eebd-164">TI de terceiros</span><span class="sxs-lookup"><span data-stu-id="2eebd-164">3rd party TI</span></span> | <span data-ttu-id="2eebd-165">Sensores de terceiros</span><span class="sxs-lookup"><span data-stu-id="2eebd-165">3rd Party sensors</span></span> | <span data-ttu-id="2eebd-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="2eebd-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="2eebd-167">O Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="2eebd-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="2eebd-168">Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2eebd-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="2eebd-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="2eebd-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="2eebd-170">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2eebd-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="2eebd-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2eebd-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="2eebd-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="2eebd-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="2eebd-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="2eebd-173">Office 365 ATP</span></span>  |<span data-ttu-id="2eebd-174">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2eebd-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="2eebd-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="2eebd-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="2eebd-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="2eebd-176">Azure ATP</span></span>    |<span data-ttu-id="2eebd-177">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="2eebd-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="2eebd-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="2eebd-178">Rebranding</span></span> |

<span data-ttu-id="2eebd-179">`DetectionSource`está disponível na [tabela AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="2eebd-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="2eebd-180">`ServiceSource`está disponível nas [tabelas AlertEvidence](advanced-hunting-alertevidence-table.md) e [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="2eebd-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="2eebd-181">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2eebd-181">Related topics</span></span>
- [<span data-ttu-id="2eebd-182">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="2eebd-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2eebd-183">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="2eebd-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)