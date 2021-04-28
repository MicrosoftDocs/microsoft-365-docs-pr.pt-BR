---
title: Listar todas as atividades de correção
description: Retorna informações sobre todas as atividades de correção.
keywords: apis, correção, api de correção, obter, tarefas de correção,
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
ms.openlocfilehash: ac4a777136dcdfc5d7ab61ddc8d496b7452f69e2
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061093"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="792e0-104">Listar todas as atividades de correção</span><span class="sxs-lookup"><span data-stu-id="792e0-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="792e0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="792e0-105">**Applies to:**</span></span>

- [<span data-ttu-id="792e0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="792e0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="792e0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="792e0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="792e0-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="792e0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="792e0-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="792e0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="792e0-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="792e0-110">API description</span></span>

<span data-ttu-id="792e0-111">Retorna informações sobre todas as atividades de correção.</span><span class="sxs-lookup"><span data-stu-id="792e0-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="792e0-112">[Saiba mais sobre atividades de correção.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="792e0-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="792e0-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="792e0-113">**URL:** GET: /api/remediationTasks</span></span>

<span data-ttu-id="792e0-114">**Detalhes das** propriedades</span><span class="sxs-lookup"><span data-stu-id="792e0-114">**Properties** details</span></span>

<span data-ttu-id="792e0-115">Propriedade (id)</span><span class="sxs-lookup"><span data-stu-id="792e0-115">Property (id)</span></span> | <span data-ttu-id="792e0-116">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="792e0-116">Data type</span></span> | <span data-ttu-id="792e0-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="792e0-117">Description</span></span> | <span data-ttu-id="792e0-118">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="792e0-118">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="792e0-119">category</span><span class="sxs-lookup"><span data-stu-id="792e0-119">category</span></span> | <span data-ttu-id="792e0-120">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-120">String</span></span> | <span data-ttu-id="792e0-121">Categoria da atividade de correção (Configuração de software/segurança)</span><span class="sxs-lookup"><span data-stu-id="792e0-121">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="792e0-122">Software</span><span class="sxs-lookup"><span data-stu-id="792e0-122">Software</span></span>
<span data-ttu-id="792e0-123">completerEmail</span><span class="sxs-lookup"><span data-stu-id="792e0-123">completerEmail</span></span> | <span data-ttu-id="792e0-124">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-124">String</span></span> | <span data-ttu-id="792e0-125">Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém seus emails</span><span class="sxs-lookup"><span data-stu-id="792e0-125">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="792e0-126">null</span><span class="sxs-lookup"><span data-stu-id="792e0-126">null</span></span>
<span data-ttu-id="792e0-127">completerId</span><span class="sxs-lookup"><span data-stu-id="792e0-127">completerId</span></span> | <span data-ttu-id="792e0-128">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-128">String</span></span> | <span data-ttu-id="792e0-129">Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém sua id de objeto</span><span class="sxs-lookup"><span data-stu-id="792e0-129">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="792e0-130">null</span><span class="sxs-lookup"><span data-stu-id="792e0-130">null</span></span>
<span data-ttu-id="792e0-131">completionMethod</span><span class="sxs-lookup"><span data-stu-id="792e0-131">completionMethod</span></span> | <span data-ttu-id="792e0-132">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-132">String</span></span> | <span data-ttu-id="792e0-133">Uma atividade de correção pode ser concluída "automaticamente" (se todos os dispositivos são remendados) ou "manualmente" por uma pessoa que seleciona "marcar como concluída"</span><span class="sxs-lookup"><span data-stu-id="792e0-133">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="792e0-134">Automático</span><span class="sxs-lookup"><span data-stu-id="792e0-134">Automatic</span></span>
<span data-ttu-id="792e0-135">createdOn</span><span class="sxs-lookup"><span data-stu-id="792e0-135">createdOn</span></span> | <span data-ttu-id="792e0-136">DateTime</span><span class="sxs-lookup"><span data-stu-id="792e0-136">DateTime</span></span> | <span data-ttu-id="792e0-137">Hora em que essa atividade de correção foi criada</span><span class="sxs-lookup"><span data-stu-id="792e0-137">Time this remediation activity was created</span></span> | <span data-ttu-id="792e0-138">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="792e0-138">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="792e0-139">description</span><span class="sxs-lookup"><span data-stu-id="792e0-139">description</span></span> | <span data-ttu-id="792e0-140">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-140">String</span></span> | <span data-ttu-id="792e0-141">Descrição dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="792e0-141">Description of this remediation activity</span></span> | <span data-ttu-id="792e0-142">Atualize o Chrome para uma versão posterior para atenuar 1248 vulnerabilidades conhecidas que afetam seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="792e0-142">Update Chrome to a later version to mitigate 1248 known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="792e0-143">dueOn</span><span class="sxs-lookup"><span data-stu-id="792e0-143">dueOn</span></span> | <span data-ttu-id="792e0-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="792e0-144">DateTime</span></span> | <span data-ttu-id="792e0-145">Data de vencimento do conjunto de criadores para essa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="792e0-145">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="792e0-146">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="792e0-146">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="792e0-147">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="792e0-147">fixedDevices</span></span> | <span data-ttu-id="792e0-148">.</span><span class="sxs-lookup"><span data-stu-id="792e0-148">.</span></span> | <span data-ttu-id="792e0-149">O número de dispositivos que foram corrigidos</span><span class="sxs-lookup"><span data-stu-id="792e0-149">The number of devices that have been fixed</span></span> | <span data-ttu-id="792e0-150">2</span><span class="sxs-lookup"><span data-stu-id="792e0-150">2</span></span>
<span data-ttu-id="792e0-151">id</span><span class="sxs-lookup"><span data-stu-id="792e0-151">id</span></span> | <span data-ttu-id="792e0-152">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-152">String</span></span> | <span data-ttu-id="792e0-153">ID dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="792e0-153">ID of this remediation activity</span></span> | <span data-ttu-id="792e0-154">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="792e0-154">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="792e0-155">nameId</span><span class="sxs-lookup"><span data-stu-id="792e0-155">nameId</span></span> | <span data-ttu-id="792e0-156">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-156">String</span></span> | <span data-ttu-id="792e0-157">Nome do produto relacionado</span><span class="sxs-lookup"><span data-stu-id="792e0-157">Related product name</span></span> | <span data-ttu-id="792e0-158">chrome</span><span class="sxs-lookup"><span data-stu-id="792e0-158">chrome</span></span>
<span data-ttu-id="792e0-159">prioridade</span><span class="sxs-lookup"><span data-stu-id="792e0-159">priority</span></span> | <span data-ttu-id="792e0-160">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-160">String</span></span> | <span data-ttu-id="792e0-161">Prioridade do conjunto de criadores para essa atividade de correção (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="792e0-161">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="792e0-162">Alto</span><span class="sxs-lookup"><span data-stu-id="792e0-162">High</span></span>
<span data-ttu-id="792e0-163">productId</span><span class="sxs-lookup"><span data-stu-id="792e0-163">productId</span></span> | <span data-ttu-id="792e0-164">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-164">String</span></span> | <span data-ttu-id="792e0-165">ID do produto relacionado</span><span class="sxs-lookup"><span data-stu-id="792e0-165">Related product ID</span></span> | <span data-ttu-id="792e0-166">google-_-chrome</span><span class="sxs-lookup"><span data-stu-id="792e0-166">google-_-chrome</span></span>
<span data-ttu-id="792e0-167">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="792e0-167">productivityImpactRemediationType</span></span> | <span data-ttu-id="792e0-168">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-168">String</span></span> | <span data-ttu-id="792e0-169">Algumas alterações de configuração só podem ser solicitadas para dispositivos sem impacto do usuário.</span><span class="sxs-lookup"><span data-stu-id="792e0-169">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="792e0-170">Esse valor indica a seleção entre "todos os dispositivos expostos" ou "somente dispositivos sem impacto do usuário".</span><span class="sxs-lookup"><span data-stu-id="792e0-170">This value indicate the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="792e0-171">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="792e0-171">AllExposedAssets</span></span>
<span data-ttu-id="792e0-172">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="792e0-172">rbacGroupNames</span></span> | <span data-ttu-id="792e0-173">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-173">String</span></span> | <span data-ttu-id="792e0-174">Nomes de grupo de dispositivos relacionados</span><span class="sxs-lookup"><span data-stu-id="792e0-174">Related device group names</span></span> | <span data-ttu-id="792e0-175">[ "Windows Servers", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="792e0-175">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="792e0-176">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="792e0-176">recommendedProgram</span></span> | <span data-ttu-id="792e0-177">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-177">String</span></span> | <span data-ttu-id="792e0-178">Programa recomendado para atualizar para</span><span class="sxs-lookup"><span data-stu-id="792e0-178">Recommended program to upgrade to</span></span> | <span data-ttu-id="792e0-179">null</span><span class="sxs-lookup"><span data-stu-id="792e0-179">null</span></span>
<span data-ttu-id="792e0-180">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="792e0-180">recommendedVendor</span></span> | <span data-ttu-id="792e0-181">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-181">String</span></span> | <span data-ttu-id="792e0-182">Fornecedor recomendado para atualizar para</span><span class="sxs-lookup"><span data-stu-id="792e0-182">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="792e0-183">null</span><span class="sxs-lookup"><span data-stu-id="792e0-183">null</span></span>
<span data-ttu-id="792e0-184">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="792e0-184">recommendedVersion</span></span> | <span data-ttu-id="792e0-185">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-185">String</span></span> | <span data-ttu-id="792e0-186">Versão recomendada para atualização/atualização para</span><span class="sxs-lookup"><span data-stu-id="792e0-186">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="792e0-187">null</span><span class="sxs-lookup"><span data-stu-id="792e0-187">null</span></span>
<span data-ttu-id="792e0-188">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="792e0-188">relatedComponent</span></span> | <span data-ttu-id="792e0-189">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-189">String</span></span> | <span data-ttu-id="792e0-190">Componente relacionado dessa atividade de correção (semelhante ao componente relacionado para uma recomendação de segurança)</span><span class="sxs-lookup"><span data-stu-id="792e0-190">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="792e0-191">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="792e0-191">Google Chrome</span></span>
<span data-ttu-id="792e0-192">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="792e0-192">requesterEmail</span></span> | <span data-ttu-id="792e0-193">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-193">String</span></span> | <span data-ttu-id="792e0-194">Endereço de email do criador</span><span class="sxs-lookup"><span data-stu-id="792e0-194">Creator email address</span></span> | <span data-ttu-id="792e0-195">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="792e0-195">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="792e0-196">requesterId</span><span class="sxs-lookup"><span data-stu-id="792e0-196">requesterId</span></span> | <span data-ttu-id="792e0-197">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-197">String</span></span> | <span data-ttu-id="792e0-198">ID do objeto Creator</span><span class="sxs-lookup"><span data-stu-id="792e0-198">Creator object id</span></span> | <span data-ttu-id="792e0-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="792e0-199">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="792e0-200">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="792e0-200">requesterNotes</span></span> | <span data-ttu-id="792e0-201">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-201">String</span></span> | <span data-ttu-id="792e0-202">As anotações (texto livre) que o criador adicionou para essa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="792e0-202">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="792e0-203">null</span><span class="sxs-lookup"><span data-stu-id="792e0-203">null</span></span>
<span data-ttu-id="792e0-204">scid</span><span class="sxs-lookup"><span data-stu-id="792e0-204">scid</span></span> | <span data-ttu-id="792e0-205">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-205">String</span></span> | <span data-ttu-id="792e0-206">SCID da recomendação de segurança relacionada</span><span class="sxs-lookup"><span data-stu-id="792e0-206">SCID of the related security recommendation</span></span> | <span data-ttu-id="792e0-207">null</span><span class="sxs-lookup"><span data-stu-id="792e0-207">null</span></span>
<span data-ttu-id="792e0-208">status</span><span class="sxs-lookup"><span data-stu-id="792e0-208">status</span></span> | <span data-ttu-id="792e0-209">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-209">String</span></span> | <span data-ttu-id="792e0-210">Status da atividade de correção (Ativo/Concluído)</span><span class="sxs-lookup"><span data-stu-id="792e0-210">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="792e0-211">Ativo</span><span class="sxs-lookup"><span data-stu-id="792e0-211">Active</span></span>
<span data-ttu-id="792e0-212">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="792e0-212">statusLastModifiedOn</span></span> | <span data-ttu-id="792e0-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="792e0-213">DateTime</span></span> | <span data-ttu-id="792e0-214">Data em que o campo de status foi atualizado</span><span class="sxs-lookup"><span data-stu-id="792e0-214">Date when the status field was updated</span></span> | <span data-ttu-id="792e0-215">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="792e0-215">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="792e0-216">targetDevices</span><span class="sxs-lookup"><span data-stu-id="792e0-216">targetDevices</span></span> | <span data-ttu-id="792e0-217">Longo</span><span class="sxs-lookup"><span data-stu-id="792e0-217">Long</span></span> | <span data-ttu-id="792e0-218">Número de dispositivos expostos a que essa correção é aplicável</span><span class="sxs-lookup"><span data-stu-id="792e0-218">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="792e0-219">43</span><span class="sxs-lookup"><span data-stu-id="792e0-219">43</span></span>
<span data-ttu-id="792e0-220">title</span><span class="sxs-lookup"><span data-stu-id="792e0-220">title</span></span> | <span data-ttu-id="792e0-221">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-221">String</span></span> | <span data-ttu-id="792e0-222">Título dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="792e0-222">Title of this remediation activity</span></span> | <span data-ttu-id="792e0-223">Atualizar o Google Chrome</span><span class="sxs-lookup"><span data-stu-id="792e0-223">Update Google Chrome</span></span>
<span data-ttu-id="792e0-224">tipo</span><span class="sxs-lookup"><span data-stu-id="792e0-224">type</span></span> | <span data-ttu-id="792e0-225">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-225">String</span></span> | <span data-ttu-id="792e0-226">Tipo de correção</span><span class="sxs-lookup"><span data-stu-id="792e0-226">Remediation type</span></span> | <span data-ttu-id="792e0-227">Atualizar</span><span class="sxs-lookup"><span data-stu-id="792e0-227">Update</span></span>
<span data-ttu-id="792e0-228">vendorId</span><span class="sxs-lookup"><span data-stu-id="792e0-228">vendorId</span></span> | <span data-ttu-id="792e0-229">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="792e0-229">String</span></span> | <span data-ttu-id="792e0-230">Nome do fornecedor relacionado</span><span class="sxs-lookup"><span data-stu-id="792e0-230">Related vendor name</span></span> | <span data-ttu-id="792e0-231">google</span><span class="sxs-lookup"><span data-stu-id="792e0-231">google</span></span>

## <a name="example"></a><span data-ttu-id="792e0-232">Exemplo</span><span class="sxs-lookup"><span data-stu-id="792e0-232">Example</span></span>

<span data-ttu-id="792e0-233">**Exemplo de** solicitação</span><span class="sxs-lookup"><span data-stu-id="792e0-233">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

<span data-ttu-id="792e0-234">**Exemplo de** resposta</span><span class="sxs-lookup"><span data-stu-id="792e0-234">**Response** example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ",
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
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="792e0-235">Confira também</span><span class="sxs-lookup"><span data-stu-id="792e0-235">See also</span></span>

- [<span data-ttu-id="792e0-236">Métodos e propriedades de correção</span><span class="sxs-lookup"><span data-stu-id="792e0-236">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="792e0-237">Obter uma atividade de correção por Id</span><span class="sxs-lookup"><span data-stu-id="792e0-237">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="792e0-238">Listar dispositivos expostos de uma atividade de correção</span><span class="sxs-lookup"><span data-stu-id="792e0-238">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="792e0-239">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="792e0-239">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="792e0-240">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="792e0-240">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
