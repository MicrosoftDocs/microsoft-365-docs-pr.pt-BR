---
title: Busca avançada com noções básicas da API do PowerShell
ms.reviewer: ''
description: Saiba as noções básicas sobre como consultar a API do Microsoft Defender para Ponto de Extremidade usando o PowerShell.
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
ms.openlocfilehash: 9192662b8d4ed23a5903dddb555f07bf182ab17f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771496"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="a21b8-104">Busca avançada usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a21b8-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a21b8-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a21b8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="a21b8-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a21b8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a21b8-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a21b8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="a21b8-108">Execute consultas avançadas usando o PowerShell, consulte [Advanced Hunting API](run-advanced-query-api.md).</span><span class="sxs-lookup"><span data-stu-id="a21b8-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="a21b8-109">Nesta seção, compartilharemos exemplos do PowerShell para recuperar um token e usá-lo para executar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="a21b8-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a21b8-110">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="a21b8-110">Before you begin</span></span>
<span data-ttu-id="a21b8-111">Primeiro, você precisa [criar um aplicativo.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a21b8-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="a21b8-112">Instruções de preparação</span><span class="sxs-lookup"><span data-stu-id="a21b8-112">Preparation instructions</span></span>

- <span data-ttu-id="a21b8-113">Abra uma janela do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a21b8-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="a21b8-114">Se sua política não permitir que você execute os comandos do PowerShell, você poderá executar o comando abaixo:</span><span class="sxs-lookup"><span data-stu-id="a21b8-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="a21b8-115">Para obter mais informações, consulte [Documentação do PowerShell](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="a21b8-115">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="a21b8-116">Obter token</span><span class="sxs-lookup"><span data-stu-id="a21b8-116">Get token</span></span>

- <span data-ttu-id="a21b8-117">Execute:</span><span class="sxs-lookup"><span data-stu-id="a21b8-117">Run the following:</span></span>

```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

<span data-ttu-id="a21b8-118">where</span><span class="sxs-lookup"><span data-stu-id="a21b8-118">where</span></span>
- <span data-ttu-id="a21b8-119">$tenantId: ID do locatário em nome do qual você deseja executar a consulta (ou seja, a consulta será executado nos dados desse locatário)</span><span class="sxs-lookup"><span data-stu-id="a21b8-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="a21b8-120">$appId: ID do seu aplicativo do Azure AD (o aplicativo deve ter permissão 'Executar consultas avançadas' para o Defender para Ponto de Extremidade)</span><span class="sxs-lookup"><span data-stu-id="a21b8-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="a21b8-121">$appSecret: Segredo do seu aplicativo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="a21b8-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="a21b8-122">Executar consulta</span><span class="sxs-lookup"><span data-stu-id="a21b8-122">Run query</span></span>

<span data-ttu-id="a21b8-123">Execute a seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="a21b8-123">Run the following query:</span></span>

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- <span data-ttu-id="a21b8-124">$results contêm os resultados de sua consulta</span><span class="sxs-lookup"><span data-stu-id="a21b8-124">$results contain the results of your query</span></span>
- <span data-ttu-id="a21b8-125">$schema contém o esquema dos resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="a21b8-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="a21b8-126">Consultas complexas</span><span class="sxs-lookup"><span data-stu-id="a21b8-126">Complex queries</span></span>

<span data-ttu-id="a21b8-127">Se você quiser executar consultas complexas (ou consultas de várias linhas), salve sua consulta em um arquivo e, em vez da primeira linha no exemplo acima, execute o comando abaixo:</span><span class="sxs-lookup"><span data-stu-id="a21b8-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="a21b8-128">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="a21b8-128">Work with query results</span></span>

<span data-ttu-id="a21b8-129">Agora você pode usar os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="a21b8-129">You can now use the query results.</span></span>

<span data-ttu-id="a21b8-130">Para saída dos resultados da consulta no formato CSV no file1.csv faça o abaixo:</span><span class="sxs-lookup"><span data-stu-id="a21b8-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="a21b8-131">Para saída dos resultados da consulta no formato JSON no arquivo file1.jsfazer o abaixo:</span><span class="sxs-lookup"><span data-stu-id="a21b8-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="a21b8-132">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a21b8-132">Related topic</span></span>
- [<span data-ttu-id="a21b8-133">APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a21b8-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="a21b8-134">API de Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="a21b8-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="a21b8-135">Busca avançada usando Python</span><span class="sxs-lookup"><span data-stu-id="a21b8-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
