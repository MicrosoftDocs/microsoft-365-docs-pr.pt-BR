---
title: Guia de API De Busca Avançada com Python
ms.reviewer: ''
description: Saiba como consultar usando a API do Microsoft Defender para Ponto de Extremidade usando Python, com exemplos.
keywords: apis, apis com suporte, busca avançada, consulta
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
ms.openlocfilehash: 17ad28121935adfc958629f7999311c11a8d784e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771432"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="58173-104">Busca avançada usando Python</span><span class="sxs-lookup"><span data-stu-id="58173-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="58173-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="58173-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="58173-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="58173-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="58173-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="58173-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="58173-108">Execute consultas avançadas usando Python, consulte [Api de Busca Avançada](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="58173-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="58173-109">Nesta seção, compartilharemos exemplos python para recuperar um token e usá-lo para executar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="58173-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

><span data-ttu-id="58173-110">**Pré-requisito:** primeiro você precisa [criar um aplicativo](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="58173-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="58173-111">Obter token</span><span class="sxs-lookup"><span data-stu-id="58173-111">Get token</span></span>

- <span data-ttu-id="58173-112">Execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="58173-112">Run the following commands:</span></span>

```

import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]

```

<span data-ttu-id="58173-113">where</span><span class="sxs-lookup"><span data-stu-id="58173-113">where</span></span>
- <span data-ttu-id="58173-114">tenantId: ID do locatário em nome do qual você deseja executar a consulta (ou seja, a consulta será executado nos dados desse locatário)</span><span class="sxs-lookup"><span data-stu-id="58173-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="58173-115">appId: ID do seu aplicativo do Azure AD (o aplicativo deve ter permissão 'Executar consultas avançadas' para o Microsoft Defender para o Ponto de Extremidade)</span><span class="sxs-lookup"><span data-stu-id="58173-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="58173-116">appSecret: Segredo do seu aplicativo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="58173-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="58173-117">Executar consulta</span><span class="sxs-lookup"><span data-stu-id="58173-117">Run query</span></span>

 <span data-ttu-id="58173-118">Execute a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="58173-118">Run the following query:</span></span>

```
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]

```

- <span data-ttu-id="58173-119">esquema contém o esquema dos resultados de sua consulta</span><span class="sxs-lookup"><span data-stu-id="58173-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="58173-120">resultados contêm os resultados de sua consulta</span><span class="sxs-lookup"><span data-stu-id="58173-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="58173-121">Consultas complexas</span><span class="sxs-lookup"><span data-stu-id="58173-121">Complex queries</span></span>

<span data-ttu-id="58173-122">Se você quiser executar consultas complexas (ou consultas de várias linhas), salve sua consulta em um arquivo e, em vez da primeira linha no exemplo acima, execute o comando abaixo:</span><span class="sxs-lookup"><span data-stu-id="58173-122">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="58173-123">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="58173-123">Work with query results</span></span>

<span data-ttu-id="58173-124">Agora você pode usar os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="58173-124">You can now use the query results.</span></span>

<span data-ttu-id="58173-125">Para iterar sobre os resultados, faça o abaixo:</span><span class="sxs-lookup"><span data-stu-id="58173-125">To iterate over the results do the below:</span></span>

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


<span data-ttu-id="58173-126">Para saída dos resultados da consulta no formato CSV no file1.csv faça o abaixo:</span><span class="sxs-lookup"><span data-stu-id="58173-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="58173-127">Para saída dos resultados da consulta no formato JSON no arquivo file1.jsfazer o abaixo:</span><span class="sxs-lookup"><span data-stu-id="58173-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a><span data-ttu-id="58173-128">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="58173-128">Related topic</span></span>
- [<span data-ttu-id="58173-129">APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="58173-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="58173-130">API de Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="58173-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="58173-131">Busca avançada usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="58173-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
