---
title: Códigos de erro comuns da API REST do Microsoft 365 defender
description: Saiba mais sobre os códigos de erro comuns da API REST do Microsoft 365 defender
keywords: API, erro, códigos, erros comuns, MTP, códigos de erro de API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719209"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a><span data-ttu-id="c5a67-104">Códigos de erro comuns da API REST do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="c5a67-104">Common Microsoft 365 Defender REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c5a67-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c5a67-105">**Applies to:**</span></span>

- <span data-ttu-id="c5a67-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c5a67-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5a67-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="c5a67-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c5a67-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="c5a67-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c5a67-109">Os códigos de erro podem ser retornados por uma operação em qualquer uma das APIs do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="c5a67-109">Error codes may be returned by an operation on any of the Microsoft 365 Defender APIs.</span></span> <span data-ttu-id="c5a67-110">Cada resposta de erro conterá uma mensagem de erro, que pode ajudar a resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="c5a67-110">Every error response will contain an error message, which can help resolve the problem.</span></span> <span data-ttu-id="c5a67-111">A coluna mensagem de erro na seção tabela fornece algumas mensagens de amostra.</span><span class="sxs-lookup"><span data-stu-id="c5a67-111">The error message column in the table section provides some sample messages.</span></span> <span data-ttu-id="c5a67-112">O conteúdo das mensagens reais irá variar com base nos fatores que acionaram a resposta.</span><span class="sxs-lookup"><span data-stu-id="c5a67-112">The content of actual messages will vary based on the factors that triggered the response.</span></span> <span data-ttu-id="c5a67-113">O conteúdo da variável é indicado na tabela por colchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="c5a67-113">Variable content is indicated in the table by angle brackets.</span></span>

## <a name="error-codes"></a><span data-ttu-id="c5a67-114">Códigos de erro</span><span class="sxs-lookup"><span data-stu-id="c5a67-114">Error codes</span></span>

<span data-ttu-id="c5a67-115">Código de erro</span><span class="sxs-lookup"><span data-stu-id="c5a67-115">Error code</span></span> | <span data-ttu-id="c5a67-116">Código de status de HTTP</span><span class="sxs-lookup"><span data-stu-id="c5a67-116">HTTP status code</span></span> | <span data-ttu-id="c5a67-117">Mensagem</span><span class="sxs-lookup"><span data-stu-id="c5a67-117">Message</span></span>
-|-|-
<span data-ttu-id="c5a67-118">BadRequest</span><span class="sxs-lookup"><span data-stu-id="c5a67-118">BadRequest</span></span> | <span data-ttu-id="c5a67-119">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-119">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-120">Mensagem geral de erro de solicitação incorreta.</span><span class="sxs-lookup"><span data-stu-id="c5a67-120">General Bad Request error message.</span></span>
<span data-ttu-id="c5a67-121">ODataError</span><span class="sxs-lookup"><span data-stu-id="c5a67-121">ODataError</span></span> | <span data-ttu-id="c5a67-122">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-122">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-123">Consulta de URI do OData inválida \<the specific error is specified\> .</span><span class="sxs-lookup"><span data-stu-id="c5a67-123">Invalid OData URI query \<the specific error is specified\>.</span></span>
<span data-ttu-id="c5a67-124">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="c5a67-124">InvalidInput</span></span> | <span data-ttu-id="c5a67-125">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-125">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-126">Entrada inválida \<the invalid input\> .</span><span class="sxs-lookup"><span data-stu-id="c5a67-126">Invalid input \<the invalid input\>.</span></span>
<span data-ttu-id="c5a67-127">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="c5a67-127">InvalidRequestBody</span></span> | <span data-ttu-id="c5a67-128">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-128">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-129">Corpo de solicitação inválido.</span><span class="sxs-lookup"><span data-stu-id="c5a67-129">Invalid request body.</span></span>
<span data-ttu-id="c5a67-130">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="c5a67-130">InvalidHashValue</span></span> | <span data-ttu-id="c5a67-131">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-131">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-132">O valor de hash \<the invalid hash\> é inválido.</span><span class="sxs-lookup"><span data-stu-id="c5a67-132">Hash value \<the invalid hash\> is invalid.</span></span>
<span data-ttu-id="c5a67-133">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="c5a67-133">InvalidDomainName</span></span> | <span data-ttu-id="c5a67-134">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-134">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-135">O nome de domínio \<the invalid domain\> é inválido.</span><span class="sxs-lookup"><span data-stu-id="c5a67-135">Domain name \<the invalid domain\> is invalid.</span></span>
<span data-ttu-id="c5a67-136">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="c5a67-136">InvalidIpAddress</span></span> | <span data-ttu-id="c5a67-137">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-137">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-138">O endereço IP \<the invalid IP\> é inválido.</span><span class="sxs-lookup"><span data-stu-id="c5a67-138">IP address \<the invalid IP\> is invalid.</span></span>
<span data-ttu-id="c5a67-139">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="c5a67-139">InvalidUrl</span></span> | <span data-ttu-id="c5a67-140">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-140">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-141">A URL \<the invalid URL\> é inválida.</span><span class="sxs-lookup"><span data-stu-id="c5a67-141">URL \<the invalid URL\> is invalid.</span></span>
<span data-ttu-id="c5a67-142">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="c5a67-142">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="c5a67-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-143">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-144">Tamanho máximo do lote excedido.</span><span class="sxs-lookup"><span data-stu-id="c5a67-144">Maximum batch size exceeded.</span></span> <span data-ttu-id="c5a67-145">Recebido: \<batch size received\> , permitido: {tamanho do lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="c5a67-145">Received: \<batch size received\>, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="c5a67-146">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="c5a67-146">MissingRequiredParameter</span></span> | <span data-ttu-id="c5a67-147">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-147">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-148">O parâmetro \<the missing parameter\> está ausente.</span><span class="sxs-lookup"><span data-stu-id="c5a67-148">Parameter \<the missing parameter\> is missing.</span></span>
<span data-ttu-id="c5a67-149">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="c5a67-149">OsPlatformNotSupported</span></span> | <span data-ttu-id="c5a67-150">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-150">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-151">A plataforma \<the client OS Platform\> de so não é suportada para esta ação.</span><span class="sxs-lookup"><span data-stu-id="c5a67-151">OS Platform \<the client OS Platform\> is not supported for this action.</span></span>
<span data-ttu-id="c5a67-152">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="c5a67-152">ClientVersionNotSupported</span></span> | <span data-ttu-id="c5a67-153">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="c5a67-153">BadRequest (400)</span></span> | <span data-ttu-id="c5a67-154">\<The requested action\> tem suporte na versão do cliente \<supported client version\> e acima.</span><span class="sxs-lookup"><span data-stu-id="c5a67-154">\<The requested action\> is supported on client version \<supported client version\> and above.</span></span>
<span data-ttu-id="c5a67-155">Não Autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="c5a67-155">Unauthorized</span></span> | <span data-ttu-id="c5a67-156">Não autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="c5a67-156">Unauthorized (401)</span></span> | <span data-ttu-id="c5a67-157">Não Autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="c5a67-157">Unauthorized</span></span> <br /><br /><span data-ttu-id="c5a67-158">*Observação: normalmente causado por um cabeçalho de autorização inválido ou expirado.*</span><span class="sxs-lookup"><span data-stu-id="c5a67-158">*Note: Usually caused by an invalid or expired authorization header.*</span></span>
<span data-ttu-id="c5a67-159">Proibido</span><span class="sxs-lookup"><span data-stu-id="c5a67-159">Forbidden</span></span> | <span data-ttu-id="c5a67-160">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="c5a67-160">Forbidden (403)</span></span> | <span data-ttu-id="c5a67-161">Proibido</span><span class="sxs-lookup"><span data-stu-id="c5a67-161">Forbidden</span></span> <br /><br /><span data-ttu-id="c5a67-162">*Observação: token válido, mas permissão insuficiente para a ação*.</span><span class="sxs-lookup"><span data-stu-id="c5a67-162">*Note: Valid token but insufficient permission for the action*.</span></span>
<span data-ttu-id="c5a67-163">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="c5a67-163">DisabledFeature</span></span> | <span data-ttu-id="c5a67-164">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="c5a67-164">Forbidden (403)</span></span> | <span data-ttu-id="c5a67-165">O recurso de locatário não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c5a67-165">Tenant feature is not enabled.</span></span>
<span data-ttu-id="c5a67-166">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="c5a67-166">DisallowedOperation</span></span> | <span data-ttu-id="c5a67-167">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="c5a67-167">Forbidden (403)</span></span> | <span data-ttu-id="c5a67-168">\<the disallowed operation and the reason\>.</span><span class="sxs-lookup"><span data-stu-id="c5a67-168">\<the disallowed operation and the reason\>.</span></span>
<span data-ttu-id="c5a67-169">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="c5a67-169">NotFound</span></span> | <span data-ttu-id="c5a67-170">Não encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="c5a67-170">Not Found (404)</span></span> | <span data-ttu-id="c5a67-171">Mensagem de erro geral não encontrado.</span><span class="sxs-lookup"><span data-stu-id="c5a67-171">General Not Found error message.</span></span>
<span data-ttu-id="c5a67-172">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="c5a67-172">ResourceNotFound</span></span> | <span data-ttu-id="c5a67-173">Não encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="c5a67-173">Not Found (404)</span></span> | <span data-ttu-id="c5a67-174">Recurso \<the requested resource\> não encontrado.</span><span class="sxs-lookup"><span data-stu-id="c5a67-174">Resource \<the requested resource\> was not found.</span></span>
<span data-ttu-id="c5a67-175">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="c5a67-175">InternalServerError</span></span> | <span data-ttu-id="c5a67-176">Erro interno do servidor (500)</span><span class="sxs-lookup"><span data-stu-id="c5a67-176">Internal Server Error (500)</span></span> | <span data-ttu-id="c5a67-177">*Observação: nenhuma mensagem de erro, tente executar a operação novamente ou contate a Microsoft se ela não for resolvida*</span><span class="sxs-lookup"><span data-stu-id="c5a67-177">*Note: No error message,  retry the operation or contact Microsoft if it does not get resolved*</span></span>

## <a name="examples"></a><span data-ttu-id="c5a67-178">Exemplos</span><span class="sxs-lookup"><span data-stu-id="c5a67-178">Examples</span></span>

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

## <a name="body-parameters"></a><span data-ttu-id="c5a67-179">Parâmetros de corpo</span><span class="sxs-lookup"><span data-stu-id="c5a67-179">Body parameters</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5a67-180">Os parâmetros de corpo diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c5a67-180">Body parameters are case-sensitive.</span></span>

<span data-ttu-id="c5a67-181">Se houver um erro de *InvalidRequestBody* ou *MissingRequiredParameter* , ele poderá ser causado por um erro de digitação.</span><span class="sxs-lookup"><span data-stu-id="c5a67-181">If you experience an *InvalidRequestBody* or *MissingRequiredParameter* error, it might be caused by a typo.</span></span> <span data-ttu-id="c5a67-182">Revise a documentação da API e verifique se os parâmetros enviados correspondem ao exemplo relevante.</span><span class="sxs-lookup"><span data-stu-id="c5a67-182">Review the API documentation and check that the submitted parameters match the relevant example.</span></span>

## <a name="tracking-id"></a><span data-ttu-id="c5a67-183">ID de acompanhamento</span><span class="sxs-lookup"><span data-stu-id="c5a67-183">Tracking ID</span></span>

<span data-ttu-id="c5a67-184">Cada resposta de erro contém um parâmetro de ID exclusivo para controle.</span><span class="sxs-lookup"><span data-stu-id="c5a67-184">Each error response contains a unique ID parameter for tracking.</span></span> <span data-ttu-id="c5a67-185">O nome da propriedade desse parâmetro é *target*.</span><span class="sxs-lookup"><span data-stu-id="c5a67-185">The property name of this parameter is *target*.</span></span> <span data-ttu-id="c5a67-186">Ao entrar em contato conosco sobre um erro, a anexação dessa ID nos ajudará a encontrar a causa raiz do problema.</span><span class="sxs-lookup"><span data-stu-id="c5a67-186">When contacting us about an error, attaching this ID will help us find the root cause of the problem.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c5a67-187">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="c5a67-187">Related articles</span></span>

- [<span data-ttu-id="c5a67-188">Visão geral das APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="c5a67-188">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="c5a67-189">APIs com suporte do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c5a67-189">Supported Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="c5a67-190">Acessar as APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="c5a67-190">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c5a67-191">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="c5a67-191">Learn about API limits and licensing</span></span>](api-terms.md)
