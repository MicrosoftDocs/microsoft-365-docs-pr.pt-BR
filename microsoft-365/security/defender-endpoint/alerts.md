---
title: Obter API de alertas
description: Saiba mais sobre os métodos e propriedades do tipo de recurso Alerta no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, alertas, recentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c935df1abddc3d0ebee74e09280d6e3ec961ca97
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769804"
---
# <a name="alert-resource-type"></a><span data-ttu-id="418b3-104">Tipo de recurso de alerta</span><span class="sxs-lookup"><span data-stu-id="418b3-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="418b3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="418b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="418b3-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="418b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="418b3-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="418b3-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="418b3-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="418b3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="418b3-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="418b3-109">Methods</span></span>

<span data-ttu-id="418b3-110">Método</span><span class="sxs-lookup"><span data-stu-id="418b3-110">Method</span></span> |<span data-ttu-id="418b3-111">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="418b3-111">Return Type</span></span> |<span data-ttu-id="418b3-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="418b3-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="418b3-113">Obter alerta</span><span class="sxs-lookup"><span data-stu-id="418b3-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="418b3-114">Alerta</span><span class="sxs-lookup"><span data-stu-id="418b3-114">Alert</span></span>](alerts.md) | <span data-ttu-id="418b3-115">Obter um único [objeto de](alerts.md) alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="418b3-116">Listar alertas</span><span class="sxs-lookup"><span data-stu-id="418b3-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="418b3-117">[Coleção Alert](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="418b3-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="418b3-118">Listar [coleção de](alerts.md) alertas.</span><span class="sxs-lookup"><span data-stu-id="418b3-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="418b3-119">Atualizar alertas</span><span class="sxs-lookup"><span data-stu-id="418b3-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="418b3-120">Alerta</span><span class="sxs-lookup"><span data-stu-id="418b3-120">Alert</span></span>](alerts.md) | <span data-ttu-id="418b3-121">Atualizar alerta [específico](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="418b3-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="418b3-122">Alertas de atualização em lotes</span><span class="sxs-lookup"><span data-stu-id="418b3-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="418b3-123">Atualizar um lote de [alertas](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="418b3-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="418b3-124">Criar alerta</span><span class="sxs-lookup"><span data-stu-id="418b3-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="418b3-125">Alerta</span><span class="sxs-lookup"><span data-stu-id="418b3-125">Alert</span></span>](alerts.md)|<span data-ttu-id="418b3-126">Criar um alerta com base nos dados de evento obtidos da [Busca Avançada](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="418b3-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="418b3-127">Listar domínios relacionados</span><span class="sxs-lookup"><span data-stu-id="418b3-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="418b3-128">Coleção Domain</span><span class="sxs-lookup"><span data-stu-id="418b3-128">Domain collection</span></span>| <span data-ttu-id="418b3-129">Listar URLs associadas ao alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="418b3-130">Listar arquivos relacionados</span><span class="sxs-lookup"><span data-stu-id="418b3-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="418b3-131">[Coleção File](files.md)</span><span class="sxs-lookup"><span data-stu-id="418b3-131">[File](files.md) collection</span></span> |  <span data-ttu-id="418b3-132">Listar [as entidades](files.md) de arquivo associadas ao [alerta](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="418b3-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="418b3-133">Listar IPs relacionados</span><span class="sxs-lookup"><span data-stu-id="418b3-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="418b3-134">Coleção IP</span><span class="sxs-lookup"><span data-stu-id="418b3-134">IP collection</span></span> | <span data-ttu-id="418b3-135">Listar IPs associados ao alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="418b3-136">Obter máquinas relacionadas</span><span class="sxs-lookup"><span data-stu-id="418b3-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="418b3-137">Computador</span><span class="sxs-lookup"><span data-stu-id="418b3-137">Machine</span></span>](machine.md) | <span data-ttu-id="418b3-138">O [computador](machine.md) associado ao [alerta](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="418b3-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="418b3-139">Obter usuários relacionados</span><span class="sxs-lookup"><span data-stu-id="418b3-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="418b3-140">Usuário</span><span class="sxs-lookup"><span data-stu-id="418b3-140">User</span></span>](user.md) | <span data-ttu-id="418b3-141">O [usuário](user.md) associado ao [alerta](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="418b3-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>


## <a name="properties"></a><span data-ttu-id="418b3-142">Propriedades</span><span class="sxs-lookup"><span data-stu-id="418b3-142">Properties</span></span>

<span data-ttu-id="418b3-143">Propriedade</span><span class="sxs-lookup"><span data-stu-id="418b3-143">Property</span></span> |    <span data-ttu-id="418b3-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="418b3-144">Type</span></span>    |    <span data-ttu-id="418b3-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="418b3-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="418b3-146">id</span><span class="sxs-lookup"><span data-stu-id="418b3-146">id</span></span> | <span data-ttu-id="418b3-147">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="418b3-147">String</span></span> | <span data-ttu-id="418b3-148">ID do alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-148">Alert ID.</span></span>
<span data-ttu-id="418b3-149">title</span><span class="sxs-lookup"><span data-stu-id="418b3-149">title</span></span> | <span data-ttu-id="418b3-150">String</span><span class="sxs-lookup"><span data-stu-id="418b3-150">String</span></span> | <span data-ttu-id="418b3-151">Título do alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-151">Alert title.</span></span>
<span data-ttu-id="418b3-152">descrição</span><span class="sxs-lookup"><span data-stu-id="418b3-152">description</span></span> | <span data-ttu-id="418b3-153">String</span><span class="sxs-lookup"><span data-stu-id="418b3-153">String</span></span> | <span data-ttu-id="418b3-154">Descrição de alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-154">Alert description.</span></span>
<span data-ttu-id="418b3-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="418b3-155">alertCreationTime</span></span> | <span data-ttu-id="418b3-156">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="418b3-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="418b3-157">A data e a hora (em UTC) em que o alerta foi criado.</span><span class="sxs-lookup"><span data-stu-id="418b3-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="418b3-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="418b3-158">lastEventTime</span></span> | <span data-ttu-id="418b3-159">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="418b3-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="418b3-160">A última ocorrência do evento que disparou o alerta no mesmo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="418b3-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="418b3-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="418b3-161">firstEventTime</span></span> | <span data-ttu-id="418b3-162">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="418b3-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="418b3-163">A primeira ocorrência do evento que disparou o alerta nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="418b3-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="418b3-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="418b3-164">lastUpdateTime</span></span> | <span data-ttu-id="418b3-165">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="418b3-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="418b3-166">A data e a hora (em UTC) em que o alerta foi atualizado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="418b3-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="418b3-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="418b3-167">resolvedTime</span></span> | <span data-ttu-id="418b3-168">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="418b3-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="418b3-169">A data e a hora em que o status do alerta foi alterado para 'Resolvido'.</span><span class="sxs-lookup"><span data-stu-id="418b3-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="418b3-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="418b3-170">incidentId</span></span> | <span data-ttu-id="418b3-171">Long anulado</span><span class="sxs-lookup"><span data-stu-id="418b3-171">Nullable Long</span></span> | <span data-ttu-id="418b3-172">A [](view-incidents-queue.md) ID do Incidente do Alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="418b3-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="418b3-173">investigationId</span></span> | <span data-ttu-id="418b3-174">Long anulado</span><span class="sxs-lookup"><span data-stu-id="418b3-174">Nullable Long</span></span> | <span data-ttu-id="418b3-175">A [](automated-investigations.md) ID da Investigação relacionada ao Alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="418b3-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="418b3-176">investigationState</span></span> | <span data-ttu-id="418b3-177">Núm anulado</span><span class="sxs-lookup"><span data-stu-id="418b3-177">Nullable Enum</span></span> | <span data-ttu-id="418b3-178">O estado atual da [Investigação](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="418b3-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="418b3-179">Os valores possíveis são: 'Unknown', 'Terminado', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="418b3-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="418b3-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="418b3-180">assignedTo</span></span> | <span data-ttu-id="418b3-181">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="418b3-181">String</span></span> | <span data-ttu-id="418b3-182">Proprietário do alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-182">Owner of the alert.</span></span>
<span data-ttu-id="418b3-183">severity</span><span class="sxs-lookup"><span data-stu-id="418b3-183">severity</span></span> | <span data-ttu-id="418b3-184">Enum</span><span class="sxs-lookup"><span data-stu-id="418b3-184">Enum</span></span> | <span data-ttu-id="418b3-185">Gravidade do alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-185">Severity of the alert.</span></span> <span data-ttu-id="418b3-186">Os valores possíveis são: 'UnSpecified', 'Informational', 'Low', 'Medium' e 'High'.</span><span class="sxs-lookup"><span data-stu-id="418b3-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="418b3-187">status</span><span class="sxs-lookup"><span data-stu-id="418b3-187">status</span></span> | <span data-ttu-id="418b3-188">Enum</span><span class="sxs-lookup"><span data-stu-id="418b3-188">Enum</span></span> | <span data-ttu-id="418b3-189">Especifica o status atual do alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="418b3-190">Os valores possíveis são: 'Unknown', 'New', 'InProgress' e 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="418b3-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="418b3-191">classificação</span><span class="sxs-lookup"><span data-stu-id="418b3-191">classification</span></span> | <span data-ttu-id="418b3-192">Núm anulado</span><span class="sxs-lookup"><span data-stu-id="418b3-192">Nullable Enum</span></span> | <span data-ttu-id="418b3-193">Especificação do alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-193">Specification of the alert.</span></span> <span data-ttu-id="418b3-194">Os valores possíveis são: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="418b3-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="418b3-195">determinação</span><span class="sxs-lookup"><span data-stu-id="418b3-195">determination</span></span> | <span data-ttu-id="418b3-196">Núm anulado</span><span class="sxs-lookup"><span data-stu-id="418b3-196">Nullable Enum</span></span> | <span data-ttu-id="418b3-197">Especifica a determinação do alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="418b3-198">Os valores possíveis são: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span><span class="sxs-lookup"><span data-stu-id="418b3-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="418b3-199">category</span><span class="sxs-lookup"><span data-stu-id="418b3-199">category</span></span>| <span data-ttu-id="418b3-200">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="418b3-200">String</span></span> | <span data-ttu-id="418b3-201">Categoria do alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-201">Category of the alert.</span></span>
<span data-ttu-id="418b3-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="418b3-202">detectionSource</span></span> | <span data-ttu-id="418b3-203">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="418b3-203">String</span></span> | <span data-ttu-id="418b3-204">Fonte de detecção.</span><span class="sxs-lookup"><span data-stu-id="418b3-204">Detection source.</span></span>
<span data-ttu-id="418b3-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="418b3-205">threatFamilyName</span></span> | <span data-ttu-id="418b3-206">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="418b3-206">String</span></span> | <span data-ttu-id="418b3-207">Família de ameaças.</span><span class="sxs-lookup"><span data-stu-id="418b3-207">Threat family.</span></span>
<span data-ttu-id="418b3-208">threatName</span><span class="sxs-lookup"><span data-stu-id="418b3-208">threatName</span></span> | <span data-ttu-id="418b3-209">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="418b3-209">String</span></span> | <span data-ttu-id="418b3-210">Nome da ameaça.</span><span class="sxs-lookup"><span data-stu-id="418b3-210">Threat name.</span></span>
<span data-ttu-id="418b3-211">machineId</span><span class="sxs-lookup"><span data-stu-id="418b3-211">machineId</span></span> | <span data-ttu-id="418b3-212">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="418b3-212">String</span></span> | <span data-ttu-id="418b3-213">ID de uma [entidade](machine.md) de máquina associada ao alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="418b3-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="418b3-214">computerDnsName</span></span> | <span data-ttu-id="418b3-215">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="418b3-215">String</span></span> | <span data-ttu-id="418b3-216">[nome](machine.md) totalmente qualificado da máquina.</span><span class="sxs-lookup"><span data-stu-id="418b3-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="418b3-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="418b3-217">aadTenantId</span></span> | <span data-ttu-id="418b3-218">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="418b3-218">String</span></span> | <span data-ttu-id="418b3-219">A Azure Active Directory ID.</span><span class="sxs-lookup"><span data-stu-id="418b3-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="418b3-220">detectorId</span><span class="sxs-lookup"><span data-stu-id="418b3-220">detectorId</span></span> | <span data-ttu-id="418b3-221">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="418b3-221">String</span></span> | <span data-ttu-id="418b3-222">A ID do detector que disparou o alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="418b3-223">comentários</span><span class="sxs-lookup"><span data-stu-id="418b3-223">comments</span></span> | <span data-ttu-id="418b3-224">Lista de comentários de alerta</span><span class="sxs-lookup"><span data-stu-id="418b3-224">List of Alert comments</span></span> | <span data-ttu-id="418b3-225">O objeto Comentário de Alerta contém: cadeia de caracteres de comentários, createdBy string e createTime date time.</span><span class="sxs-lookup"><span data-stu-id="418b3-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="418b3-226">Evidências</span><span class="sxs-lookup"><span data-stu-id="418b3-226">Evidence</span></span> | <span data-ttu-id="418b3-227">Lista de evidências de alerta</span><span class="sxs-lookup"><span data-stu-id="418b3-227">List of Alert evidence</span></span> | <span data-ttu-id="418b3-228">Evidências relacionadas ao alerta.</span><span class="sxs-lookup"><span data-stu-id="418b3-228">Evidence related to the alert.</span></span> <span data-ttu-id="418b3-229">Veja o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="418b3-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="418b3-230">Exemplo de resposta para obter um único alerta:</span><span class="sxs-lookup"><span data-stu-id="418b3-230">Response example for getting single alert:</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
