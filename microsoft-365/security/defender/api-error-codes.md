---
title: Códigos de Microsoft 365 de erro da API REST do Defender
description: Saiba mais sobre os códigos de erro comuns Microsoft 365 API REST do Defender
keywords: api, erro, códigos, erros comuns, Microsoft 365 Defender, códigos de erro de api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e621b79d37a2c3a22394bd51e0493334eff461c7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932876"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="e57b0-104">Códigos de Microsoft 365 de erro da API REST do Defender</span><span class="sxs-lookup"><span data-stu-id="e57b0-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e57b0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e57b0-105">**Applies to:**</span></span>

- <span data-ttu-id="e57b0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e57b0-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e57b0-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="e57b0-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e57b0-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="e57b0-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e57b0-109">Os códigos de erro podem ser retornados por uma operação em qualquer uma das APIs Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e57b0-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="e57b0-110">Cada resposta de erro conterá uma mensagem de erro, o que pode ajudar a resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="e57b0-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="e57b0-111">A coluna mensagem de erro na seção tabela fornece algumas mensagens de exemplo.</span><span class="sxs-lookup"><span data-stu-id="e57b0-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="e57b0-112">O conteúdo das mensagens reais variará com base nos fatores que dispararam a resposta.</span><span class="sxs-lookup"><span data-stu-id="e57b0-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="e57b0-113">O conteúdo variável é indicado na tabela por colchetes de ângulo.</span><span class="sxs-lookup"><span data-stu-id="e57b0-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="e57b0-114">Códigos de erro</span><span class="sxs-lookup"><span data-stu-id="e57b0-114">Error codes</span></span>

<span data-ttu-id="e57b0-115">Código de erro</span><span class="sxs-lookup"><span data-stu-id="e57b0-115">Error code</span></span> | <span data-ttu-id="e57b0-116">Código de status de HTTP</span><span class="sxs-lookup"><span data-stu-id="e57b0-116">HTTP status code</span></span> | <span data-ttu-id="e57b0-117">Mensagem</span><span class="sxs-lookup"><span data-stu-id="e57b0-117">Message</span></span>
-|-|-
<span data-ttu-id="e57b0-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="e57b0-118">BadRequest</span></span> | <span data-ttu-id="e57b0-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-119">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-120">Mensagem de erro de Solicitação Geral de Erro.</span><span class="sxs-lookup"><span data-stu-id="e57b0-120">General Bad Request error message.</span></span>
<span data-ttu-id="e57b0-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="e57b0-121">ODataError</span></span> | <span data-ttu-id="e57b0-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-122">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-123">Consulta OData URI inválida \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="e57b0-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="e57b0-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="e57b0-124">InvalidInput</span></span> | <span data-ttu-id="e57b0-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-125">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-126">Entrada inválida \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="e57b0-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="e57b0-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="e57b0-127">InvalidRequestBody</span></span> | <span data-ttu-id="e57b0-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-128">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-129">Corpo da solicitação inválido.</span><span class="sxs-lookup"><span data-stu-id="e57b0-129">Invalid request body.</span></span>
<span data-ttu-id="e57b0-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="e57b0-130">InvalidHashValue</span></span> | <span data-ttu-id="e57b0-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-131">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-132">O valor hash \<the invalid hash\> é inválido.</span><span class="sxs-lookup"><span data-stu-id="e57b0-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="e57b0-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="e57b0-133">InvalidDomainName</span></span> | <span data-ttu-id="e57b0-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-134">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-135">O nome \<the invalid domain\> de domínio é inválido.</span><span class="sxs-lookup"><span data-stu-id="e57b0-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="e57b0-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="e57b0-136">InvalidIpAddress</span></span> | <span data-ttu-id="e57b0-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-137">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-138">O endereço IP \<the invalid IP\> é inválido.</span><span class="sxs-lookup"><span data-stu-id="e57b0-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="e57b0-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="e57b0-139">InvalidUrl</span></span> | <span data-ttu-id="e57b0-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-140">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-141">A URL \<the invalid URL\> é inválida.</span><span class="sxs-lookup"><span data-stu-id="e57b0-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="e57b0-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="e57b0-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="e57b0-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-143">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-144">Tamanho máximo do lote excedido.</span><span class="sxs-lookup"><span data-stu-id="e57b0-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="e57b0-145">Recebido: \<batch size received\> , permitido: {tamanho do lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="e57b0-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="e57b0-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="e57b0-146">MissingRequiredParameter</span></span> | <span data-ttu-id="e57b0-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-147">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-148">O \<the missing parameter\> parâmetro está faltando.</span><span class="sxs-lookup"><span data-stu-id="e57b0-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="e57b0-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="e57b0-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="e57b0-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-150">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-151">A Plataforma \<the client OS Platform\> do sistema operacional não tem suporte para essa ação.</span><span class="sxs-lookup"><span data-stu-id="e57b0-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="e57b0-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="e57b0-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="e57b0-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="e57b0-153">BadRequest (400)</span></span> | <span data-ttu-id="e57b0-154">\<The requested action\> tem suporte na versão do cliente \<supported client version\> e acima.</span><span class="sxs-lookup"><span data-stu-id="e57b0-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="e57b0-155">Não Autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="e57b0-155">Unauthorized</span></span> | <span data-ttu-id="e57b0-156">Não autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="e57b0-156">Unauthorized (401)</span></span> | <span data-ttu-id="e57b0-157">Não Autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="e57b0-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="e57b0-158">*Observação: geralmente causada por um header de autorização inválido ou expirado.*</span><span class="sxs-lookup"><span data-stu-id="e57b0-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="e57b0-159">Proibido</span><span class="sxs-lookup"><span data-stu-id="e57b0-159">Forbidden</span></span> | <span data-ttu-id="e57b0-160">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="e57b0-160">Forbidden (403)</span></span> | <span data-ttu-id="e57b0-161">Proibido</span><span class="sxs-lookup"><span data-stu-id="e57b0-161">Forbidden</span></span> <br /><br /><span data-ttu-id="e57b0-162">*Observação: Token válido, mas permissão insuficiente para a ação*.</span><span class="sxs-lookup"><span data-stu-id="e57b0-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="e57b0-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="e57b0-163">DisabledFeature</span></span> | <span data-ttu-id="e57b0-164">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="e57b0-164">Forbidden (403)</span></span> | <span data-ttu-id="e57b0-165">O recurso locatário não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="e57b0-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="e57b0-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="e57b0-166">DisallowedOperation</span></span> | <span data-ttu-id="e57b0-167">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="e57b0-167">Forbidden (403)</span></span> | <span data-ttu-id="e57b0-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="e57b0-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="e57b0-169">NotFound</span><span class="sxs-lookup"><span data-stu-id="e57b0-169">NotFound</span></span> | <span data-ttu-id="e57b0-170">Não encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="e57b0-170">Not Found (404)</span></span> | <span data-ttu-id="e57b0-171">Mensagem de erro Geral Não Encontrada.</span><span class="sxs-lookup"><span data-stu-id="e57b0-171">General Not Found error message.</span></span>
<span data-ttu-id="e57b0-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="e57b0-172">ResourceNotFound</span></span> | <span data-ttu-id="e57b0-173">Não encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="e57b0-173">Not Found (404)</span></span> | <span data-ttu-id="e57b0-174">O \<the requested resource\> recurso não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="e57b0-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="e57b0-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="e57b0-175">InternalServerError</span></span> | <span data-ttu-id="e57b0-176">Erro interno do servidor (500)</span><span class="sxs-lookup"><span data-stu-id="e57b0-176">Internal Server Error (500)</span></span> | <span data-ttu-id="e57b0-177">*Observação: nenhuma mensagem de erro, repetir a operação ou entrar em contato com a Microsoft se ela não for resolvida*</span><span class="sxs-lookup"><span data-stu-id="e57b0-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="e57b0-178">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e57b0-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="e57b0-179">Parâmetros de corpo</span><span class="sxs-lookup"><span data-stu-id="e57b0-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e57b0-180">Os parâmetros do corpo são sensíveis a minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e57b0-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="e57b0-181">Se você experimentar um *erro InvalidRequestBody* ou *MissingRequiredParameter,* ele pode ser causado por um erro de digitação.</span><span class="sxs-lookup"><span data-stu-id="e57b0-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="e57b0-182">Revise a documentação da API e verifique se os parâmetros enviados corresponderão ao exemplo relevante.</span><span class="sxs-lookup"><span data-stu-id="e57b0-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="e57b0-183">ID de rastreamento</span><span class="sxs-lookup"><span data-stu-id="e57b0-183">Tracking ID</span></span>

<span data-ttu-id="e57b0-184">Cada resposta de erro contém um parâmetro de ID exclusivo para rastreamento.</span><span class="sxs-lookup"><span data-stu-id="e57b0-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="e57b0-185">O nome da propriedade desse parâmetro é *target*.</span><span class="sxs-lookup"><span data-stu-id="e57b0-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="e57b0-186">Ao entrar em contato conosco sobre um erro, anexar essa ID nos ajudará a encontrar a causa raiz do problema.</span><span class="sxs-lookup"><span data-stu-id="e57b0-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e57b0-187">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="e57b0-187">Related articles</span></span>

- [<span data-ttu-id="e57b0-188">Microsoft 365 Visão geral das APIs do Defender</span><span class="sxs-lookup"><span data-stu-id="e57b0-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="e57b0-189">APIs com suporte do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e57b0-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="e57b0-190">Acessar as APIs Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e57b0-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="e57b0-191">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="e57b0-191">Learn about API limits and licensing</span></span>](api-terms.md)
