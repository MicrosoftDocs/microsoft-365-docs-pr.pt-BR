---
title: API de Indicadores de Lista
description: Saiba como usar a API indicadores de lista para recuperar uma coleção de todos os Indicadores ativos no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api pública, apis com suporte, coleção Indicators
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 868fd141cda3b3d92464a2d9247780e0e74d6de8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198548"
---
# <a name="list-indicators-api"></a><span data-ttu-id="39bf7-104">API de Indicadores de Lista</span><span class="sxs-lookup"><span data-stu-id="39bf7-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="39bf7-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="39bf7-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="39bf7-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="39bf7-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="39bf7-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="39bf7-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="39bf7-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="39bf7-108">API description</span></span>
<span data-ttu-id="39bf7-109">Recupera uma coleção de todos os [Indicadores ativos.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="39bf7-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="39bf7-110">Oferece suporte [a consultas OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="39bf7-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="39bf7-111">A consulta OData tem suporte ```$filter``` em: ```indicatorValue``` , , , e ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` ```severity``` propriedades.</span><span class="sxs-lookup"><span data-stu-id="39bf7-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="39bf7-112">Consulte exemplos em [Consultas OData com o Microsoft Defender para Ponto de Extremidade](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="39bf7-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="39bf7-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="39bf7-113">Limitations</span></span>
1. <span data-ttu-id="39bf7-114">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="39bf7-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="39bf7-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="39bf7-115">Permissions</span></span>
<span data-ttu-id="39bf7-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="39bf7-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="39bf7-117">Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="39bf7-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="39bf7-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="39bf7-118">Permission type</span></span> |   <span data-ttu-id="39bf7-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="39bf7-119">Permission</span></span>  |   <span data-ttu-id="39bf7-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="39bf7-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="39bf7-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="39bf7-121">Application</span></span> |   <span data-ttu-id="39bf7-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="39bf7-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="39bf7-123">'Indicadores de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="39bf7-123">'Read and write Indicators'</span></span>
<span data-ttu-id="39bf7-124">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="39bf7-124">Application</span></span> |   <span data-ttu-id="39bf7-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="39bf7-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="39bf7-126">'Ler e gravar Todos os Indicadores'</span><span class="sxs-lookup"><span data-stu-id="39bf7-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="39bf7-127">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="39bf7-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="39bf7-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="39bf7-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="39bf7-129">'Indicadores de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="39bf7-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="39bf7-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="39bf7-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="39bf7-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="39bf7-131">Request headers</span></span>

<span data-ttu-id="39bf7-132">Nome</span><span class="sxs-lookup"><span data-stu-id="39bf7-132">Name</span></span> | <span data-ttu-id="39bf7-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="39bf7-133">Type</span></span> | <span data-ttu-id="39bf7-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="39bf7-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="39bf7-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="39bf7-135">Authorization</span></span> | <span data-ttu-id="39bf7-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39bf7-136">String</span></span> | <span data-ttu-id="39bf7-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="39bf7-137">Bearer {token}.</span></span> <span data-ttu-id="39bf7-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="39bf7-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="39bf7-139">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="39bf7-139">Request body</span></span>
<span data-ttu-id="39bf7-140">Vazio</span><span class="sxs-lookup"><span data-stu-id="39bf7-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="39bf7-141">Resposta</span><span class="sxs-lookup"><span data-stu-id="39bf7-141">Response</span></span>
<span data-ttu-id="39bf7-142">Se tiver êxito, este método retornará 200, código de resposta Ok com uma coleção de entidades [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="39bf7-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="39bf7-143">Se o aplicativo tiver permissão 'Ti.ReadWrite.All', ele será exposto a todos os Indicadores.</span><span class="sxs-lookup"><span data-stu-id="39bf7-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="39bf7-144">Caso contrário, ele será exposto somente aos Indicadores criados.</span><span class="sxs-lookup"><span data-stu-id="39bf7-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="39bf7-145">Exemplo 1:</span><span class="sxs-lookup"><span data-stu-id="39bf7-145">Example 1:</span></span>

<span data-ttu-id="39bf7-146">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="39bf7-146">**Request**</span></span>

<span data-ttu-id="39bf7-147">Aqui está um exemplo de uma solicitação que obtém todos os Indicadores</span><span class="sxs-lookup"><span data-stu-id="39bf7-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="39bf7-148">**Response**</span><span class="sxs-lookup"><span data-stu-id="39bf7-148">**Response**</span></span>

<span data-ttu-id="39bf7-149">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="39bf7-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="39bf7-150">Exemplo 2:</span><span class="sxs-lookup"><span data-stu-id="39bf7-150">Example 2:</span></span>

<span data-ttu-id="39bf7-151">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="39bf7-151">**Request**</span></span>

<span data-ttu-id="39bf7-152">Aqui está um exemplo de uma solicitação que obtém todos os Indicadores com a ação "AlertAndBlock"</span><span class="sxs-lookup"><span data-stu-id="39bf7-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="39bf7-153">**Response**</span><span class="sxs-lookup"><span data-stu-id="39bf7-153">**Response**</span></span>

<span data-ttu-id="39bf7-154">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="39bf7-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
