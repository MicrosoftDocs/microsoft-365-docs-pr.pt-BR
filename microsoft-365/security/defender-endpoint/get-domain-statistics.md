---
title: Obter API de estatísticas de domínio
description: Saiba como usar a API Obter estatísticas de domínio para recuperar as estatísticas sobre o domínio determinado no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, domínio, dispositivos relacionados ao domínio
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d2edc5d429d124412134b466753b65506d2dd7a9
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772180"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="07d15-104">Obter API de estatísticas de domínio</span><span class="sxs-lookup"><span data-stu-id="07d15-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07d15-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="07d15-105">**Applies to:**</span></span>
- [<span data-ttu-id="07d15-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="07d15-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="07d15-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07d15-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="07d15-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="07d15-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="07d15-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="07d15-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="07d15-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="07d15-110">API description</span></span>
<span data-ttu-id="07d15-111">Recupera as estatísticas no domínio determinado.</span><span class="sxs-lookup"><span data-stu-id="07d15-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="07d15-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="07d15-112">Limitations</span></span>
1. <span data-ttu-id="07d15-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="07d15-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="07d15-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="07d15-114">Permissions</span></span>
<span data-ttu-id="07d15-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="07d15-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="07d15-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="07d15-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="07d15-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="07d15-117">Permission type</span></span> |   <span data-ttu-id="07d15-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="07d15-118">Permission</span></span>  |   <span data-ttu-id="07d15-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="07d15-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="07d15-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="07d15-120">Application</span></span> |   <span data-ttu-id="07d15-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="07d15-121">URL.Read.All</span></span> |  <span data-ttu-id="07d15-122">'URLs de leitura'</span><span class="sxs-lookup"><span data-stu-id="07d15-122">'Read URLs'</span></span>
<span data-ttu-id="07d15-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="07d15-123">Delegated (work or school account)</span></span> | <span data-ttu-id="07d15-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="07d15-124">URL.Read.All</span></span> | <span data-ttu-id="07d15-125">'URLs de leitura'</span><span class="sxs-lookup"><span data-stu-id="07d15-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="07d15-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="07d15-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="07d15-127">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="07d15-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="07d15-128">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="07d15-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="07d15-129">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="07d15-129">Request headers</span></span>

<span data-ttu-id="07d15-130">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="07d15-130">Header</span></span> | <span data-ttu-id="07d15-131">Valor</span><span class="sxs-lookup"><span data-stu-id="07d15-131">Value</span></span> 
:---|:---
<span data-ttu-id="07d15-132">Autorização</span><span class="sxs-lookup"><span data-stu-id="07d15-132">Authorization</span></span> | <span data-ttu-id="07d15-133">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="07d15-133">Bearer {token}.</span></span> <span data-ttu-id="07d15-134">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="07d15-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="07d15-135">Solicitar parâmetros URI</span><span class="sxs-lookup"><span data-stu-id="07d15-135">Request URI parameters</span></span>

<span data-ttu-id="07d15-136">Nome</span><span class="sxs-lookup"><span data-stu-id="07d15-136">Name</span></span> | <span data-ttu-id="07d15-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="07d15-137">Type</span></span> | <span data-ttu-id="07d15-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="07d15-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="07d15-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="07d15-139">lookBackHours</span></span> | <span data-ttu-id="07d15-140">Int32</span><span class="sxs-lookup"><span data-stu-id="07d15-140">Int32</span></span> | <span data-ttu-id="07d15-141">Define as horas que pesquisamos de volta para obter as estatísticas.</span><span class="sxs-lookup"><span data-stu-id="07d15-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="07d15-142">O padrão é 30 dias.</span><span class="sxs-lookup"><span data-stu-id="07d15-142">Defaults to 30 days.</span></span> <span data-ttu-id="07d15-143">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="07d15-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="07d15-144">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="07d15-144">Request body</span></span>
<span data-ttu-id="07d15-145">Vazio</span><span class="sxs-lookup"><span data-stu-id="07d15-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="07d15-146">Resposta</span><span class="sxs-lookup"><span data-stu-id="07d15-146">Response</span></span>
<span data-ttu-id="07d15-147">Se bem-sucedido e o domínio existir - 200 OK, com o objeto statistics no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="07d15-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="07d15-148">Se o domínio não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="07d15-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="07d15-149">Exemplo</span><span class="sxs-lookup"><span data-stu-id="07d15-149">Example</span></span>

<span data-ttu-id="07d15-150">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="07d15-150">**Request**</span></span>

<span data-ttu-id="07d15-151">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="07d15-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="07d15-152">**Response**</span><span class="sxs-lookup"><span data-stu-id="07d15-152">**Response**</span></span>

<span data-ttu-id="07d15-153">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="07d15-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
