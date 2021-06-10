---
title: Importar API de indicadores
description: Saiba como usar o lote de importação da API de indicador no Microsoft Defender para Ponto de Extremidade.
keywords: apis, apis com suporte, enviar, ti, indicador, atualização
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198240"
---
# <a name="import-indicators-api"></a><span data-ttu-id="6c897-104">Importar API de indicadores</span><span class="sxs-lookup"><span data-stu-id="6c897-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6c897-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6c897-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6c897-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6c897-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6c897-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6c897-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="6c897-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="6c897-108">API description</span></span>
<span data-ttu-id="6c897-109">Envia ou atualiza o lote de entidades [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="6c897-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="6c897-110">A notação CIDR para IPs não é suportada.</span><span class="sxs-lookup"><span data-stu-id="6c897-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="6c897-111">Limitações</span><span class="sxs-lookup"><span data-stu-id="6c897-111">Limitations</span></span>
1. <span data-ttu-id="6c897-112">Limitações de taxa para essa API são 30 chamadas por minuto.</span><span class="sxs-lookup"><span data-stu-id="6c897-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="6c897-113">Há um limite de 15.000 Indicadores [ativos](ti-indicator.md) por locatário.</span><span class="sxs-lookup"><span data-stu-id="6c897-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="6c897-114">O tamanho máximo de lote para uma chamada de API é 500.</span><span class="sxs-lookup"><span data-stu-id="6c897-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="6c897-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="6c897-115">Permissions</span></span>
<span data-ttu-id="6c897-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="6c897-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6c897-117">Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="6c897-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="6c897-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="6c897-118">Permission type</span></span> |   <span data-ttu-id="6c897-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="6c897-119">Permission</span></span>  |   <span data-ttu-id="6c897-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="6c897-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6c897-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="6c897-121">Application</span></span> |   <span data-ttu-id="6c897-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6c897-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="6c897-123">'Indicadores de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="6c897-123">'Read and write Indicators'</span></span>
<span data-ttu-id="6c897-124">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="6c897-124">Application</span></span> |   <span data-ttu-id="6c897-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="6c897-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="6c897-126">'Ler e gravar Todos os Indicadores'</span><span class="sxs-lookup"><span data-stu-id="6c897-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="6c897-127">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="6c897-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="6c897-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6c897-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="6c897-129">'Indicadores de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="6c897-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="6c897-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="6c897-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="6c897-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="6c897-131">Request headers</span></span>

<span data-ttu-id="6c897-132">Nome</span><span class="sxs-lookup"><span data-stu-id="6c897-132">Name</span></span> | <span data-ttu-id="6c897-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="6c897-133">Type</span></span> | <span data-ttu-id="6c897-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="6c897-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="6c897-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="6c897-135">Authorization</span></span> | <span data-ttu-id="6c897-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6c897-136">String</span></span> | <span data-ttu-id="6c897-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="6c897-137">Bearer {token}.</span></span> <span data-ttu-id="6c897-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="6c897-138">**Required**.</span></span>
<span data-ttu-id="6c897-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="6c897-139">Content-Type</span></span> | <span data-ttu-id="6c897-140">string</span><span class="sxs-lookup"><span data-stu-id="6c897-140">string</span></span> | <span data-ttu-id="6c897-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="6c897-141">application/json.</span></span> <span data-ttu-id="6c897-142">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="6c897-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="6c897-143">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="6c897-143">Request body</span></span>
<span data-ttu-id="6c897-144">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="6c897-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="6c897-145">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="6c897-145">Parameter</span></span> | <span data-ttu-id="6c897-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="6c897-146">Type</span></span>    | <span data-ttu-id="6c897-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="6c897-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="6c897-148">Indicadores</span><span class="sxs-lookup"><span data-stu-id="6c897-148">Indicators</span></span> | <span data-ttu-id="6c897-149">Indicador de<[de lista](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="6c897-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="6c897-150">Lista de [indicadores](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="6c897-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="6c897-151">**Required**</span><span class="sxs-lookup"><span data-stu-id="6c897-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="6c897-152">Resposta</span><span class="sxs-lookup"><span data-stu-id="6c897-152">Response</span></span>
- <span data-ttu-id="6c897-153">Se tiver êxito, este método retornará 200 - código de resposta OK com uma lista de resultados de importação por indicador, consulte o exemplo abaixo.</span><span class="sxs-lookup"><span data-stu-id="6c897-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="6c897-154">Se não tiver êxito: este método retornará 400 - Solicitação Ruim.</span><span class="sxs-lookup"><span data-stu-id="6c897-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="6c897-155">A solicitação incorreta geralmente indica o corpo incorreto.</span><span class="sxs-lookup"><span data-stu-id="6c897-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="6c897-156">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6c897-156">Example</span></span>

<span data-ttu-id="6c897-157">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="6c897-157">**Request**</span></span>

<span data-ttu-id="6c897-158">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="6c897-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="6c897-159">**Response**</span><span class="sxs-lookup"><span data-stu-id="6c897-159">**Response**</span></span>

<span data-ttu-id="6c897-160">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="6c897-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="6c897-161">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6c897-161">Related topic</span></span>
- [<span data-ttu-id="6c897-162">Gerenciar indicadores</span><span class="sxs-lookup"><span data-stu-id="6c897-162">Manage indicators</span></span>](manage-indicators.md)
