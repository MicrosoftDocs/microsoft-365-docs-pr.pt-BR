---
title: Excluir API de Indicador.
description: Saiba como usar a API Excluir Indicador para excluir uma entidade Indicator por ID no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api pública, apis com suporte, excluir, indicador ti, entidade, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1305be897dff6932713cf294eb4e5cd53692681c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166346"
---
# <a name="delete-indicator-api"></a><span data-ttu-id="4709a-104">Excluir API de Indicador</span><span class="sxs-lookup"><span data-stu-id="4709a-104">Delete Indicator API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4709a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4709a-105">**Applies to:**</span></span>
- [<span data-ttu-id="4709a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4709a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4709a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4709a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4709a-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4709a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4709a-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4709a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)  

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4709a-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="4709a-110">API description</span></span>
<span data-ttu-id="4709a-111">Exclui uma [entidade Indicator](ti-indicator.md) por ID.</span><span class="sxs-lookup"><span data-stu-id="4709a-111">Deletes an [Indicator](ti-indicator.md) entity by ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="4709a-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="4709a-112">Limitations</span></span>
1. <span data-ttu-id="4709a-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="4709a-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4709a-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="4709a-114">Permissions</span></span>
<span data-ttu-id="4709a-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="4709a-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4709a-116">Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4709a-116">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="4709a-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="4709a-117">Permission type</span></span> |   <span data-ttu-id="4709a-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="4709a-118">Permission</span></span>  |   <span data-ttu-id="4709a-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="4709a-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4709a-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="4709a-120">Application</span></span> |   <span data-ttu-id="4709a-121">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4709a-121">Ti.ReadWrite</span></span> |  <span data-ttu-id="4709a-122">'Indicadores de TI de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="4709a-122">'Read and write TI Indicators'</span></span>
<span data-ttu-id="4709a-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="4709a-123">Application</span></span> |   <span data-ttu-id="4709a-124">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4709a-124">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="4709a-125">'Indicadores de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="4709a-125">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="4709a-126">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="4709a-126">HTTP request</span></span>
```
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a><span data-ttu-id="4709a-127">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="4709a-127">Request headers</span></span>

<span data-ttu-id="4709a-128">Nome</span><span class="sxs-lookup"><span data-stu-id="4709a-128">Name</span></span> | <span data-ttu-id="4709a-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="4709a-129">Type</span></span> | <span data-ttu-id="4709a-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="4709a-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="4709a-131">Autorização</span><span class="sxs-lookup"><span data-stu-id="4709a-131">Authorization</span></span> | <span data-ttu-id="4709a-132">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4709a-132">String</span></span> | <span data-ttu-id="4709a-133">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="4709a-133">Bearer {token}.</span></span> <span data-ttu-id="4709a-134">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="4709a-134">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4709a-135">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="4709a-135">Request body</span></span>
<span data-ttu-id="4709a-136">Vazio</span><span class="sxs-lookup"><span data-stu-id="4709a-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4709a-137">Resposta</span><span class="sxs-lookup"><span data-stu-id="4709a-137">Response</span></span>
<span data-ttu-id="4709a-138">Se Indicator existir e excluído com êxito - 204 OK sem conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4709a-138">If Indicator exist and deleted successfully - 204 OK without content.</span></span>
<span data-ttu-id="4709a-139">Se Indicator com a id especificada não for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="4709a-139">If Indicator with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="4709a-140">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4709a-140">Example</span></span>

<span data-ttu-id="4709a-141">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="4709a-141">**Request**</span></span>

<span data-ttu-id="4709a-142">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="4709a-142">Here is an example of the request.</span></span>

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
