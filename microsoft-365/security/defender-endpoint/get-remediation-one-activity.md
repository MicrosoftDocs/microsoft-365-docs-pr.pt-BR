---
title: Obter uma atividade de correção por Id
description: Retorna informações para a atividade de correção especificada.
keywords: apis, correção, api de correção, obter, tarefas de correção, correção por ID,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2b7afef2c090df709f9209f450d8d3aab0424bf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772144"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="19545-104">Obter uma atividade de correção por Id</span><span class="sxs-lookup"><span data-stu-id="19545-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19545-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="19545-105">**Applies to:**</span></span>

- [<span data-ttu-id="19545-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="19545-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="19545-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19545-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="19545-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="19545-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="19545-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="19545-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="19545-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="19545-110">API description</span></span>

<span data-ttu-id="19545-111">Retorna informações para a atividade de correção especificada.</span><span class="sxs-lookup"><span data-stu-id="19545-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="19545-112">Apresenta as mesmas colunas que Obter todas as atividades [de correção](get-remediation-all-activities.md)", mas retorna resultados apenas para a atividade de _correção especificada_.</span><span class="sxs-lookup"><span data-stu-id="19545-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="19545-113">[Saiba mais sobre atividades de correção.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="19545-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="19545-114">Listar uma atividade de correção especificada para (id)</span><span class="sxs-lookup"><span data-stu-id="19545-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="19545-115">**URL:** GET: /api/remediationTasks/id \{\}</span><span class="sxs-lookup"><span data-stu-id="19545-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

## <a name="permissions"></a><span data-ttu-id="19545-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="19545-116">Permissions</span></span>

<span data-ttu-id="19545-117">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="19545-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="19545-118">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="19545-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="19545-119">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="19545-119">Permission type</span></span> | <span data-ttu-id="19545-120">Permissão</span><span class="sxs-lookup"><span data-stu-id="19545-120">Permission</span></span> | <span data-ttu-id="19545-121">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="19545-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="19545-122">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="19545-122">Application</span></span> | <span data-ttu-id="19545-123">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="19545-123">RemediationTask.Read.All</span></span> | <span data-ttu-id="19545-124">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="19545-124">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="19545-125">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="19545-125">Delegated (work or school account)</span></span> | <span data-ttu-id="19545-126">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="19545-126">RemediationTask.Read.Read</span></span> | <span data-ttu-id="19545-127">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="19545-127">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="19545-128">Propriedades</span><span class="sxs-lookup"><span data-stu-id="19545-128">Properties</span></span>

<span data-ttu-id="19545-129">Propriedade (id)</span><span class="sxs-lookup"><span data-stu-id="19545-129">Property (id)</span></span> | <span data-ttu-id="19545-130">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="19545-130">Data type</span></span> | <span data-ttu-id="19545-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="19545-131">Description</span></span> | <span data-ttu-id="19545-132">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="19545-132">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="19545-133">category</span><span class="sxs-lookup"><span data-stu-id="19545-133">category</span></span> | <span data-ttu-id="19545-134">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-134">String</span></span> | <span data-ttu-id="19545-135">Categoria da atividade de correção (Configuração de software/segurança)</span><span class="sxs-lookup"><span data-stu-id="19545-135">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="19545-136">Software</span><span class="sxs-lookup"><span data-stu-id="19545-136">Software</span></span>
<span data-ttu-id="19545-137">completerEmail</span><span class="sxs-lookup"><span data-stu-id="19545-137">completerEmail</span></span> | <span data-ttu-id="19545-138">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-138">String</span></span> | <span data-ttu-id="19545-139">Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém seus emails</span><span class="sxs-lookup"><span data-stu-id="19545-139">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="19545-140">null</span><span class="sxs-lookup"><span data-stu-id="19545-140">null</span></span>
<span data-ttu-id="19545-141">completerId</span><span class="sxs-lookup"><span data-stu-id="19545-141">completerId</span></span> | <span data-ttu-id="19545-142">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-142">String</span></span> | <span data-ttu-id="19545-143">Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém sua id de objeto</span><span class="sxs-lookup"><span data-stu-id="19545-143">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="19545-144">null</span><span class="sxs-lookup"><span data-stu-id="19545-144">null</span></span>
<span data-ttu-id="19545-145">completionMethod</span><span class="sxs-lookup"><span data-stu-id="19545-145">completionMethod</span></span> | <span data-ttu-id="19545-146">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-146">String</span></span> | <span data-ttu-id="19545-147">Uma atividade de correção pode ser concluída "automaticamente" (se todos os dispositivos são remendados) ou "manualmente" por uma pessoa que seleciona "marcar como concluída"</span><span class="sxs-lookup"><span data-stu-id="19545-147">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="19545-148">Automático</span><span class="sxs-lookup"><span data-stu-id="19545-148">Automatic</span></span>
<span data-ttu-id="19545-149">createdOn</span><span class="sxs-lookup"><span data-stu-id="19545-149">createdOn</span></span> | <span data-ttu-id="19545-150">DateTime</span><span class="sxs-lookup"><span data-stu-id="19545-150">DateTime</span></span> | <span data-ttu-id="19545-151">Hora em que essa atividade de correção foi criada</span><span class="sxs-lookup"><span data-stu-id="19545-151">Time this remediation activity was created</span></span> | <span data-ttu-id="19545-152">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="19545-152">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="19545-153">descrição</span><span class="sxs-lookup"><span data-stu-id="19545-153">description</span></span> | <span data-ttu-id="19545-154">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-154">String</span></span> | <span data-ttu-id="19545-155">Descrição dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="19545-155">Description of this remediation activity</span></span> | <span data-ttu-id="19545-156">Atualize o Microsoft Silverlight para uma versão posterior para atenuar vulnerabilidades conhecidas que afetam seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="19545-156">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="19545-157">dueOn</span><span class="sxs-lookup"><span data-stu-id="19545-157">dueOn</span></span> | <span data-ttu-id="19545-158">DateTime</span><span class="sxs-lookup"><span data-stu-id="19545-158">DateTime</span></span> | <span data-ttu-id="19545-159">Data de vencimento do conjunto de criadores para essa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="19545-159">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="19545-160">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="19545-160">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="19545-161">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="19545-161">fixedDevices</span></span> |  | <span data-ttu-id="19545-162">O número de dispositivos que foram corrigidos</span><span class="sxs-lookup"><span data-stu-id="19545-162">The number of devices that have been fixed</span></span> | <span data-ttu-id="19545-163">2</span><span class="sxs-lookup"><span data-stu-id="19545-163">2</span></span>
<span data-ttu-id="19545-164">id</span><span class="sxs-lookup"><span data-stu-id="19545-164">id</span></span> | <span data-ttu-id="19545-165">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-165">String</span></span> | <span data-ttu-id="19545-166">ID dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="19545-166">ID of this remediation activity</span></span> | <span data-ttu-id="19545-167">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="19545-167">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="19545-168">nameId</span><span class="sxs-lookup"><span data-stu-id="19545-168">nameId</span></span> | <span data-ttu-id="19545-169">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-169">String</span></span> | <span data-ttu-id="19545-170">Nome do produto relacionado</span><span class="sxs-lookup"><span data-stu-id="19545-170">Related product name</span></span> | <span data-ttu-id="19545-171">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="19545-171">Microsoft Silverlight</span></span>
<span data-ttu-id="19545-172">prioridade</span><span class="sxs-lookup"><span data-stu-id="19545-172">priority</span></span> | <span data-ttu-id="19545-173">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-173">String</span></span> | <span data-ttu-id="19545-174">Prioridade do conjunto de criadores para essa atividade de correção (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="19545-174">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="19545-175">Alto</span><span class="sxs-lookup"><span data-stu-id="19545-175">High</span></span>
<span data-ttu-id="19545-176">productId</span><span class="sxs-lookup"><span data-stu-id="19545-176">productId</span></span> | <span data-ttu-id="19545-177">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-177">String</span></span> | <span data-ttu-id="19545-178">ID do produto relacionado</span><span class="sxs-lookup"><span data-stu-id="19545-178">Related product ID</span></span> | <span data-ttu-id="19545-179">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="19545-179">microsoft-_-silverlight</span></span>
<span data-ttu-id="19545-180">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="19545-180">productivityImpactRemediationType</span></span> | <span data-ttu-id="19545-181">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-181">String</span></span> | <span data-ttu-id="19545-182">Algumas alterações de configuração só podem ser solicitadas para dispositivos sem impacto do usuário.</span><span class="sxs-lookup"><span data-stu-id="19545-182">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="19545-183">Esse valor indica a seleção entre "todos os dispositivos expostos" ou "somente dispositivos sem impacto do usuário".</span><span class="sxs-lookup"><span data-stu-id="19545-183">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="19545-184">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="19545-184">AllExposedAssets</span></span>
<span data-ttu-id="19545-185">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="19545-185">rbacGroupNames</span></span> | <span data-ttu-id="19545-186">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-186">String</span></span> | <span data-ttu-id="19545-187">Nomes de grupo de dispositivos relacionados</span><span class="sxs-lookup"><span data-stu-id="19545-187">Related device group names</span></span> | <span data-ttu-id="19545-188">[ "Windows Servidores", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="19545-188">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="19545-189">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="19545-189">recommendedProgram</span></span> | <span data-ttu-id="19545-190">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-190">String</span></span> | <span data-ttu-id="19545-191">Programa recomendado para atualizar para</span><span class="sxs-lookup"><span data-stu-id="19545-191">Recommended program to upgrade to</span></span> | <span data-ttu-id="19545-192">null</span><span class="sxs-lookup"><span data-stu-id="19545-192">null</span></span>
<span data-ttu-id="19545-193">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="19545-193">recommendedVendor</span></span> | <span data-ttu-id="19545-194">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-194">String</span></span> | <span data-ttu-id="19545-195">Fornecedor recomendado para atualizar para</span><span class="sxs-lookup"><span data-stu-id="19545-195">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="19545-196">null</span><span class="sxs-lookup"><span data-stu-id="19545-196">null</span></span>
<span data-ttu-id="19545-197">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="19545-197">recommendedVersion</span></span> | <span data-ttu-id="19545-198">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-198">String</span></span> | <span data-ttu-id="19545-199">Versão recomendada para atualização/atualização para</span><span class="sxs-lookup"><span data-stu-id="19545-199">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="19545-200">null</span><span class="sxs-lookup"><span data-stu-id="19545-200">null</span></span>
<span data-ttu-id="19545-201">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="19545-201">relatedComponent</span></span> | <span data-ttu-id="19545-202">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-202">String</span></span> | <span data-ttu-id="19545-203">Componente relacionado dessa atividade de correção (semelhante ao componente relacionado para uma recomendação de segurança)</span><span class="sxs-lookup"><span data-stu-id="19545-203">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="19545-204">Microsoft Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="19545-204">Microsoft Microsoft Silverlight</span></span>
<span data-ttu-id="19545-205">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="19545-205">requesterEmail</span></span> | <span data-ttu-id="19545-206">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-206">String</span></span> | <span data-ttu-id="19545-207">Endereço de email do criador</span><span class="sxs-lookup"><span data-stu-id="19545-207">Creator email address</span></span> | <span data-ttu-id="19545-208">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="19545-208">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="19545-209">requesterId</span><span class="sxs-lookup"><span data-stu-id="19545-209">requesterId</span></span> | <span data-ttu-id="19545-210">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-210">String</span></span> | <span data-ttu-id="19545-211">ID do objeto Creator</span><span class="sxs-lookup"><span data-stu-id="19545-211">Creator object id</span></span> | <span data-ttu-id="19545-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="19545-212">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="19545-213">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="19545-213">requesterNotes</span></span> | <span data-ttu-id="19545-214">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-214">String</span></span> | <span data-ttu-id="19545-215">As anotações (texto livre) que o criador adicionou para essa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="19545-215">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="19545-216">null</span><span class="sxs-lookup"><span data-stu-id="19545-216">null</span></span>
<span data-ttu-id="19545-217">scid</span><span class="sxs-lookup"><span data-stu-id="19545-217">scid</span></span> | <span data-ttu-id="19545-218">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-218">String</span></span> | <span data-ttu-id="19545-219">SCID da recomendação de segurança relacionada</span><span class="sxs-lookup"><span data-stu-id="19545-219">SCID of the related security recommendation</span></span> | <span data-ttu-id="19545-220">null</span><span class="sxs-lookup"><span data-stu-id="19545-220">null</span></span>
<span data-ttu-id="19545-221">status</span><span class="sxs-lookup"><span data-stu-id="19545-221">status</span></span> | <span data-ttu-id="19545-222">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-222">String</span></span> | <span data-ttu-id="19545-223">Status da atividade de correção (Ativo/Concluído)</span><span class="sxs-lookup"><span data-stu-id="19545-223">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="19545-224">Ativo</span><span class="sxs-lookup"><span data-stu-id="19545-224">Active</span></span>
<span data-ttu-id="19545-225">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="19545-225">statusLastModifiedOn</span></span> | <span data-ttu-id="19545-226">DateTime</span><span class="sxs-lookup"><span data-stu-id="19545-226">DateTime</span></span> | <span data-ttu-id="19545-227">Data em que o campo de status foi atualizado</span><span class="sxs-lookup"><span data-stu-id="19545-227">Date when the status field was updated</span></span> | <span data-ttu-id="19545-228">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="19545-228">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="19545-229">targetDevices</span><span class="sxs-lookup"><span data-stu-id="19545-229">targetDevices</span></span> | <span data-ttu-id="19545-230">Longo</span><span class="sxs-lookup"><span data-stu-id="19545-230">Long</span></span> | <span data-ttu-id="19545-231">Número de dispositivos expostos a que essa correção é aplicável</span><span class="sxs-lookup"><span data-stu-id="19545-231">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="19545-232">43</span><span class="sxs-lookup"><span data-stu-id="19545-232">43</span></span>
<span data-ttu-id="19545-233">title</span><span class="sxs-lookup"><span data-stu-id="19545-233">title</span></span> | <span data-ttu-id="19545-234">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-234">String</span></span> | <span data-ttu-id="19545-235">Título dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="19545-235">Title of this remediation activity</span></span> | <span data-ttu-id="19545-236">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="19545-236">Microsoft Silverlight</span></span>
<span data-ttu-id="19545-237">tipo</span><span class="sxs-lookup"><span data-stu-id="19545-237">type</span></span> | <span data-ttu-id="19545-238">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-238">String</span></span> | <span data-ttu-id="19545-239">Tipo de correção</span><span class="sxs-lookup"><span data-stu-id="19545-239">Remediation type</span></span> | <span data-ttu-id="19545-240">Atualizar</span><span class="sxs-lookup"><span data-stu-id="19545-240">Update</span></span>
<span data-ttu-id="19545-241">vendorId</span><span class="sxs-lookup"><span data-stu-id="19545-241">vendorId</span></span> | <span data-ttu-id="19545-242">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="19545-242">String</span></span> | <span data-ttu-id="19545-243">Nome do fornecedor relacionado</span><span class="sxs-lookup"><span data-stu-id="19545-243">Related vendor name</span></span> | <span data-ttu-id="19545-244">Microsoft</span><span class="sxs-lookup"><span data-stu-id="19545-244">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="19545-245">Exemplo</span><span class="sxs-lookup"><span data-stu-id="19545-245">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="19545-246">Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="19545-246">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a><span data-ttu-id="19545-247">Exemplo de resposta</span><span class="sxs-lookup"><span data-stu-id="19545-247">Response example</span></span>

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
    "relatedComponent": "Microsoft Silverlight", 
    "targetDevices": 18511, 
    "rbacGroupNames": [ 
        "UnassignedGroup", 
        "hhh" 
    ], 
    "fixedDevices": 2866, 
    "requesterNotes": "test", 
    "dueOn": "2021-02-11T00:00:00Z", 
    "category": "Software", 
    "productivityImpactRemediationType": null, 
    "priority": "Medium", 
    "completionMethod": null, 
    "completerId": null, 
    "completerEmail": null, 
    "scid": null, 
    "type": "Update", 
    "productId": "microsoft-_-silverlight", 
    "vendorId": "microsoft", 
    "nameId": "silverlight", 
    "recommendedVersion": null, 
    "recommendedVendor": null, 
    "recommendedProgram": null 
} 
```

## <a name="see-also"></a><span data-ttu-id="19545-248">Confira também</span><span class="sxs-lookup"><span data-stu-id="19545-248">See also</span></span>

- [<span data-ttu-id="19545-249">Métodos e propriedades de correção</span><span class="sxs-lookup"><span data-stu-id="19545-249">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="19545-250">Listar todas as atividades de correção</span><span class="sxs-lookup"><span data-stu-id="19545-250">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="19545-251">Listar dispositivos expostos de uma atividade de correção</span><span class="sxs-lookup"><span data-stu-id="19545-251">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="19545-252">Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="19545-252">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="19545-253">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="19545-253">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
