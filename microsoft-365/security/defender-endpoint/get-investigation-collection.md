---
title: API de Investigações de Lista
description: Usar essa API para criar chamadas relacionadas a obter a coleção Investigations
keywords: apis, api gráfica, apis com suporte, coleção Investigations
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
ms.openlocfilehash: 9ad1216a05846b48bff4186c7e6f39e9da3623b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166348"
---
# <a name="list-investigations-api"></a><span data-ttu-id="03211-104">API de Investigações de Lista</span><span class="sxs-lookup"><span data-stu-id="03211-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="03211-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="03211-105">**Applies to:**</span></span>
- [<span data-ttu-id="03211-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="03211-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="03211-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03211-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="03211-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="03211-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="03211-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="03211-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="03211-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="03211-110">API description</span></span>
<span data-ttu-id="03211-111">Recupera uma coleção de [Investigações](investigation.md).</span><span class="sxs-lookup"><span data-stu-id="03211-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="03211-112">Oferece suporte [a consultas OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="03211-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="03211-113">A consulta OData tem suporte ```$filter``` em: ```startTime``` , e ```state``` ```machineId``` ```triggeringAlertId``` propriedades.</span><span class="sxs-lookup"><span data-stu-id="03211-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="03211-114">Consulte exemplos em [Consultas OData com o Microsoft Defender para Ponto de Extremidade](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="03211-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="03211-115">Limitações</span><span class="sxs-lookup"><span data-stu-id="03211-115">Limitations</span></span>
1. <span data-ttu-id="03211-116">O tamanho máximo da página é 10.000.</span><span class="sxs-lookup"><span data-stu-id="03211-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="03211-117">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="03211-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="03211-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="03211-118">Permissions</span></span>
<span data-ttu-id="03211-119">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="03211-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="03211-120">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="03211-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="03211-121">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="03211-121">Permission type</span></span> |   <span data-ttu-id="03211-122">Permissão</span><span class="sxs-lookup"><span data-stu-id="03211-122">Permission</span></span>  |   <span data-ttu-id="03211-123">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="03211-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="03211-124">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="03211-124">Application</span></span> |   <span data-ttu-id="03211-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="03211-125">Alert.Read.All</span></span> |    <span data-ttu-id="03211-126">'Ler todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="03211-126">'Read all alerts'</span></span>
<span data-ttu-id="03211-127">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="03211-127">Application</span></span> |   <span data-ttu-id="03211-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="03211-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="03211-129">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="03211-129">'Read and write all alerts'</span></span>
<span data-ttu-id="03211-130">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="03211-130">Delegated (work or school account)</span></span> | <span data-ttu-id="03211-131">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="03211-131">Alert.Read</span></span> | <span data-ttu-id="03211-132">'Alertas de leitura'</span><span class="sxs-lookup"><span data-stu-id="03211-132">'Read alerts'</span></span>
<span data-ttu-id="03211-133">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="03211-133">Delegated (work or school account)</span></span> | <span data-ttu-id="03211-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="03211-134">Alert.ReadWrite</span></span> | <span data-ttu-id="03211-135">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="03211-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="03211-136">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="03211-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="03211-137">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="03211-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="03211-138">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="03211-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="03211-139">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="03211-139">Request headers</span></span>

<span data-ttu-id="03211-140">Nome</span><span class="sxs-lookup"><span data-stu-id="03211-140">Name</span></span> | <span data-ttu-id="03211-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="03211-141">Type</span></span> | <span data-ttu-id="03211-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="03211-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="03211-143">Autorização</span><span class="sxs-lookup"><span data-stu-id="03211-143">Authorization</span></span> | <span data-ttu-id="03211-144">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="03211-144">String</span></span> | <span data-ttu-id="03211-145">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="03211-145">Bearer {token}.</span></span> <span data-ttu-id="03211-146">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="03211-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="03211-147">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="03211-147">Request body</span></span>
<span data-ttu-id="03211-148">Vazio</span><span class="sxs-lookup"><span data-stu-id="03211-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="03211-149">Resposta</span><span class="sxs-lookup"><span data-stu-id="03211-149">Response</span></span>
<span data-ttu-id="03211-150">Se tiver êxito, este método retornará 200, código de resposta Ok com uma coleção [de entidades de Investigações.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="03211-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="03211-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="03211-151">Example</span></span>

<span data-ttu-id="03211-152">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="03211-152">**Request**</span></span>

<span data-ttu-id="03211-153">Aqui está um exemplo de uma solicitação para obter todas as investigações:</span><span class="sxs-lookup"><span data-stu-id="03211-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="03211-154">**Response**</span><span class="sxs-lookup"><span data-stu-id="03211-154">**Response**</span></span>

<span data-ttu-id="03211-155">Veja um exemplo da resposta:</span><span class="sxs-lookup"><span data-stu-id="03211-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
