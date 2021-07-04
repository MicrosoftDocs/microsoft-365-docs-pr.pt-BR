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
ms.openlocfilehash: bbd3e496b50d3fddb31342fbc07d30984544e744
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287448"
---
# <a name="batchdelete"></a><span data-ttu-id="ee724-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="ee724-103">BatchDelete</span></span>

<span data-ttu-id="ee724-104">Remove um modelo de compreensão de documentos aplicado de uma ou mais bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="ee724-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="ee724-105">Observe que um modelo deve ser removido de todas as bibliotecas antes de poder ser excluído (consulte [exemplo](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="ee724-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="ee724-106">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="ee724-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="ee724-107">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="ee724-107">URI parameters</span></span>

<span data-ttu-id="ee724-108">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ee724-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="ee724-109">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="ee724-109">Request headers</span></span>

| <span data-ttu-id="ee724-110">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="ee724-110">Header</span></span> | <span data-ttu-id="ee724-111">Valor</span><span class="sxs-lookup"><span data-stu-id="ee724-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="ee724-112">Aceitar</span><span class="sxs-lookup"><span data-stu-id="ee724-112">Accept</span></span>|<span data-ttu-id="ee724-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="ee724-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="ee724-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ee724-114">Content-Type</span></span>|<span data-ttu-id="ee724-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="ee724-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="ee724-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="ee724-116">x-requestdigest</span></span>|<span data-ttu-id="ee724-117">O resumo apropriado para o site atual.</span><span class="sxs-lookup"><span data-stu-id="ee724-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="ee724-118">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="ee724-118">Request body</span></span>

| <span data-ttu-id="ee724-119">Nome</span><span class="sxs-lookup"><span data-stu-id="ee724-119">Name</span></span> | <span data-ttu-id="ee724-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="ee724-120">Required</span></span> | <span data-ttu-id="ee724-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee724-121">Type</span></span> | <span data-ttu-id="ee724-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee724-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="ee724-123">Publicações</span><span class="sxs-lookup"><span data-stu-id="ee724-123">Publications</span></span>|<span data-ttu-id="ee724-124">sim</span><span class="sxs-lookup"><span data-stu-id="ee724-124">yes</span></span>|<span data-ttu-id="ee724-125">MachineLearningPublicationEntityData[]</span><span class="sxs-lookup"><span data-stu-id="ee724-125">MachineLearningPublicationEntityData[]</span></span>|<span data-ttu-id="ee724-126">A coleção do MachineLearningPublicationEntityData de cada um deles especifica o modelo e a biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="ee724-126">The collection of MachineLearningPublicationEntityData each of which specifies the model and target document library.</span></span>|

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="ee724-127">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="ee724-127">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="ee724-128">Nome</span><span class="sxs-lookup"><span data-stu-id="ee724-128">Name</span></span> | <span data-ttu-id="ee724-129">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="ee724-129">Required</span></span> | <span data-ttu-id="ee724-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee724-130">Type</span></span> | <span data-ttu-id="ee724-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee724-131">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="ee724-132">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="ee724-132">ModelUniqueId</span></span>|<span data-ttu-id="ee724-133">sim</span><span class="sxs-lookup"><span data-stu-id="ee724-133">yes</span></span>|<span data-ttu-id="ee724-134">string</span><span class="sxs-lookup"><span data-stu-id="ee724-134">string</span></span>|<span data-ttu-id="ee724-135">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="ee724-135">The unique ID of the model file.</span></span>|
|<span data-ttu-id="ee724-136">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="ee724-136">TargetSiteUrl</span></span>|<span data-ttu-id="ee724-137">sim</span><span class="sxs-lookup"><span data-stu-id="ee724-137">yes</span></span>|<span data-ttu-id="ee724-138">string</span><span class="sxs-lookup"><span data-stu-id="ee724-138">string</span></span>|<span data-ttu-id="ee724-139">A URL completa do site da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="ee724-139">The full URL of the target library site.</span></span>|
|<span data-ttu-id="ee724-140">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="ee724-140">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="ee724-141">sim</span><span class="sxs-lookup"><span data-stu-id="ee724-141">yes</span></span>|<span data-ttu-id="ee724-142">string</span><span class="sxs-lookup"><span data-stu-id="ee724-142">string</span></span>|<span data-ttu-id="ee724-143">A URL relativa do servidor da web para a biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="ee724-143">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="ee724-144">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="ee724-144">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="ee724-145">sim</span><span class="sxs-lookup"><span data-stu-id="ee724-145">yes</span></span>|<span data-ttu-id="ee724-146">string</span><span class="sxs-lookup"><span data-stu-id="ee724-146">string</span></span>|<span data-ttu-id="ee724-147">A URL relativa do servidor da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="ee724-147">The server relative URL of the target library.</span></span>|

## <a name="response"></a><span data-ttu-id="ee724-148">Resposta</span><span class="sxs-lookup"><span data-stu-id="ee724-148">Response</span></span>

| <span data-ttu-id="ee724-149">Nome</span><span class="sxs-lookup"><span data-stu-id="ee724-149">Name</span></span>   | <span data-ttu-id="ee724-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee724-150">Type</span></span>  | <span data-ttu-id="ee724-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee724-151">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="ee724-152">200 OK</span><span class="sxs-lookup"><span data-stu-id="ee724-152">200 OK</span></span>||<span data-ttu-id="ee724-p102">Esta é uma API personalizada para suportar a remoção de um modelo de bibliotecas de documentos múltiplos. No caso de êxito parcial, 200 OK ainda pode ser retornado e o chamador precisa inspecionar o corpo da resposta para entender se o modelo foi removido com êxito de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="ee724-p102">This is a customized API to support removing a model from multi document libraries. In the case of partial success, 200 OK could still be returned and the caller needs to inspect the response body to understand if the model has been successfully removed from a document library.</span></span>|

## <a name="response-body"></a><span data-ttu-id="ee724-155">Corpo da resposta</span><span class="sxs-lookup"><span data-stu-id="ee724-155">Response Body</span></span>

| <span data-ttu-id="ee724-156">Nome</span><span class="sxs-lookup"><span data-stu-id="ee724-156">Name</span></span>   | <span data-ttu-id="ee724-157">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee724-157">Type</span></span>  | <span data-ttu-id="ee724-158">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee724-158">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="ee724-159">TotalSuccesses</span><span class="sxs-lookup"><span data-stu-id="ee724-159">TotalSuccesses</span></span>|<span data-ttu-id="ee724-160">int</span><span class="sxs-lookup"><span data-stu-id="ee724-160">int</span></span>|<span data-ttu-id="ee724-161">O número total de um modelo que está sendo removido com êxito de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="ee724-161">The total number of a model being successfully removed from a document library.</span></span>|
|<span data-ttu-id="ee724-162">TotalFailures</span><span class="sxs-lookup"><span data-stu-id="ee724-162">TotalFailures</span></span>|<span data-ttu-id="ee724-163">int</span><span class="sxs-lookup"><span data-stu-id="ee724-163">int</span></span>|<span data-ttu-id="ee724-164">O número total de um modelo que não foi removido de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="ee724-164">The total number of a model failing to be removed from a document library.</span></span>|
|<span data-ttu-id="ee724-165">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ee724-165">Details</span></span>|<span data-ttu-id="ee724-166">MachineLearningPublicationResult[]</span><span class="sxs-lookup"><span data-stu-id="ee724-166">MachineLearningPublicationResult[]</span></span>|<span data-ttu-id="ee724-167">A coleção do MachineLearningPublicationResult de cada um deles especifica o resultado detalhado da remoção do modelo de uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="ee724-167">The collection of MachineLearningPublicationResult each of which specifies the detailed result of removing the model from a document library.</span></span>|

### <a name="machinelearningpublicationresult"></a><span data-ttu-id="ee724-168">MachineLearningPublicationResult</span><span class="sxs-lookup"><span data-stu-id="ee724-168">MachineLearningPublicationResult</span></span>

| <span data-ttu-id="ee724-169">Nome</span><span class="sxs-lookup"><span data-stu-id="ee724-169">Name</span></span>   | <span data-ttu-id="ee724-170">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee724-170">Type</span></span>  | <span data-ttu-id="ee724-171">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee724-171">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="ee724-172">StatusCode</span><span class="sxs-lookup"><span data-stu-id="ee724-172">StatusCode</span></span>|<span data-ttu-id="ee724-173">int</span><span class="sxs-lookup"><span data-stu-id="ee724-173">int</span></span>|<span data-ttu-id="ee724-174">O código de status HTTP.</span><span class="sxs-lookup"><span data-stu-id="ee724-174">The HTTP status code.</span></span>|
|<span data-ttu-id="ee724-175">ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="ee724-175">ErrorMessage</span></span>|<span data-ttu-id="ee724-176">string</span><span class="sxs-lookup"><span data-stu-id="ee724-176">string</span></span>|<span data-ttu-id="ee724-177">A mensagem de erro que informa o que há de errado ao aplicar o modelo à biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="ee724-177">The error message which tells what's wrong when apply the model to the document library.</span></span>|
|<span data-ttu-id="ee724-178">Publicação</span><span class="sxs-lookup"><span data-stu-id="ee724-178">Publication</span></span>|<span data-ttu-id="ee724-179">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="ee724-179">MachineLearningPublicationEntityData</span></span>|<span data-ttu-id="ee724-180">Especifica as informações do modelo e a biblioteca de documentos de destino.</span><span class="sxs-lookup"><span data-stu-id="ee724-180">It specifies the model info and the target document library.</span></span>| 

### <a name="machinelearningpublicationentitydata"></a><span data-ttu-id="ee724-181">MachineLearningPublicationEntityData</span><span class="sxs-lookup"><span data-stu-id="ee724-181">MachineLearningPublicationEntityData</span></span>

| <span data-ttu-id="ee724-182">Nome</span><span class="sxs-lookup"><span data-stu-id="ee724-182">Name</span></span> | <span data-ttu-id="ee724-183">Tipo</span><span class="sxs-lookup"><span data-stu-id="ee724-183">Type</span></span> | <span data-ttu-id="ee724-184">Descrição</span><span class="sxs-lookup"><span data-stu-id="ee724-184">Description</span></span> |
|--------|--------|------------|
|<span data-ttu-id="ee724-185">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="ee724-185">ModelUniqueId</span></span>|<span data-ttu-id="ee724-186">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ee724-186">string</span></span>|<span data-ttu-id="ee724-187">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="ee724-187">The unique ID of the model file.</span></span>|
|<span data-ttu-id="ee724-188">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="ee724-188">TargetSiteUrl</span></span>|<span data-ttu-id="ee724-189">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ee724-189">string</span></span>|<span data-ttu-id="ee724-190">A URL completa do site da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="ee724-190">The full URL of the target library site.</span></span>|
|<span data-ttu-id="ee724-191">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="ee724-191">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="ee724-192">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ee724-192">string</span></span>|<span data-ttu-id="ee724-193">A URL relativa do servidor da web para a biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="ee724-193">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="ee724-194">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="ee724-194">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="ee724-195">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ee724-195">string</span></span>|<span data-ttu-id="ee724-196">A URL relativa do servidor da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="ee724-196">The server relative URL of the target library.</span></span>|

## <a name="examples"></a><span data-ttu-id="ee724-197">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ee724-197">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="ee724-198">Remover um modelo da biblioteca de documentos de contratos no site de repositório</span><span class="sxs-lookup"><span data-stu-id="ee724-198">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="ee724-199">Nesse exemplo, a ID do modelo de compreensão de documentos do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="ee724-199">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="ee724-200">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="ee724-200">Sample request</span></span>

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

#### <a name="sample-response"></a><span data-ttu-id="ee724-201">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="ee724-201">Sample response</span></span>

<span data-ttu-id="ee724-202">Na resposta, TotalFailures e TotalSuccesses se referem ao número de falhas e sucessos do modelo que está sendo removido das bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="ee724-202">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being removed from the specified libraries.</span></span>

<span data-ttu-id="ee724-203">**Código de status:** 200</span><span class="sxs-lookup"><span data-stu-id="ee724-203">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ee724-204">Confira também</span><span class="sxs-lookup"><span data-stu-id="ee724-204">See also</span></span>

[<span data-ttu-id="ee724-205">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="ee724-205">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
