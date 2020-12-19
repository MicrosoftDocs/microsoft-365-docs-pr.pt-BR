---
title: API de busca avançada do Microsoft 365 defender
description: Saiba como executar consultas de busca avançada usando a API de busca avançada do Microsoft 365 defender
keywords: Caça avançada, APIs, API, MTP, M365 defender, Microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e7cd9192ec25e01ed06b77cb2b39357cb9df79bd
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719375"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="b0b5f-104">API de busca avançada do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b0b5f-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b0b5f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b0b5f-105">**Applies to:**</span></span>

- <span data-ttu-id="b0b5f-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0b5f-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0b5f-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b0b5f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b0b5f-109">A [busca avançada](advanced-hunting-overview.md) é uma ferramenta de busca de ameaças que usa [consultas especialmente construídas](advanced-hunting-query-language.md) para examinar os últimos 30 dias de dados de evento no Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="b0b5f-110">Você pode usar consultas de busca avançada para inspecionar atividades anormais, detectar possíveis ameaças e até mesmo responder a ataques.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="b0b5f-111">A API de busca avançada permite que você consulte programaticamente dados de eventos.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="b0b5f-112">Cotas e alocação de recursos</span><span class="sxs-lookup"><span data-stu-id="b0b5f-112">Quotas and resource allocation</span></span>

<span data-ttu-id="b0b5f-113">As condições a seguir se relacionam a todas as consultas.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="b0b5f-114">As consultas exploram e retornam dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="b0b5f-115">Os resultados podem retornar até 100.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="b0b5f-116">Você pode fazer até 10 chamadas por minuto por locatário.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-116">You can make up to 10 calls per minute per tenant.</span></span>
4. <span data-ttu-id="b0b5f-117">Você tem 10 minutos de tempo de execução por hora por locatário.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="b0b5f-118">Você tem quatro horas de tempo de execução por locatário.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-118">You have four total hours of running time day per tenant.</span></span>
6. <span data-ttu-id="b0b5f-119">Se uma única solicitação for executada por mais de 10 minutos, o tempo limite expirará e retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="b0b5f-120">Um `429` código de resposta http indica que você atingiu uma cota, seja pelo número de solicitações enviadas ou pelo tempo de execução alocado.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="b0b5f-121">O corpo da resposta incluirá o tempo até que a cota que você atingiu seja redefinida.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-121">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="b0b5f-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="b0b5f-122">Permissions</span></span>

<span data-ttu-id="b0b5f-123">Uma das seguintes permissões é necessária para chamar a API de busca avançada.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-123">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="b0b5f-124">Para saber mais, incluindo como escolher permissões, confira [acessar as APIs de proteção do Microsoft 365 defender](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="b0b5f-124">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="b0b5f-125">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="b0b5f-125">Permission type</span></span> | <span data-ttu-id="b0b5f-126">Permissão</span><span class="sxs-lookup"><span data-stu-id="b0b5f-126">Permission</span></span> | <span data-ttu-id="b0b5f-127">Nome para exibição da permissão</span><span class="sxs-lookup"><span data-stu-id="b0b5f-127">Permission display name</span></span>
-|-|-
<span data-ttu-id="b0b5f-128">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="b0b5f-128">Application</span></span> | <span data-ttu-id="b0b5f-129">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="b0b5f-129">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="b0b5f-130">Executar consultas avançadas</span><span class="sxs-lookup"><span data-stu-id="b0b5f-130">Run advanced queries</span></span>
<span data-ttu-id="b0b5f-131">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="b0b5f-131">Delegated (work or school account)</span></span> | <span data-ttu-id="b0b5f-132">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="b0b5f-132">AdvancedHunting.Read</span></span> | <span data-ttu-id="b0b5f-133">Executar consultas avançadas</span><span class="sxs-lookup"><span data-stu-id="b0b5f-133">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="b0b5f-134">Ao obter um token usando as credenciais do usuário:</span><span class="sxs-lookup"><span data-stu-id="b0b5f-134">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="b0b5f-135">O usuário precisa ter a função de AD ' exibir dados '</span><span class="sxs-lookup"><span data-stu-id="b0b5f-135">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="b0b5f-136">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-136">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="b0b5f-137">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="b0b5f-137">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="b0b5f-138">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="b0b5f-138">Request headers</span></span>

<span data-ttu-id="b0b5f-139">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="b0b5f-139">Header</span></span> | <span data-ttu-id="b0b5f-140">Valor</span><span class="sxs-lookup"><span data-stu-id="b0b5f-140">Value</span></span>
-|-
<span data-ttu-id="b0b5f-141">Autorização</span><span class="sxs-lookup"><span data-stu-id="b0b5f-141">Authorization</span></span> | <span data-ttu-id="b0b5f-142">Portador {token} **Observação: obrigatório**</span><span class="sxs-lookup"><span data-stu-id="b0b5f-142">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="b0b5f-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b0b5f-143">Content-Type</span></span> | <span data-ttu-id="b0b5f-144">application/json</span><span class="sxs-lookup"><span data-stu-id="b0b5f-144">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="b0b5f-145">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="b0b5f-145">Request body</span></span>

<span data-ttu-id="b0b5f-146">No corpo da solicitação, forneça um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="b0b5f-146">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="b0b5f-147">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="b0b5f-147">Parameter</span></span> | <span data-ttu-id="b0b5f-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="b0b5f-148">Type</span></span> | <span data-ttu-id="b0b5f-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="b0b5f-149">Description</span></span>
-|-|-
<span data-ttu-id="b0b5f-150">Consulta</span><span class="sxs-lookup"><span data-stu-id="b0b5f-150">Query</span></span> | <span data-ttu-id="b0b5f-151">Texto</span><span class="sxs-lookup"><span data-stu-id="b0b5f-151">Text</span></span> | <span data-ttu-id="b0b5f-152">A consulta a ser executada.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-152">The query to run.</span></span> <span data-ttu-id="b0b5f-153">**Observação: obrigatório**</span><span class="sxs-lookup"><span data-stu-id="b0b5f-153">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="b0b5f-154">Resposta</span><span class="sxs-lookup"><span data-stu-id="b0b5f-154">Response</span></span>

<span data-ttu-id="b0b5f-155">Se tiver êxito, este método retornará `200 OK` e um objeto _QueryResponse_ no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-155">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="b0b5f-156">O objeto Response contém três propriedades de nível superior:</span><span class="sxs-lookup"><span data-stu-id="b0b5f-156">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="b0b5f-157">Stats-um dicionário de estatísticas de desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-157">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="b0b5f-158">Schema-o esquema da resposta, uma lista de pares de Name-Type de cada coluna.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-158">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="b0b5f-159">Resultados-uma lista de eventos de busca avançados.</span><span class="sxs-lookup"><span data-stu-id="b0b5f-159">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="b0b5f-160">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b0b5f-160">Example</span></span>

<span data-ttu-id="b0b5f-161">No exemplo a seguir, um usuário envia a consulta abaixo e recebe um objeto de resposta da API contendo `Stats` , `Schema` e `Results` .</span><span class="sxs-lookup"><span data-stu-id="b0b5f-161">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="b0b5f-162">Consulta</span><span class="sxs-lookup"><span data-stu-id="b0b5f-162">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="b0b5f-163">Objeto Response</span><span class="sxs-lookup"><span data-stu-id="b0b5f-163">Response object</span></span>

```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="b0b5f-164">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="b0b5f-164">Related articles</span></span>

- [<span data-ttu-id="b0b5f-165">Acessar as APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b0b5f-165">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="b0b5f-166">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="b0b5f-166">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="b0b5f-167">Entender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="b0b5f-167">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="b0b5f-168">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="b0b5f-168">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
