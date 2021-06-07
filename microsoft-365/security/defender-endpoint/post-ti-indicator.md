---
title: Api de Indicador de Envio ou Atualização
description: Saiba como usar a API Enviar ou Atualizar Indicador para enviar ou atualizar uma nova entidade Indicator no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, enviar, ti, indicador, atualização
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
ms.openlocfilehash: ce0dc0ce255e9717082687bd1f8bf5941739261d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771700"
---
# <a name="submit-or-update-indicator-api"></a><span data-ttu-id="ab4a0-104">Api de Indicador de Envio ou Atualização</span><span class="sxs-lookup"><span data-stu-id="ab4a0-104">Submit or Update Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ab4a0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab4a0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ab4a0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab4a0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab4a0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ab4a0-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ab4a0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab4a0-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="ab4a0-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="ab4a0-110">API description</span></span>
<span data-ttu-id="ab4a0-111">Envia ou atualiza a nova [entidade Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="ab4a0-111">Submits or Updates new [Indicator](ti-indicator.md) entity.</span></span>
<br><span data-ttu-id="ab4a0-112">A notação CIDR para IPs não é suportada.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-112">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="ab4a0-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="ab4a0-113">Limitations</span></span>
1. <span data-ttu-id="ab4a0-114">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="ab4a0-115">Há um limite de 15.000 indicadores ativos por locatário.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-115">There is a limit of 15,000 active indicators per tenant.</span></span> 


## <a name="permissions"></a><span data-ttu-id="ab4a0-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="ab4a0-116">Permissions</span></span>
<span data-ttu-id="ab4a0-117">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ab4a0-118">Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ab4a0-118">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="ab4a0-119">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="ab4a0-119">Permission type</span></span> |   <span data-ttu-id="ab4a0-120">Permissão</span><span class="sxs-lookup"><span data-stu-id="ab4a0-120">Permission</span></span>  |   <span data-ttu-id="ab4a0-121">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="ab4a0-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ab4a0-122">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="ab4a0-122">Application</span></span> |   <span data-ttu-id="ab4a0-123">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ab4a0-123">Ti.ReadWrite</span></span> |  <span data-ttu-id="ab4a0-124">'Indicadores de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="ab4a0-124">'Read and write Indicators'</span></span>
<span data-ttu-id="ab4a0-125">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="ab4a0-125">Application</span></span> |   <span data-ttu-id="ab4a0-126">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="ab4a0-126">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="ab4a0-127">'Ler e gravar Todos os Indicadores'</span><span class="sxs-lookup"><span data-stu-id="ab4a0-127">'Read and write All Indicators'</span></span>
<span data-ttu-id="ab4a0-128">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="ab4a0-128">Delegated (work or school account)</span></span> |    <span data-ttu-id="ab4a0-129">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="ab4a0-129">Ti.ReadWrite</span></span> |  <span data-ttu-id="ab4a0-130">'Indicadores de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="ab4a0-130">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="ab4a0-131">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="ab4a0-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="ab4a0-132">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="ab4a0-132">Request headers</span></span>

<span data-ttu-id="ab4a0-133">Nome</span><span class="sxs-lookup"><span data-stu-id="ab4a0-133">Name</span></span> | <span data-ttu-id="ab4a0-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab4a0-134">Type</span></span> | <span data-ttu-id="ab4a0-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="ab4a0-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="ab4a0-136">Autorização</span><span class="sxs-lookup"><span data-stu-id="ab4a0-136">Authorization</span></span> | <span data-ttu-id="ab4a0-137">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ab4a0-137">String</span></span> | <span data-ttu-id="ab4a0-138">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-138">Bearer {token}.</span></span> <span data-ttu-id="ab4a0-139">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-139">**Required**.</span></span>
<span data-ttu-id="ab4a0-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ab4a0-140">Content-Type</span></span> | <span data-ttu-id="ab4a0-141">string</span><span class="sxs-lookup"><span data-stu-id="ab4a0-141">string</span></span> | <span data-ttu-id="ab4a0-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-142">application/json.</span></span> <span data-ttu-id="ab4a0-143">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ab4a0-144">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="ab4a0-144">Request body</span></span>
<span data-ttu-id="ab4a0-145">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="ab4a0-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="ab4a0-146">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="ab4a0-146">Parameter</span></span> | <span data-ttu-id="ab4a0-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab4a0-147">Type</span></span>    | <span data-ttu-id="ab4a0-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="ab4a0-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="ab4a0-149">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="ab4a0-149">indicatorValue</span></span> | <span data-ttu-id="ab4a0-150">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ab4a0-150">String</span></span> | <span data-ttu-id="ab4a0-151">Identidade da entidade [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="ab4a0-151">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="ab4a0-152">**Required**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-152">**Required**</span></span>
<span data-ttu-id="ab4a0-153">indicatorType</span><span class="sxs-lookup"><span data-stu-id="ab4a0-153">indicatorType</span></span> | <span data-ttu-id="ab4a0-154">Enum</span><span class="sxs-lookup"><span data-stu-id="ab4a0-154">Enum</span></span> | <span data-ttu-id="ab4a0-155">Tipo do indicador.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-155">Type of the indicator.</span></span> <span data-ttu-id="ab4a0-156">Os valores possíveis são: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url".</span><span class="sxs-lookup"><span data-stu-id="ab4a0-156">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="ab4a0-157">**Required**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-157">**Required**</span></span>
<span data-ttu-id="ab4a0-158">ação</span><span class="sxs-lookup"><span data-stu-id="ab4a0-158">action</span></span> | <span data-ttu-id="ab4a0-159">Enum</span><span class="sxs-lookup"><span data-stu-id="ab4a0-159">Enum</span></span> | <span data-ttu-id="ab4a0-160">A ação que será tomada se o indicador for descoberto na organização.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-160">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="ab4a0-161">Os valores possíveis são: "Alert", "AlertAndBlock" e "Allowed".</span><span class="sxs-lookup"><span data-stu-id="ab4a0-161">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="ab4a0-162">**Required**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-162">**Required**</span></span>
<span data-ttu-id="ab4a0-163">aplicação</span><span class="sxs-lookup"><span data-stu-id="ab4a0-163">application</span></span> | <span data-ttu-id="ab4a0-164">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ab4a0-164">String</span></span> | <span data-ttu-id="ab4a0-165">O aplicativo associado ao indicador.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-165">The application associated with the indicator.</span></span> <span data-ttu-id="ab4a0-166">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-166">**Optional**</span></span>
<span data-ttu-id="ab4a0-167">title</span><span class="sxs-lookup"><span data-stu-id="ab4a0-167">title</span></span> | <span data-ttu-id="ab4a0-168">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ab4a0-168">String</span></span> | <span data-ttu-id="ab4a0-169">Título de alerta de indicador.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-169">Indicator alert title.</span></span> <span data-ttu-id="ab4a0-170">**Required**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-170">**Required**</span></span>
<span data-ttu-id="ab4a0-171">description</span><span class="sxs-lookup"><span data-stu-id="ab4a0-171">description</span></span> | <span data-ttu-id="ab4a0-172">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ab4a0-172">String</span></span> | <span data-ttu-id="ab4a0-173">Descrição do indicador.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-173">Description of the indicator.</span></span> <span data-ttu-id="ab4a0-174">**Required**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-174">**Required**</span></span>
<span data-ttu-id="ab4a0-175">expirationTime</span><span class="sxs-lookup"><span data-stu-id="ab4a0-175">expirationTime</span></span> | <span data-ttu-id="ab4a0-176">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="ab4a0-176">DateTimeOffset</span></span> | <span data-ttu-id="ab4a0-177">O tempo de expiração do indicador.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-177">The expiration time of the indicator.</span></span> <span data-ttu-id="ab4a0-178">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-178">**Optional**</span></span>
<span data-ttu-id="ab4a0-179">severity</span><span class="sxs-lookup"><span data-stu-id="ab4a0-179">severity</span></span> | <span data-ttu-id="ab4a0-180">Enum</span><span class="sxs-lookup"><span data-stu-id="ab4a0-180">Enum</span></span> | <span data-ttu-id="ab4a0-181">A gravidade do indicador.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-181">The severity of the indicator.</span></span> <span data-ttu-id="ab4a0-182">os valores possíveis são: "Informacional", "Baixo", "Médio" e "Alto".</span><span class="sxs-lookup"><span data-stu-id="ab4a0-182">possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="ab4a0-183">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-183">**Optional**</span></span>
<span data-ttu-id="ab4a0-184">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="ab4a0-184">recommendedActions</span></span> | <span data-ttu-id="ab4a0-185">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ab4a0-185">String</span></span> | <span data-ttu-id="ab4a0-186">Ações recomendadas do alerta de ti.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-186">TI indicator alert recommended actions.</span></span> <span data-ttu-id="ab4a0-187">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-187">**Optional**</span></span>
<span data-ttu-id="ab4a0-188">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="ab4a0-188">rbacGroupNames</span></span> | <span data-ttu-id="ab4a0-189">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ab4a0-189">String</span></span> | <span data-ttu-id="ab4a0-190">Lista separada por vírgulas de nomes de grupo do RBAC aos que o indicador seria aplicado.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-190">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="ab4a0-191">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-191">**Optional**</span></span>


## <a name="response"></a><span data-ttu-id="ab4a0-192">Resposta</span><span class="sxs-lookup"><span data-stu-id="ab4a0-192">Response</span></span>
- <span data-ttu-id="ab4a0-193">Se tiver êxito, este método retornará 200 - código de resposta OK e a entidade [Indicator](ti-indicator.md) criada/atualizada no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-193">If successful, this method returns 200 - OK response code and the created / updated [Indicator](ti-indicator.md) entity in the response body.</span></span>
- <span data-ttu-id="ab4a0-194">Se não tiver êxito: este método retornará 400 - Solicitação Ruim.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-194">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="ab4a0-195">A solicitação incorreta geralmente indica o corpo incorreto.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-195">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="ab4a0-196">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ab4a0-196">Example</span></span>

<span data-ttu-id="ab4a0-197">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="ab4a0-197">**Request**</span></span>

<span data-ttu-id="ab4a0-198">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="ab4a0-198">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators
```

```json
{
    "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
    "indicatorType": "FileSha1",
    "title": "test",
    "application": "demo-test",
    "expirationTime": "2020-12-12T00:00:00Z",
    "action": "AlertAndBlock",
    "severity": "Informational",
    "description": "test",
    "recommendedActions": "nothing",
    "rbacGroupNames": ["group1", "group2"]
}
```

## <a name="related-topic"></a><span data-ttu-id="ab4a0-199">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ab4a0-199">Related topic</span></span>
- [<span data-ttu-id="ab4a0-200">Gerenciar indicadores</span><span class="sxs-lookup"><span data-stu-id="ab4a0-200">Manage indicators</span></span>](manage-indicators.md)
