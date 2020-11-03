---
title: APIs de busca avançada
description: Saiba como executar consultas de busca avançada usando a API do Microsoft 365 defender
keywords: Caça avançada, APIs, API, MTP
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
ms.openlocfilehash: c43d263009578af6280ffdc780ab0f9a174a3b97
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844027"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="636ec-104">APIs de busca avançada</span><span class="sxs-lookup"><span data-stu-id="636ec-104">Advanced hunting APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="636ec-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="636ec-105">**Applies to:**</span></span>
- <span data-ttu-id="636ec-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="636ec-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="636ec-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="636ec-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="636ec-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="636ec-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="636ec-109">Limitações</span><span class="sxs-lookup"><span data-stu-id="636ec-109">Limitations</span></span>
1. <span data-ttu-id="636ec-110">Você só pode executar uma consulta nos dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="636ec-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="636ec-111">Os resultados incluirão um máximo de 100.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="636ec-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="636ec-112">O número de execuções é limitado por locatário: até 10 chamadas por minuto, 10 minutos de tempo de execução a cada hora e 4 horas de tempo de execução por dia.</span><span class="sxs-lookup"><span data-stu-id="636ec-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="636ec-113">O tempo máximo de execução de uma única solicitação é de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="636ec-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="636ec-114">429 a resposta representará um limite de cota de alcance por número de solicitações ou por CPU.</span><span class="sxs-lookup"><span data-stu-id="636ec-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="636ec-115">O corpo da resposta 429 também indicará o tempo até que a cota seja renovada.</span><span class="sxs-lookup"><span data-stu-id="636ec-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="636ec-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="636ec-116">Permissions</span></span>
<span data-ttu-id="636ec-117">Uma das seguintes permissões é necessária para chamar esta API.</span><span class="sxs-lookup"><span data-stu-id="636ec-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="636ec-118">Para saber mais, incluindo como escolher permissões, consulte [Access The Microsoft 365 defender APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="636ec-118">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="636ec-119">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="636ec-119">Permission type</span></span> |   <span data-ttu-id="636ec-120">Permissão</span><span class="sxs-lookup"><span data-stu-id="636ec-120">Permission</span></span>  |   <span data-ttu-id="636ec-121">Nome para exibição da permissão</span><span class="sxs-lookup"><span data-stu-id="636ec-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="636ec-122">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="636ec-122">Application</span></span> |   <span data-ttu-id="636ec-123">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="636ec-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="636ec-124">' Executar consultas avançadas '</span><span class="sxs-lookup"><span data-stu-id="636ec-124">'Run advanced queries'</span></span>
<span data-ttu-id="636ec-125">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="636ec-125">Delegated (work or school account)</span></span> | <span data-ttu-id="636ec-126">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="636ec-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="636ec-127">' Executar consultas avançadas '</span><span class="sxs-lookup"><span data-stu-id="636ec-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="636ec-128">Ao obter um token usando as credenciais do usuário:</span><span class="sxs-lookup"><span data-stu-id="636ec-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="636ec-129">O usuário precisa ter a função de AD ' exibir dados '</span><span class="sxs-lookup"><span data-stu-id="636ec-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="636ec-130">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="636ec-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="636ec-131">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="636ec-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="636ec-132">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="636ec-132">Request headers</span></span>

<span data-ttu-id="636ec-133">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="636ec-133">Header</span></span> | <span data-ttu-id="636ec-134">Valor</span><span class="sxs-lookup"><span data-stu-id="636ec-134">Value</span></span> 
:---|:---
<span data-ttu-id="636ec-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="636ec-135">Authorization</span></span> | <span data-ttu-id="636ec-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="636ec-136">Bearer {token}.</span></span> <span data-ttu-id="636ec-137">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="636ec-137">**Required**.</span></span>
<span data-ttu-id="636ec-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="636ec-138">Content-Type</span></span>    | <span data-ttu-id="636ec-139">application/json</span><span class="sxs-lookup"><span data-stu-id="636ec-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="636ec-140">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="636ec-140">Request body</span></span>
<span data-ttu-id="636ec-141">No corpo da solicitação, forneça um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="636ec-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="636ec-142">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="636ec-142">Parameter</span></span> | <span data-ttu-id="636ec-143">Tipo</span><span class="sxs-lookup"><span data-stu-id="636ec-143">Type</span></span>    | <span data-ttu-id="636ec-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="636ec-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="636ec-145">Consulta</span><span class="sxs-lookup"><span data-stu-id="636ec-145">Query</span></span> | <span data-ttu-id="636ec-146">Texto</span><span class="sxs-lookup"><span data-stu-id="636ec-146">Text</span></span> |  <span data-ttu-id="636ec-147">A consulta a ser executada.</span><span class="sxs-lookup"><span data-stu-id="636ec-147">The query to run.</span></span> <span data-ttu-id="636ec-148">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="636ec-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="636ec-149">Resposta</span><span class="sxs-lookup"><span data-stu-id="636ec-149">Response</span></span>
<span data-ttu-id="636ec-150">Se tiver êxito, este método retornará 200 OK e o objeto _QueryResponse_ no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="636ec-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="636ec-151">O objeto Response é dividido como 3 partes (Propriedades):</span><span class="sxs-lookup"><span data-stu-id="636ec-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="636ec-152">```Stats``` – Estatísticas de desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="636ec-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="636ec-153">```Schema``` – O esquema da resposta, uma lista de pares de Name-Type de cada coluna.</span><span class="sxs-lookup"><span data-stu-id="636ec-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="636ec-154">```Results``` – Uma lista de eventos de busca avançados.</span><span class="sxs-lookup"><span data-stu-id="636ec-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="636ec-155">Exemplo</span><span class="sxs-lookup"><span data-stu-id="636ec-155">Example</span></span>

<span data-ttu-id="636ec-156">Solicitação</span><span class="sxs-lookup"><span data-stu-id="636ec-156">Request</span></span>

<span data-ttu-id="636ec-157">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="636ec-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="636ec-158">Resposta</span><span class="sxs-lookup"><span data-stu-id="636ec-158">Response</span></span>

<span data-ttu-id="636ec-159">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="636ec-159">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="636ec-160">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="636ec-160">Related topic</span></span>
- [<span data-ttu-id="636ec-161">Acessar as APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="636ec-161">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
