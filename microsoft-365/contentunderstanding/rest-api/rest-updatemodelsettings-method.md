---
title: UpdateModelSettings
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
description: Use a API REST para atualizar as configurações de modelos disponíveis para um modelo de compreensão de documentos.
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904153"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="13635-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="13635-103">UpdateModelSettings</span></span>

<span data-ttu-id="13635-104">Atualiza as configurações de modelos disponíveis (descrição de modelo e rótulo de retenção associado) para um modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex (consulte [exemplo](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="13635-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="13635-105">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="13635-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="13635-106">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="13635-106">URI parameters</span></span>

<span data-ttu-id="13635-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="13635-107">None</span></span>

## <a name="request-headers"></a><span data-ttu-id="13635-108">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="13635-108">Request headers</span></span>

| <span data-ttu-id="13635-109">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="13635-109">Header</span></span> | <span data-ttu-id="13635-110">Valor</span><span class="sxs-lookup"><span data-stu-id="13635-110">Value</span></span> |
|--------|-------|
|<span data-ttu-id="13635-111">Aceitar</span><span class="sxs-lookup"><span data-stu-id="13635-111">Accept</span></span>|<span data-ttu-id="13635-112">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="13635-112">application/json;odata=verbose</span></span>|
|<span data-ttu-id="13635-113">Content-Type</span><span class="sxs-lookup"><span data-stu-id="13635-113">Content-Type</span></span>|<span data-ttu-id="13635-114">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="13635-114">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="13635-115">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="13635-115">x-requestdigest</span></span>|<span data-ttu-id="13635-116">O resumo apropriado para o site atual.</span><span class="sxs-lookup"><span data-stu-id="13635-116">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="13635-117">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="13635-117">Request body</span></span>

|<span data-ttu-id="13635-118">Nome</span><span class="sxs-lookup"><span data-stu-id="13635-118">Name</span></span>    |<span data-ttu-id="13635-119">Tipo</span><span class="sxs-lookup"><span data-stu-id="13635-119">Type</span></span>   |<span data-ttu-id="13635-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="13635-120">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="13635-121">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="13635-121">ModelSettings</span></span>|<span data-ttu-id="13635-122">string</span><span class="sxs-lookup"><span data-stu-id="13635-122">string</span></span>|<span data-ttu-id="13635-123">Configurações do modelo JSON.</span><span class="sxs-lookup"><span data-stu-id="13635-123">JSON of model settings.</span></span>|
|<span data-ttu-id="13635-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="13635-124">Description</span></span>|<span data-ttu-id="13635-125">string</span><span class="sxs-lookup"><span data-stu-id="13635-125">string</span></span>|<span data-ttu-id="13635-126">A descrição do modelo.</span><span class="sxs-lookup"><span data-stu-id="13635-126">The model description.</span></span>|
|<span data-ttu-id="13635-127">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="13635-127">RetentionLabel</span></span>| |<span data-ttu-id="13635-128">Informações do rótulo associado (ID do rótulo e nome).</span><span class="sxs-lookup"><span data-stu-id="13635-128">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="13635-129">Respostas</span><span class="sxs-lookup"><span data-stu-id="13635-129">Responses</span></span>

| <span data-ttu-id="13635-130">Nome</span><span class="sxs-lookup"><span data-stu-id="13635-130">Name</span></span>   | <span data-ttu-id="13635-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="13635-131">Type</span></span>  | <span data-ttu-id="13635-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="13635-132">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="13635-133">200 OK</span><span class="sxs-lookup"><span data-stu-id="13635-133">200 OK</span></span>| |<span data-ttu-id="13635-134">Êxito</span><span class="sxs-lookup"><span data-stu-id="13635-134">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="13635-135">Exemplos</span><span class="sxs-lookup"><span data-stu-id="13635-135">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="13635-136">Atualizar as configurações do modelo para o Contrato da Contoso</span><span class="sxs-lookup"><span data-stu-id="13635-136">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="13635-137">Nesse exemplo, a descrição do modelo e o rótulo de retenção "Standard Hold" são atualizados.</span><span class="sxs-lookup"><span data-stu-id="13635-137">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="13635-138">A ID do rótulo de retenção é `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="13635-138">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="13635-139">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="13635-139">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="13635-140">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="13635-140">Sample response</span></span>

<span data-ttu-id="13635-141">**Código de status:** 200</span><span class="sxs-lookup"><span data-stu-id="13635-141">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="13635-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="13635-142">See also</span></span>

[<span data-ttu-id="13635-143">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="13635-143">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
