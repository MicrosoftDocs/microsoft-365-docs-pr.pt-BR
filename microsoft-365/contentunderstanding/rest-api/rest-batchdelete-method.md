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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904147"
---
# <a name="batchdelete"></a><span data-ttu-id="e3ff3-103">BatchDelete</span><span class="sxs-lookup"><span data-stu-id="e3ff3-103">BatchDelete</span></span>

<span data-ttu-id="e3ff3-104">Remove um modelo de compreensão de documentos aplicado de uma ou mais bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="e3ff3-104">Removes an applied document understanding model from one or more libraries.</span></span> <span data-ttu-id="e3ff3-105">Observe que um modelo deve ser removido de todas as bibliotecas antes de poder ser excluído (consulte [exemplo](rest-batchdelete-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="e3ff3-105">Note that a model must be removed from all libraries before it can be deleted (see [example](rest-batchdelete-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="e3ff3-106">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="e3ff3-106">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="e3ff3-107">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="e3ff3-107">URI parameters</span></span>

<span data-ttu-id="e3ff3-108">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e3ff3-108">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="e3ff3-109">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="e3ff3-109">Request headers</span></span>

| <span data-ttu-id="e3ff3-110">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="e3ff3-110">Header</span></span> | <span data-ttu-id="e3ff3-111">Valor</span><span class="sxs-lookup"><span data-stu-id="e3ff3-111">Value</span></span> |
|--------|-------|
|<span data-ttu-id="e3ff3-112">Aceitar</span><span class="sxs-lookup"><span data-stu-id="e3ff3-112">Accept</span></span>|<span data-ttu-id="e3ff3-113">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="e3ff3-113">application/json;odata=verbose</span></span>|
|<span data-ttu-id="e3ff3-114">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e3ff3-114">Content-Type</span></span>|<span data-ttu-id="e3ff3-115">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="e3ff3-115">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="e3ff3-116">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="e3ff3-116">x-requestdigest</span></span>|<span data-ttu-id="e3ff3-117">O resumo apropriado para o site atual.</span><span class="sxs-lookup"><span data-stu-id="e3ff3-117">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="e3ff3-118">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="e3ff3-118">Request body</span></span>

| <span data-ttu-id="e3ff3-119">Nome</span><span class="sxs-lookup"><span data-stu-id="e3ff3-119">Name</span></span> | <span data-ttu-id="e3ff3-120">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="e3ff3-120">Required</span></span> | <span data-ttu-id="e3ff3-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="e3ff3-121">Type</span></span> | <span data-ttu-id="e3ff3-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="e3ff3-122">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="e3ff3-123">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="e3ff3-123">ModelUniqueId</span></span>|<span data-ttu-id="e3ff3-124">sim</span><span class="sxs-lookup"><span data-stu-id="e3ff3-124">yes</span></span>|<span data-ttu-id="e3ff3-125">string</span><span class="sxs-lookup"><span data-stu-id="e3ff3-125">string</span></span>|<span data-ttu-id="e3ff3-126">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="e3ff3-126">The unique ID of the model file.</span></span>|
<span data-ttu-id="e3ff3-127">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="e3ff3-127">TargetSiteUrl</span></span>|<span data-ttu-id="e3ff3-128">sim</span><span class="sxs-lookup"><span data-stu-id="e3ff3-128">yes</span></span>|<span data-ttu-id="e3ff3-129">string</span><span class="sxs-lookup"><span data-stu-id="e3ff3-129">string</span></span>|<span data-ttu-id="e3ff3-130">A URL completa do site da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="e3ff3-130">The full URL of the target library site.</span></span>|
<span data-ttu-id="e3ff3-131">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="e3ff3-131">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="e3ff3-132">sim</span><span class="sxs-lookup"><span data-stu-id="e3ff3-132">yes</span></span>|<span data-ttu-id="e3ff3-133">string</span><span class="sxs-lookup"><span data-stu-id="e3ff3-133">string</span></span>|<span data-ttu-id="e3ff3-134">A URL relativa do servidor da web para a biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="e3ff3-134">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="e3ff3-135">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="e3ff3-135">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="e3ff3-136">sim</span><span class="sxs-lookup"><span data-stu-id="e3ff3-136">yes</span></span>|<span data-ttu-id="e3ff3-137">string</span><span class="sxs-lookup"><span data-stu-id="e3ff3-137">string</span></span>|<span data-ttu-id="e3ff3-138">A URL relativa do servidor da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="e3ff3-138">The server relative URL of the target library.</span></span>|
<span data-ttu-id="e3ff3-139">ViewOption</span><span class="sxs-lookup"><span data-stu-id="e3ff3-139">ViewOption</span></span>|<span data-ttu-id="e3ff3-140">não</span><span class="sxs-lookup"><span data-stu-id="e3ff3-140">no</span></span>|<span data-ttu-id="e3ff3-141">string</span><span class="sxs-lookup"><span data-stu-id="e3ff3-141">string</span></span>|<span data-ttu-id="e3ff3-142">Especifica se o novo modo de exibição de modelo deve ser definido como o padrão da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e3ff3-142">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="e3ff3-143">Resposta</span><span class="sxs-lookup"><span data-stu-id="e3ff3-143">Response</span></span>

| <span data-ttu-id="e3ff3-144">Nome</span><span class="sxs-lookup"><span data-stu-id="e3ff3-144">Name</span></span>   | <span data-ttu-id="e3ff3-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="e3ff3-145">Type</span></span>  | <span data-ttu-id="e3ff3-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="e3ff3-146">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="e3ff3-147">200 OK</span><span class="sxs-lookup"><span data-stu-id="e3ff3-147">200 OK</span></span>| |<span data-ttu-id="e3ff3-148">Êxito</span><span class="sxs-lookup"><span data-stu-id="e3ff3-148">Success</span></span>|


## <a name="examples"></a><span data-ttu-id="e3ff3-149">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e3ff3-149">Examples</span></span>

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="e3ff3-150">Remover um modelo da biblioteca de documentos de contratos no site de repositório</span><span class="sxs-lookup"><span data-stu-id="e3ff3-150">Remove a model from the contracts document library in the repository site</span></span>

<span data-ttu-id="e3ff3-151">Nesse exemplo, a ID do modelo de compreensão de documentos do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="e3ff3-151">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="e3ff3-152">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="e3ff3-152">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="e3ff3-153">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="e3ff3-153">Sample response</span></span>

<span data-ttu-id="e3ff3-154">Na resposta, TotalFailures e TotalSuccesses se referem ao número de falhas e sucessos do modelo que está sendo aplicado às bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="e3ff3-154">In the response, TotalFailures and TotalSuccesses refer to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="e3ff3-155">**Código de status:** 200</span><span class="sxs-lookup"><span data-stu-id="e3ff3-155">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e3ff3-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="e3ff3-156">See also</span></span>

[<span data-ttu-id="e3ff3-157">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="e3ff3-157">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
