---
title: Obter informações sobre modelo e biblioteca
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
description: Use a API REST para obter informações sobre um modelo e a biblioteca onde ele foi aplicado.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904152"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="a3c00-103">Obter informações sobre modelo e biblioteca</span><span class="sxs-lookup"><span data-stu-id="a3c00-103">Get model and library information</span></span>

<span data-ttu-id="a3c00-104">Obtém informações sobre um modelo e a biblioteca onde ele foi aplicado (veja o [exemplo](rest-getmodelandlibraryinfo.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="a3c00-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="a3c00-105">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="a3c00-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="a3c00-106">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="a3c00-106">URI parameters</span></span>

| <span data-ttu-id="a3c00-107">Nome</span><span class="sxs-lookup"><span data-stu-id="a3c00-107">Name</span></span> | <span data-ttu-id="a3c00-108">Em</span><span class="sxs-lookup"><span data-stu-id="a3c00-108">In</span></span> | <span data-ttu-id="a3c00-109">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a3c00-109">Required</span></span> | <span data-ttu-id="a3c00-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="a3c00-110">Type</span></span> | <span data-ttu-id="a3c00-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="a3c00-111">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="a3c00-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="a3c00-112">ModelUniqueId</span></span>|<span data-ttu-id="a3c00-113">consulta</span><span class="sxs-lookup"><span data-stu-id="a3c00-113">query</span></span>|<span data-ttu-id="a3c00-114">True</span><span class="sxs-lookup"><span data-stu-id="a3c00-114">True</span></span>|<span data-ttu-id="a3c00-115">GUID</span><span class="sxs-lookup"><span data-stu-id="a3c00-115">GUID</span></span>|<span data-ttu-id="a3c00-116">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="a3c00-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="a3c00-117">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="a3c00-117">Request headers</span></span>

| <span data-ttu-id="a3c00-118">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="a3c00-118">Header</span></span> | <span data-ttu-id="a3c00-119">Valor</span><span class="sxs-lookup"><span data-stu-id="a3c00-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="a3c00-120">Aceitar</span><span class="sxs-lookup"><span data-stu-id="a3c00-120">Accept</span></span>|<span data-ttu-id="a3c00-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="a3c00-121">application/json;odata=verbose</span></span>|


## <a name="request-body"></a><span data-ttu-id="a3c00-122">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="a3c00-122">Request body</span></span>

| <span data-ttu-id="a3c00-123">Nome</span><span class="sxs-lookup"><span data-stu-id="a3c00-123">Name</span></span> | <span data-ttu-id="a3c00-124">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a3c00-124">Required</span></span> | <span data-ttu-id="a3c00-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="a3c00-125">Type</span></span> | <span data-ttu-id="a3c00-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="a3c00-126">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="a3c00-127">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="a3c00-127">ModelUniqueId</span></span>|<span data-ttu-id="a3c00-128">sim</span><span class="sxs-lookup"><span data-stu-id="a3c00-128">yes</span></span>|<span data-ttu-id="a3c00-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a3c00-129">string</span></span>|<span data-ttu-id="a3c00-130">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="a3c00-130">The unique ID of the model file.</span></span>|
|<span data-ttu-id="a3c00-131">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="a3c00-131">TargetSiteUrl</span></span>|<span data-ttu-id="a3c00-132">sim</span><span class="sxs-lookup"><span data-stu-id="a3c00-132">yes</span></span>|<span data-ttu-id="a3c00-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a3c00-133">string</span></span>|<span data-ttu-id="a3c00-134">A URL completa do site da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a3c00-134">The full URL of the target library site.</span></span>|
|<span data-ttu-id="a3c00-135">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a3c00-135">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="a3c00-136">sim</span><span class="sxs-lookup"><span data-stu-id="a3c00-136">yes</span></span>|<span data-ttu-id="a3c00-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a3c00-137">string</span></span>|<span data-ttu-id="a3c00-138">A URL relativa do servidor da Web para a biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a3c00-138">The server relative URL of the web for the target library.</span></span>|
|<span data-ttu-id="a3c00-139">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="a3c00-139">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="a3c00-140">sim</span><span class="sxs-lookup"><span data-stu-id="a3c00-140">yes</span></span>|<span data-ttu-id="a3c00-141">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a3c00-141">string</span></span>|<span data-ttu-id="a3c00-142">A URL relativa do servidor da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="a3c00-142">The server relative URL of the target library.</span></span>|
|<span data-ttu-id="a3c00-143">TargetLibraryRemoved</span><span class="sxs-lookup"><span data-stu-id="a3c00-143">TargetLibraryRemoved</span></span>|<span data-ttu-id="a3c00-144">sim</span><span class="sxs-lookup"><span data-stu-id="a3c00-144">yes</span></span>|<span data-ttu-id="a3c00-145">int</span><span class="sxs-lookup"><span data-stu-id="a3c00-145">int</span></span>|<span data-ttu-id="a3c00-146">O sinalizador que indica se a biblioteca de destino foi removida ou não.</span><span class="sxs-lookup"><span data-stu-id="a3c00-146">The flag that indicates if the target library has been removed or not.</span></span>|

## <a name="response"></a><span data-ttu-id="a3c00-147">Resposta</span><span class="sxs-lookup"><span data-stu-id="a3c00-147">Response</span></span>

| <span data-ttu-id="a3c00-148">Nome</span><span class="sxs-lookup"><span data-stu-id="a3c00-148">Name</span></span>   | <span data-ttu-id="a3c00-149">Tipo</span><span class="sxs-lookup"><span data-stu-id="a3c00-149">Type</span></span>  | <span data-ttu-id="a3c00-150">Descrição</span><span class="sxs-lookup"><span data-stu-id="a3c00-150">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="a3c00-151">200 OK</span><span class="sxs-lookup"><span data-stu-id="a3c00-151">200 OK</span></span>| |<span data-ttu-id="a3c00-152">Sucesso</span><span class="sxs-lookup"><span data-stu-id="a3c00-152">Success</span></span>|
|<span data-ttu-id="a3c00-153">201 criado</span><span class="sxs-lookup"><span data-stu-id="a3c00-153">201 Created</span></span>| |<span data-ttu-id="a3c00-154">Observe que, como esta API oferece suporte à aplicação do modelo a várias bibliotecas, um 201 pode ser retornado mesmo se houver uma falha ao aplicar o modelo a uma das bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="a3c00-154">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="a3c00-155">Verifique o corpo da resposta para saber se o modelo foi aplicado com sucesso a todas as bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="a3c00-155">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="a3c00-156">Confira o [Corpo da solicitação](rest-getmodelandlibraryinfo.md#request-body) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="a3c00-156">See [Request body](rest-getmodelandlibraryinfo.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="a3c00-157">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a3c00-157">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="a3c00-158">Obtenha informações sobre o modelo de contratos e biblioteca de documentos preparados no site do repositório</span><span class="sxs-lookup"><span data-stu-id="a3c00-158">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="a3c00-159">Neste exemplo, a ID do modelo de compreensão de documentos do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="a3c00-159">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="a3c00-160">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="a3c00-160">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="a3c00-161">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="a3c00-161">Sample response</span></span>

<span data-ttu-id="a3c00-162">**Código de status:** 200</span><span class="sxs-lookup"><span data-stu-id="a3c00-162">**Status code:** 200</span></span>

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a><span data-ttu-id="a3c00-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="a3c00-163">See also</span></span>

[<span data-ttu-id="a3c00-164">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="a3c00-164">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
