---
title: Nomenisar alterações no esquema de busca avançada do Microsoft 365 Defender
description: Controlar e revisar as alterações de nomenis e colunas no esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, dados, alterações de nomeação, renomear
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
ms.openlocfilehash: 22d26dac6b7ee502d6934349d22b1d40532f575f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935768"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="69ff2-104">Esquema de busca avançado - Alterações de nomenis</span><span class="sxs-lookup"><span data-stu-id="69ff2-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="69ff2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="69ff2-105">**Applies to:**</span></span>
- <span data-ttu-id="69ff2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69ff2-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="69ff2-107">O [esquema de busca avançado](advanced-hunting-schema-tables.md) é atualizado regularmente para adicionar novas tabelas e colunas.</span><span class="sxs-lookup"><span data-stu-id="69ff2-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="69ff2-108">Em alguns casos, os nomes de colunas existentes são renomeados ou substituídos para melhorar a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="69ff2-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="69ff2-109">Consulte este artigo para revisar as alterações de nomeniso que podem afetar suas consultas.</span><span class="sxs-lookup"><span data-stu-id="69ff2-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="69ff2-110">As alterações de nomenisagem são aplicadas automaticamente a consultas salvas no centro de segurança, incluindo consultas usadas por regras de detecção personalizadas.</span><span class="sxs-lookup"><span data-stu-id="69ff2-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="69ff2-111">Você não precisa atualizar essas consultas manualmente.</span><span class="sxs-lookup"><span data-stu-id="69ff2-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="69ff2-112">No entanto, você precisará atualizar as seguintes consultas:</span><span class="sxs-lookup"><span data-stu-id="69ff2-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="69ff2-113">Consultas que são executados usando a API</span><span class="sxs-lookup"><span data-stu-id="69ff2-113">Queries that are run using the API</span></span>
- <span data-ttu-id="69ff2-114">Consultas salvas em outro lugar fora do centro de segurança</span><span class="sxs-lookup"><span data-stu-id="69ff2-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="69ff2-115">Dezembro de 2020</span><span class="sxs-lookup"><span data-stu-id="69ff2-115">December 2020</span></span>

| <span data-ttu-id="69ff2-116">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="69ff2-116">Table name</span></span> | <span data-ttu-id="69ff2-117">Nome da coluna original</span><span class="sxs-lookup"><span data-stu-id="69ff2-117">Original column name</span></span> | <span data-ttu-id="69ff2-118">Novo nome da coluna</span><span class="sxs-lookup"><span data-stu-id="69ff2-118">New column name</span></span> | <span data-ttu-id="69ff2-119">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="69ff2-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="69ff2-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="69ff2-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="69ff2-121">Comentários do cliente</span><span class="sxs-lookup"><span data-stu-id="69ff2-121">Customer feedback</span></span> |
| [<span data-ttu-id="69ff2-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="69ff2-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="69ff2-123">Comentários do cliente</span><span class="sxs-lookup"><span data-stu-id="69ff2-123">Customer feedback</span></span> |
| [<span data-ttu-id="69ff2-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="69ff2-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="69ff2-125">Comentários do cliente</span><span class="sxs-lookup"><span data-stu-id="69ff2-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="69ff2-126">Janeiro de 2021</span><span class="sxs-lookup"><span data-stu-id="69ff2-126">January 2021</span></span>

| <span data-ttu-id="69ff2-127">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="69ff2-127">Column name</span></span> | <span data-ttu-id="69ff2-128">Nome do valor original</span><span class="sxs-lookup"><span data-stu-id="69ff2-128">Original value name</span></span> | <span data-ttu-id="69ff2-129">Novo nome de valor</span><span class="sxs-lookup"><span data-stu-id="69ff2-129">New value name</span></span> | <span data-ttu-id="69ff2-130">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="69ff2-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="69ff2-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="69ff2-131">MCAS</span></span> |    <span data-ttu-id="69ff2-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="69ff2-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="69ff2-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="69ff2-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="69ff2-135">EDR</span><span class="sxs-lookup"><span data-stu-id="69ff2-135">EDR</span></span>| <span data-ttu-id="69ff2-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="69ff2-137">WindowsDefenderAv</span></span> | <span data-ttu-id="69ff2-138">Antivírus</span><span class="sxs-lookup"><span data-stu-id="69ff2-138">Antivirus</span></span> | <span data-ttu-id="69ff2-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="69ff2-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="69ff2-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="69ff2-141">SmartScreen</span></span> | <span data-ttu-id="69ff2-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="69ff2-143">CustomerTI</span></span> |  <span data-ttu-id="69ff2-144">TI personalizada</span><span class="sxs-lookup"><span data-stu-id="69ff2-144">Custom TI</span></span> | <span data-ttu-id="69ff2-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="69ff2-146">OfficeATP</span></span> | <span data-ttu-id="69ff2-147">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="69ff2-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="69ff2-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-149">MTP</span><span class="sxs-lookup"><span data-stu-id="69ff2-149">MTP</span></span>   | <span data-ttu-id="69ff2-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69ff2-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="69ff2-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="69ff2-152">AzureATP</span></span> |    <span data-ttu-id="69ff2-153">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="69ff2-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="69ff2-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="69ff2-155">CustomDetection</span></span>   | <span data-ttu-id="69ff2-156">Detecção personalizada</span><span class="sxs-lookup"><span data-stu-id="69ff2-156">Custom detection</span></span> | <span data-ttu-id="69ff2-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="69ff2-158">AutomatedInvestigation</span></span> |<span data-ttu-id="69ff2-159">Investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="69ff2-159">Automated investigation</span></span> | <span data-ttu-id="69ff2-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="69ff2-161">ThreatExperts</span></span> | <span data-ttu-id="69ff2-162">Especialistas em Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="69ff2-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="69ff2-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="69ff2-164">TI de terceiros</span><span class="sxs-lookup"><span data-stu-id="69ff2-164">3rd party TI</span></span> | <span data-ttu-id="69ff2-165">Sensores de terceiros</span><span class="sxs-lookup"><span data-stu-id="69ff2-165">3rd Party sensors</span></span> | <span data-ttu-id="69ff2-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="69ff2-167">O Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="69ff2-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="69ff2-168">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="69ff2-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="69ff2-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="69ff2-170">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="69ff2-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="69ff2-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69ff2-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="69ff2-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="69ff2-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="69ff2-173">Office 365 ATP</span></span>  |<span data-ttu-id="69ff2-174">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="69ff2-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="69ff2-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="69ff2-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="69ff2-176">Azure ATP</span></span>    |<span data-ttu-id="69ff2-177">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="69ff2-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="69ff2-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="69ff2-178">Rebranding</span></span> |

<span data-ttu-id="69ff2-179">`DetectionSource`está disponível na tabela [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="69ff2-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="69ff2-180">`ServiceSource`está disponível nas tabelas [AlertEvidence e](advanced-hunting-alertevidence-table.md) [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="69ff2-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="69ff2-181">Fevereiro de 2021</span><span class="sxs-lookup"><span data-stu-id="69ff2-181">February 2021</span></span>

1. <span data-ttu-id="69ff2-182">Nas tabelas [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) e [EmailEvents,](advanced-hunting-emailevents-table.md) as colunas e foram `MalwareFilterVerdict` `PhishFilterVerdict` substituídas pela `ThreatTypes` coluna.</span><span class="sxs-lookup"><span data-stu-id="69ff2-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="69ff2-183">As `MalwareDetectionMethod` `PhishDetectionMethod` colunas e também foram substituídas pela `DetectionMethods` coluna.</span><span class="sxs-lookup"><span data-stu-id="69ff2-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="69ff2-184">Esse fluxo permite que forneçamos mais informações nas novas colunas.</span><span class="sxs-lookup"><span data-stu-id="69ff2-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="69ff2-185">O mapeamento é fornecido abaixo.</span><span class="sxs-lookup"><span data-stu-id="69ff2-185">The mapping is provided below.</span></span>

| <span data-ttu-id="69ff2-186">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="69ff2-186">Table name</span></span> | <span data-ttu-id="69ff2-187">Nome da coluna original</span><span class="sxs-lookup"><span data-stu-id="69ff2-187">Original column name</span></span> | <span data-ttu-id="69ff2-188">Novo nome da coluna</span><span class="sxs-lookup"><span data-stu-id="69ff2-188">New column name</span></span> | <span data-ttu-id="69ff2-189">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="69ff2-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="69ff2-190">Incluir mais métodos de detecção</span><span class="sxs-lookup"><span data-stu-id="69ff2-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="69ff2-191">Incluir mais tipos de ameaça</span><span class="sxs-lookup"><span data-stu-id="69ff2-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="69ff2-192">Incluir mais métodos de detecção</span><span class="sxs-lookup"><span data-stu-id="69ff2-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="69ff2-193">Incluir mais tipos de ameaça</span><span class="sxs-lookup"><span data-stu-id="69ff2-193">Include more threat types</span></span> |


2. <span data-ttu-id="69ff2-194">Nas `EmailAttachmentInfo` `EmailEvents` tabelas e, a `ThreatNames` coluna foi adicionada para dar mais informações sobre a ameaça de email.</span><span class="sxs-lookup"><span data-stu-id="69ff2-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="69ff2-195">Esta coluna contém valores como Spam ou Phish.</span><span class="sxs-lookup"><span data-stu-id="69ff2-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="69ff2-196">Na tabela [DeviceInfo,](advanced-hunting-deviceinfo-table.md) a coluna foi substituída pela coluna `DeviceObjectId` com base nos comentários do `AadDeviceId` cliente.</span><span class="sxs-lookup"><span data-stu-id="69ff2-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="69ff2-197">Na tabela [DeviceEvents,](advanced-hunting-deviceevents-table.md) vários nomes ActionType foram modificados para refletir melhor a descrição da ação.</span><span class="sxs-lookup"><span data-stu-id="69ff2-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="69ff2-198">Detalhes das alterações podem ser encontrados abaixo.</span><span class="sxs-lookup"><span data-stu-id="69ff2-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="69ff2-199">Nome da tabela</span><span class="sxs-lookup"><span data-stu-id="69ff2-199">Table name</span></span> | <span data-ttu-id="69ff2-200">Nome actionType original</span><span class="sxs-lookup"><span data-stu-id="69ff2-200">Original ActionType name</span></span> | <span data-ttu-id="69ff2-201">Novo nome ActionType</span><span class="sxs-lookup"><span data-stu-id="69ff2-201">New ActionType name</span></span> | <span data-ttu-id="69ff2-202">Motivo da alteração</span><span class="sxs-lookup"><span data-stu-id="69ff2-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="69ff2-203">Comentários do cliente</span><span class="sxs-lookup"><span data-stu-id="69ff2-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="69ff2-204">Comentários do cliente</span><span class="sxs-lookup"><span data-stu-id="69ff2-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="69ff2-205">Comentários do cliente</span><span class="sxs-lookup"><span data-stu-id="69ff2-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="69ff2-206">Comentários do cliente</span><span class="sxs-lookup"><span data-stu-id="69ff2-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="69ff2-207">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="69ff2-207">Related topics</span></span>
- [<span data-ttu-id="69ff2-208">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="69ff2-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="69ff2-209">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="69ff2-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)