---
title: Guia de API de Busca Avançada com o PowerShell
ms.reviewer: ''
description: Use esses exemplos de código, consultando várias APIs do Microsoft Defender para Ponto de Extremidade.
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
ms.date: 09/24/2018
ms.technology: mde
ms.openlocfilehash: ef6d05bb27018bb72f731da2e8b7837c9d9f0127
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842057"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a><span data-ttu-id="880f8-104">Microsoft Defender para APIs de ponto de extremidade usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="880f8-104">Microsoft Defender for Endpoint APIs using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="880f8-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="880f8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="880f8-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="880f8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="880f8-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="880f8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

><span data-ttu-id="880f8-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="880f8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="880f8-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="880f8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="880f8-110">Cenário completo usando várias APIs do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="880f8-110">Full scenario using multiple APIs from Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="880f8-111">Nesta seção, compartilharemos exemplos do PowerShell para</span><span class="sxs-lookup"><span data-stu-id="880f8-111">In this section, we share PowerShell samples to</span></span> 
- <span data-ttu-id="880f8-112">Recuperar um token</span><span class="sxs-lookup"><span data-stu-id="880f8-112">Retrieve a token</span></span> 
- <span data-ttu-id="880f8-113">Usar token para recuperar os alertas mais recentes no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="880f8-113">Use token to retrieve the latest alerts in Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="880f8-114">Para cada alerta, se o alerta tiver prioridade média ou alta e ainda estiver em andamento, verifique quantas vezes o dispositivo se conectou a URL suspeita.</span><span class="sxs-lookup"><span data-stu-id="880f8-114">For each alert, if the alert has medium or high priority and is still in progress, check how many times the device has connected to suspicious URL.</span></span>

<span data-ttu-id="880f8-115">**Pré-requisito:** primeiro você precisa [criar um aplicativo](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="880f8-115">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="880f8-116">Instruções de preparação</span><span class="sxs-lookup"><span data-stu-id="880f8-116">Preparation instructions</span></span>

- <span data-ttu-id="880f8-117">Abra uma janela do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="880f8-117">Open a PowerShell window.</span></span>
- <span data-ttu-id="880f8-118">Se sua política não permitir que você execute os comandos do PowerShell, você poderá executar o comando abaixo:</span><span class="sxs-lookup"><span data-stu-id="880f8-118">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

<span data-ttu-id="880f8-119">Para obter mais informações, consulte [Documentação do PowerShell](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="880f8-119">For more information, see [PowerShell documentation](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="880f8-120">Obter token</span><span class="sxs-lookup"><span data-stu-id="880f8-120">Get token</span></span>

<span data-ttu-id="880f8-121">Execute o abaixo:</span><span class="sxs-lookup"><span data-stu-id="880f8-121">Run the below:</span></span>

- <span data-ttu-id="880f8-122">$tenantId: ID do locatário em nome do qual você deseja executar a consulta (ou seja, a consulta será executado nos dados desse locatário)</span><span class="sxs-lookup"><span data-stu-id="880f8-122">$tenantId: ID of the tenant on behalf of which you want to run the query (i.e., the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="880f8-123">$appId: ID do seu aplicativo AAD (o aplicativo deve ter permissão 'Executar consultas avançadas' para o Defender para o Ponto de Extremidade)</span><span class="sxs-lookup"><span data-stu-id="880f8-123">$appId: ID of your AAD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="880f8-124">$appSecret: Segredo do seu aplicativo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="880f8-124">$appSecret: Secret of your Azure AD app</span></span>

- <span data-ttu-id="880f8-125">$suspiciousUrl: a URL</span><span class="sxs-lookup"><span data-stu-id="880f8-125">$suspiciousUrl: The URL</span></span>


```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here
$suspiciousUrl = 'www.suspiciousUrl.com' # Paste your own URL here

$resourceAppIdUri = 'https://securitycenter.onmicrosoft.com/windowsatpservice'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$aadToken = $authResponse.access_token


#Get latest alert
$alertUrl = "https://api.securitycenter.microsoft.com/api/alerts?`$top=10"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$alertResponse = Invoke-WebRequest -Method Get -Uri $alertUrl -Headers $headers -ErrorAction Stop
$alerts =  ($alertResponse | ConvertFrom-Json).value

$machinesToInvestigate = New-Object System.Collections.ArrayList

Foreach($alert in $alerts)
{
    #echo $alert.id $alert.machineId    $alert.severity $alert.status

    $isSevereAlert = $alert.severity -in 'Medium', 'High'
    $isOpenAlert = $alert.status -in 'InProgress', 'New'
    if($isOpenAlert -and $isSevereAlert)
    {
        if (-not $machinesToInvestigate.Contains($alert.machineId))
        {
            $machinesToInvestigate.Add($alert.machineId) > $null
        }
    }
}

$commaSeparatedMachines = '"{0}"' -f ($machinesToInvestigate -join '","')

$query = "NetworkCommunicationEvents
| where MachineId in ($commaSeparatedMachines)
| where RemoteUrl  == `"$suspiciousUrl`"
| summarize ConnectionsCount = count() by MachineId"

$queryUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"

$queryBody = ConvertTo-Json -InputObject @{ 'Query' = $query }
$queryResponse = Invoke-WebRequest -Method Post -Uri $queryUrl -Headers $headers -Body $queryBody -ErrorAction Stop
$response =  ($queryResponse | ConvertFrom-Json).Results
$response
```


## <a name="see-also"></a><span data-ttu-id="880f8-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="880f8-126">See also</span></span>
- [<span data-ttu-id="880f8-127">APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="880f8-127">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="880f8-128">API de Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="880f8-128">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="880f8-129">Busca avançada usando Python</span><span class="sxs-lookup"><span data-stu-id="880f8-129">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
