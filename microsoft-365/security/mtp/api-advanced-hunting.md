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
ms.openlocfilehash: dd7b02200e370588bbb9470a3d7e897b30234ead
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197804"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="80ee7-104">APIs de busca avançada</span><span class="sxs-lookup"><span data-stu-id="80ee7-104">Advanced hunting APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="80ee7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="80ee7-105">**Applies to:**</span></span>
- <span data-ttu-id="80ee7-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="80ee7-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="80ee7-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="80ee7-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="80ee7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="80ee7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="80ee7-109">Limitações</span><span class="sxs-lookup"><span data-stu-id="80ee7-109">Limitations</span></span>
1. <span data-ttu-id="80ee7-110">Você só pode executar uma consulta nos dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="80ee7-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="80ee7-111">Os resultados incluirão um máximo de 100.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="80ee7-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="80ee7-112">O número de execuções é limitado por locatário: até 10 chamadas por minuto, 10 minutos de tempo de execução a cada hora e 4 horas de tempo de execução por dia.</span><span class="sxs-lookup"><span data-stu-id="80ee7-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="80ee7-113">O tempo máximo de execução de uma única solicitação é de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="80ee7-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="80ee7-114">429 a resposta representará um limite de cota de alcance por número de solicitações ou por CPU.</span><span class="sxs-lookup"><span data-stu-id="80ee7-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="80ee7-115">O corpo da resposta 429 também indicará o tempo até que a cota seja renovada.</span><span class="sxs-lookup"><span data-stu-id="80ee7-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="80ee7-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="80ee7-116">Permissions</span></span>
<span data-ttu-id="80ee7-117">Uma das seguintes permissões é necessária para chamar esta API.</span><span class="sxs-lookup"><span data-stu-id="80ee7-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="80ee7-118">Para saber mais, incluindo como escolher permissões, confira [acessar as APIs de proteção contra ameaças da Microsoft](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="80ee7-118">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="80ee7-119">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="80ee7-119">Permission type</span></span> |   <span data-ttu-id="80ee7-120">Permissão</span><span class="sxs-lookup"><span data-stu-id="80ee7-120">Permission</span></span>  |   <span data-ttu-id="80ee7-121">Nome para exibição da permissão</span><span class="sxs-lookup"><span data-stu-id="80ee7-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="80ee7-122">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="80ee7-122">Application</span></span> |   <span data-ttu-id="80ee7-123">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="80ee7-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="80ee7-124">' Executar consultas avançadas '</span><span class="sxs-lookup"><span data-stu-id="80ee7-124">'Run advanced queries'</span></span>
<span data-ttu-id="80ee7-125">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="80ee7-125">Delegated (work or school account)</span></span> | <span data-ttu-id="80ee7-126">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="80ee7-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="80ee7-127">' Executar consultas avançadas '</span><span class="sxs-lookup"><span data-stu-id="80ee7-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="80ee7-128">Ao obter um token usando as credenciais do usuário:</span><span class="sxs-lookup"><span data-stu-id="80ee7-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="80ee7-129">O usuário precisa ter a função de AD ' exibir dados '</span><span class="sxs-lookup"><span data-stu-id="80ee7-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="80ee7-130">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="80ee7-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="80ee7-131">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="80ee7-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="80ee7-132">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="80ee7-132">Request headers</span></span>

<span data-ttu-id="80ee7-133">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="80ee7-133">Header</span></span> | <span data-ttu-id="80ee7-134">Valor</span><span class="sxs-lookup"><span data-stu-id="80ee7-134">Value</span></span> 
:---|:---
<span data-ttu-id="80ee7-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="80ee7-135">Authorization</span></span> | <span data-ttu-id="80ee7-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="80ee7-136">Bearer {token}.</span></span> <span data-ttu-id="80ee7-137">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="80ee7-137">**Required**.</span></span>
<span data-ttu-id="80ee7-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="80ee7-138">Content-Type</span></span>    | <span data-ttu-id="80ee7-139">application/json</span><span class="sxs-lookup"><span data-stu-id="80ee7-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="80ee7-140">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="80ee7-140">Request body</span></span>
<span data-ttu-id="80ee7-141">No corpo da solicitação, forneça um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="80ee7-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="80ee7-142">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="80ee7-142">Parameter</span></span> | <span data-ttu-id="80ee7-143">Tipo</span><span class="sxs-lookup"><span data-stu-id="80ee7-143">Type</span></span>    | <span data-ttu-id="80ee7-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="80ee7-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="80ee7-145">Consulta</span><span class="sxs-lookup"><span data-stu-id="80ee7-145">Query</span></span> | <span data-ttu-id="80ee7-146">Texto</span><span class="sxs-lookup"><span data-stu-id="80ee7-146">Text</span></span> |  <span data-ttu-id="80ee7-147">A consulta a ser executada.</span><span class="sxs-lookup"><span data-stu-id="80ee7-147">The query to run.</span></span> <span data-ttu-id="80ee7-148">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="80ee7-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="80ee7-149">Resposta</span><span class="sxs-lookup"><span data-stu-id="80ee7-149">Response</span></span>
<span data-ttu-id="80ee7-150">Se tiver êxito, este método retornará 200 OK e o objeto _QueryResponse_ no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="80ee7-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="80ee7-151">O objeto Response é dividido como 3 partes (Propriedades):</span><span class="sxs-lookup"><span data-stu-id="80ee7-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="80ee7-152">```Stats``` – Estatísticas de desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="80ee7-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="80ee7-153">```Schema``` – O esquema da resposta, uma lista de pares de tipo de nome para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="80ee7-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="80ee7-154">```Results``` – Uma lista de eventos de busca avançados.</span><span class="sxs-lookup"><span data-stu-id="80ee7-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="80ee7-155">Exemplo</span><span class="sxs-lookup"><span data-stu-id="80ee7-155">Example</span></span>

<span data-ttu-id="80ee7-156">Solicitação</span><span class="sxs-lookup"><span data-stu-id="80ee7-156">Request</span></span>

<span data-ttu-id="80ee7-157">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="80ee7-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="80ee7-158">Resposta</span><span class="sxs-lookup"><span data-stu-id="80ee7-158">Response</span></span>

<span data-ttu-id="80ee7-159">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="80ee7-159">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="80ee7-160">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="80ee7-160">Related topic</span></span>
- [<span data-ttu-id="80ee7-161">Acessar as APIs de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="80ee7-161">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
