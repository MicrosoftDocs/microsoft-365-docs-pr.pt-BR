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
ms.openlocfilehash: cd288812044f3b02839c3c11c321947bd02cccaa
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177160"
---
# <a name="updatemodelsettings"></a><span data-ttu-id="29b38-103">UpdateModelSettings</span><span class="sxs-lookup"><span data-stu-id="29b38-103">UpdateModelSettings</span></span>

<span data-ttu-id="29b38-104">Atualiza as configurações de modelos disponíveis (descrição de modelo e rótulo de retenção associado) para um modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex (consulte [exemplo](rest-updatemodelsettings-method.md#examples)).</span><span class="sxs-lookup"><span data-stu-id="29b38-104">Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model (see [example](rest-updatemodelsettings-method.md#examples)).</span></span>

## <a name="http-request"></a><span data-ttu-id="29b38-105">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="29b38-105">HTTP request</span></span>

```HTTP
POST /_api/machinelearning/models/getbytitle('{modelFileName}')/updatemodelsettings HTTP/1.1
```

## <a name="uri-parameters"></a><span data-ttu-id="29b38-106">Parâmetros de URI</span><span class="sxs-lookup"><span data-stu-id="29b38-106">URI parameters</span></span>

|<span data-ttu-id="29b38-107">Nome</span><span class="sxs-lookup"><span data-stu-id="29b38-107">Name</span></span> |<span data-ttu-id="29b38-108">Em</span><span class="sxs-lookup"><span data-stu-id="29b38-108">In</span></span> |<span data-ttu-id="29b38-109">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="29b38-109">Required</span></span>|<span data-ttu-id="29b38-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="29b38-110">Type</span></span>|<span data-ttu-id="29b38-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="29b38-111">Description</span></span>|
|-----|---|--------|----|-----------|
|<span data-ttu-id="29b38-112">modelFileName</span><span class="sxs-lookup"><span data-stu-id="29b38-112">modelFileName</span></span>|<span data-ttu-id="29b38-113">consulta</span><span class="sxs-lookup"><span data-stu-id="29b38-113">query</span></span>|<span data-ttu-id="29b38-114">True</span><span class="sxs-lookup"><span data-stu-id="29b38-114">True</span></span>|<span data-ttu-id="29b38-115">string</span><span class="sxs-lookup"><span data-stu-id="29b38-115">string</span></span>|<span data-ttu-id="29b38-116">Nome do arquivo do modelo Syntex.</span><span class="sxs-lookup"><span data-stu-id="29b38-116">Name of the Syntex model file.</span></span>|

## <a name="request-headers"></a><span data-ttu-id="29b38-117">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="29b38-117">Request headers</span></span>

| <span data-ttu-id="29b38-118">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="29b38-118">Header</span></span> | <span data-ttu-id="29b38-119">Valor</span><span class="sxs-lookup"><span data-stu-id="29b38-119">Value</span></span> |
|--------|-------|
|<span data-ttu-id="29b38-120">Aceitar</span><span class="sxs-lookup"><span data-stu-id="29b38-120">Accept</span></span>|<span data-ttu-id="29b38-121">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="29b38-121">application/json;odata=verbose</span></span>|
|<span data-ttu-id="29b38-122">Content-Type</span><span class="sxs-lookup"><span data-stu-id="29b38-122">Content-Type</span></span>|<span data-ttu-id="29b38-123">application/json;odata=verbose;charset=utf-8</span><span class="sxs-lookup"><span data-stu-id="29b38-123">application/json;odata=verbose;charset=utf-8</span></span>|
|<span data-ttu-id="29b38-124">x-requestdigest</span><span class="sxs-lookup"><span data-stu-id="29b38-124">x-requestdigest</span></span>|<span data-ttu-id="29b38-125">O resumo apropriado para o site atual.</span><span class="sxs-lookup"><span data-stu-id="29b38-125">The appropriate digest for the current site.</span></span>|

## <a name="request-body"></a><span data-ttu-id="29b38-126">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="29b38-126">Request body</span></span>

|<span data-ttu-id="29b38-127">Nome</span><span class="sxs-lookup"><span data-stu-id="29b38-127">Name</span></span>    |<span data-ttu-id="29b38-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="29b38-128">Type</span></span>   |<span data-ttu-id="29b38-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="29b38-129">Description</span></span> |
|--------|-------|-------|
|<span data-ttu-id="29b38-130">ModelSettings</span><span class="sxs-lookup"><span data-stu-id="29b38-130">ModelSettings</span></span>|<span data-ttu-id="29b38-131">string</span><span class="sxs-lookup"><span data-stu-id="29b38-131">string</span></span>|<span data-ttu-id="29b38-132">Configurações do modelo JSON.</span><span class="sxs-lookup"><span data-stu-id="29b38-132">JSON of model settings.</span></span>|
|<span data-ttu-id="29b38-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="29b38-133">Description</span></span>|<span data-ttu-id="29b38-134">string</span><span class="sxs-lookup"><span data-stu-id="29b38-134">string</span></span>|<span data-ttu-id="29b38-135">A descrição do modelo.</span><span class="sxs-lookup"><span data-stu-id="29b38-135">The model description.</span></span>|
|<span data-ttu-id="29b38-136">RetentionLabel</span><span class="sxs-lookup"><span data-stu-id="29b38-136">RetentionLabel</span></span>| |<span data-ttu-id="29b38-137">Informações do rótulo associado (ID do rótulo e nome).</span><span class="sxs-lookup"><span data-stu-id="29b38-137">Info for the associated label (label ID and name).</span></span>|

## <a name="responses"></a><span data-ttu-id="29b38-138">Respostas</span><span class="sxs-lookup"><span data-stu-id="29b38-138">Responses</span></span>

| <span data-ttu-id="29b38-139">Nome</span><span class="sxs-lookup"><span data-stu-id="29b38-139">Name</span></span>   | <span data-ttu-id="29b38-140">Tipo</span><span class="sxs-lookup"><span data-stu-id="29b38-140">Type</span></span>  | <span data-ttu-id="29b38-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="29b38-141">Description</span></span>|
|--------|-------|------------|
|<span data-ttu-id="29b38-142">200 OK</span><span class="sxs-lookup"><span data-stu-id="29b38-142">200 OK</span></span>| |<span data-ttu-id="29b38-143">Êxito</span><span class="sxs-lookup"><span data-stu-id="29b38-143">Success</span></span>|

## <a name="examples"></a><span data-ttu-id="29b38-144">Exemplos</span><span class="sxs-lookup"><span data-stu-id="29b38-144">Examples</span></span>

### <a name="update-model-settings-for-contoso-contract"></a><span data-ttu-id="29b38-145">Atualizar as configurações do modelo para o Contrato da Contoso</span><span class="sxs-lookup"><span data-stu-id="29b38-145">Update model settings for Contoso Contract</span></span>

<span data-ttu-id="29b38-146">Nesse exemplo, a descrição do modelo e o rótulo de retenção "Standard Hold" são atualizados.</span><span class="sxs-lookup"><span data-stu-id="29b38-146">In this example, the model description and "Standard Hold" retention label are updated.</span></span> <span data-ttu-id="29b38-147">A ID do rótulo de retenção é `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span><span class="sxs-lookup"><span data-stu-id="29b38-147">The ID of the retention label is `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.</span></span>

#### <a name="sample-request"></a><span data-ttu-id="29b38-148">Solicitação de amostra</span><span class="sxs-lookup"><span data-stu-id="29b38-148">Sample request</span></span>

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a><span data-ttu-id="29b38-149">Resposta de amostra</span><span class="sxs-lookup"><span data-stu-id="29b38-149">Sample response</span></span>

<span data-ttu-id="29b38-150">**Código de status:** 200</span><span class="sxs-lookup"><span data-stu-id="29b38-150">**Status code:** 200</span></span>

## <a name="see-also"></a><span data-ttu-id="29b38-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="29b38-151">See also</span></span>

[<span data-ttu-id="29b38-152">API REST do modelo de compreensão de documentos do Syntex</span><span class="sxs-lookup"><span data-stu-id="29b38-152">Syntex document understanding model REST API</span></span>](syntex-model-rest-api.md)
