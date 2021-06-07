---
title: Microsoft 365 API de busca avançada do Defender
description: Saiba como executar consultas de busca avançadas usando Microsoft 365 API de busca avançada do Defender
keywords: Busca avançada, APIs, api, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: 3ff62265783be846a95964164e372100fe1ef662
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769579"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="71d42-104">Microsoft 365 API de busca avançada do Defender</span><span class="sxs-lookup"><span data-stu-id="71d42-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="71d42-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="71d42-105">**Applies to:**</span></span>

- <span data-ttu-id="71d42-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71d42-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71d42-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="71d42-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="71d42-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="71d42-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="71d42-109">[A busca](advanced-hunting-overview.md) avançada é uma [](advanced-hunting-query-language.md) ferramenta de busca de ameaças que usa consultas especialmente construídas para examinar os últimos 30 dias de dados de eventos no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="71d42-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="71d42-110">Você pode usar consultas avançadas de busca para inspecionar atividades incomuns, detectar possíveis ameaças e até mesmo responder a ataques.</span><span class="sxs-lookup"><span data-stu-id="71d42-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="71d42-111">A API de busca avançada permite que você consulte programaticamente dados de eventos.</span><span class="sxs-lookup"><span data-stu-id="71d42-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="71d42-112">Cotas e alocação de recursos</span><span class="sxs-lookup"><span data-stu-id="71d42-112">Quotas and resource allocation</span></span>

<span data-ttu-id="71d42-113">As condições a seguir se relacionam a todas as consultas.</span><span class="sxs-lookup"><span data-stu-id="71d42-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="71d42-114">As consultas exploram e retornam dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="71d42-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="71d42-115">Os resultados podem retornar até 100.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="71d42-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="71d42-116">Você pode fazer até 15 chamadas por minuto por locatário.</span><span class="sxs-lookup"><span data-stu-id="71d42-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="71d42-117">As consultas serão bloqueadas se o locatário tiver atingido 100% até após o próximo ciclo de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="71d42-117">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span>
5. <span data-ttu-id="71d42-118">Se uma única solicitação for executado por mais de 10 minutos, ela passará o tempo e retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="71d42-118">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
6. <span data-ttu-id="71d42-119">Um código de resposta HTTP indica que você atingiu uma cota, por número de solicitações enviadas ou pelo tempo de `429` execução alocado.</span><span class="sxs-lookup"><span data-stu-id="71d42-119">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="71d42-120">Leia o corpo da resposta para entender o limite atingido.</span><span class="sxs-lookup"><span data-stu-id="71d42-120">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="71d42-121">Todas as cotas listadas acima (por exemplo, 15 chamadas por minuto) são por tamanho de locatário.</span><span class="sxs-lookup"><span data-stu-id="71d42-121">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="71d42-122">Essas cotas são mínimas.</span><span class="sxs-lookup"><span data-stu-id="71d42-122">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="71d42-123">Permissões</span><span class="sxs-lookup"><span data-stu-id="71d42-123">Permissions</span></span>

<span data-ttu-id="71d42-124">Uma das seguintes permissões é necessária para chamar a API de busca avançada.</span><span class="sxs-lookup"><span data-stu-id="71d42-124">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="71d42-125">Para saber mais, incluindo como escolher permissões, consulte [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="71d42-125">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="71d42-126">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="71d42-126">Permission type</span></span> | <span data-ttu-id="71d42-127">Permissão</span><span class="sxs-lookup"><span data-stu-id="71d42-127">Permission</span></span> | <span data-ttu-id="71d42-128">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="71d42-128">Permission display name</span></span>
-|-|-
<span data-ttu-id="71d42-129">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="71d42-129">Application</span></span> | <span data-ttu-id="71d42-130">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="71d42-130">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="71d42-131">Executar consultas avançadas</span><span class="sxs-lookup"><span data-stu-id="71d42-131">Run advanced queries</span></span>
<span data-ttu-id="71d42-132">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="71d42-132">Delegated (work or school account)</span></span> | <span data-ttu-id="71d42-133">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="71d42-133">AdvancedHunting.Read</span></span> | <span data-ttu-id="71d42-134">Executar consultas avançadas</span><span class="sxs-lookup"><span data-stu-id="71d42-134">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="71d42-135">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="71d42-135">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="71d42-136">O usuário precisa ter a função AD 'Exibir Dados'</span><span class="sxs-lookup"><span data-stu-id="71d42-136">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="71d42-137">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="71d42-137">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="71d42-138">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="71d42-138">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="71d42-139">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="71d42-139">Request headers</span></span>

<span data-ttu-id="71d42-140">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="71d42-140">Header</span></span> | <span data-ttu-id="71d42-141">Valor</span><span class="sxs-lookup"><span data-stu-id="71d42-141">Value</span></span>
-|-
<span data-ttu-id="71d42-142">Autorização</span><span class="sxs-lookup"><span data-stu-id="71d42-142">Authorization</span></span> | <span data-ttu-id="71d42-143">Portador {token} **Observação: obrigatório**</span><span class="sxs-lookup"><span data-stu-id="71d42-143">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="71d42-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="71d42-144">Content-Type</span></span> | <span data-ttu-id="71d42-145">application/json</span><span class="sxs-lookup"><span data-stu-id="71d42-145">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="71d42-146">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="71d42-146">Request body</span></span>

<span data-ttu-id="71d42-147">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="71d42-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="71d42-148">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="71d42-148">Parameter</span></span> | <span data-ttu-id="71d42-149">Tipo</span><span class="sxs-lookup"><span data-stu-id="71d42-149">Type</span></span> | <span data-ttu-id="71d42-150">Descrição</span><span class="sxs-lookup"><span data-stu-id="71d42-150">Description</span></span>
-|-|-
<span data-ttu-id="71d42-151">Consulta</span><span class="sxs-lookup"><span data-stu-id="71d42-151">Query</span></span> | <span data-ttu-id="71d42-152">Texto</span><span class="sxs-lookup"><span data-stu-id="71d42-152">Text</span></span> | <span data-ttu-id="71d42-153">A consulta a ser executado.</span><span class="sxs-lookup"><span data-stu-id="71d42-153">The query to run.</span></span> <span data-ttu-id="71d42-154">**Observação: obrigatório**</span><span class="sxs-lookup"><span data-stu-id="71d42-154">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="71d42-155">Resposta</span><span class="sxs-lookup"><span data-stu-id="71d42-155">Response</span></span>

<span data-ttu-id="71d42-156">Se tiver êxito, este método retornará `200 OK` e um _objeto QueryResponse_ no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="71d42-156">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="71d42-157">O objeto response contém três propriedades de nível superior:</span><span class="sxs-lookup"><span data-stu-id="71d42-157">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="71d42-158">Estatísticas - Um dicionário de estatísticas de desempenho de consulta.</span><span class="sxs-lookup"><span data-stu-id="71d42-158">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="71d42-159">Esquema - O esquema da resposta, uma lista de Name-Type pares para cada coluna.</span><span class="sxs-lookup"><span data-stu-id="71d42-159">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="71d42-160">Resultados - Uma lista de eventos de busca avançada.</span><span class="sxs-lookup"><span data-stu-id="71d42-160">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="71d42-161">Exemplo</span><span class="sxs-lookup"><span data-stu-id="71d42-161">Example</span></span>

<span data-ttu-id="71d42-162">No exemplo a seguir, um usuário envia a consulta abaixo e recebe um objeto de resposta da API contendo `Stats` `Schema` , e `Results` .</span><span class="sxs-lookup"><span data-stu-id="71d42-162">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="71d42-163">Consulta</span><span class="sxs-lookup"><span data-stu-id="71d42-163">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="71d42-164">Objeto Response</span><span class="sxs-lookup"><span data-stu-id="71d42-164">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="71d42-165">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="71d42-165">Related articles</span></span>

- [<span data-ttu-id="71d42-166">Acessar as APIs Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71d42-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="71d42-167">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="71d42-167">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="71d42-168">Compreender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="71d42-168">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="71d42-169">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="71d42-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
