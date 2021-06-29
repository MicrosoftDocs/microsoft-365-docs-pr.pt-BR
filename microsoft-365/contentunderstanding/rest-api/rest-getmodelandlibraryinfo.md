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
ms.openlocfilehash: 2449084653c6d9af8d774edc306c485e7a466bf6
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177064"
---
# <a name="get-model-and-library-information"></a><span data-ttu-id="61907-103">Obter informações sobre modelo e biblioteca</span><span class="sxs-lookup"><span data-stu-id="61907-103">Get model and library information</span></span>

<span data-ttu-id="61907-104">Obtém informações sobre um modelo e a biblioteca onde ele foi aplicado (veja o [exemplo](rest-getmodelandlibraryinfo.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="61907-104">Gets information about a model and the library where it has been applied (see [example](rest-getmodelandlibraryinfo.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="61907-105">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="61907-105">HTTP request</span></span>

```HTTP
GET /_api/machinelearning/publications/getbymodeluniqueid('{modelUniqueId}') HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="61907-106">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="61907-106">URI parameters</span></span>

| <span data-ttu-id="61907-107">Nome</span><span class="sxs-lookup"><span data-stu-id="61907-107">Name</span></span> | <span data-ttu-id="61907-108">Em</span><span class="sxs-lookup"><span data-stu-id="61907-108">In</span></span> | <span data-ttu-id="61907-109">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="61907-109">Required</span></span> | <span data-ttu-id="61907-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="61907-110">Type</span></span> | <span data-ttu-id="61907-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="61907-111">Description</span></span> |
|--------|-------|--------|------------|-----------|
|<span data-ttu-id="61907-112">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="61907-112">ModelUniqueId</span></span>|<span data-ttu-id="61907-113">consulta</span><span class="sxs-lookup"><span data-stu-id="61907-113">query</span></span>|<span data-ttu-id="61907-114">True</span><span class="sxs-lookup"><span data-stu-id="61907-114">True</span></span>|<span data-ttu-id="61907-115">GUID</span><span class="sxs-lookup"><span data-stu-id="61907-115">GUID</span></span>|<span data-ttu-id="61907-116">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="61907-116">The unique id of the model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="61907-117">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="61907-117">Request headers</span></span>

| <span data-ttu-id="61907-118">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="61907-118">Header</span></span> | <span data-ttu-id="61907-119">Valor</span><span class="sxs-lookup"><span data-stu-id="61907-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="61907-120">Aceitar</span><span class="sxs-lookup"><span data-stu-id="61907-120">Accept</span></span>|<span data-ttu-id="61907-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="61907-121">application/json;odata=verbose</span></span>|


## <a name="response"></a><span data-ttu-id="61907-122">Resposta</span><span class="sxs-lookup"><span data-stu-id="61907-122">Response</span></span>

| <span data-ttu-id="61907-123">Nome</span><span class="sxs-lookup"><span data-stu-id="61907-123">Name</span></span>   | <span data-ttu-id="61907-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="61907-124">Type</span></span>  | <span data-ttu-id="61907-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="61907-125">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="61907-126">200 OK</span><span class="sxs-lookup"><span data-stu-id="61907-126">200 OK</span></span>| |<span data-ttu-id="61907-127">Êxito</span><span class="sxs-lookup"><span data-stu-id="61907-127">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="61907-128">Exemplos</span><span class="sxs-lookup"><span data-stu-id="61907-128">Examples</span></span>

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a><span data-ttu-id="61907-129">Obtenha informações sobre o modelo de contratos e biblioteca de documentos preparados no site do repositório</span><span class="sxs-lookup"><span data-stu-id="61907-129">Get information about the contracts model and primed document library in the repository site</span></span>

<span data-ttu-id="61907-130">Neste exemplo, a ID do modelo de compreensão de documentos do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="61907-130">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="61907-131">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="61907-131">Sample request</span></span>

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc') HTTP/1.1
```
#### <a name="sample-response"></a><span data-ttu-id="61907-132">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="61907-132">Sample response</span></span>

<span data-ttu-id="61907-133">**Código de status:** 200</span><span class="sxs-lookup"><span data-stu-id="61907-133">**Status code:** 200</span></span>

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
}
```

## <a name="see-also"></a><span data-ttu-id="61907-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="61907-134">See also</span></span>

[<span data-ttu-id="61907-135">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="61907-135">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
