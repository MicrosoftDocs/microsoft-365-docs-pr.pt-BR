---
title: Aplicar modelo
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
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904175"
---
# <a name="apply-model"></a><span data-ttu-id="8e9aa-103">Aplicar modelo</span><span class="sxs-lookup"><span data-stu-id="8e9aa-103">Apply model</span></span>

<span data-ttu-id="8e9aa-104">Aplica (ou sincroniza) um modelo treinado de compreensão de documento a uma ou mais bibliotecas (consulte o [exemplo](rest-applymodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="8e9aa-104">Applies (or syncs) a trained document understanding model to one or more libraries (see [example](rest-applymodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="8e9aa-105">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="8e9aa-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="8e9aa-106">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="8e9aa-106">URI parameters</span></span>

<span data-ttu-id="8e9aa-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8e9aa-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="8e9aa-108">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="8e9aa-108">Request headers</span></span>

| <span data-ttu-id="8e9aa-109">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="8e9aa-109">Header</span></span> | <span data-ttu-id="8e9aa-110">Valor</span><span class="sxs-lookup"><span data-stu-id="8e9aa-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="8e9aa-111">Aceitar</span><span class="sxs-lookup"><span data-stu-id="8e9aa-111">Accept</span></span>|<span data-ttu-id="8e9aa-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="8e9aa-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="8e9aa-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="8e9aa-113">Content-Type</span></span>|<span data-ttu-id="8e9aa-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="8e9aa-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="8e9aa-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="8e9aa-115">x-requestdigest</span></span>|<span data-ttu-id="8e9aa-116">O resumo apropriado para o site atual.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-116">The appropriate digest for current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="8e9aa-117">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="8e9aa-117">Request body</span></span>

| <span data-ttu-id="8e9aa-118">Nome</span><span class="sxs-lookup"><span data-stu-id="8e9aa-118">Name</span></span> | <span data-ttu-id="8e9aa-119">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="8e9aa-119">Required</span></span> | <span data-ttu-id="8e9aa-120">Tipo</span><span class="sxs-lookup"><span data-stu-id="8e9aa-120">Type</span></span> | <span data-ttu-id="8e9aa-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e9aa-121">Description</span></span> |
|--------|-------|--------|------------|
|<span data-ttu-id="8e9aa-122">ModelUniqueId</span><span class="sxs-lookup"><span data-stu-id="8e9aa-122">ModelUniqueId</span></span>|<span data-ttu-id="8e9aa-123">sim</span><span class="sxs-lookup"><span data-stu-id="8e9aa-123">yes</span></span>|<span data-ttu-id="8e9aa-124">string</span><span class="sxs-lookup"><span data-stu-id="8e9aa-124">string</span></span>|<span data-ttu-id="8e9aa-125">A ID exclusiva do arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-125">The unique ID of the model file.</span></span>|
<span data-ttu-id="8e9aa-126">TargetSiteUrl</span><span class="sxs-lookup"><span data-stu-id="8e9aa-126">TargetSiteUrl</span></span>|<span data-ttu-id="8e9aa-127">sim</span><span class="sxs-lookup"><span data-stu-id="8e9aa-127">yes</span></span>|<span data-ttu-id="8e9aa-128">string</span><span class="sxs-lookup"><span data-stu-id="8e9aa-128">string</span></span>|<span data-ttu-id="8e9aa-129">A URL completa do site da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-129">The full URL of the target library site.</span></span>|
<span data-ttu-id="8e9aa-130">TargetWebServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="8e9aa-130">TargetWebServerRelativeUrl</span></span>|<span data-ttu-id="8e9aa-131">sim</span><span class="sxs-lookup"><span data-stu-id="8e9aa-131">yes</span></span>|<span data-ttu-id="8e9aa-132">string</span><span class="sxs-lookup"><span data-stu-id="8e9aa-132">string</span></span>|<span data-ttu-id="8e9aa-133">A URL relativa do servidor da Web para a biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-133">The server relative URL of the web for the target library.</span></span>|
<span data-ttu-id="8e9aa-134">TargetLibraryServerRelativeUrl</span><span class="sxs-lookup"><span data-stu-id="8e9aa-134">TargetLibraryServerRelativeUrl</span></span>|<span data-ttu-id="8e9aa-135">sim</span><span class="sxs-lookup"><span data-stu-id="8e9aa-135">yes</span></span>|<span data-ttu-id="8e9aa-136">string</span><span class="sxs-lookup"><span data-stu-id="8e9aa-136">string</span></span>|<span data-ttu-id="8e9aa-137">A URL relativa do servidor da biblioteca de destino.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-137">The server relative URL of the target library.</span></span>|
<span data-ttu-id="8e9aa-138">Viewoption</span><span class="sxs-lookup"><span data-stu-id="8e9aa-138">ViewOption</span></span>|<span data-ttu-id="8e9aa-139">não</span><span class="sxs-lookup"><span data-stu-id="8e9aa-139">no</span></span>|<span data-ttu-id="8e9aa-140">string</span><span class="sxs-lookup"><span data-stu-id="8e9aa-140">string</span></span>|<span data-ttu-id="8e9aa-141">Especifica se o novo modo de exibição de modelo deve ser definido como o padrão da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-141">Specifies whether to set new model view as the library default.</span></span>|

## <a name="response"></a><span data-ttu-id="8e9aa-142">Resposta</span><span class="sxs-lookup"><span data-stu-id="8e9aa-142">Response</span></span>

| <span data-ttu-id="8e9aa-143">Nome</span><span class="sxs-lookup"><span data-stu-id="8e9aa-143">Name</span></span>   | <span data-ttu-id="8e9aa-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="8e9aa-144">Type</span></span>  | <span data-ttu-id="8e9aa-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="8e9aa-145">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="8e9aa-146">200 OK</span><span class="sxs-lookup"><span data-stu-id="8e9aa-146">200 OK</span></span>| |<span data-ttu-id="8e9aa-147">Êxito</span><span class="sxs-lookup"><span data-stu-id="8e9aa-147">Success</span></span>|
|<span data-ttu-id="8e9aa-148">201 Criado</span><span class="sxs-lookup"><span data-stu-id="8e9aa-148">201 Created</span></span>| |<span data-ttu-id="8e9aa-149">Observe que como essa API dá suporte à aplicação de modelo a várias bibliotecas, um 201 pode ser retornado mesmo se houver uma falha aplicando o modelo a uma das bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-149">Note that because this API supports applying model to multiple libraries, a 201 could be returned even if there's a failure applying the model to one of the libraries.</span></span> <br><span data-ttu-id="8e9aa-150">Verifique o corpo da resposta para compreender se o modelo foi aplicado com êxito a todas as bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-150">Check the response body to understand if the model has been successfully applied to all the specified libraries.</span></span> <span data-ttu-id="8e9aa-151">Consulte [Solicitar corpo](rest-applymodel-method.md#request-body) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-151">See [Request body](rest-applymodel-method.md#request-body) for details.</span></span>|

## <a name="examples"></a><span data-ttu-id="8e9aa-152">Exemplos</span><span class="sxs-lookup"><span data-stu-id="8e9aa-152">Examples</span></span>

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a><span data-ttu-id="8e9aa-153">Aplicar um modelo à biblioteca de documentos de contratos no site de repositório</span><span class="sxs-lookup"><span data-stu-id="8e9aa-153">Apply a model to the contracts document library in the repository site</span></span>

<span data-ttu-id="8e9aa-154">Neste exemplo, a ID do modelo de compreensão de documento do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-154">In this sample, the ID of the Contoso Contract document understanding model is `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="8e9aa-155">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="8e9aa-155">Sample request</span></span>

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


#### <a name="sample-response"></a><span data-ttu-id="8e9aa-156">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="8e9aa-156">Sample response</span></span>

<span data-ttu-id="8e9aa-157">Na resposta, TotalFailures e TotalSuccesses se referem ao número de falhas e sucessos do modelo que está sendo aplicado às bibliotecas especificadas.</span><span class="sxs-lookup"><span data-stu-id="8e9aa-157">In the response, TotalFailures and TotalSuccesses refers to the number of failures and successes of the model being applies to the specified libraries.</span></span>

<span data-ttu-id="8e9aa-158">**Código de status:** 200</span><span class="sxs-lookup"><span data-stu-id="8e9aa-158">**Status code:** 200</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8e9aa-159">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e9aa-159">See also</span></span>

[<span data-ttu-id="8e9aa-160">API REST do modelo de compreensão de documento Syntex</span><span class="sxs-lookup"><span data-stu-id="8e9aa-160">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
