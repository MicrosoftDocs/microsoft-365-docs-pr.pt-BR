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
ms.openlocfilehash: 0a1b6ef9b7e38f2c4f52082103530da432e3e855
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177148"
---
# <a name="create-model"></a><span data-ttu-id="6b5ec-103">Criar um modelo</span><span class="sxs-lookup"><span data-stu-id="6b5ec-103">Create model</span></span>

<span data-ttu-id="6b5ec-104">Cria um modelo e seu tipo de conteúdo associado.</span><span class="sxs-lookup"><span data-stu-id="6b5ec-104">Creates a model and its associated content type.</span></span> <span data-ttu-id="6b5ec-105">Observe que isso apenas cria o modelo.</span><span class="sxs-lookup"><span data-stu-id="6b5ec-105">Note that this only creates the model.</span></span> <span data-ttu-id="6b5ec-106">Ele ainda precisará ser treinado no centro de conteúdo (consulte [exemplos](rest-createmodel-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="6b5ec-106">It will still need to be trained in the content center (see [example](rest-createmodel-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="6b5ec-107">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="6b5ec-107">HTTP request</span></span>

```
POST /_api/machinelearning/models HTTP/1.1
```
## <a name="uri-parameters"></a><span data-ttu-id="6b5ec-108">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="6b5ec-108">URI Parameters</span></span>

<span data-ttu-id="6b5ec-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6b5ec-109">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="6b5ec-110">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="6b5ec-110">Request headers</span></span>

| <span data-ttu-id="6b5ec-111">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="6b5ec-111">Header</span></span> | <span data-ttu-id="6b5ec-112">Valor</span><span class="sxs-lookup"><span data-stu-id="6b5ec-112">Value</span></span> |
|--------|-------|
|<span data-ttu-id="6b5ec-113">Aceitar</span><span class="sxs-lookup"><span data-stu-id="6b5ec-113">Accept</span></span>|<span data-ttu-id="6b5ec-114">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="6b5ec-114">application/json;odata=verbose</span></span>|
|<span data-ttu-id="6b5ec-115">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6b5ec-115">Content-Type</span></span>|<span data-ttu-id="6b5ec-116">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="6b5ec-116">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="6b5ec-117">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="6b5ec-117">x-requestdigest</span></span>|<span data-ttu-id="6b5ec-118">O resumo apropriado para o site atual</span><span class="sxs-lookup"><span data-stu-id="6b5ec-118">The appropriate digest for current site</span></span>|

## <a name="request-body"></a><span data-ttu-id="6b5ec-119">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="6b5ec-119">Request body</span></span>

|<span data-ttu-id="6b5ec-120">Nome</span><span class="sxs-lookup"><span data-stu-id="6b5ec-120">Name</span></span>    |<span data-ttu-id="6b5ec-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="6b5ec-121">Type</span></span>   |<span data-ttu-id="6b5ec-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="6b5ec-122">Description</span></span> |
|--------|-------|------------|
|<span data-ttu-id="6b5ec-123">_metadata</span><span class="sxs-lookup"><span data-stu-id="6b5ec-123">_metadata</span></span>|  |<span data-ttu-id="6b5ec-124">Definir o metadado do objeto no SPO.</span><span class="sxs-lookup"><span data-stu-id="6b5ec-124">Set the object meta on the SPO.</span></span> <span data-ttu-id="6b5ec-125">Sempre use o valor: {"tipo": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span><span class="sxs-lookup"><span data-stu-id="6b5ec-125">Always use the value: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}.</span></span> |
|<span data-ttu-id="6b5ec-126">ContentTypeGroup</span><span class="sxs-lookup"><span data-stu-id="6b5ec-126">ContentTypeGroup</span></span>|<span data-ttu-id="6b5ec-127">string</span><span class="sxs-lookup"><span data-stu-id="6b5ec-127">string</span></span>|<span data-ttu-id="6b5ec-128">O grupo de tipo de conteúdo associado ao modelo.</span><span class="sxs-lookup"><span data-stu-id="6b5ec-128">The associated content type group associated with the model.</span></span> <span data-ttu-id="6b5ec-129">Padrão para "Tipos de Conteúdo de Documento Inteligente".</span><span class="sxs-lookup"><span data-stu-id="6b5ec-129">Defaulted to "Intelligent Document Content Types".</span></span>|
|<span data-ttu-id="6b5ec-130">ContentTypeName</span><span class="sxs-lookup"><span data-stu-id="6b5ec-130">ContentTypeName</span></span>|<span data-ttu-id="6b5ec-131">string</span><span class="sxs-lookup"><span data-stu-id="6b5ec-131">string</span></span>|<span data-ttu-id="6b5ec-132">O nome do tipo de conteúdo associado.</span><span class="sxs-lookup"><span data-stu-id="6b5ec-132">The associated content type name.</span></span> <span data-ttu-id="6b5ec-133">O arquivo de modelo criado terá o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="6b5ec-133">The created model file will have the same name.</span></span>|

## <a name="responses"></a><span data-ttu-id="6b5ec-134">Respostas</span><span class="sxs-lookup"><span data-stu-id="6b5ec-134">Responses</span></span>

| <span data-ttu-id="6b5ec-135">Nome</span><span class="sxs-lookup"><span data-stu-id="6b5ec-135">Name</span></span>   | <span data-ttu-id="6b5ec-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="6b5ec-136">Type</span></span>  | <span data-ttu-id="6b5ec-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="6b5ec-137">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="6b5ec-138">201 Criado</span><span class="sxs-lookup"><span data-stu-id="6b5ec-138">201 Created</span></span>| |<span data-ttu-id="6b5ec-139">Êxito</span><span class="sxs-lookup"><span data-stu-id="6b5ec-139">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="6b5ec-140">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6b5ec-140">Examples</span></span>

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a><span data-ttu-id="6b5ec-141">Criar um novo modelo de compreensão de documento chamado "Contrato Contoso"</span><span class="sxs-lookup"><span data-stu-id="6b5ec-141">Create a new document understanding model called "Contoso Contract"</span></span>

#### <a name="sample-request"></a><span data-ttu-id="6b5ec-142">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="6b5ec-142">Sample request</span></span>

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a><span data-ttu-id="6b5ec-143">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="6b5ec-143">Sample response</span></span>

<span data-ttu-id="6b5ec-144">**Código de status:** 201</span><span class="sxs-lookup"><span data-stu-id="6b5ec-144">**Status code:** 201</span></span>

## <a name="see-also"></a><span data-ttu-id="6b5ec-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="6b5ec-145">See also</span></span>

[<span data-ttu-id="6b5ec-146">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="6b5ec-146">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
