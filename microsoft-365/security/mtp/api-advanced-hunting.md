---
title: APIs de busca avançada
description: Saiba como executar consultas de busca avançada usando a API de proteção contra ameaças da Microsoft
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
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650132"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="49e55-104">APIs de busca avançada</span><span class="sxs-lookup"><span data-stu-id="49e55-104">Advanced hunting APIs</span></span>

<span data-ttu-id="49e55-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="49e55-105">**Applies to:**</span></span>
- <span data-ttu-id="49e55-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="49e55-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="49e55-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="49e55-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="49e55-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="49e55-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="49e55-109">Limitações</span><span class="sxs-lookup"><span data-stu-id="49e55-109">Limitations</span></span>
1. <span data-ttu-id="49e55-110">Você só pode executar uma consulta nos dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="49e55-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="49e55-111">Os resultados incluirão um máximo de 100.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="49e55-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="49e55-112">O número de execuções é limitado por locatário: até 15 chamadas por minuto, 15 minutos de tempo de execução a cada hora e 4 horas de tempo de execução por dia.</span><span class="sxs-lookup"><span data-stu-id="49e55-112">The number of executions is limited per tenant: up to 15 calls per minute, 15 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="49e55-113">O tempo máximo de execução de uma única solicitação é de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="49e55-113">The maximal execution time of a single request is 10 minutes.</span></span>

## <a name="permissions"></a><span data-ttu-id="49e55-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="49e55-114">Permissions</span></span>
<span data-ttu-id="49e55-115">Uma das seguintes permissões é necessária para chamar esta API.</span><span class="sxs-lookup"><span data-stu-id="49e55-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="49e55-116">Para saber mais, incluindo como escolher permissões, confira [acessar as APIs de proteção contra ameaças da Microsoft](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="49e55-116">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="49e55-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="49e55-117">Permission type</span></span> |   <span data-ttu-id="49e55-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="49e55-118">Permission</span></span>  |   <span data-ttu-id="49e55-119">Nome para exibição da permissão</span><span class="sxs-lookup"><span data-stu-id="49e55-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="49e55-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="49e55-120">Application</span></span> |   <span data-ttu-id="49e55-121">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="49e55-121">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="49e55-122">' Executar consultas avançadas '</span><span class="sxs-lookup"><span data-stu-id="49e55-122">'Run advanced queries'</span></span>
<span data-ttu-id="49e55-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="49e55-123">Delegated (work or school account)</span></span> | <span data-ttu-id="49e55-124">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="49e55-124">AdvancedHunting.Read</span></span> | <span data-ttu-id="49e55-125">' Executar consultas avançadas '</span><span class="sxs-lookup"><span data-stu-id="49e55-125">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="49e55-126">Ao obter um token usando as credenciais do usuário:</span><span class="sxs-lookup"><span data-stu-id="49e55-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="49e55-127">O usuário precisa ter a função de AD ' exibir dados '</span><span class="sxs-lookup"><span data-stu-id="49e55-127">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="49e55-128">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="49e55-128">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="49e55-129">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="49e55-129">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="49e55-130">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="49e55-130">Request headers</span></span>

<span data-ttu-id="49e55-131">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="49e55-131">Header</span></span> | <span data-ttu-id="49e55-132">Valor</span><span class="sxs-lookup"><span data-stu-id="49e55-132">Value</span></span> 
:---|:---
<span data-ttu-id="49e55-133">Autorização</span><span class="sxs-lookup"><span data-stu-id="49e55-133">Authorization</span></span> | <span data-ttu-id="49e55-134">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="49e55-134">Bearer {token}.</span></span> <span data-ttu-id="49e55-135">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="49e55-135">**Required**.</span></span>
<span data-ttu-id="49e55-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="49e55-136">Content-Type</span></span>    | <span data-ttu-id="49e55-137">application/json</span><span class="sxs-lookup"><span data-stu-id="49e55-137">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="49e55-138">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="49e55-138">Request body</span></span>
<span data-ttu-id="49e55-139">No corpo da solicitação, forneça um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="49e55-139">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="49e55-140">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="49e55-140">Parameter</span></span> | <span data-ttu-id="49e55-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="49e55-141">Type</span></span>    | <span data-ttu-id="49e55-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="49e55-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="49e55-143">Consulta</span><span class="sxs-lookup"><span data-stu-id="49e55-143">Query</span></span> | <span data-ttu-id="49e55-144">Texto</span><span class="sxs-lookup"><span data-stu-id="49e55-144">Text</span></span> |  <span data-ttu-id="49e55-145">A consulta a ser executada.</span><span class="sxs-lookup"><span data-stu-id="49e55-145">The query to run.</span></span> <span data-ttu-id="49e55-146">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="49e55-146">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="49e55-147">Resposta</span><span class="sxs-lookup"><span data-stu-id="49e55-147">Response</span></span>
<span data-ttu-id="49e55-148">Se tiver êxito, este método retornará 200 OK e o objeto _QueryResponse_ no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="49e55-148">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="49e55-149">O objeto Response é dividido como 3 partes (Propriedades):</span><span class="sxs-lookup"><span data-stu-id="49e55-149">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="49e55-150">```Stats``` – Estatísticas de desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="49e55-150">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="49e55-151">```Schema``` – O esquema da resposta, uma lista de pares de tipo de nome para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="49e55-151">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="49e55-152">```Results``` – Uma lista de eventos de busca avançados.</span><span class="sxs-lookup"><span data-stu-id="49e55-152">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="49e55-153">Exemplo</span><span class="sxs-lookup"><span data-stu-id="49e55-153">Example</span></span>

<span data-ttu-id="49e55-154">Solicitação</span><span class="sxs-lookup"><span data-stu-id="49e55-154">Request</span></span>

<span data-ttu-id="49e55-155">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="49e55-155">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="49e55-156">Resposta</span><span class="sxs-lookup"><span data-stu-id="49e55-156">Response</span></span>

<span data-ttu-id="49e55-157">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="49e55-157">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="49e55-158">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="49e55-158">Related topic</span></span>
- [<span data-ttu-id="49e55-159">Acessar as APIs de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="49e55-159">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
