---
title: BatchDelete
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Use a API REST para remover um modelo de compreensão de documentos aplicado de uma ou mais bibliotecas.
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177232"
---
# <a name="batchdelete"></a><span data-ttu-id="8af3d-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="8af3d-103">BatchDelete</span></span>

<span data-ttu-id="8af3d-104">Remove um modelo de compreensão de documentos aplicado de uma ou mais bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="8af3d-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="8af3d-105">Observe que um modelo deve ser removido de todas as bibliotecas antes de poder ser excluído (consulte [exemplo](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="8af3d-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="8af3d-106">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="8af3d-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="8af3d-107">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="8af3d-107">URI parameters</span></span>

<span data-ttu-id="8af3d-108">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8af3d-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="8af3d-109">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="8af3d-109">Request headers</span></span>

| <span data-ttu-id="8af3d-110">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="8af3d-110">Header</span></span> | <span data-ttu-id="8af3d-111">Valor</span><span class="sxs-lookup"><span data-stu-id="8af3d-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="8af3d-112">Aceitar</span><span class="sxs-lookup"><span data-stu-id="8af3d-112">Accept</span></span>|<span data-ttu-id="8af3d-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="8af3d-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="8af3d-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8af3d-114">Content-Type</span></span>|<span data-ttu-id="8af3d-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="8af3d-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="8af3d-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="8af3d-116">x-requestdigest</span></span>|<span data-ttu-id="8af3d-117">O resumo apropriado para o site atual.</span><span class="sxs-lookup"><span data-stu-id="8af3d-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="8af3d-118">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="8af3d-118">Request body</span></span>

| <span data-ttu-id="8af3d-119">Nome</span><span class="sxs-lookup"><span data-stu-id="8af3d-119">Name</span></span> | <span data-ttu-id="8af3d-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8af3d-120">Required</span></span> | <span data-ttu-id="8af3d-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="8af3d-121">Type</span></span> | <span data-ttu-id="8af3d-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="8af3d-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="8af3d-123">Publicações</span><span class="sxs-lookup"><span data-stu-id="8af3d-123">Publications</span></span>|<span data-ttu-id="8af3d-124">sim</span><span class="sxs-lookup"><span data-stu-id="8af3d-124">yes</span></span>|<span data-ttu-id="8af3d-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="8af3d-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="8af3d-126">A coleção do MachineLearningPublicationEntityData de cada um deles especifica o modelo e a biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="8af3d-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="8af3d-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="8af3d-127">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="8af3d-128">Nome</span><span class="sxs-lookup"><span data-stu-id="8af3d-128">Name</span></span> | <span data-ttu-id="8af3d-129">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8af3d-129">Required</span></span> | <span data-ttu-id="8af3d-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="8af3d-130">Type</span></span> | <span data-ttu-id="8af3d-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="8af3d-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="8af3d-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="8af3d-132">ModelUniqueId</span></span>|<span data-ttu-id="8af3d-133">sim</span><span class="sxs-lookup"><span data-stu-id="8af3d-133">yes</span></span>|<span data-ttu-id="8af3d-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8af3d-134">string</span></span>|<span data-ttu-id="8af3d-135">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="8af3d-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="8af3d-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="8af3d-136">TargetSiteUrl</span></span>|<span data-ttu-id="8af3d-137">sim</span><span class="sxs-lookup"><span data-stu-id="8af3d-137">yes</span></span>|<span data-ttu-id="8af3d-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8af3d-138">string</span></span>|<span data-ttu-id="8af3d-139">A URL completa do site da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="8af3d-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="8af3d-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="8af3d-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="8af3d-141">sim</span><span class="sxs-lookup"><span data-stu-id="8af3d-141">yes</span></span>|<span data-ttu-id="8af3d-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8af3d-142">string</span></span>|<span data-ttu-id="8af3d-143">A URL relativa do servidor da web para a biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="8af3d-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="8af3d-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="8af3d-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="8af3d-145">sim</span><span class="sxs-lookup"><span data-stu-id="8af3d-145">yes</span></span>|<span data-ttu-id="8af3d-146">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8af3d-146">string</span></span>|<span data-ttu-id="8af3d-147">A URL relativa do servidor da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="8af3d-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="8af3d-148">Resposta</span><span class="sxs-lookup"><span data-stu-id="8af3d-148">Response</span></span>

| <span data-ttu-id="8af3d-149">Nome</span><span class="sxs-lookup"><span data-stu-id="8af3d-149">Name</span></span>   | <span data-ttu-id="8af3d-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="8af3d-150">Type</span></span>  | <span data-ttu-id="8af3d-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="8af3d-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="8af3d-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="8af3d-152">200 OK</span></span>||<span data-ttu-id="8af3d-153">Esta é uma API personalizada para dar suporte à remoção de um modelo de bibliotecas de documentos múltiplos.</span><span class="sxs-lookup"><span data-stu-id="8af3d-153">This is a customized API to support removing a model from multi document libraries.</span></span> <span data-ttu-id="8af3d-154">No caso de êxito parcial, ainda é possível retornar 200 OK e o chamador precisa inspecionar o corpo da resposta para entender se o modelo foi removido com êxito de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="8af3d-154">In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="8af3d-155">Corpo da resposta</span><span class="sxs-lookup"><span data-stu-id="8af3d-155">Response Body</span></span>
| <span data-ttu-id="8af3d-156">Nome</span><span class="sxs-lookup"><span data-stu-id="8af3d-156">Name</span></span>   | <span data-ttu-id="8af3d-157">Tipo</span><span class="sxs-lookup"><span data-stu-id="8af3d-157">Type</span></span>  | <span data-ttu-id="8af3d-158">Descrição</span><span class="sxs-lookup"><span data-stu-id="8af3d-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="8af3d-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="8af3d-159">TotalSuccesses</span></span>|<span data-ttu-id="8af3d-160">int</span><span class="sxs-lookup"><span data-stu-id="8af3d-160">int</span></span>|<span data-ttu-id="8af3d-161">O número total de um modelo que está sendo removido com êxito de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="8af3d-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="8af3d-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="8af3d-162">TotalFailures</span></span>|<span data-ttu-id="8af3d-163">int</span><span class="sxs-lookup"><span data-stu-id="8af3d-163">int</span></span>|<span data-ttu-id="8af3d-164">O número total de um modelo que não foi removido de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="8af3d-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="8af3d-165">Detalhes</span><span class="sxs-lookup"><span data-stu-id="8af3d-165">Details</span></span>|<span data-ttu-id="8af3d-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="8af3d-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="8af3d-167">A coleção do MachineLearningPublicationResult de cada um deles especifica o resultado detalhado da remoção do modelo de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="8af3d-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="8af3d-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="8af3d-168">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="8af3d-169">Nome</span><span class="sxs-lookup"><span data-stu-id="8af3d-169">Name</span></span>   | <span data-ttu-id="8af3d-170">Tipo</span><span class="sxs-lookup"><span data-stu-id="8af3d-170">Type</span></span>  | <span data-ttu-id="8af3d-171">Descrição</span><span class="sxs-lookup"><span data-stu-id="8af3d-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="8af3d-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="8af3d-172">StatusCode</span></span>|<span data-ttu-id="8af3d-173">int</span><span class="sxs-lookup"><span data-stu-id="8af3d-173">int</span></span>|<span data-ttu-id="8af3d-174">O código de status HTTP.</span><span class="sxs-lookup"><span data-stu-id="8af3d-174">The HTTP status code.</span></span>|
|<span data-ttu-id="8af3d-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="8af3d-175">ErrorMessage</span></span>|<span data-ttu-id="8af3d-176">string</span><span class="sxs-lookup"><span data-stu-id="8af3d-176">string</span></span>|<span data-ttu-id="8af3d-177">A mensagem de erro que informa o que há de errado ao aplicar o modelo à biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="8af3d-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="8af3d-178">Publicação</span><span class="sxs-lookup"><span data-stu-id="8af3d-178">Publication</span></span>|<span data-ttu-id="8af3d-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="8af3d-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="8af3d-180">Especifica as informações do modelo e a biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="8af3d-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="8af3d-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="8af3d-181">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="8af3d-182">Nome</span><span class="sxs-lookup"><span data-stu-id="8af3d-182">Name</span></span> | <span data-ttu-id="8af3d-183">Tipo</span><span class="sxs-lookup"><span data-stu-id="8af3d-183">Type</span></span> | <span data-ttu-id="8af3d-184">Descrição</span><span class="sxs-lookup"><span data-stu-id="8af3d-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="8af3d-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="8af3d-185">ModelUniqueId</span></span>|<span data-ttu-id="8af3d-186">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8af3d-186">string</span></span>|<span data-ttu-id="8af3d-187">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="8af3d-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="8af3d-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="8af3d-188">TargetSiteUrl</span></span>|<span data-ttu-id="8af3d-189">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8af3d-189">string</span></span>|<span data-ttu-id="8af3d-190">A URL completa do site da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="8af3d-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="8af3d-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="8af3d-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="8af3d-192">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8af3d-192">string</span></span>|<span data-ttu-id="8af3d-193">A URL relativa do servidor da web para a biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="8af3d-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="8af3d-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="8af3d-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="8af3d-195">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8af3d-195">string</span></span>|<span data-ttu-id="8af3d-196">A URL relativa do servidor da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="8af3d-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="8af3d-197">Exemplos</span><span class="sxs-lookup"><span data-stu-id="8af3d-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="8af3d-198">Remover um modelo da biblioteca de documentos de contratos no site de repositório</span><span class="sxs-lookup"><span data-stu-id="8af3d-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="8af3d-199">Nesse exemplo, a ID do modelo de compreensão de documentos do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="8af3d-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="8af3d-200">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="8af3d-200">Sample request</span></span>

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a><span data-ttu-id="8af3d-201">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="8af3d-201">Sample response</span></span>

<span data-ttu-id="8af3d-202">Na resposta, TotalFailures e TotalSuccesses se referem ao número de falhas e sucessos do modelo que está sendo removido das bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="8af3d-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="8af3d-203">**Código de status:** 200</span><span class="sxs-lookup"><span data-stu-id="8af3d-203">**Status code:** 200</span></span>

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="8af3d-204">Confira também</span><span class="sxs-lookup"><span data-stu-id="8af3d-204">See also</span></span>

[<span data-ttu-id="8af3d-205">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="8af3d-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
