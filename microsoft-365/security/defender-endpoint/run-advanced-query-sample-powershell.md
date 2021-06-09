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
ms.openlocfilehash: 0d44f59f69c590ecd8d61207de8784af3e32197d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844881"
---
# <a name="advanced-hunting-using-powershell"></a>Busca avançada usando o PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Execute consultas avançadas usando o PowerShell, consulte [Advanced Hunting API](run-advanced-query-api.md).

Nesta seção, compartilharemos exemplos do PowerShell para recuperar um token e usá-lo para executar uma consulta.

## <a name="before-you-begin"></a>Antes de começar
Primeiro, você precisa [criar um aplicativo.](apis-intro.md)

## <a name="preparation-instructions"></a>Instruções de preparação

- Abra uma janela do PowerShell.
- Se sua política não permitir que você execute os comandos do PowerShell, você poderá executar o comando abaixo:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>Para obter mais informações, consulte [Documentação do PowerShell](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>Obter token

- Execute:

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

where
- $tenantId: ID do locatário em nome do qual você deseja executar a consulta (ou seja, a consulta será executado nos dados desse locatário)
- $appId: ID do seu aplicativo do Azure AD (o aplicativo deve ter permissão 'Executar consultas avançadas' para o Defender para Ponto de Extremidade)
- $appSecret: Segredo do seu aplicativo do Azure AD

## <a name="run-query"></a>Executar consulta

Execute a seguinte consulta:

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

- $results contêm os resultados de sua consulta
- $schema contém o esquema dos resultados da consulta

### <a name="complex-queries"></a>Consultas complexas

Se você quiser executar consultas complexas (ou consultas de várias linhas), salve sua consulta em um arquivo e, em vez da primeira linha no exemplo acima, execute o comando abaixo:

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>Trabalhar com os resultados da consulta

Agora você pode usar os resultados da consulta.

Para saída dos resultados da consulta no formato CSV no file1.csv faça o abaixo:

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

Para saída dos resultados da consulta no formato JSON no arquivo file1.jsfazer o abaixo:

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>Tópicos relacionados
- [APIs do Microsoft Defender para Ponto de Extremidade](apis-intro.md)
- [API de Busca Avançada](run-advanced-query-api.md)
- [Busca avançada usando Python](run-advanced-query-sample-python.md)
