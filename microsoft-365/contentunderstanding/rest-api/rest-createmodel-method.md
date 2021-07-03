---
title: Criar um modelo
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
description: Use a API REST para criar um modelo e seu tipo de conteúdo associado.
ms.openlocfilehash: 1c5bd84c777774edc1aa0c2419181f7b84aa4707
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287240"
---
# <a name="create-model"></a><span data-ttu-id="e12b1-103">Criar um modelo</span><span class="sxs-lookup"><span data-stu-id="e12b1-103">Create model</span></span>

<span data-ttu-id="e12b1-104">Cria um modelo e seu tipo de conteúdo associado.</span><span class="sxs-lookup"><span data-stu-id="e12b1-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="e12b1-105">Observe que isso apenas cria o modelo.</span><span class="sxs-lookup"><span data-stu-id="e12b1-105">Note that this only creates the model.</span></span> <span data-ttu-id="e12b1-106">Ele ainda precisará ser treinado no centro de conteúdo (consulte [exemplos](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="e12b1-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="e12b1-107">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="e12b1-107">HTTP request</span></span>

```http
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="e12b1-108">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="e12b1-108">URI Parameters</span></span>

<span data-ttu-id="e12b1-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e12b1-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="e12b1-110">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="e12b1-110">Request headers</span></span>

| <span data-ttu-id="e12b1-111">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="e12b1-111">Header</span></span> | <span data-ttu-id="e12b1-112">Valor</span><span class="sxs-lookup"><span data-stu-id="e12b1-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="e12b1-113">Aceitar</span><span class="sxs-lookup"><span data-stu-id="e12b1-113">Accept</span></span>|<span data-ttu-id="e12b1-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="e12b1-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="e12b1-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="e12b1-115">Content-Type</span></span>|<span data-ttu-id="e12b1-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="e12b1-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="e12b1-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="e12b1-117">x-requestdigest</span></span>|<span data-ttu-id="e12b1-118">O resumo apropriado para o site atual</span><span class="sxs-lookup"><span data-stu-id="e12b1-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="e12b1-119">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="e12b1-119">Request body</span></span>

|<span data-ttu-id="e12b1-120">Nome</span><span class="sxs-lookup"><span data-stu-id="e12b1-120">Name</span></span>    |<span data-ttu-id="e12b1-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="e12b1-121">Type</span></span>   |<span data-ttu-id="e12b1-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="e12b1-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="e12b1-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="e12b1-123">_metadata</span></span>|  |<span data-ttu-id="e12b1-124">Definir o metadado do objeto no SPO.</span><span class="sxs-lookup"><span data-stu-id="e12b1-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="e12b1-125">Sempre use o valor: {"tipo": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="e12b1-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="e12b1-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="e12b1-126">ContentTypeGroup</span></span>|<span data-ttu-id="e12b1-127">string</span><span class="sxs-lookup"><span data-stu-id="e12b1-127">string</span></span>|<span data-ttu-id="e12b1-128">O grupo de tipo de conteúdo associado ao modelo.</span><span class="sxs-lookup"><span data-stu-id="e12b1-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="e12b1-129">Padrão para "Tipos de Conteúdo de Documento Inteligente".</span><span class="sxs-lookup"><span data-stu-id="e12b1-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="e12b1-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="e12b1-130">ContentTypeName</span></span>|<span data-ttu-id="e12b1-131">string</span><span class="sxs-lookup"><span data-stu-id="e12b1-131">string</span></span>|<span data-ttu-id="e12b1-132">O nome do tipo de conteúdo associado.</span><span class="sxs-lookup"><span data-stu-id="e12b1-132">The associated content type name.</span></span> <span data-ttu-id="e12b1-133">O arquivo de modelo criado terá o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="e12b1-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="e12b1-134">Respostas</span><span class="sxs-lookup"><span data-stu-id="e12b1-134">Responses</span></span>

| <span data-ttu-id="e12b1-135">Nome</span><span class="sxs-lookup"><span data-stu-id="e12b1-135">Name</span></span>   | <span data-ttu-id="e12b1-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="e12b1-136">Type</span></span>  | <span data-ttu-id="e12b1-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="e12b1-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="e12b1-138">201 Criado</span><span class="sxs-lookup"><span data-stu-id="e12b1-138">201 Created</span></span>| |<span data-ttu-id="e12b1-139">Êxito</span><span class="sxs-lookup"><span data-stu-id="e12b1-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="e12b1-140">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e12b1-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="e12b1-141">Criar um novo modelo de compreensão de documento chamado "Contrato Contoso"</span><span class="sxs-lookup"><span data-stu-id="e12b1-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="e12b1-142">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="e12b1-142">Sample request</span></span>

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="e12b1-143">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="e12b1-143">Sample response</span></span>

<span data-ttu-id="e12b1-144">**Código de status:** 201</span><span class="sxs-lookup"><span data-stu-id="e12b1-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="e12b1-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="e12b1-145">See also</span></span>

[<span data-ttu-id="e12b1-146">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="e12b1-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
