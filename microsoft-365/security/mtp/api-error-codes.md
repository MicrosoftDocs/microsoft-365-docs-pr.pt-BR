---
title: Códigos de erro comuns da API REST do Microsoft 365 Defender
description: Saiba mais sobre os códigos de erro comuns da API REST do Microsoft 365 Defender
keywords: api, erro, códigos, erros comuns, mtp, códigos de erro de api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928385"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="4e982-104">Códigos de erro comuns da API REST do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e982-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4e982-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4e982-105">**Applies to:**</span></span>

- <span data-ttu-id="4e982-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4e982-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e982-107">Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente.</span><span class="sxs-lookup"><span data-stu-id="4e982-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4e982-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="4e982-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="4e982-109">Os códigos de erro podem ser retornados por uma operação em qualquer uma das APIs do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4e982-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="4e982-110">Cada resposta de erro conterá uma mensagem de erro, o que pode ajudar a resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="4e982-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="4e982-111">A coluna de mensagem de erro na seção de tabela fornece algumas mensagens de exemplo.</span><span class="sxs-lookup"><span data-stu-id="4e982-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="4e982-112">O conteúdo das mensagens reais variará com base nos fatores que dispararam a resposta.</span><span class="sxs-lookup"><span data-stu-id="4e982-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="4e982-113">O conteúdo variável é indicado na tabela por colchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="4e982-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="4e982-114">Códigos de erro</span><span class="sxs-lookup"><span data-stu-id="4e982-114">Error codes</span></span>

<span data-ttu-id="4e982-115">Código de erro</span><span class="sxs-lookup"><span data-stu-id="4e982-115">Error code</span></span> | <span data-ttu-id="4e982-116">Código de status de HTTP</span><span class="sxs-lookup"><span data-stu-id="4e982-116">HTTP status code</span></span> | <span data-ttu-id="4e982-117">Mensagem</span><span class="sxs-lookup"><span data-stu-id="4e982-117">Message</span></span>
-|-|-
<span data-ttu-id="4e982-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="4e982-118">BadRequest</span></span> | <span data-ttu-id="4e982-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-119">BadRequest (400)</span></span> | <span data-ttu-id="4e982-120">General Bad Request error message.</span><span class="sxs-lookup"><span data-stu-id="4e982-120">General Bad Request error message.</span></span>
<span data-ttu-id="4e982-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="4e982-121">ODataError</span></span> | <span data-ttu-id="4e982-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-122">BadRequest (400)</span></span> | <span data-ttu-id="4e982-123">Consulta OData URI \<the specific error is specified\> inválida.</span><span class="sxs-lookup"><span data-stu-id="4e982-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="4e982-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="4e982-124">InvalidInput</span></span> | <span data-ttu-id="4e982-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-125">BadRequest (400)</span></span> | <span data-ttu-id="4e982-126">Entrada \<the invalid input\> inválida.</span><span class="sxs-lookup"><span data-stu-id="4e982-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="4e982-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="4e982-127">InvalidRequestBody</span></span> | <span data-ttu-id="4e982-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-128">BadRequest (400)</span></span> | <span data-ttu-id="4e982-129">Corpo da solicitação inválido.</span><span class="sxs-lookup"><span data-stu-id="4e982-129">Invalid request body.</span></span>
<span data-ttu-id="4e982-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="4e982-130">InvalidHashValue</span></span> | <span data-ttu-id="4e982-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-131">BadRequest (400)</span></span> | <span data-ttu-id="4e982-132">O valor de \<the invalid hash\> hash é inválido.</span><span class="sxs-lookup"><span data-stu-id="4e982-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="4e982-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="4e982-133">InvalidDomainName</span></span> | <span data-ttu-id="4e982-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-134">BadRequest (400)</span></span> | <span data-ttu-id="4e982-135">O nome do \<the invalid domain\> domínio é inválido.</span><span class="sxs-lookup"><span data-stu-id="4e982-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="4e982-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="4e982-136">InvalidIpAddress</span></span> | <span data-ttu-id="4e982-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-137">BadRequest (400)</span></span> | <span data-ttu-id="4e982-138">O endereço IP \<the invalid IP\> é inválido.</span><span class="sxs-lookup"><span data-stu-id="4e982-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="4e982-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="4e982-139">InvalidUrl</span></span> | <span data-ttu-id="4e982-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-140">BadRequest (400)</span></span> | <span data-ttu-id="4e982-141">A URL \<the invalid URL\> é inválida.</span><span class="sxs-lookup"><span data-stu-id="4e982-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="4e982-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="4e982-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="4e982-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-143">BadRequest (400)</span></span> | <span data-ttu-id="4e982-144">Tamanho máximo do lote excedido.</span><span class="sxs-lookup"><span data-stu-id="4e982-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="4e982-145">Recebido: \<batch size received\> , permitido: {tamanho do lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="4e982-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="4e982-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="4e982-146">MissingRequiredParameter</span></span> | <span data-ttu-id="4e982-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-147">BadRequest (400)</span></span> | <span data-ttu-id="4e982-148">O \<the missing parameter\> parâmetro está ausente.</span><span class="sxs-lookup"><span data-stu-id="4e982-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="4e982-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="4e982-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="4e982-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-150">BadRequest (400)</span></span> | <span data-ttu-id="4e982-151">Não há \<the client OS Platform\> suporte para a plataforma do sistema operacional para essa ação.</span><span class="sxs-lookup"><span data-stu-id="4e982-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="4e982-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="4e982-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="4e982-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="4e982-153">BadRequest (400)</span></span> | <span data-ttu-id="4e982-154">\<The requested action\> é suportado na versão do cliente \<supported client version\> e acima.</span><span class="sxs-lookup"><span data-stu-id="4e982-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="4e982-155">Não Autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="4e982-155">Unauthorized</span></span> | <span data-ttu-id="4e982-156">Não autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="4e982-156">Unauthorized (401)</span></span> | <span data-ttu-id="4e982-157">Não Autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="4e982-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="4e982-158">*Observação: geralmente causada por um header de autorização inválido ou expirado.*</span><span class="sxs-lookup"><span data-stu-id="4e982-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="4e982-159">Proibido</span><span class="sxs-lookup"><span data-stu-id="4e982-159">Forbidden</span></span> | <span data-ttu-id="4e982-160">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="4e982-160">Forbidden (403)</span></span> | <span data-ttu-id="4e982-161">Proibido</span><span class="sxs-lookup"><span data-stu-id="4e982-161">Forbidden</span></span> <br /><br /><span data-ttu-id="4e982-162">*Observação: Token válido, mas permissão insuficiente para a ação.*</span><span class="sxs-lookup"><span data-stu-id="4e982-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="4e982-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="4e982-163">DisabledFeature</span></span> | <span data-ttu-id="4e982-164">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="4e982-164">Forbidden (403)</span></span> | <span data-ttu-id="4e982-165">O recurso de locatário não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="4e982-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="4e982-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="4e982-166">DisallowedOperation</span></span> | <span data-ttu-id="4e982-167">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="4e982-167">Forbidden (403)</span></span> | <span data-ttu-id="4e982-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="4e982-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="4e982-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="4e982-169">NotFound</span></span> | <span data-ttu-id="4e982-170">Não Encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="4e982-170">Not Found (404)</span></span> | <span data-ttu-id="4e982-171">Mensagem de erro Geral Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="4e982-171">General Not Found error message.</span></span>
<span data-ttu-id="4e982-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="4e982-172">ResourceNotFound</span></span> | <span data-ttu-id="4e982-173">Não Encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="4e982-173">Not Found (404)</span></span> | <span data-ttu-id="4e982-174">O \<the requested resource\> recurso não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="4e982-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="4e982-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="4e982-175">InternalServerError</span></span> | <span data-ttu-id="4e982-176">Erro interno do servidor (500)</span><span class="sxs-lookup"><span data-stu-id="4e982-176">Internal Server Error (500)</span></span> | <span data-ttu-id="4e982-177">*Observação: nenhuma mensagem de erro, repetir a operação ou entrar em contato com a Microsoft se ela não for resolvida*</span><span class="sxs-lookup"><span data-stu-id="4e982-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="4e982-178">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4e982-178">Examples</span></span>

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a><span data-ttu-id="4e982-179">Parâmetros de corpo</span><span class="sxs-lookup"><span data-stu-id="4e982-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e982-180">Os parâmetros do corpo são sensíveis a minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4e982-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="4e982-181">Se você tiver um *erro InvalidRequestBody* ou *MissingRequiredParameter,* ele poderá ser causado por um erro de digitação.</span><span class="sxs-lookup"><span data-stu-id="4e982-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="4e982-182">Revise a documentação da API e verifique se os parâmetros enviados estão de acordo com o exemplo relevante.</span><span class="sxs-lookup"><span data-stu-id="4e982-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="4e982-183">ID de rastreamento</span><span class="sxs-lookup"><span data-stu-id="4e982-183">Tracking ID</span></span>

<span data-ttu-id="4e982-184">Cada resposta de erro contém um parâmetro de ID exclusivo para rastreamento.</span><span class="sxs-lookup"><span data-stu-id="4e982-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="4e982-185">O nome da propriedade deste parâmetro é *o destino.*</span><span class="sxs-lookup"><span data-stu-id="4e982-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="4e982-186">Ao entrar em contato conosco sobre um erro, anexar essa ID nos ajudará a encontrar a causa raiz do problema.</span><span class="sxs-lookup"><span data-stu-id="4e982-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4e982-187">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="4e982-187">Related articles</span></span>

- [<span data-ttu-id="4e982-188">Visão geral das APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e982-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="4e982-189">APIs com suporte do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e982-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="4e982-190">Acessar as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e982-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="4e982-191">Saiba mais sobre limites e licenciamento de API</span><span class="sxs-lookup"><span data-stu-id="4e982-191">Learn about API limits and licensing</span></span>](api-terms.md)
