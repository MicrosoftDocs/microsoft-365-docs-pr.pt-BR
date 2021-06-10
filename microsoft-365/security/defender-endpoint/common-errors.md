---
title: Erros comuns da API do Microsoft Defender para Ponto de Extremidade
description: Lista de erros comuns da API do Microsoft Defender para Ponto de Extremidade com descrições.
keywords: APIs, API do Microsoft Defender para Ponto de Extremidade, erros, solução de problemas
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
ms.openlocfilehash: c2e52b7074dcd15e7f6852a11ccb7793572cd9b5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771004"
---
# <a name="common-rest-api-error-codes"></a><span data-ttu-id="8135a-104">Códigos de erro comuns da API REST</span><span class="sxs-lookup"><span data-stu-id="8135a-104">Common REST API error codes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* <span data-ttu-id="8135a-105">Os códigos de erro listados na tabela a seguir podem ser retornados por uma operação em qualquer uma das APIs do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="8135a-105">The error codes listed in the following table may be returned by an operation on any of Microsoft Defender for Endpoint APIs.</span></span>
* <span data-ttu-id="8135a-106">Além do código de erro, cada resposta de erro contém uma mensagem de erro, que pode ajudar a resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="8135a-106">In addition to the error code, every error response contains an error message, which can help resolve the problem.</span></span>
* <span data-ttu-id="8135a-107">A mensagem é um texto livre que pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="8135a-107">The message is a free text that can be changed.</span></span>
* <span data-ttu-id="8135a-108">Na parte inferior da página, você pode encontrar exemplos de resposta.</span><span class="sxs-lookup"><span data-stu-id="8135a-108">At the bottom of the page, you can find response examples.</span></span>

><span data-ttu-id="8135a-109">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8135a-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8135a-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8135a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8135a-111">Código de erro</span><span class="sxs-lookup"><span data-stu-id="8135a-111">Error code</span></span> |<span data-ttu-id="8135a-112">Código de status de HTTP</span><span class="sxs-lookup"><span data-stu-id="8135a-112">HTTP status code</span></span> |<span data-ttu-id="8135a-113">Mensagem</span><span class="sxs-lookup"><span data-stu-id="8135a-113">Message</span></span> 
:---|:---|:---
<span data-ttu-id="8135a-114">BadRequest</span><span class="sxs-lookup"><span data-stu-id="8135a-114">BadRequest</span></span> | <span data-ttu-id="8135a-115">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-115">BadRequest (400)</span></span> | <span data-ttu-id="8135a-116">Mensagem de erro de Solicitação Geral de Erro.</span><span class="sxs-lookup"><span data-stu-id="8135a-116">General Bad Request error message.</span></span>
<span data-ttu-id="8135a-117">ODataError</span><span class="sxs-lookup"><span data-stu-id="8135a-117">ODataError</span></span> | <span data-ttu-id="8135a-118">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-118">BadRequest (400)</span></span> | <span data-ttu-id="8135a-119">Consulta OData URI inválida (o erro específico é especificado).</span><span class="sxs-lookup"><span data-stu-id="8135a-119">Invalid OData URI query (the specific error is specified).</span></span>
<span data-ttu-id="8135a-120">InvalidInput</span><span class="sxs-lookup"><span data-stu-id="8135a-120">InvalidInput</span></span> | <span data-ttu-id="8135a-121">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-121">BadRequest (400)</span></span> | <span data-ttu-id="8135a-122">Entrada inválida {a entrada inválida}.</span><span class="sxs-lookup"><span data-stu-id="8135a-122">Invalid input {the invalid input}.</span></span>
<span data-ttu-id="8135a-123">InvalidRequestBody</span><span class="sxs-lookup"><span data-stu-id="8135a-123">InvalidRequestBody</span></span> | <span data-ttu-id="8135a-124">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-124">BadRequest (400)</span></span> | <span data-ttu-id="8135a-125">Corpo da solicitação inválido.</span><span class="sxs-lookup"><span data-stu-id="8135a-125">Invalid request body.</span></span>
<span data-ttu-id="8135a-126">InvalidHashValue</span><span class="sxs-lookup"><span data-stu-id="8135a-126">InvalidHashValue</span></span> | <span data-ttu-id="8135a-127">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-127">BadRequest (400)</span></span> | <span data-ttu-id="8135a-128">O valor de hash {o hash inválido} é inválido.</span><span class="sxs-lookup"><span data-stu-id="8135a-128">Hash value {the invalid hash} is invalid.</span></span>
<span data-ttu-id="8135a-129">InvalidDomainName</span><span class="sxs-lookup"><span data-stu-id="8135a-129">InvalidDomainName</span></span> | <span data-ttu-id="8135a-130">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-130">BadRequest (400)</span></span> | <span data-ttu-id="8135a-131">O nome de domínio {o domínio inválido} é inválido.</span><span class="sxs-lookup"><span data-stu-id="8135a-131">Domain name {the invalid domain} is invalid.</span></span>
<span data-ttu-id="8135a-132">InvalidIpAddress</span><span class="sxs-lookup"><span data-stu-id="8135a-132">InvalidIpAddress</span></span> | <span data-ttu-id="8135a-133">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-133">BadRequest (400)</span></span> | <span data-ttu-id="8135a-134">O endereço IP {o IP inválido} é inválido.</span><span class="sxs-lookup"><span data-stu-id="8135a-134">IP address {the invalid IP} is invalid.</span></span>
<span data-ttu-id="8135a-135">InvalidUrl</span><span class="sxs-lookup"><span data-stu-id="8135a-135">InvalidUrl</span></span> | <span data-ttu-id="8135a-136">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-136">BadRequest (400)</span></span> | <span data-ttu-id="8135a-137">URL {a URL inválida} é inválida.</span><span class="sxs-lookup"><span data-stu-id="8135a-137">URL {the invalid URL} is invalid.</span></span>
<span data-ttu-id="8135a-138">MaximumBatchSizeExceeded</span><span class="sxs-lookup"><span data-stu-id="8135a-138">MaximumBatchSizeExceeded</span></span> | <span data-ttu-id="8135a-139">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-139">BadRequest (400)</span></span> | <span data-ttu-id="8135a-140">Tamanho máximo do lote excedido.</span><span class="sxs-lookup"><span data-stu-id="8135a-140">Maximum batch size exceeded.</span></span> <span data-ttu-id="8135a-141">Recebido: {tamanho do lote recebido}, permitido: {tamanho do lote permitido}.</span><span class="sxs-lookup"><span data-stu-id="8135a-141">Received: {batch size received}, allowed: {batch size allowed}.</span></span>
<span data-ttu-id="8135a-142">MissingRequiredParameter</span><span class="sxs-lookup"><span data-stu-id="8135a-142">MissingRequiredParameter</span></span> | <span data-ttu-id="8135a-143">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-143">BadRequest (400)</span></span> | <span data-ttu-id="8135a-144">O parâmetro {o parâmetro ausente} está ausente.</span><span class="sxs-lookup"><span data-stu-id="8135a-144">Parameter {the missing parameter} is missing.</span></span>
<span data-ttu-id="8135a-145">OsPlatformNotSupported</span><span class="sxs-lookup"><span data-stu-id="8135a-145">OsPlatformNotSupported</span></span> | <span data-ttu-id="8135a-146">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-146">BadRequest (400)</span></span> | <span data-ttu-id="8135a-147">A plataforma do sistema operacional {a Plataforma do sistema operacional do cliente} não é suportada para essa ação.</span><span class="sxs-lookup"><span data-stu-id="8135a-147">OS Platform {the client OS Platform} is not supported for this action.</span></span>
<span data-ttu-id="8135a-148">ClientVersionNotSupported</span><span class="sxs-lookup"><span data-stu-id="8135a-148">ClientVersionNotSupported</span></span> | <span data-ttu-id="8135a-149">BadRequest (400)</span><span class="sxs-lookup"><span data-stu-id="8135a-149">BadRequest (400)</span></span> | <span data-ttu-id="8135a-150">{A ação solicitada} é suportada na versão do cliente {versão do cliente suportada} e acima.</span><span class="sxs-lookup"><span data-stu-id="8135a-150">{The requested action} is supported on client version {supported client version} and above.</span></span>
<span data-ttu-id="8135a-151">Não Autorizado (Unauthorized)</span><span class="sxs-lookup"><span data-stu-id="8135a-151">Unauthorized</span></span> | <span data-ttu-id="8135a-152">Não autorizado (401)</span><span class="sxs-lookup"><span data-stu-id="8135a-152">Unauthorized (401)</span></span> | <span data-ttu-id="8135a-153">Não autorizado (header de autorização inválido ou expirado).</span><span class="sxs-lookup"><span data-stu-id="8135a-153">Unauthorized (invalid or expired authorization header).</span></span>
<span data-ttu-id="8135a-154">Proibido</span><span class="sxs-lookup"><span data-stu-id="8135a-154">Forbidden</span></span> | <span data-ttu-id="8135a-155">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="8135a-155">Forbidden (403)</span></span> | <span data-ttu-id="8135a-156">Proibido (token válido, mas permissão insuficiente para a ação).</span><span class="sxs-lookup"><span data-stu-id="8135a-156">Forbidden (valid token but insufficient permission for the action).</span></span>
<span data-ttu-id="8135a-157">DisabledFeature</span><span class="sxs-lookup"><span data-stu-id="8135a-157">DisabledFeature</span></span> | <span data-ttu-id="8135a-158">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="8135a-158">Forbidden (403)</span></span> | <span data-ttu-id="8135a-159">O recurso locatário não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="8135a-159">Tenant feature is not enabled.</span></span>
<span data-ttu-id="8135a-160">DisallowedOperation</span><span class="sxs-lookup"><span data-stu-id="8135a-160">DisallowedOperation</span></span> | <span data-ttu-id="8135a-161">Proibido (403)</span><span class="sxs-lookup"><span data-stu-id="8135a-161">Forbidden (403)</span></span> | <span data-ttu-id="8135a-162">{a operação não permitido e o motivo}.</span><span class="sxs-lookup"><span data-stu-id="8135a-162">{the disallowed operation and the reason}.</span></span>
<span data-ttu-id="8135a-163">NotFound</span><span class="sxs-lookup"><span data-stu-id="8135a-163">NotFound</span></span> | <span data-ttu-id="8135a-164">Não encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="8135a-164">Not Found (404)</span></span> | <span data-ttu-id="8135a-165">Mensagem de erro Geral Não Encontrada.</span><span class="sxs-lookup"><span data-stu-id="8135a-165">General Not Found error message.</span></span>
<span data-ttu-id="8135a-166">ResourceNotFound</span><span class="sxs-lookup"><span data-stu-id="8135a-166">ResourceNotFound</span></span> | <span data-ttu-id="8135a-167">Não encontrado (404)</span><span class="sxs-lookup"><span data-stu-id="8135a-167">Not Found (404)</span></span> | <span data-ttu-id="8135a-168">O recurso {o recurso solicitado} não foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="8135a-168">Resource {the requested resource} was not found.</span></span>
<span data-ttu-id="8135a-169">InternalServerError</span><span class="sxs-lookup"><span data-stu-id="8135a-169">InternalServerError</span></span> | <span data-ttu-id="8135a-170">Erro interno do servidor (500)</span><span class="sxs-lookup"><span data-stu-id="8135a-170">Internal Server Error (500)</span></span> | <span data-ttu-id="8135a-171">(Nenhuma mensagem de erro, repetir a operação)</span><span class="sxs-lookup"><span data-stu-id="8135a-171">(No error message, retry the operation)</span></span>
<span data-ttu-id="8135a-172">TooManyRequests</span><span class="sxs-lookup"><span data-stu-id="8135a-172">TooManyRequests</span></span> | <span data-ttu-id="8135a-173">Solicitações demais (429)</span><span class="sxs-lookup"><span data-stu-id="8135a-173">Too Many Requests (429)</span></span> | <span data-ttu-id="8135a-174">A resposta representará atingir o limite de cota por número de solicitações ou pela CPU.</span><span class="sxs-lookup"><span data-stu-id="8135a-174">Response will represent reaching quota limit either by number of requests or by CPU.</span></span>

## <a name="body-parameters-are-case-sensitive"></a><span data-ttu-id="8135a-175">Os parâmetros body são sensíveis a minúsculas</span><span class="sxs-lookup"><span data-stu-id="8135a-175">Body parameters are case-sensitive</span></span>

<span data-ttu-id="8135a-176">No momento, os parâmetros do corpo enviado são sensíveis a minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8135a-176">The submitted body parameters are currently case-sensitive.</span></span>
<br><span data-ttu-id="8135a-177">Se você experimentar um **erro InvalidRequestBody** ou **MissingRequiredParameter,** ele pode ser causado por uma maiúscula de parâmetro errada ou letra de maiúsculas e maiúsculas de maiúsculas e baixos.</span><span class="sxs-lookup"><span data-stu-id="8135a-177">If you experience an **InvalidRequestBody** or **MissingRequiredParameter** errors, it might be caused from a wrong parameter capital or lower-case letter.</span></span>
<br><span data-ttu-id="8135a-178">Revise a página de documentação da API e verifique se os parâmetros enviados corresponderão ao exemplo relevante.</span><span class="sxs-lookup"><span data-stu-id="8135a-178">Review the API documentation page and check that the submitted parameters match the relevant example.</span></span>

## <a name="correlation-request-id"></a><span data-ttu-id="8135a-179">ID da solicitação de correlação</span><span class="sxs-lookup"><span data-stu-id="8135a-179">Correlation request ID</span></span>

<span data-ttu-id="8135a-180">Cada resposta de erro contém um parâmetro de ID exclusivo para rastreamento.</span><span class="sxs-lookup"><span data-stu-id="8135a-180">Each error response contains a unique ID parameter for tracking.</span></span>
<br><span data-ttu-id="8135a-181">O nome da propriedade desse parâmetro é "target".</span><span class="sxs-lookup"><span data-stu-id="8135a-181">The property name of this parameter is "target".</span></span>
<br><span data-ttu-id="8135a-182">Ao entrar em contato conosco sobre um erro, anexar essa ID ajudará a encontrar a causa raiz do problema.</span><span class="sxs-lookup"><span data-stu-id="8135a-182">When contacting us about an error, attaching this ID will help find the root cause of the problem.</span></span>

## <a name="examples"></a><span data-ttu-id="8135a-183">Exemplos</span><span class="sxs-lookup"><span data-stu-id="8135a-183">Examples</span></span>

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
