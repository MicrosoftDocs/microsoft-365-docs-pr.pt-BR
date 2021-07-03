---
title: Criar solicitação de classificação
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
description: Use a API REST para criar uma solicitação para classificar um ou mais arquivos usando um modelo de compreensão de documento treinado.
ms.openlocfilehash: b1022787d6e11ebe36c88ecd29936a777289dd74
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287228"
---
# <a name="create-classification-request"></a><span data-ttu-id="eac7a-103">Criar solicitação de classificação</span><span class="sxs-lookup"><span data-stu-id="eac7a-103">Create classification request</span></span>

<span data-ttu-id="eac7a-104">Cria uma solicitação para classificar um ou mais arquivos usando o modelo de compreensão de documento aplicado (consulte [exemplo](rest-createclassificationrequest.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="eac7a-104">Creates a request to classify one or more files using the applied document understanding model (see [example](rest-createclassificationrequest.md#examples)).</span></span>

<span data-ttu-id="eac7a-105">O serviço REST do SharePoint Online (e o SharePoint 2016 e posterior local) dá suporte à combinação de várias solicitações.</span><span class="sxs-lookup"><span data-stu-id="eac7a-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests.</span></span> <span data-ttu-id="eac7a-106">As solicitações são combinadas em uma única chamada de serviço, usando a opção de consulta OData $batch.</span><span class="sxs-lookup"><span data-stu-id="eac7a-106">Requests are combined into a single call to the service by using the OData $batch query option.</span></span> <span data-ttu-id="eac7a-107">Esse método pode ser usado para sequenciar itens do trabalho de classificação para centenas de documentos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="eac7a-107">This method can be used to enqueue classification work items for hundreds of documents at one time.</span></span>

## <a name="http-request"></a><span data-ttu-id="eac7a-108">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="eac7a-108">HTTP request</span></span>

```http
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="eac7a-109">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="eac7a-109">URI Parameters</span></span>

<span data-ttu-id="eac7a-110">Nenhum</span><span class="sxs-lookup"><span data-stu-id="eac7a-110">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="eac7a-111">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="eac7a-111">Request headers</span></span>

| <span data-ttu-id="eac7a-112">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="eac7a-112">Header</span></span> | <span data-ttu-id="eac7a-113">Valor</span><span class="sxs-lookup"><span data-stu-id="eac7a-113">Value</span></span> |
|--------|-------|
|<span data-ttu-id="eac7a-114">Aceitar</span><span class="sxs-lookup"><span data-stu-id="eac7a-114">Accept</span></span>|<span data-ttu-id="eac7a-115">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="eac7a-115">application/json;odata=verbose</span></span>|
|<span data-ttu-id="eac7a-116">Content-Type</span><span class="sxs-lookup"><span data-stu-id="eac7a-116">Content-Type</span></span>|<span data-ttu-id="eac7a-117">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="eac7a-117">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="eac7a-118">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="eac7a-118">x-requestdigest</span></span>|<span data-ttu-id="eac7a-119">O resumo apropriado para o site atual</span><span class="sxs-lookup"><span data-stu-id="eac7a-119">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="eac7a-120">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="eac7a-120">Request body</span></span>

|<span data-ttu-id="eac7a-121">Nome</span><span class="sxs-lookup"><span data-stu-id="eac7a-121">Name</span></span>    |<span data-ttu-id="eac7a-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="eac7a-122">Type</span></span>   |<span data-ttu-id="eac7a-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="eac7a-123">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="eac7a-124">_metadata</span><span class="sxs-lookup"><span data-stu-id="eac7a-124">_metadata</span></span>|<span data-ttu-id="eac7a-125">string</span><span class="sxs-lookup"><span data-stu-id="eac7a-125">string</span></span> |<span data-ttu-id="eac7a-126">Definir o metadado do objeto no SPO.</span><span class="sxs-lookup"><span data-stu-id="eac7a-126">Set the object meta on the SPO.</span></span> <span data-ttu-id="eac7a-127">Sempre use o valor: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="eac7a-127">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"}.</span></span> |
|<span data-ttu-id="eac7a-128">TargetSiteId</span><span class="sxs-lookup"><span data-stu-id="eac7a-128">TargetSiteId</span></span>|<span data-ttu-id="eac7a-129">guid</span><span class="sxs-lookup"><span data-stu-id="eac7a-129">guid</span></span>|<span data-ttu-id="eac7a-130">A ID do site onde o arquivo a ser classificado está localizado.</span><span class="sxs-lookup"><span data-stu-id="eac7a-130">The id of the site where the file to classify is located.</span></span>|
|<span data-ttu-id="eac7a-131">TargetWebId</span><span class="sxs-lookup"><span data-stu-id="eac7a-131">TargetWebId</span></span>|<span data-ttu-id="eac7a-132">guid</span><span class="sxs-lookup"><span data-stu-id="eac7a-132">guid</span></span>|<span data-ttu-id="eac7a-133">A ID da web onde o arquivo a ser classificado está localizado.</span><span class="sxs-lookup"><span data-stu-id="eac7a-133">The id of the web where the file to classify is located.</span></span>|
|<span data-ttu-id="eac7a-134">TargetUniqueId</span><span class="sxs-lookup"><span data-stu-id="eac7a-134">TargetUniqueId</span></span>|<span data-ttu-id="eac7a-135">guid</span><span class="sxs-lookup"><span data-stu-id="eac7a-135">guid</span></span>|<span data-ttu-id="eac7a-136">A ID do arquivo a ser classificado.</span><span class="sxs-lookup"><span data-stu-id="eac7a-136">The id of the file to classify.</span></span>|

## <a name="responses"></a><span data-ttu-id="eac7a-137">Respostas</span><span class="sxs-lookup"><span data-stu-id="eac7a-137">Responses</span></span>

| <span data-ttu-id="eac7a-138">Nome</span><span class="sxs-lookup"><span data-stu-id="eac7a-138">Name</span></span>   | <span data-ttu-id="eac7a-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="eac7a-139">Type</span></span>  | <span data-ttu-id="eac7a-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="eac7a-140">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="eac7a-141">201 Criado</span><span class="sxs-lookup"><span data-stu-id="eac7a-141">201 Created</span></span>| |<span data-ttu-id="eac7a-142">Êxito</span><span class="sxs-lookup"><span data-stu-id="eac7a-142">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="eac7a-143">Exemplos</span><span class="sxs-lookup"><span data-stu-id="eac7a-143">Examples</span></span>

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a><span data-ttu-id="eac7a-144">Solicitar a classificação de um arquivo "e6cff8b7-c90c-4564-b5b8-033449090932"</span><span class="sxs-lookup"><span data-stu-id="eac7a-144">Enqueue a request to classify a file of id "e6cff8b7-c90c-4564-b5b8-033449090932"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="eac7a-145">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="eac7a-145">Sample request</span></span>

```JSON
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningWorkItemEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a><span data-ttu-id="eac7a-146">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="eac7a-146">Sample response</span></span>

<span data-ttu-id="eac7a-147">**Código de status:** 201</span><span class="sxs-lookup"><span data-stu-id="eac7a-147">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="eac7a-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="eac7a-148">See also</span></span>

[<span data-ttu-id="eac7a-149">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="eac7a-149">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
