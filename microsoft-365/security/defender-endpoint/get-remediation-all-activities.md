---
title: Listar todas as atividades de correção
description: Retorna informações sobre todas as atividades de correção.
keywords: apis, correção, api de correção, obter, tarefas de correção, tudo correção,
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
ms.openlocfilehash: 60f80e78a5f5c7da44a218c30f4b0173d4ecc829
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845122"
---
# <a name="list-all-remediation-activities"></a><span data-ttu-id="28b0c-104">Listar todas as atividades de correção</span><span class="sxs-lookup"><span data-stu-id="28b0c-104">List all remediation activities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28b0c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="28b0c-105">**Applies to:**</span></span>

- [<span data-ttu-id="28b0c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="28b0c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="28b0c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28b0c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="28b0c-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="28b0c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="28b0c-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="28b0c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="28b0c-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="28b0c-110">API description</span></span>

<span data-ttu-id="28b0c-111">Retorna informações sobre todas as atividades de correção.</span><span class="sxs-lookup"><span data-stu-id="28b0c-111">Returns information about all remediation activities.</span></span>

<span data-ttu-id="28b0c-112">[Saiba mais sobre atividades de correção.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="28b0c-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

<span data-ttu-id="28b0c-113">**URL:** GET: /api/remediationTasks</span><span class="sxs-lookup"><span data-stu-id="28b0c-113">**URL:** GET: /api/remediationTasks</span></span>

## <a name="permissions"></a><span data-ttu-id="28b0c-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="28b0c-114">Permissions</span></span>

<span data-ttu-id="28b0c-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="28b0c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="28b0c-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="28b0c-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="28b0c-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="28b0c-117">Permission type</span></span> | <span data-ttu-id="28b0c-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="28b0c-118">Permission</span></span> | <span data-ttu-id="28b0c-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="28b0c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="28b0c-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="28b0c-120">Application</span></span> | <span data-ttu-id="28b0c-121">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="28b0c-121">RemediationTask.Read.All</span></span> | <span data-ttu-id="28b0c-122">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="28b0c-122">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="28b0c-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="28b0c-123">Delegated (work or school account)</span></span> | <span data-ttu-id="28b0c-124">RemediationTask.Read</span><span class="sxs-lookup"><span data-stu-id="28b0c-124">RemediationTask.Read</span></span> | <span data-ttu-id="28b0c-125">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="28b0c-125">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties"></a><span data-ttu-id="28b0c-126">Propriedades</span><span class="sxs-lookup"><span data-stu-id="28b0c-126">Properties</span></span>

<span data-ttu-id="28b0c-127">Propriedade (id)</span><span class="sxs-lookup"><span data-stu-id="28b0c-127">Property (id)</span></span> | <span data-ttu-id="28b0c-128">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="28b0c-128">Data type</span></span> | <span data-ttu-id="28b0c-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="28b0c-129">Description</span></span> | <span data-ttu-id="28b0c-130">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="28b0c-130">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="28b0c-131">category</span><span class="sxs-lookup"><span data-stu-id="28b0c-131">category</span></span> | <span data-ttu-id="28b0c-132">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-132">String</span></span> | <span data-ttu-id="28b0c-133">Categoria da atividade de correção (Configuração de software/segurança)</span><span class="sxs-lookup"><span data-stu-id="28b0c-133">Category of the remediation activity (Software/Security configuration)</span></span> | <span data-ttu-id="28b0c-134">Software</span><span class="sxs-lookup"><span data-stu-id="28b0c-134">Software</span></span>
<span data-ttu-id="28b0c-135">completerEmail</span><span class="sxs-lookup"><span data-stu-id="28b0c-135">completerEmail</span></span> | <span data-ttu-id="28b0c-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-136">String</span></span> | <span data-ttu-id="28b0c-137">Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém seus emails</span><span class="sxs-lookup"><span data-stu-id="28b0c-137">If the remediation activity was manually completed by someone, this column contains their email</span></span> | <span data-ttu-id="28b0c-138">null</span><span class="sxs-lookup"><span data-stu-id="28b0c-138">null</span></span>
<span data-ttu-id="28b0c-139">completerId</span><span class="sxs-lookup"><span data-stu-id="28b0c-139">completerId</span></span> | <span data-ttu-id="28b0c-140">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-140">String</span></span> | <span data-ttu-id="28b0c-141">Se a atividade de correção foi concluída manualmente por alguém, esta coluna contém sua id de objeto</span><span class="sxs-lookup"><span data-stu-id="28b0c-141">If the remediation activity was manually completed by someone, this column contains their object id</span></span> | <span data-ttu-id="28b0c-142">null</span><span class="sxs-lookup"><span data-stu-id="28b0c-142">null</span></span>
<span data-ttu-id="28b0c-143">completionMethod</span><span class="sxs-lookup"><span data-stu-id="28b0c-143">completionMethod</span></span> | <span data-ttu-id="28b0c-144">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-144">String</span></span> | <span data-ttu-id="28b0c-145">Uma atividade de correção pode ser concluída "automaticamente" (se todos os dispositivos são remendados) ou "manualmente" por uma pessoa que seleciona "marcar como concluída"</span><span class="sxs-lookup"><span data-stu-id="28b0c-145">A remediation activity can be completed “automatically” (if all the devices are patched) or “manually” by a person who selects “mark as completed”</span></span> | <span data-ttu-id="28b0c-146">Automático</span><span class="sxs-lookup"><span data-stu-id="28b0c-146">Automatic</span></span>
<span data-ttu-id="28b0c-147">createdOn</span><span class="sxs-lookup"><span data-stu-id="28b0c-147">createdOn</span></span> | <span data-ttu-id="28b0c-148">DateTime</span><span class="sxs-lookup"><span data-stu-id="28b0c-148">DateTime</span></span> | <span data-ttu-id="28b0c-149">Hora em que essa atividade de correção foi criada</span><span class="sxs-lookup"><span data-stu-id="28b0c-149">Time this remediation activity was created</span></span> | <span data-ttu-id="28b0c-150">2021-01-12T18:54:11.5499478Z</span><span class="sxs-lookup"><span data-stu-id="28b0c-150">2021-01-12T18:54:11.5499478Z</span></span>
<span data-ttu-id="28b0c-151">descrição</span><span class="sxs-lookup"><span data-stu-id="28b0c-151">description</span></span> | <span data-ttu-id="28b0c-152">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-152">String</span></span> | <span data-ttu-id="28b0c-153">Descrição dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="28b0c-153">Description of this remediation activity</span></span> | <span data-ttu-id="28b0c-154">Atualize o Microsoft Silverlight para uma versão posterior para atenuar vulnerabilidades conhecidas que afetam seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="28b0c-154">Update Microsoft Silverlight  to a later version to mitigate known vulnerabilities affecting your devices.</span></span>
<span data-ttu-id="28b0c-155">dueOn</span><span class="sxs-lookup"><span data-stu-id="28b0c-155">dueOn</span></span> | <span data-ttu-id="28b0c-156">DateTime</span><span class="sxs-lookup"><span data-stu-id="28b0c-156">DateTime</span></span> | <span data-ttu-id="28b0c-157">Data de vencimento do conjunto de criadores para essa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="28b0c-157">Due date the creator set for this remediation activity</span></span> | <span data-ttu-id="28b0c-158">2021-01-13T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="28b0c-158">2021-01-13T00:00:00Z</span></span>
<span data-ttu-id="28b0c-159">fixedDevices</span><span class="sxs-lookup"><span data-stu-id="28b0c-159">fixedDevices</span></span> | <span data-ttu-id="28b0c-160">.</span><span class="sxs-lookup"><span data-stu-id="28b0c-160">.</span></span> | <span data-ttu-id="28b0c-161">O número de dispositivos que foram corrigidos</span><span class="sxs-lookup"><span data-stu-id="28b0c-161">The number of devices that have been fixed</span></span> | <span data-ttu-id="28b0c-162">2</span><span class="sxs-lookup"><span data-stu-id="28b0c-162">2</span></span>
<span data-ttu-id="28b0c-163">id</span><span class="sxs-lookup"><span data-stu-id="28b0c-163">id</span></span> | <span data-ttu-id="28b0c-164">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-164">String</span></span> | <span data-ttu-id="28b0c-165">ID dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="28b0c-165">ID of this remediation activity</span></span> | <span data-ttu-id="28b0c-166">097d9735-5479-4899-b1b7-77398899df92</span><span class="sxs-lookup"><span data-stu-id="28b0c-166">097d9735-5479-4899-b1b7-77398899df92</span></span>
<span data-ttu-id="28b0c-167">nameId</span><span class="sxs-lookup"><span data-stu-id="28b0c-167">nameId</span></span> | <span data-ttu-id="28b0c-168">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-168">String</span></span> | <span data-ttu-id="28b0c-169">Nome do produto relacionado</span><span class="sxs-lookup"><span data-stu-id="28b0c-169">Related product name</span></span> | <span data-ttu-id="28b0c-170">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="28b0c-170">Microsoft Silverlight</span></span>
<span data-ttu-id="28b0c-171">prioridade</span><span class="sxs-lookup"><span data-stu-id="28b0c-171">priority</span></span> | <span data-ttu-id="28b0c-172">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-172">String</span></span> | <span data-ttu-id="28b0c-173">Prioridade do conjunto de criadores para essa atividade de correção (High\Medium\Low)</span><span class="sxs-lookup"><span data-stu-id="28b0c-173">Priority the creator set for this remediation activity (High\Medium\Low)</span></span> | <span data-ttu-id="28b0c-174">Alto</span><span class="sxs-lookup"><span data-stu-id="28b0c-174">High</span></span>
<span data-ttu-id="28b0c-175">productId</span><span class="sxs-lookup"><span data-stu-id="28b0c-175">productId</span></span> | <span data-ttu-id="28b0c-176">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-176">String</span></span> | <span data-ttu-id="28b0c-177">ID do produto relacionado</span><span class="sxs-lookup"><span data-stu-id="28b0c-177">Related product ID</span></span> | <span data-ttu-id="28b0c-178">microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="28b0c-178">microsoft-_-silverlight</span></span>
<span data-ttu-id="28b0c-179">productivityImpactRemediationType</span><span class="sxs-lookup"><span data-stu-id="28b0c-179">productivityImpactRemediationType</span></span> | <span data-ttu-id="28b0c-180">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-180">String</span></span> | <span data-ttu-id="28b0c-181">Algumas alterações de configuração só podem ser solicitadas para dispositivos sem impacto do usuário.</span><span class="sxs-lookup"><span data-stu-id="28b0c-181">A few configuration changes could be requested only for devices with no user impact.</span></span> <span data-ttu-id="28b0c-182">Esse valor indica a seleção entre "todos os dispositivos expostos" ou "somente dispositivos sem impacto do usuário".</span><span class="sxs-lookup"><span data-stu-id="28b0c-182">This value indicates the selection between “all exposed devices” or “only devices with no user impact.”</span></span> | <span data-ttu-id="28b0c-183">AllExposedAssets</span><span class="sxs-lookup"><span data-stu-id="28b0c-183">AllExposedAssets</span></span>
<span data-ttu-id="28b0c-184">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="28b0c-184">rbacGroupNames</span></span> | <span data-ttu-id="28b0c-185">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-185">String</span></span> | <span data-ttu-id="28b0c-186">Nomes de grupo de dispositivos relacionados</span><span class="sxs-lookup"><span data-stu-id="28b0c-186">Related device group names</span></span> | <span data-ttu-id="28b0c-187">[ "Windows Servidores", "Windows 10" ]</span><span class="sxs-lookup"><span data-stu-id="28b0c-187">[ "Windows Servers", "Windows 10" ]</span></span>
<span data-ttu-id="28b0c-188">recommendedProgram</span><span class="sxs-lookup"><span data-stu-id="28b0c-188">recommendedProgram</span></span> | <span data-ttu-id="28b0c-189">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-189">String</span></span> | <span data-ttu-id="28b0c-190">Programa recomendado para atualizar para</span><span class="sxs-lookup"><span data-stu-id="28b0c-190">Recommended program to upgrade to</span></span> | <span data-ttu-id="28b0c-191">null</span><span class="sxs-lookup"><span data-stu-id="28b0c-191">null</span></span>
<span data-ttu-id="28b0c-192">recommendedVendor</span><span class="sxs-lookup"><span data-stu-id="28b0c-192">recommendedVendor</span></span> | <span data-ttu-id="28b0c-193">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-193">String</span></span> | <span data-ttu-id="28b0c-194">Fornecedor recomendado para atualizar para</span><span class="sxs-lookup"><span data-stu-id="28b0c-194">Recommended vendor to upgrade to</span></span> | <span data-ttu-id="28b0c-195">null</span><span class="sxs-lookup"><span data-stu-id="28b0c-195">null</span></span>
<span data-ttu-id="28b0c-196">recommendedVersion</span><span class="sxs-lookup"><span data-stu-id="28b0c-196">recommendedVersion</span></span> | <span data-ttu-id="28b0c-197">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-197">String</span></span> | <span data-ttu-id="28b0c-198">Versão recomendada para atualização/atualização para</span><span class="sxs-lookup"><span data-stu-id="28b0c-198">Recommended version to update/upgrade to</span></span> | <span data-ttu-id="28b0c-199">null</span><span class="sxs-lookup"><span data-stu-id="28b0c-199">null</span></span>
<span data-ttu-id="28b0c-200">relatedComponent</span><span class="sxs-lookup"><span data-stu-id="28b0c-200">relatedComponent</span></span> | <span data-ttu-id="28b0c-201">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-201">String</span></span> | <span data-ttu-id="28b0c-202">Componente relacionado dessa atividade de correção (semelhante ao componente relacionado para uma recomendação de segurança)</span><span class="sxs-lookup"><span data-stu-id="28b0c-202">Related component of this remediation activity (similar to the related component for a security recommendation)</span></span> | <span data-ttu-id="28b0c-203">Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="28b0c-203">Microsoft Silverlight</span></span>
<span data-ttu-id="28b0c-204">requesterEmail</span><span class="sxs-lookup"><span data-stu-id="28b0c-204">requesterEmail</span></span> | <span data-ttu-id="28b0c-205">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-205">String</span></span> | <span data-ttu-id="28b0c-206">Endereço de email do criador</span><span class="sxs-lookup"><span data-stu-id="28b0c-206">Creator email address</span></span> | <span data-ttu-id="28b0c-207">globaladmin@UserName.contoso.com</span><span class="sxs-lookup"><span data-stu-id="28b0c-207">globaladmin@UserName.contoso.com</span></span>
<span data-ttu-id="28b0c-208">requesterId</span><span class="sxs-lookup"><span data-stu-id="28b0c-208">requesterId</span></span> | <span data-ttu-id="28b0c-209">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-209">String</span></span> | <span data-ttu-id="28b0c-210">ID do objeto Creator</span><span class="sxs-lookup"><span data-stu-id="28b0c-210">Creator object id</span></span> | <span data-ttu-id="28b0c-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span><span class="sxs-lookup"><span data-stu-id="28b0c-211">r647211f-2e16-43f2-a480-16ar3a2a796r</span></span>
<span data-ttu-id="28b0c-212">requesterNotes</span><span class="sxs-lookup"><span data-stu-id="28b0c-212">requesterNotes</span></span> | <span data-ttu-id="28b0c-213">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-213">String</span></span> | <span data-ttu-id="28b0c-214">As anotações (texto livre) que o criador adicionou para essa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="28b0c-214">The notes (free text) the creator added for this remediation activity</span></span> | <span data-ttu-id="28b0c-215">null</span><span class="sxs-lookup"><span data-stu-id="28b0c-215">null</span></span>
<span data-ttu-id="28b0c-216">scid</span><span class="sxs-lookup"><span data-stu-id="28b0c-216">scid</span></span> | <span data-ttu-id="28b0c-217">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-217">String</span></span> | <span data-ttu-id="28b0c-218">SCID da recomendação de segurança relacionada</span><span class="sxs-lookup"><span data-stu-id="28b0c-218">SCID of the related security recommendation</span></span> | <span data-ttu-id="28b0c-219">null</span><span class="sxs-lookup"><span data-stu-id="28b0c-219">null</span></span>
<span data-ttu-id="28b0c-220">status</span><span class="sxs-lookup"><span data-stu-id="28b0c-220">status</span></span> | <span data-ttu-id="28b0c-221">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-221">String</span></span> | <span data-ttu-id="28b0c-222">Status da atividade de correção (Ativo/Concluído)</span><span class="sxs-lookup"><span data-stu-id="28b0c-222">Remediation activity status (Active/Completed)</span></span> | <span data-ttu-id="28b0c-223">Ativo</span><span class="sxs-lookup"><span data-stu-id="28b0c-223">Active</span></span>
<span data-ttu-id="28b0c-224">statusLastModifiedOn</span><span class="sxs-lookup"><span data-stu-id="28b0c-224">statusLastModifiedOn</span></span> | <span data-ttu-id="28b0c-225">DateTime</span><span class="sxs-lookup"><span data-stu-id="28b0c-225">DateTime</span></span> | <span data-ttu-id="28b0c-226">Data em que o campo de status foi atualizado</span><span class="sxs-lookup"><span data-stu-id="28b0c-226">Date when the status field was updated</span></span> | <span data-ttu-id="28b0c-227">2021-01-12T18:54:11.5499487Z</span><span class="sxs-lookup"><span data-stu-id="28b0c-227">2021-01-12T18:54:11.5499487Z</span></span>
<span data-ttu-id="28b0c-228">targetDevices</span><span class="sxs-lookup"><span data-stu-id="28b0c-228">targetDevices</span></span> | <span data-ttu-id="28b0c-229">Longo</span><span class="sxs-lookup"><span data-stu-id="28b0c-229">Long</span></span> | <span data-ttu-id="28b0c-230">Número de dispositivos expostos a que essa correção é aplicável</span><span class="sxs-lookup"><span data-stu-id="28b0c-230">Number of exposed devices that this remediation is applicable to</span></span> | <span data-ttu-id="28b0c-231">43</span><span class="sxs-lookup"><span data-stu-id="28b0c-231">43</span></span>
<span data-ttu-id="28b0c-232">title</span><span class="sxs-lookup"><span data-stu-id="28b0c-232">title</span></span> | <span data-ttu-id="28b0c-233">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-233">String</span></span> | <span data-ttu-id="28b0c-234">Título dessa atividade de correção</span><span class="sxs-lookup"><span data-stu-id="28b0c-234">Title of this remediation activity</span></span> | <span data-ttu-id="28b0c-235">Atualizar o Microsoft Silverlight</span><span class="sxs-lookup"><span data-stu-id="28b0c-235">Update Microsoft Silverlight</span></span>
<span data-ttu-id="28b0c-236">tipo</span><span class="sxs-lookup"><span data-stu-id="28b0c-236">type</span></span> | <span data-ttu-id="28b0c-237">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-237">String</span></span> | <span data-ttu-id="28b0c-238">Tipo de correção</span><span class="sxs-lookup"><span data-stu-id="28b0c-238">Remediation type</span></span> | <span data-ttu-id="28b0c-239">Atualizar</span><span class="sxs-lookup"><span data-stu-id="28b0c-239">Update</span></span>
<span data-ttu-id="28b0c-240">vendorId</span><span class="sxs-lookup"><span data-stu-id="28b0c-240">vendorId</span></span> | <span data-ttu-id="28b0c-241">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="28b0c-241">String</span></span> | <span data-ttu-id="28b0c-242">Nome do fornecedor relacionado</span><span class="sxs-lookup"><span data-stu-id="28b0c-242">Related vendor name</span></span> | <span data-ttu-id="28b0c-243">Microsoft</span><span class="sxs-lookup"><span data-stu-id="28b0c-243">Microsoft</span></span>

## <a name="example"></a><span data-ttu-id="28b0c-244">Exemplo</span><span class="sxs-lookup"><span data-stu-id="28b0c-244">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="28b0c-245">Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="28b0c-245">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a><span data-ttu-id="28b0c-246">Exemplo de resposta</span><span class="sxs-lookup"><span data-stu-id="28b0c-246">Response example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="28b0c-247">Confira também</span><span class="sxs-lookup"><span data-stu-id="28b0c-247">See also</span></span>

- [<span data-ttu-id="28b0c-248">Métodos e propriedades de correção</span><span class="sxs-lookup"><span data-stu-id="28b0c-248">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="28b0c-249">Obter uma atividade de correção por ID</span><span class="sxs-lookup"><span data-stu-id="28b0c-249">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="28b0c-250">Listar dispositivos expostos de uma atividade de correção</span><span class="sxs-lookup"><span data-stu-id="28b0c-250">List exposed devices of one remediation activity</span></span>](get-remediation-exposed-devices-activities.md)

- [<span data-ttu-id="28b0c-251">Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="28b0c-251">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="28b0c-252">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="28b0c-252">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
