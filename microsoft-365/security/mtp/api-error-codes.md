---
title: Códigos de erro da API REST de proteção de ameaças comuns da Microsoft
description: Saiba mais sobre os códigos de erro comuns da API REST de proteção contra ameaças da Microsoft
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
ms.openlocfilehash: 36a1cedacc5f16c422e2b0d458b0d1767cf08b64
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650125"
---
# <a name="common-microsoft-threat-protection-rest-api-error-codes"></a><span data-ttu-id="b2364-104">Códigos de erro da API REST de proteção de ameaças comuns da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b2364-104">Common Microsoft Threat Protection REST API error codes</span></span>

<span data-ttu-id="b2364-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b2364-105">**Applies to:**</span></span>
- <span data-ttu-id="b2364-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b2364-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="b2364-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="b2364-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b2364-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b2364-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b2364-109">Os códigos de erro listados na tabela a seguir podem ser retornados por uma operação em qualquer uma das APIs de proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b2364-109">The error codes listed in the following table may be returned by an operation on any of Microsoft Threat Protection APIs.</span></span>

<span data-ttu-id="b2364-110">Cada resposta de erro contém uma mensagem de erro, que pode ajudar a resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="b2364-110">Every error response contains an error message, which can help resolving the problem.</span></span>

<span data-ttu-id="b2364-111">A mensagem é um texto livre que pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="b2364-111">The message is a free text that can be changed.</span></span>

<span data-ttu-id="b2364-112">Na parte inferior da página, você pode encontrar exemplos de resposta.</span><span class="sxs-lookup"><span data-stu-id="b2364-112">At the bottom of the page, you can find response examples.</span></span>

<span data-ttu-id="b2364-113">Código de erro</span><span class="sxs-lookup"><span data-stu-id="b2364-113">Error code</span></span> |<span data-ttu-id="b2364-114">Código de status de HTTP</span><span class="sxs-lookup"><span data-stu-id="b2364-114">HTTP status code</span></span> |<span data-ttu-id="b2364-115">Mensagem</span><span class="sxs-lookup"><span data-stu-id="b2364-115">Message</span></span> 
:---|:---|:---
<span data-ttu-id="b2364-116">BadRequest</span><span class="sxs-lookup"><span data-stu-id="b2364-116">BadRequest</span></span> | <span data-ttu-id="b2364-117">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-117">BadRequest (400)</span></span> | <span data-ttu-id="b2364-118">Mensagem geral de erro de solicitação incorreta.</span><span class="sxs-lookup"><span data-stu-id="b2364-118">General Bad Request error message.</span></span>
<span data-ttu-id="b2364-119">ODataError</span><span class="sxs-lookup"><span data-stu-id="b2364-119">ODataError</span></span> | <span data-ttu-id="b2364-120">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-120">BadRequest (400)</span></span> | <span data-ttu-id="b2364-121">Consulta de URI de OData inválida (o erro específico foi especificado).</span><span class="sxs-lookup"><span data-stu-id="b2364-121">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="b2364-122">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="b2364-122">InvalidInput</span></span> | <span data-ttu-id="b2364-123">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-123">BadRequest (400)</span></span> | <span data-ttu-id="b2364-124">Entrada inválida {a entrada inválida}.</span><span class="sxs-lookup"><span data-stu-id="b2364-124">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="b2364-125">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="b2364-125">InvalidRequestBody</span></span> | <span data-ttu-id="b2364-126">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-126">BadRequest (400)</span></span> | <span data-ttu-id="b2364-127">Corpo de solicitação inválido.</span><span class="sxs-lookup"><span data-stu-id="b2364-127">Invalid request body.</span></span>
<span data-ttu-id="b2364-128">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="b2364-128">InvalidHashValue</span></span> | <span data-ttu-id="b2364-129">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-129">BadRequest (400)</span></span> | <span data-ttu-id="b2364-130">O valor de hash {o hash inválido} é inválido.</span><span class="sxs-lookup"><span data-stu-id="b2364-130">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="b2364-131">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="b2364-131">InvalidDomainName</span></span> | <span data-ttu-id="b2364-132">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-132">BadRequest (400)</span></span> | <span data-ttu-id="b2364-133">Nome do domínio {o domínio inválido} é inválido.</span><span class="sxs-lookup"><span data-stu-id="b2364-133">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="b2364-134">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="b2364-134">InvalidIpAddress</span></span> | <span data-ttu-id="b2364-135">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-135">BadRequest (400)</span></span> | <span data-ttu-id="b2364-136">Endereço IP {o IP inválido} é inválido.</span><span class="sxs-lookup"><span data-stu-id="b2364-136">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="b2364-137">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="b2364-137">InvalidUrl</span></span> | <span data-ttu-id="b2364-138">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-138">BadRequest (400)</span></span> | <span data-ttu-id="b2364-139">URL {a URL inválida} é inválida.</span><span class="sxs-lookup"><span data-stu-id="b2364-139">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="b2364-140">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="b2364-140">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="b2364-141">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-141">BadRequest (400)</span></span> | <span data-ttu-id="b2364-142">Tamanho máximo do lote excedido.</span><span class="sxs-lookup"><span data-stu-id="b2364-142">Maximum batch size exceeded.</span></span> <span data-ttu-id="b2364-143">Recebido: {tamanho do lote recebido}, permitido: {tamanho do lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="b2364-143">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="b2364-144">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="b2364-144">MissingRequiredParameter</span></span> | <span data-ttu-id="b2364-145">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-145">BadRequest (400)</span></span> | <span data-ttu-id="b2364-146">Parâmetro {o parâmetro ausente} está ausente.</span><span class="sxs-lookup"><span data-stu-id="b2364-146">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="b2364-147">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="b2364-147">OsPlatformNotSupported</span></span> | <span data-ttu-id="b2364-148">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-148">BadRequest (400)</span></span> | <span data-ttu-id="b2364-149">Plataforma do sistema operacional {a plataforma do sistema operacional do cliente não tem suporte para esta ação.</span><span class="sxs-lookup"><span data-stu-id="b2364-149">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="b2364-150">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="b2364-150">ClientVersionNotSupported</span></span> | <span data-ttu-id="b2364-151">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="b2364-151">BadRequest (400)</span></span> | <span data-ttu-id="b2364-152">{A ação solicitada} é suportada na versão do cliente {versão do cliente com suporte} e acima.</span><span class="sxs-lookup"><span data-stu-id="b2364-152">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="b2364-153">Não Autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="b2364-153">Unauthorized</span></span> | <span data-ttu-id="b2364-154">Não autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="b2364-154">Unauthorized (401)</span></span> | <span data-ttu-id="b2364-155">Não autorizado (cabeçalho de autorização geralmente inválido ou expirado).</span><span class="sxs-lookup"><span data-stu-id="b2364-155">Unauthorized (usually invalid or expired authorization header).</span></span>
<span data-ttu-id="b2364-156">Proibido</span><span class="sxs-lookup"><span data-stu-id="b2364-156">Forbidden</span></span> | <span data-ttu-id="b2364-157">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="b2364-157">Forbidden (403)</span></span> | <span data-ttu-id="b2364-158">Proibido (token válido, mas permissão insuficiente para a ação).</span><span class="sxs-lookup"><span data-stu-id="b2364-158">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="b2364-159">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="b2364-159">DisabledFeature</span></span> | <span data-ttu-id="b2364-160">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="b2364-160">Forbidden (403)</span></span> | <span data-ttu-id="b2364-161">O recurso de locatário não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b2364-161">Tenant feature is not enabled.</span></span>
<span data-ttu-id="b2364-162">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="b2364-162">DisallowedOperation</span></span> | <span data-ttu-id="b2364-163">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="b2364-163">Forbidden (403)</span></span> | <span data-ttu-id="b2364-164">{a operação não permitido e o motivo}.</span><span class="sxs-lookup"><span data-stu-id="b2364-164">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="b2364-165">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="b2364-165">NotFound</span></span> | <span data-ttu-id="b2364-166">Não encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="b2364-166">Not Found (404)</span></span> | <span data-ttu-id="b2364-167">Mensagem de erro geral não encontrado.</span><span class="sxs-lookup"><span data-stu-id="b2364-167">General Not Found error message.</span></span>
<span data-ttu-id="b2364-168">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="b2364-168">ResourceNotFound</span></span> | <span data-ttu-id="b2364-169">Não encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="b2364-169">Not Found (404)</span></span> | <span data-ttu-id="b2364-170">Recurso {o recurso solicitado} não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="b2364-170">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="b2364-171">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="b2364-171">InternalServerError</span></span> | <span data-ttu-id="b2364-172">Erro interno do servidor (500)</span><span class="sxs-lookup"><span data-stu-id="b2364-172">Internal Server Error (500)</span></span> | <span data-ttu-id="b2364-173">(Sem mensagem de erro, repita a operação ou fale conosco se não for resolvido)</span><span class="sxs-lookup"><span data-stu-id="b2364-173">(No error message,  retry the operation or contact us if it does not get resolved)</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="b2364-174">Os parâmetros de corpo diferenciam maiúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="b2364-174">Body parameters are case-sensitive</span></span>

<span data-ttu-id="b2364-175">Os parâmetros de corpo enviados diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b2364-175">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="b2364-176">Se você tiver erros de **InvalidRequestBody** ou **MissingRequiredParameter** , ele poderá ser causado por uma letra maiúscula ou minúscula de parâmetro incorreto.</span><span class="sxs-lookup"><span data-stu-id="b2364-176">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="b2364-177">Recomendamos que você revise a página de documentação da API e verifique se os parâmetros enviados correspondem ao exemplo relevante.</span><span class="sxs-lookup"><span data-stu-id="b2364-177">We recommend that you review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="b2364-178">ID de solicitação de correlação</span><span class="sxs-lookup"><span data-stu-id="b2364-178">Correlation request ID</span></span>

<span data-ttu-id="b2364-179">Cada resposta de erro contém um parâmetro de ID exclusivo para controle.</span><span class="sxs-lookup"><span data-stu-id="b2364-179">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="b2364-180">O nome da propriedade desse parâmetro é "target".</span><span class="sxs-lookup"><span data-stu-id="b2364-180">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="b2364-181">Ao entrar em contato conosco sobre um erro, a anexação dessa ID ajudará a encontrar a causa raiz do problema.</span><span class="sxs-lookup"><span data-stu-id="b2364-181">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="b2364-182">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b2364-182">Examples</span></span>

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

