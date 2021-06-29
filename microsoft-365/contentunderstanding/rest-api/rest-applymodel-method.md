---
title: Modelo de aplicação em lote
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
description: Use a API REST para aplicar um modelo de compreensão de documento a uma ou mais bibliotecas.
ms.openlocfilehash: 24ea9a480bc3ce5a7745857de17a6fab6ed97685
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177256"
---
# <a name="batch-apply-model"></a><span data-ttu-id="3b96c-103">Modelo de Aplicação em lote</span><span class="sxs-lookup"><span data-stu-id="3b96c-103">Batch Apply model</span></span>

<span data-ttu-id="3b96c-104">Aplica (ou sincroniza) um modelo treinado de compreensão de documento a uma ou mais bibliotecas (consulte o [exemplo](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="3b96c-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="3b96c-105">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="3b96c-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="3b96c-106">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="3b96c-106">URI parameters</span></span>

<span data-ttu-id="3b96c-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="3b96c-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="3b96c-108">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="3b96c-108">Request headers</span></span>

| <span data-ttu-id="3b96c-109">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="3b96c-109">Header</span></span> | <span data-ttu-id="3b96c-110">Valor</span><span class="sxs-lookup"><span data-stu-id="3b96c-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="3b96c-111">Aceitar</span><span class="sxs-lookup"><span data-stu-id="3b96c-111">Accept</span></span>|<span data-ttu-id="3b96c-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="3b96c-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="3b96c-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3b96c-113">Content-Type</span></span>|<span data-ttu-id="3b96c-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="3b96c-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="3b96c-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="3b96c-115">x-requestdigest</span></span>|<span data-ttu-id="3b96c-116">O resumo apropriado para o site atual.</span><span class="sxs-lookup"><span data-stu-id="3b96c-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="3b96c-117">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="3b96c-117">Request body</span></span>

| <span data-ttu-id="3b96c-118">Nome</span><span class="sxs-lookup"><span data-stu-id="3b96c-118">Name</span></span> | <span data-ttu-id="3b96c-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="3b96c-119">Required</span></span> | <span data-ttu-id="3b96c-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="3b96c-120">Type</span></span> | <span data-ttu-id="3b96c-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b96c-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="3b96c-122">__metadata</span><span class="sxs-lookup"><span data-stu-id="3b96c-122">__metadata</span></span>|<span data-ttu-id="3b96c-123">sim</span><span class="sxs-lookup"><span data-stu-id="3b96c-123">yes</span></span>|<span data-ttu-id="3b96c-124">string</span><span class="sxs-lookup"><span data-stu-id="3b96c-124">string</span></span>|<span data-ttu-id="3b96c-125">Definir o metadado do objeto no SPO.</span><span class="sxs-lookup"><span data-stu-id="3b96c-125">Set the object meta on the SPO.</span></span> <span data-ttu-id="3b96c-126">Sempre use o valor: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="3b96c-126">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.</span></span>|
|<span data-ttu-id="3b96c-127">Publicações</span><span class="sxs-lookup"><span data-stu-id="3b96c-127">Publications</span></span>|<span data-ttu-id="3b96c-128">sim</span><span class="sxs-lookup"><span data-stu-id="3b96c-128">yes</span></span>|<span data-ttu-id="3b96c-129">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="3b96c-129">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="3b96c-130">A coleção do MachineLearningPublicationEntityData de cada um deles especifica o modelo e a biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="3b96c-130">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="3b96c-131">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="3b96c-131">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="3b96c-132">Nome</span><span class="sxs-lookup"><span data-stu-id="3b96c-132">Name</span></span> | <span data-ttu-id="3b96c-133">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="3b96c-133">Required</span></span> | <span data-ttu-id="3b96c-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="3b96c-134">Type</span></span> | <span data-ttu-id="3b96c-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b96c-135">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="3b96c-136">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="3b96c-136">ModelUniqueId</span></span>|<span data-ttu-id="3b96c-137">sim</span><span class="sxs-lookup"><span data-stu-id="3b96c-137">yes</span></span>|<span data-ttu-id="3b96c-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3b96c-138">string</span></span>|<span data-ttu-id="3b96c-139">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="3b96c-139">The unique ID of the model file.</span></span>|
|<span data-ttu-id="3b96c-140">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="3b96c-140">TargetSiteUrl</span></span>|<span data-ttu-id="3b96c-141">sim</span><span class="sxs-lookup"><span data-stu-id="3b96c-141">yes</span></span>|<span data-ttu-id="3b96c-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3b96c-142">string</span></span>|<span data-ttu-id="3b96c-143">A URL completa do site da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="3b96c-143">The full URL of the target library site.</span></span>|
|<span data-ttu-id="3b96c-144">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="3b96c-144">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="3b96c-145">sim</span><span class="sxs-lookup"><span data-stu-id="3b96c-145">yes</span></span>|<span data-ttu-id="3b96c-146">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3b96c-146">string</span></span>|<span data-ttu-id="3b96c-147">A URL relativa do servidor da web para a biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="3b96c-147">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="3b96c-148">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="3b96c-148">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="3b96c-149">sim</span><span class="sxs-lookup"><span data-stu-id="3b96c-149">yes</span></span>|<span data-ttu-id="3b96c-150">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3b96c-150">string</span></span>|<span data-ttu-id="3b96c-151">A URL relativa do servidor da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="3b96c-151">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="3b96c-152">ViewOption</span><span class="sxs-lookup"><span data-stu-id="3b96c-152">ViewOption</span></span>|<span data-ttu-id="3b96c-153">não</span><span class="sxs-lookup"><span data-stu-id="3b96c-153">no</span></span>|<span data-ttu-id="3b96c-154">string</span><span class="sxs-lookup"><span data-stu-id="3b96c-154">string</span></span>|<span data-ttu-id="3b96c-155">Especifica se o novo modo de exibição de modelo deve ser definido como o padrão da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="3b96c-155">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="3b96c-156">Resposta</span><span class="sxs-lookup"><span data-stu-id="3b96c-156">Response</span></span>

| <span data-ttu-id="3b96c-157">Nome</span><span class="sxs-lookup"><span data-stu-id="3b96c-157">Name</span></span>   | <span data-ttu-id="3b96c-158">Tipo</span><span class="sxs-lookup"><span data-stu-id="3b96c-158">Type</span></span>  | <span data-ttu-id="3b96c-159">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b96c-159">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="3b96c-160">201 Criado</span><span class="sxs-lookup"><span data-stu-id="3b96c-160">201 Created</span></span>||<span data-ttu-id="3b96c-161">Esta é uma API personalizada para dar suporte à aplicação de um modelo a bibliotecas de documentos múltiplos.</span><span class="sxs-lookup"><span data-stu-id="3b96c-161">This is a customized API to support applying a model to multi document libraries.</span></span> <span data-ttu-id="3b96c-162">No caso de êxito parcial, ainda é possível retornar 201 criado e o chamador precisa inspecionar o corpo da resposta para entender se o modelo foi aplicado com êxito de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="3b96c-162">In the case of partial success, 201 created could still be returned and the caller needs to inspect the response body to understand if the model has been successfully applied to a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="3b96c-163">Corpo da resposta</span><span class="sxs-lookup"><span data-stu-id="3b96c-163">Response Body</span></span>
| <span data-ttu-id="3b96c-164">Nome</span><span class="sxs-lookup"><span data-stu-id="3b96c-164">Name</span></span>   | <span data-ttu-id="3b96c-165">Tipo</span><span class="sxs-lookup"><span data-stu-id="3b96c-165">Type</span></span>  | <span data-ttu-id="3b96c-166">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b96c-166">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="3b96c-167">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="3b96c-167">TotalSuccesses</span></span>|<span data-ttu-id="3b96c-168">int</span><span class="sxs-lookup"><span data-stu-id="3b96c-168">int</span></span>|<span data-ttu-id="3b96c-169">O número total de um modelo que está sendo aplicado com êxito de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="3b96c-169">The total number of a model being successfully applied to a document library.</span></span>|
|<span data-ttu-id="3b96c-170">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="3b96c-170">TotalFailures</span></span>|<span data-ttu-id="3b96c-171">int</span><span class="sxs-lookup"><span data-stu-id="3b96c-171">int</span></span>|<span data-ttu-id="3b96c-172">O número total de um modelo que não foi aplicado a uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="3b96c-172">The total number of a model failing to be applied to a document library.</span></span>|
|<span data-ttu-id="3b96c-173">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3b96c-173">Details</span></span>|<span data-ttu-id="3b96c-174">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="3b96c-174">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="3b96c-175">A coleção do MachineLearningPublicationResult de cada um deles especifica o resultado detalhado da aplicação do modelo à uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="3b96c-175">The collection of MachineLearningPublicationResult each of which specifies the detailed result of applying the model to the document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="3b96c-176">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="3b96c-176">MachineLearningPublicationResult</span></span>
| <span data-ttu-id="3b96c-177">Nome</span><span class="sxs-lookup"><span data-stu-id="3b96c-177">Name</span></span>   | <span data-ttu-id="3b96c-178">Tipo</span><span class="sxs-lookup"><span data-stu-id="3b96c-178">Type</span></span>  | <span data-ttu-id="3b96c-179">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b96c-179">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="3b96c-180">StatusCode</span><span class="sxs-lookup"><span data-stu-id="3b96c-180">StatusCode</span></span>|<span data-ttu-id="3b96c-181">int</span><span class="sxs-lookup"><span data-stu-id="3b96c-181">int</span></span>|<span data-ttu-id="3b96c-182">O código de status HTTP.</span><span class="sxs-lookup"><span data-stu-id="3b96c-182">The HTTP status code.</span></span>|
|<span data-ttu-id="3b96c-183">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="3b96c-183">ErrorMessage</span></span>|<span data-ttu-id="3b96c-184">string</span><span class="sxs-lookup"><span data-stu-id="3b96c-184">string</span></span>|<span data-ttu-id="3b96c-185">A mensagem de erro que informa o que há de errado ao aplicar o modelo à biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="3b96c-185">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="3b96c-186">Publicação</span><span class="sxs-lookup"><span data-stu-id="3b96c-186">Publication</span></span>|<span data-ttu-id="3b96c-187">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="3b96c-187">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="3b96c-188">Especifica as informações do modelo e a biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="3b96c-188">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="3b96c-189">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="3b96c-189">MachineLearningPublicationEntityData</span></span>
| <span data-ttu-id="3b96c-190">Nome</span><span class="sxs-lookup"><span data-stu-id="3b96c-190">Name</span></span> | <span data-ttu-id="3b96c-191">Tipo</span><span class="sxs-lookup"><span data-stu-id="3b96c-191">Type</span></span> | <span data-ttu-id="3b96c-192">Descrição</span><span class="sxs-lookup"><span data-stu-id="3b96c-192">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="3b96c-193">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="3b96c-193">ModelUniqueId</span></span>|<span data-ttu-id="3b96c-194">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3b96c-194">string</span></span>|<span data-ttu-id="3b96c-195">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="3b96c-195">The unique ID of the model file.</span></span>|
|<span data-ttu-id="3b96c-196">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="3b96c-196">TargetSiteUrl</span></span>|<span data-ttu-id="3b96c-197">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3b96c-197">string</span></span>|<span data-ttu-id="3b96c-198">A URL completa do site da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="3b96c-198">The full URL of the target library site.</span></span>|
|<span data-ttu-id="3b96c-199">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="3b96c-199">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="3b96c-200">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3b96c-200">string</span></span>|<span data-ttu-id="3b96c-201">A URL relativa do servidor da web para a biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="3b96c-201">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="3b96c-202">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="3b96c-202">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="3b96c-203">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3b96c-203">string</span></span>|<span data-ttu-id="3b96c-204">A URL relativa do servidor da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="3b96c-204">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="3b96c-205">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3b96c-205">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="3b96c-206">Aplicar um modelo à biblioteca de documentos de contratos no site de repositório</span><span class="sxs-lookup"><span data-stu-id="3b96c-206">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="3b96c-207">Neste exemplo, a ID do modelo de compreensão de documento do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="3b96c-207">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="3b96c-208">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="3b96c-208">Sample request</span></span>

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a><span data-ttu-id="3b96c-209">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="3b96c-209">Sample response</span></span>

<span data-ttu-id="3b96c-210">Na resposta, TotalFailures e TotalSuccesses se referem ao número de falhas e sucessos do modelo que está sendo aplicado às bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="3b96c-210">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="3b96c-211">**Código de status:** 201</span><span class="sxs-lookup"><span data-stu-id="3b96c-211">**Status code:** 201</span></span>

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a><span data-ttu-id="3b96c-212">Confira também</span><span class="sxs-lookup"><span data-stu-id="3b96c-212">See also</span></span>

[<span data-ttu-id="3b96c-213">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="3b96c-213">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
