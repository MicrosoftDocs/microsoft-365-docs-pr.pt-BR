---
title: Obter uma atividade de correção por Id
description: Retorna informações para a atividade de correção especificada.
keywords: apis, correção, api de correção, obter, tarefas de correção, lista
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
ms.technology: mde
ms.openlocfilehash: 40a7102a8c7dbf63641daaf47bbd9aa9f2e54649
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061094"
---
# <a name="get-one-remediation-activity-by-id"></a><span data-ttu-id="f6338-104">Obter uma atividade de correção por Id</span><span class="sxs-lookup"><span data-stu-id="f6338-104">Get one remediation activity by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f6338-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f6338-105">**Applies to:**</span></span>

- [<span data-ttu-id="f6338-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f6338-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f6338-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6338-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f6338-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f6338-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6338-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f6338-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="f6338-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="f6338-110">API description</span></span>

<span data-ttu-id="f6338-111">Retorna informações para a atividade de correção especificada.</span><span class="sxs-lookup"><span data-stu-id="f6338-111">Returns information for the specified remediation activity.</span></span> <span data-ttu-id="f6338-112">Apresenta as mesmas colunas que Obter todas as atividades [de correção](get-remediation-all-activities.md)", mas retorna resultados apenas para a atividade de _correção especificada_.</span><span class="sxs-lookup"><span data-stu-id="f6338-112">Presents the same columns as [Get all remediation activity](get-remediation-all-activities.md)", but returns results _only for the one specified remediation activity_.</span></span>

<span data-ttu-id="f6338-113">[Saiba mais sobre atividades de correção.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="f6338-113">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-a-specified-remediation-activity-for-id"></a><span data-ttu-id="f6338-114">Listar uma atividade de correção especificada para (id)</span><span class="sxs-lookup"><span data-stu-id="f6338-114">List a specified remediation activity for (id)</span></span>

<span data-ttu-id="f6338-115">**URL:** GET: /api/remediationTasks/id \{\}</span><span class="sxs-lookup"><span data-stu-id="f6338-115">**URL:** GET: /api/remediationTasks/\{id\}</span></span>

<span data-ttu-id="f6338-116">**Detalhes das** propriedades</span><span class="sxs-lookup"><span data-stu-id="f6338-116">**Properties** details</span></span>

<span data-ttu-id="f6338-117">Propriedade (id)</span><span class="sxs-lookup"><span data-stu-id="f6338-117">Property (id)</span></span> | <span data-ttu-id="f6338-118">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f6338-118">Data type</span></span> | <span data-ttu-id="f6338-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="f6338-119">Description</span></span> | <span data-ttu-id="f6338-120">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="f6338-120">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="f6338-121">category</span><span class="sxs-lookup"><span data-stu-id="f6338-121">category</span></span> | <span data-ttu-id="f6338-122">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-122">String</span></span> | <span data-ttu-id="f6338-123">Categoria da atividade de correção (Configuração de software/segurança)</span><span class="sxs-lookup"><span data-stu-id="f6338-123">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="f6338-124">Software</span><span class="sxs-lookup"><span data-stu-id="f6338-124">Software</span></span>
<span data-ttu-id="f6338-125">completerEmail</span><span class="sxs-lookup"><span data-stu-id="f6338-125">completerEmail</span></span> | <span data-ttu-id="f6338-126">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-126">String</span></span> | <span data-ttu-id="f6338-127">Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém seus emails</span><span class="sxs-lookup"><span data-stu-id="f6338-127">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="f6338-128">null</span><span class="sxs-lookup"><span data-stu-id="f6338-128">null</span></span>
<span data-ttu-id="f6338-129">completerId</span><span class="sxs-lookup"><span data-stu-id="f6338-129">completerId</span></span> | <span data-ttu-id="f6338-130">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-130">String</span></span> | <span data-ttu-id="f6338-131">Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém sua id de objeto</span><span class="sxs-lookup"><span data-stu-id="f6338-131">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="f6338-132">null</span><span class="sxs-lookup"><span data-stu-id="f6338-132">null</span></span>
<span data-ttu-id="f6338-133">completionMethod</span><span class="sxs-lookup"><span data-stu-id="f6338-133">completionMethod</span></span> | <span data-ttu-id="f6338-134">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-134">String</span></span> | <span data-ttu-id="f6338-135">Uma atividade de correção pode ser concluída "automaticamente" (se todos os dispositivos são remendados) ou "manualmente" por uma pessoa que seleciona "marcar como concluída"</span><span class="sxs-lookup"><span data-stu-id="f6338-135">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="f6338-136">Automático</span><span class="sxs-lookup"><span data-stu-id="f6338-136">Automatic</span></span>
<span data-ttu-id="f6338-137">createdOn</span><span class="sxs-lookup"><span data-stu-id="f6338-137">createdOn</span></span> | <span data-ttu-id="f6338-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="f6338-138">DateTime</span></span> | <span data-ttu-id="f6338-139">Hora em que essa atividade de correção foi criada</span><span class="sxs-lookup"><span data-stu-id="f6338-139">Time this remediation activity was created</span></span> | <span data-ttu-id="f6338-140">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="f6338-140">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="f6338-141">description</span><span class="sxs-lookup"><span data-stu-id="f6338-141">description</span></span> | <span data-ttu-id="f6338-142">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-142">String</span></span> | <span data-ttu-id="f6338-143">Descrição dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="f6338-143">Description of this remediation activity</span></span> | <span data-ttu-id="f6338-144">Atualize o Chrome para uma versão posterior para atenuar 1248 vulnerabilidades conhecidas que afetam seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f6338-144">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="f6338-145">dueOn</span><span class="sxs-lookup"><span data-stu-id="f6338-145">dueOn</span></span> | <span data-ttu-id="f6338-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="f6338-146">DateTime</span></span> | <span data-ttu-id="f6338-147">Data de vencimento do conjunto de criadores para essa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="f6338-147">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="f6338-148">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="f6338-148">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="f6338-149">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="f6338-149">fixedDevices</span></span> |  | <span data-ttu-id="f6338-150">O número de dispositivos que foram corrigidos</span><span class="sxs-lookup"><span data-stu-id="f6338-150">The number of devices that have been fixed</span></span> | <span data-ttu-id="f6338-151">2</span><span class="sxs-lookup"><span data-stu-id="f6338-151">2</span></span>
<span data-ttu-id="f6338-152">id</span><span class="sxs-lookup"><span data-stu-id="f6338-152">id</span></span> | <span data-ttu-id="f6338-153">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-153">String</span></span> | <span data-ttu-id="f6338-154">ID dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="f6338-154">ID of this remediation activity</span></span> | <span data-ttu-id="f6338-155">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="f6338-155">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="f6338-156">nameId</span><span class="sxs-lookup"><span data-stu-id="f6338-156">nameId</span></span> | <span data-ttu-id="f6338-157">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-157">String</span></span> | <span data-ttu-id="f6338-158">Nome do produto relacionado</span><span class="sxs-lookup"><span data-stu-id="f6338-158">Related product name</span></span> | <span data-ttu-id="f6338-159">chrome</span><span class="sxs-lookup"><span data-stu-id="f6338-159">chrome</span></span>
<span data-ttu-id="f6338-160">prioridade</span><span class="sxs-lookup"><span data-stu-id="f6338-160">priority</span></span> | <span data-ttu-id="f6338-161">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-161">String</span></span> | <span data-ttu-id="f6338-162">Prioridade do conjunto de criadores para essa atividade de correção (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="f6338-162">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="f6338-163">Alto</span><span class="sxs-lookup"><span data-stu-id="f6338-163">High</span></span>
<span data-ttu-id="f6338-164">productId</span><span class="sxs-lookup"><span data-stu-id="f6338-164">productId</span></span> | <span data-ttu-id="f6338-165">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-165">String</span></span> | <span data-ttu-id="f6338-166">ID do produto relacionado</span><span class="sxs-lookup"><span data-stu-id="f6338-166">Related product ID</span></span> | <span data-ttu-id="f6338-167">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="f6338-167">google-_-chrome</span></span>
<span data-ttu-id="f6338-168">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="f6338-168">productivityImpactRemediationType</span></span> | <span data-ttu-id="f6338-169">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-169">String</span></span> | <span data-ttu-id="f6338-170">Algumas alterações de configuração só podem ser solicitadas para dispositivos sem impacto do usuário.</span><span class="sxs-lookup"><span data-stu-id="f6338-170">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="f6338-171">Esse valor indica a seleção entre "todos os dispositivos expostos" ou "somente dispositivos sem impacto do usuário".</span><span class="sxs-lookup"><span data-stu-id="f6338-171">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="f6338-172">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="f6338-172">AllExposedAssets</span></span>
<span data-ttu-id="f6338-173">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="f6338-173">rbacGroupNames</span></span> | <span data-ttu-id="f6338-174">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-174">String</span></span> | <span data-ttu-id="f6338-175">Nomes de grupo de dispositivos relacionados</span><span class="sxs-lookup"><span data-stu-id="f6338-175">Related device group names</span></span> | <span data-ttu-id="f6338-176">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="f6338-176">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="f6338-177">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="f6338-177">recommendedProgram</span></span> | <span data-ttu-id="f6338-178">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-178">String</span></span> | <span data-ttu-id="f6338-179">Programa recomendado para atualizar para</span><span class="sxs-lookup"><span data-stu-id="f6338-179">Recommended program to upgrade to</span></span> | <span data-ttu-id="f6338-180">null</span><span class="sxs-lookup"><span data-stu-id="f6338-180">null</span></span>
<span data-ttu-id="f6338-181">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="f6338-181">recommendedVendor</span></span> | <span data-ttu-id="f6338-182">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-182">String</span></span> | <span data-ttu-id="f6338-183">Fornecedor recomendado para atualizar para</span><span class="sxs-lookup"><span data-stu-id="f6338-183">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="f6338-184">null</span><span class="sxs-lookup"><span data-stu-id="f6338-184">null</span></span>
<span data-ttu-id="f6338-185">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="f6338-185">recommendedVersion</span></span> | <span data-ttu-id="f6338-186">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-186">String</span></span> | <span data-ttu-id="f6338-187">Versão recomendada para atualização/atualização para</span><span class="sxs-lookup"><span data-stu-id="f6338-187">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="f6338-188">null</span><span class="sxs-lookup"><span data-stu-id="f6338-188">null</span></span>
<span data-ttu-id="f6338-189">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="f6338-189">relatedComponent</span></span> | <span data-ttu-id="f6338-190">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-190">String</span></span> | <span data-ttu-id="f6338-191">Componente relacionado dessa atividade de correção (semelhante ao componente relacionado para uma recomendação de segurança)</span><span class="sxs-lookup"><span data-stu-id="f6338-191">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="f6338-192">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="f6338-192">Google Chrome</span></span>
<span data-ttu-id="f6338-193">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="f6338-193">requesterEmail</span></span> | <span data-ttu-id="f6338-194">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-194">String</span></span> | <span data-ttu-id="f6338-195">Endereço de email do criador</span><span class="sxs-lookup"><span data-stu-id="f6338-195">Creator email address</span></span> | <span data-ttu-id="f6338-196">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f6338-196">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="f6338-197">requesterId</span><span class="sxs-lookup"><span data-stu-id="f6338-197">requesterId</span></span> | <span data-ttu-id="f6338-198">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-198">String</span></span> | <span data-ttu-id="f6338-199">ID do objeto Creator</span><span class="sxs-lookup"><span data-stu-id="f6338-199">Creator object id</span></span> | <span data-ttu-id="f6338-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="f6338-200">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="f6338-201">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="f6338-201">requesterNotes</span></span> | <span data-ttu-id="f6338-202">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-202">String</span></span> | <span data-ttu-id="f6338-203">As anotações (texto livre) que o criador adicionou para essa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="f6338-203">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="f6338-204">null</span><span class="sxs-lookup"><span data-stu-id="f6338-204">null</span></span>
<span data-ttu-id="f6338-205">scid</span><span class="sxs-lookup"><span data-stu-id="f6338-205">scid</span></span> | <span data-ttu-id="f6338-206">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-206">String</span></span> | <span data-ttu-id="f6338-207">SCID da recomendação de segurança relacionada</span><span class="sxs-lookup"><span data-stu-id="f6338-207">SCID of the related security recommendation</span></span> | <span data-ttu-id="f6338-208">null</span><span class="sxs-lookup"><span data-stu-id="f6338-208">null</span></span>
<span data-ttu-id="f6338-209">status</span><span class="sxs-lookup"><span data-stu-id="f6338-209">status</span></span> | <span data-ttu-id="f6338-210">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-210">String</span></span> | <span data-ttu-id="f6338-211">Status da atividade de correção (Ativo/Concluído)</span><span class="sxs-lookup"><span data-stu-id="f6338-211">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="f6338-212">Ativo</span><span class="sxs-lookup"><span data-stu-id="f6338-212">Active</span></span>
<span data-ttu-id="f6338-213">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="f6338-213">statusLastModifiedOn</span></span> | <span data-ttu-id="f6338-214">DateTime</span><span class="sxs-lookup"><span data-stu-id="f6338-214">DateTime</span></span> | <span data-ttu-id="f6338-215">Data em que o campo de status foi atualizado</span><span class="sxs-lookup"><span data-stu-id="f6338-215">Date when the status field was updated</span></span> | <span data-ttu-id="f6338-216">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="f6338-216">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="f6338-217">targetDevices</span><span class="sxs-lookup"><span data-stu-id="f6338-217">targetDevices</span></span> | <span data-ttu-id="f6338-218">Longo</span><span class="sxs-lookup"><span data-stu-id="f6338-218">Long</span></span> | <span data-ttu-id="f6338-219">Número de dispositivos expostos a que essa correção é aplicável</span><span class="sxs-lookup"><span data-stu-id="f6338-219">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="f6338-220">43</span><span class="sxs-lookup"><span data-stu-id="f6338-220">43</span></span>
<span data-ttu-id="f6338-221">title</span><span class="sxs-lookup"><span data-stu-id="f6338-221">title</span></span> | <span data-ttu-id="f6338-222">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-222">String</span></span> | <span data-ttu-id="f6338-223">Título dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="f6338-223">Title of this remediation activity</span></span> | <span data-ttu-id="f6338-224">Atualizar o Google Chrome</span><span class="sxs-lookup"><span data-stu-id="f6338-224">Update Google Chrome</span></span>
<span data-ttu-id="f6338-225">tipo</span><span class="sxs-lookup"><span data-stu-id="f6338-225">type</span></span> | <span data-ttu-id="f6338-226">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-226">String</span></span> | <span data-ttu-id="f6338-227">Tipo de correção</span><span class="sxs-lookup"><span data-stu-id="f6338-227">Remediation type</span></span> | <span data-ttu-id="f6338-228">Atualizar</span><span class="sxs-lookup"><span data-stu-id="f6338-228">Update</span></span>
<span data-ttu-id="f6338-229">vendorId</span><span class="sxs-lookup"><span data-stu-id="f6338-229">vendorId</span></span> | <span data-ttu-id="f6338-230">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f6338-230">String</span></span> | <span data-ttu-id="f6338-231">Nome do fornecedor relacionado</span><span class="sxs-lookup"><span data-stu-id="f6338-231">Related vendor name</span></span> | <span data-ttu-id="f6338-232">google</span><span class="sxs-lookup"><span data-stu-id="f6338-232">google</span></span>

## <a name="example"></a><span data-ttu-id="f6338-233">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f6338-233">Example</span></span>

<span data-ttu-id="f6338-234">**Exemplo de** solicitação</span><span class="sxs-lookup"><span data-stu-id="f6338-234">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

<span data-ttu-id="f6338-235">**Exemplo de** resposta</span><span class="sxs-lookup"><span data-stu-id="f6338-235">**Response** example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f6338-236">Confira também</span><span class="sxs-lookup"><span data-stu-id="f6338-236">See also</span></span>

- [<span data-ttu-id="f6338-237">Métodos e propriedades de correção</span><span class="sxs-lookup"><span data-stu-id="f6338-237">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="f6338-238">Listar todas as atividades de correção</span><span class="sxs-lookup"><span data-stu-id="f6338-238">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="f6338-239">Listar dispositivos expostos de uma atividade de correção</span><span class="sxs-lookup"><span data-stu-id="f6338-239">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="f6338-240">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="f6338-240">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="f6338-241">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="f6338-241">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
