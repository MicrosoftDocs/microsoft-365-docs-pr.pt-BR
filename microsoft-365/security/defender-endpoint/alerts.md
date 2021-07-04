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
ms.openlocfilehash: df1a032ffab0490c41edc7d282f0f2cc60608870
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289674"
---
# <a name="alert-resource-type"></a><span data-ttu-id="09567-104">Tipo de recurso de alerta</span><span class="sxs-lookup"><span data-stu-id="09567-104">Alert resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09567-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="09567-105">**Applies to:**</span></span>
- [<span data-ttu-id="09567-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="09567-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="09567-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="09567-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="09567-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="09567-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a><span data-ttu-id="09567-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="09567-109">Methods</span></span>

<span data-ttu-id="09567-110">Método</span><span class="sxs-lookup"><span data-stu-id="09567-110">Method</span></span> |<span data-ttu-id="09567-111">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="09567-111">Return Type</span></span> |<span data-ttu-id="09567-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="09567-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="09567-113">Obter alerta</span><span class="sxs-lookup"><span data-stu-id="09567-113">Get alert</span></span>](get-alert-info-by-id.md) | [<span data-ttu-id="09567-114">Alerta</span><span class="sxs-lookup"><span data-stu-id="09567-114">Alert</span></span>](alerts.md) | <span data-ttu-id="09567-115">Obter um único [objeto de](alerts.md) alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-115">Get a single [alert](alerts.md) object.</span></span>
[<span data-ttu-id="09567-116">Listar alertas</span><span class="sxs-lookup"><span data-stu-id="09567-116">List alerts</span></span>](get-alerts.md) | <span data-ttu-id="09567-117">[Coleção Alert](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="09567-117">[Alert](alerts.md) collection</span></span> | <span data-ttu-id="09567-118">Listar [coleção de](alerts.md) alertas.</span><span class="sxs-lookup"><span data-stu-id="09567-118">List [alert](alerts.md) collection.</span></span>
[<span data-ttu-id="09567-119">Atualizar alertas</span><span class="sxs-lookup"><span data-stu-id="09567-119">Update alert</span></span>](update-alert.md) | [<span data-ttu-id="09567-120">Alerta</span><span class="sxs-lookup"><span data-stu-id="09567-120">Alert</span></span>](alerts.md) | <span data-ttu-id="09567-121">Atualizar alerta [específico](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="09567-121">Update specific [alert](alerts.md).</span></span>
[<span data-ttu-id="09567-122">Alertas de atualização em lotes</span><span class="sxs-lookup"><span data-stu-id="09567-122">Batch update alerts</span></span>](batch-update-alerts.md) | | <span data-ttu-id="09567-123">Atualizar um lote de [alertas](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="09567-123">Update a batch of [alerts](alerts.md).</span></span>
[<span data-ttu-id="09567-124">Criar alerta</span><span class="sxs-lookup"><span data-stu-id="09567-124">Create alert</span></span>](create-alert-by-reference.md)|[<span data-ttu-id="09567-125">Alerta</span><span class="sxs-lookup"><span data-stu-id="09567-125">Alert</span></span>](alerts.md)|<span data-ttu-id="09567-126">Criar um alerta com base nos dados de evento obtidos da [Busca Avançada](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="09567-126">Create an alert based on event data obtained from [Advanced Hunting](run-advanced-query-api.md).</span></span>
[<span data-ttu-id="09567-127">Listar domínios relacionados</span><span class="sxs-lookup"><span data-stu-id="09567-127">List related domains</span></span>](get-alert-related-domain-info.md)|<span data-ttu-id="09567-128">Coleção Domain</span><span class="sxs-lookup"><span data-stu-id="09567-128">Domain collection</span></span>| <span data-ttu-id="09567-129">Listar URLs associadas ao alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-129">List URLs associated with the alert.</span></span>
[<span data-ttu-id="09567-130">Listar arquivos relacionados</span><span class="sxs-lookup"><span data-stu-id="09567-130">List related files</span></span>](get-alert-related-files-info.md) | <span data-ttu-id="09567-131">[Coleção File](files.md)</span><span class="sxs-lookup"><span data-stu-id="09567-131">[File](files.md) collection</span></span> |  <span data-ttu-id="09567-132">Listar [as entidades](files.md) de arquivo associadas ao [alerta](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="09567-132">List the [file](files.md) entities that are associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="09567-133">Listar IPs relacionados</span><span class="sxs-lookup"><span data-stu-id="09567-133">List related IPs</span></span>](get-alert-related-ip-info.md) | <span data-ttu-id="09567-134">Coleção IP</span><span class="sxs-lookup"><span data-stu-id="09567-134">IP collection</span></span> | <span data-ttu-id="09567-135">Listar IPs associados ao alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-135">List IPs that are associated with the alert.</span></span>
[<span data-ttu-id="09567-136">Obter máquinas relacionadas</span><span class="sxs-lookup"><span data-stu-id="09567-136">Get related machines</span></span>](get-alert-related-machine-info.md) | [<span data-ttu-id="09567-137">Computador</span><span class="sxs-lookup"><span data-stu-id="09567-137">Machine</span></span>](machine.md) | <span data-ttu-id="09567-138">O [computador](machine.md) associado ao [alerta](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="09567-138">The [machine](machine.md) that is associated with the [alert](alerts.md).</span></span>
[<span data-ttu-id="09567-139">Obter usuários relacionados</span><span class="sxs-lookup"><span data-stu-id="09567-139">Get related users</span></span>](get-alert-related-user-info.md) | [<span data-ttu-id="09567-140">Usuário</span><span class="sxs-lookup"><span data-stu-id="09567-140">User</span></span>](user.md) | <span data-ttu-id="09567-141">O [usuário](user.md) associado ao [alerta](alerts.md).</span><span class="sxs-lookup"><span data-stu-id="09567-141">The [user](user.md) that is associated with the [alert](alerts.md).</span></span>

## <a name="properties"></a><span data-ttu-id="09567-142">Propriedades</span><span class="sxs-lookup"><span data-stu-id="09567-142">Properties</span></span>

<span data-ttu-id="09567-143">Propriedade</span><span class="sxs-lookup"><span data-stu-id="09567-143">Property</span></span> |    <span data-ttu-id="09567-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="09567-144">Type</span></span>    |    <span data-ttu-id="09567-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="09567-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="09567-146">id</span><span class="sxs-lookup"><span data-stu-id="09567-146">id</span></span> | <span data-ttu-id="09567-147">String</span><span class="sxs-lookup"><span data-stu-id="09567-147">String</span></span> | <span data-ttu-id="09567-148">ID do alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-148">Alert ID.</span></span>
<span data-ttu-id="09567-149">title</span><span class="sxs-lookup"><span data-stu-id="09567-149">title</span></span> | <span data-ttu-id="09567-150">String</span><span class="sxs-lookup"><span data-stu-id="09567-150">String</span></span> | <span data-ttu-id="09567-151">Título do alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-151">Alert title.</span></span>
<span data-ttu-id="09567-152">description</span><span class="sxs-lookup"><span data-stu-id="09567-152">description</span></span> | <span data-ttu-id="09567-153">String</span><span class="sxs-lookup"><span data-stu-id="09567-153">String</span></span> | <span data-ttu-id="09567-154">Descrição de alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-154">Alert description.</span></span>
<span data-ttu-id="09567-155">alertCreationTime</span><span class="sxs-lookup"><span data-stu-id="09567-155">alertCreationTime</span></span> | <span data-ttu-id="09567-156">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="09567-156">Nullable DateTimeOffset</span></span> | <span data-ttu-id="09567-157">A data e a hora (em UTC) em que o alerta foi criado.</span><span class="sxs-lookup"><span data-stu-id="09567-157">The date and time (in UTC) the alert was created.</span></span>
<span data-ttu-id="09567-158">lastEventTime</span><span class="sxs-lookup"><span data-stu-id="09567-158">lastEventTime</span></span> | <span data-ttu-id="09567-159">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="09567-159">Nullable DateTimeOffset</span></span> | <span data-ttu-id="09567-160">A última ocorrência do evento que disparou o alerta no mesmo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="09567-160">The last occurrence of the event that triggered the alert on the same device.</span></span>
<span data-ttu-id="09567-161">firstEventTime</span><span class="sxs-lookup"><span data-stu-id="09567-161">firstEventTime</span></span> | <span data-ttu-id="09567-162">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="09567-162">Nullable DateTimeOffset</span></span> | <span data-ttu-id="09567-163">A primeira ocorrência do evento que disparou o alerta nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="09567-163">The first occurrence of the event that triggered the alert on that device.</span></span>
<span data-ttu-id="09567-164">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="09567-164">lastUpdateTime</span></span> | <span data-ttu-id="09567-165">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="09567-165">Nullable DateTimeOffset</span></span> | <span data-ttu-id="09567-166">A data e a hora (em UTC) em que o alerta foi atualizado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="09567-166">The date and time (in UTC) the alert was last updated.</span></span>
<span data-ttu-id="09567-167">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="09567-167">resolvedTime</span></span> | <span data-ttu-id="09567-168">Nullable DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="09567-168">Nullable DateTimeOffset</span></span> | <span data-ttu-id="09567-169">A data e a hora em que o status do alerta foi alterado para 'Resolvido'.</span><span class="sxs-lookup"><span data-stu-id="09567-169">The date and time in which the status of the alert was changed to 'Resolved'.</span></span>
<span data-ttu-id="09567-170">incidentId</span><span class="sxs-lookup"><span data-stu-id="09567-170">incidentId</span></span> | <span data-ttu-id="09567-171">Long anulado</span><span class="sxs-lookup"><span data-stu-id="09567-171">Nullable Long</span></span> | <span data-ttu-id="09567-172">A [](view-incidents-queue.md) ID do Incidente do Alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-172">The [Incident](view-incidents-queue.md) ID of the Alert.</span></span>
<span data-ttu-id="09567-173">investigationId</span><span class="sxs-lookup"><span data-stu-id="09567-173">investigationId</span></span> | <span data-ttu-id="09567-174">Long anulado</span><span class="sxs-lookup"><span data-stu-id="09567-174">Nullable Long</span></span> | <span data-ttu-id="09567-175">A [](automated-investigations.md) ID da Investigação relacionada ao Alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-175">The [Investigation](automated-investigations.md) ID related to the Alert.</span></span>
<span data-ttu-id="09567-176">investigationState</span><span class="sxs-lookup"><span data-stu-id="09567-176">investigationState</span></span> | <span data-ttu-id="09567-177">Núm anulado</span><span class="sxs-lookup"><span data-stu-id="09567-177">Nullable Enum</span></span> | <span data-ttu-id="09567-178">O estado atual da [Investigação](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="09567-178">The current state of the [Investigation](automated-investigations.md).</span></span> <span data-ttu-id="09567-179">Os valores possíveis são: 'Unknown', 'Terminado', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span><span class="sxs-lookup"><span data-stu-id="09567-179">Possible values are: 'Unknown', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.</span></span>
<span data-ttu-id="09567-180">assignedTo</span><span class="sxs-lookup"><span data-stu-id="09567-180">assignedTo</span></span> | <span data-ttu-id="09567-181">String</span><span class="sxs-lookup"><span data-stu-id="09567-181">String</span></span> | <span data-ttu-id="09567-182">Proprietário do alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-182">Owner of the alert.</span></span>
<span data-ttu-id="09567-183">severity</span><span class="sxs-lookup"><span data-stu-id="09567-183">severity</span></span> | <span data-ttu-id="09567-184">Enum</span><span class="sxs-lookup"><span data-stu-id="09567-184">Enum</span></span> | <span data-ttu-id="09567-185">Gravidade do alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-185">Severity of the alert.</span></span> <span data-ttu-id="09567-186">Os valores possíveis são: 'UnSpecified', 'Informational', 'Low', 'Medium' e 'High'.</span><span class="sxs-lookup"><span data-stu-id="09567-186">Possible values are: 'UnSpecified', 'Informational', 'Low', 'Medium' and 'High'.</span></span>
<span data-ttu-id="09567-187">status</span><span class="sxs-lookup"><span data-stu-id="09567-187">status</span></span> | <span data-ttu-id="09567-188">Enum</span><span class="sxs-lookup"><span data-stu-id="09567-188">Enum</span></span> | <span data-ttu-id="09567-189">Especifica o status atual do alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-189">Specifies the current status of the alert.</span></span> <span data-ttu-id="09567-190">Os valores possíveis são: 'Unknown', 'New', 'InProgress' e 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="09567-190">Possible values are: 'Unknown', 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="09567-191">classificação</span><span class="sxs-lookup"><span data-stu-id="09567-191">classification</span></span> | <span data-ttu-id="09567-192">Núm anulado</span><span class="sxs-lookup"><span data-stu-id="09567-192">Nullable Enum</span></span> | <span data-ttu-id="09567-193">Especificação do alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-193">Specification of the alert.</span></span> <span data-ttu-id="09567-194">Os valores possíveis são: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="09567-194">Possible values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span>
<span data-ttu-id="09567-195">determinação</span><span class="sxs-lookup"><span data-stu-id="09567-195">determination</span></span> | <span data-ttu-id="09567-196">Núm anulado</span><span class="sxs-lookup"><span data-stu-id="09567-196">Nullable Enum</span></span> | <span data-ttu-id="09567-197">Especifica a determinação do alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-197">Specifies the determination of the alert.</span></span> <span data-ttu-id="09567-198">Os valores possíveis são: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span><span class="sxs-lookup"><span data-stu-id="09567-198">Possible values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.</span></span>
<span data-ttu-id="09567-199">category</span><span class="sxs-lookup"><span data-stu-id="09567-199">category</span></span>| <span data-ttu-id="09567-200">String</span><span class="sxs-lookup"><span data-stu-id="09567-200">String</span></span> | <span data-ttu-id="09567-201">Categoria do alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-201">Category of the alert.</span></span>
<span data-ttu-id="09567-202">detectionSource</span><span class="sxs-lookup"><span data-stu-id="09567-202">detectionSource</span></span> | <span data-ttu-id="09567-203">String</span><span class="sxs-lookup"><span data-stu-id="09567-203">String</span></span> | <span data-ttu-id="09567-204">Fonte de detecção.</span><span class="sxs-lookup"><span data-stu-id="09567-204">Detection source.</span></span>
<span data-ttu-id="09567-205">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="09567-205">threatFamilyName</span></span> | <span data-ttu-id="09567-206">String</span><span class="sxs-lookup"><span data-stu-id="09567-206">String</span></span> | <span data-ttu-id="09567-207">Família de ameaças.</span><span class="sxs-lookup"><span data-stu-id="09567-207">Threat family.</span></span>
<span data-ttu-id="09567-208">threatName</span><span class="sxs-lookup"><span data-stu-id="09567-208">threatName</span></span> | <span data-ttu-id="09567-209">String</span><span class="sxs-lookup"><span data-stu-id="09567-209">String</span></span> | <span data-ttu-id="09567-210">Nome da ameaça.</span><span class="sxs-lookup"><span data-stu-id="09567-210">Threat name.</span></span>
<span data-ttu-id="09567-211">machineId</span><span class="sxs-lookup"><span data-stu-id="09567-211">machineId</span></span> | <span data-ttu-id="09567-212">String</span><span class="sxs-lookup"><span data-stu-id="09567-212">String</span></span> | <span data-ttu-id="09567-213">ID de uma [entidade](machine.md) de máquina associada ao alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-213">ID of a [machine](machine.md) entity that is associated with the alert.</span></span>
<span data-ttu-id="09567-214">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="09567-214">computerDnsName</span></span> | <span data-ttu-id="09567-215">String</span><span class="sxs-lookup"><span data-stu-id="09567-215">String</span></span> | <span data-ttu-id="09567-216">[nome](machine.md) totalmente qualificado da máquina.</span><span class="sxs-lookup"><span data-stu-id="09567-216">[machine](machine.md) fully qualified name.</span></span>
<span data-ttu-id="09567-217">aadTenantId</span><span class="sxs-lookup"><span data-stu-id="09567-217">aadTenantId</span></span> | <span data-ttu-id="09567-218">String</span><span class="sxs-lookup"><span data-stu-id="09567-218">String</span></span> | <span data-ttu-id="09567-219">A Azure Active Directory ID.</span><span class="sxs-lookup"><span data-stu-id="09567-219">The Azure Active Directory ID.</span></span>
<span data-ttu-id="09567-220">detectorId</span><span class="sxs-lookup"><span data-stu-id="09567-220">detectorId</span></span> | <span data-ttu-id="09567-221">String</span><span class="sxs-lookup"><span data-stu-id="09567-221">String</span></span> | <span data-ttu-id="09567-222">A ID do detector que disparou o alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-222">The ID of the detector that triggered the alert.</span></span>
<span data-ttu-id="09567-223">comentários</span><span class="sxs-lookup"><span data-stu-id="09567-223">comments</span></span> | <span data-ttu-id="09567-224">Lista de comentários de alerta</span><span class="sxs-lookup"><span data-stu-id="09567-224">List of Alert comments</span></span> | <span data-ttu-id="09567-225">O objeto Comentário de Alerta contém: cadeia de caracteres de comentários, createdBy string e createTime date time.</span><span class="sxs-lookup"><span data-stu-id="09567-225">Alert Comment object contains: comment string, createdBy string and createTime date time.</span></span>
<span data-ttu-id="09567-226">Evidências</span><span class="sxs-lookup"><span data-stu-id="09567-226">Evidence</span></span> | <span data-ttu-id="09567-227">Lista de evidências de alerta</span><span class="sxs-lookup"><span data-stu-id="09567-227">List of Alert evidence</span></span> | <span data-ttu-id="09567-228">Evidências relacionadas ao alerta.</span><span class="sxs-lookup"><span data-stu-id="09567-228">Evidence related to the alert.</span></span> <span data-ttu-id="09567-229">Veja o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="09567-229">See example below.</span></span>

### <a name="response-example-for-getting-single-alert"></a><span data-ttu-id="09567-230">Exemplo de resposta para obter um único alerta:</span><span class="sxs-lookup"><span data-stu-id="09567-230">Response example for getting single alert:</span></span>

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
