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
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a>Microsoft Defender para APIs de ponto de extremidade usando o PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Cenário completo usando várias APIs do Microsoft Defender para Ponto de Extremidade.

Nesta seção, compartilharemos exemplos do PowerShell para 
- Recuperar um token 
- Usar token para recuperar os alertas mais recentes no Microsoft Defender para Ponto de Extremidade
- Para cada alerta, se o alerta tiver prioridade média ou alta e ainda estiver em andamento, verifique quantas vezes o dispositivo se conectou a URL suspeita.

**Pré-requisito:** primeiro você precisa [criar um aplicativo](apis-intro.md).

## <a name="preparation-instructions"></a>Instruções de preparação

- Abra uma janela do PowerShell.
- Se sua política não permitir que você execute os comandos do PowerShell, você poderá executar o comando abaixo:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

Para obter mais informações, consulte [Documentação do PowerShell](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>Obter token

Execute o abaixo:

- $tenantId: ID do locatário em nome do qual você deseja executar a consulta (ou seja, a consulta será executado nos dados desse locatário)
- $appId: ID do seu aplicativo AAD (o aplicativo deve ter permissão 'Executar consultas avançadas' para o Defender para o Ponto de Extremidade)
- $appSecret: Segredo do seu aplicativo do Azure AD

- $suspiciousUrl: a URL


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


## <a name="see-also"></a>Confira também
- [APIs do Microsoft Defender para Ponto de Extremidade](apis-intro.md)
- [API de Busca Avançada](run-advanced-query-api.md)
- [Busca avançada usando Python](run-advanced-query-sample-python.md)
