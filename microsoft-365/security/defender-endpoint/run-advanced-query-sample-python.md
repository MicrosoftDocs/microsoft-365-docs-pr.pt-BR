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
ms.technology: mde
ms.openlocfilehash: 78b6097ea9c3a83f35585f3b13fec4d9056ac25a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199712"
---
# <a name="advanced-hunting-using-python"></a>Busca Avançada usando Python

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Execute consultas avançadas usando Python, consulte [Api de Busca Avançada](run-advanced-query-api.md).

Nesta seção, compartilharemos exemplos python para recuperar um token e usá-lo para executar uma consulta.

>**Pré-requisito:** primeiro você precisa [criar um aplicativo](apis-intro.md).

## <a name="get-token"></a>Obter token

- Execute os seguintes comandos:

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

where
- tenantId: ID do locatário em nome do qual você deseja executar a consulta (ou seja, a consulta será executado nos dados desse locatário)
- appId: ID do seu aplicativo do Azure AD (o aplicativo deve ter permissão 'Executar consultas avançadas' para o Microsoft Defender para o Ponto de Extremidade)
- appSecret: Segredo do seu aplicativo do Azure AD

## <a name="run-query"></a>Executar consulta

 Execute a seguinte consulta:

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

- esquema contém o esquema dos resultados de sua consulta
- resultados contêm os resultados de sua consulta

### <a name="complex-queries"></a>Consultas complexas

Se você quiser executar consultas complexas (ou consultas de várias linhas), salve sua consulta em um arquivo e, em vez da primeira linha no exemplo acima, execute o comando abaixo:

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>Trabalhar com os resultados da consulta

Agora você pode usar os resultados da consulta.

Para iterar sobre os resultados, faça o abaixo:

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


Para saída dos resultados da consulta no formato CSV no file1.csv faça o abaixo:

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

Para saída dos resultados da consulta no formato JSON no arquivo file1.jsfazer o abaixo:

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a>Tópicos relacionados
- [APIs do Microsoft Defender para Ponto de Extremidade](apis-intro.md)
- [API de Busca Avançada](run-advanced-query-api.md)
- [Busca Avançada usando o PowerShell](run-advanced-query-sample-powershell.md)
