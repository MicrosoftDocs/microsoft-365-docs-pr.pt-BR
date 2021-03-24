---
title: API de busca avançada do Microsoft 365 Defender
description: Saiba como executar consultas de busca avançadas usando a API de busca avançada do Microsoft 365 Defender
keywords: Busca avançada, APIs, api, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 482801bb47429ae370e06cfcbcf26bacfb8b2a92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054035"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="d678b-104">API de busca avançada do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d678b-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d678b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d678b-105">**Applies to:**</span></span>

- <span data-ttu-id="d678b-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d678b-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d678b-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="d678b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d678b-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="d678b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d678b-109">[A busca avançada](advanced-hunting-overview.md) é uma [](advanced-hunting-query-language.md) ferramenta de busca de ameaças que usa consultas especialmente construídas para examinar os últimos 30 dias de dados de eventos no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d678b-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="d678b-110">Você pode usar consultas avançadas de busca para inspecionar atividades incomuns, detectar possíveis ameaças e até mesmo responder a ataques.</span><span class="sxs-lookup"><span data-stu-id="d678b-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="d678b-111">A API de busca avançada permite que você consulte programaticamente dados de eventos.</span><span class="sxs-lookup"><span data-stu-id="d678b-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="d678b-112">Cotas e alocação de recursos</span><span class="sxs-lookup"><span data-stu-id="d678b-112">Quotas and resource allocation</span></span>

<span data-ttu-id="d678b-113">As condições a seguir se relacionam a todas as consultas.</span><span class="sxs-lookup"><span data-stu-id="d678b-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="d678b-114">As consultas exploram e retornam dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="d678b-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="d678b-115">Os resultados podem retornar até 100.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="d678b-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="d678b-116">Você pode fazer até 15 chamadas por minuto por locatário.</span><span class="sxs-lookup"><span data-stu-id="d678b-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="d678b-117">Você tem 10 minutos de tempo de execução por hora por locatário.</span><span class="sxs-lookup"><span data-stu-id="d678b-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="d678b-118">Você tem quatro horas totais de tempo de execução por dia por locatário.</span><span class="sxs-lookup"><span data-stu-id="d678b-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="d678b-119">Se uma única solicitação for executado por mais de 10 minutos, ela passará o tempo e retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="d678b-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="d678b-120">Um código de resposta HTTP indica que você atingiu uma cota, por número de solicitações enviadas ou pelo tempo de `429` execução alocado.</span><span class="sxs-lookup"><span data-stu-id="d678b-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="d678b-121">Leia o corpo da resposta para entender o limite atingido.</span><span class="sxs-lookup"><span data-stu-id="d678b-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="d678b-122">Todas as cotas listadas acima (por exemplo, 15 chamadas por minuto) são por tamanho de locatário.</span><span class="sxs-lookup"><span data-stu-id="d678b-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="d678b-123">Essas cotas são mínimas.</span><span class="sxs-lookup"><span data-stu-id="d678b-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="d678b-124">Permissões</span><span class="sxs-lookup"><span data-stu-id="d678b-124">Permissions</span></span>

<span data-ttu-id="d678b-125">Uma das seguintes permissões é necessária para chamar a API de busca avançada.</span><span class="sxs-lookup"><span data-stu-id="d678b-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="d678b-126">Para saber mais, incluindo como escolher permissões, consulte [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="d678b-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="d678b-127">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="d678b-127">Permission type</span></span> | <span data-ttu-id="d678b-128">Permissão</span><span class="sxs-lookup"><span data-stu-id="d678b-128">Permission</span></span> | <span data-ttu-id="d678b-129">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="d678b-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="d678b-130">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="d678b-130">Application</span></span> | <span data-ttu-id="d678b-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="d678b-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="d678b-132">Executar consultas avançadas</span><span class="sxs-lookup"><span data-stu-id="d678b-132">Run advanced queries</span></span>
<span data-ttu-id="d678b-133">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="d678b-133">Delegated (work or school account)</span></span> | <span data-ttu-id="d678b-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="d678b-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="d678b-135">Executar consultas avançadas</span><span class="sxs-lookup"><span data-stu-id="d678b-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="d678b-136">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="d678b-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="d678b-137">O usuário precisa ter a função AD 'Exibir Dados'</span><span class="sxs-lookup"><span data-stu-id="d678b-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="d678b-138">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d678b-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="d678b-139">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="d678b-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="d678b-140">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="d678b-140">Request headers</span></span>

<span data-ttu-id="d678b-141">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="d678b-141">Header</span></span> | <span data-ttu-id="d678b-142">Valor</span><span class="sxs-lookup"><span data-stu-id="d678b-142">Value</span></span>
-|-
<span data-ttu-id="d678b-143">Autorização</span><span class="sxs-lookup"><span data-stu-id="d678b-143">Authorization</span></span> | <span data-ttu-id="d678b-144">Portador {token} **Observação: obrigatório**</span><span class="sxs-lookup"><span data-stu-id="d678b-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="d678b-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="d678b-145">Content-Type</span></span> | <span data-ttu-id="d678b-146">application/json</span><span class="sxs-lookup"><span data-stu-id="d678b-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="d678b-147">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="d678b-147">Request body</span></span>

<span data-ttu-id="d678b-148">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="d678b-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="d678b-149">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="d678b-149">Parameter</span></span> | <span data-ttu-id="d678b-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="d678b-150">Type</span></span> | <span data-ttu-id="d678b-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="d678b-151">Description</span></span>
-|-|-
<span data-ttu-id="d678b-152">Consulta</span><span class="sxs-lookup"><span data-stu-id="d678b-152">Query</span></span> | <span data-ttu-id="d678b-153">Texto</span><span class="sxs-lookup"><span data-stu-id="d678b-153">Text</span></span> | <span data-ttu-id="d678b-154">A consulta a ser executado.</span><span class="sxs-lookup"><span data-stu-id="d678b-154">The query to run.</span></span> <span data-ttu-id="d678b-155">**Observação: obrigatório**</span><span class="sxs-lookup"><span data-stu-id="d678b-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="d678b-156">Resposta</span><span class="sxs-lookup"><span data-stu-id="d678b-156">Response</span></span>

<span data-ttu-id="d678b-157">Se tiver êxito, este método retornará `200 OK` e um _objeto QueryResponse_ no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="d678b-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="d678b-158">O objeto response contém três propriedades de nível superior:</span><span class="sxs-lookup"><span data-stu-id="d678b-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="d678b-159">Estatísticas - Um dicionário de estatísticas de desempenho de consulta.</span><span class="sxs-lookup"><span data-stu-id="d678b-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="d678b-160">Esquema - O esquema da resposta, uma lista de Name-Type pares para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="d678b-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="d678b-161">Resultados - Uma lista de eventos de busca avançada.</span><span class="sxs-lookup"><span data-stu-id="d678b-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="d678b-162">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d678b-162">Example</span></span>

<span data-ttu-id="d678b-163">No exemplo a seguir, um usuário envia a consulta abaixo e recebe um objeto de resposta da API contendo `Stats` `Schema` , e `Results` .</span><span class="sxs-lookup"><span data-stu-id="d678b-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="d678b-164">Consulta</span><span class="sxs-lookup"><span data-stu-id="d678b-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="d678b-165">Objeto Response</span><span class="sxs-lookup"><span data-stu-id="d678b-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="d678b-166">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="d678b-166">Related articles</span></span>

- [<span data-ttu-id="d678b-167">Acessar as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d678b-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="d678b-168">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="d678b-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="d678b-169">Compreender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="d678b-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="d678b-170">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="d678b-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
