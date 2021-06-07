---
title: Puxar o Microsoft Defender para detecções de ponto de extremidade usando a API REST
description: Saiba como chamar um ponto de extremidade da API do Microsoft Defender para Endpoint para puxar detecções no formato JSON usando a API REST siem.
keywords: detecções, detecções de pull, api de repouso, solicitação, resposta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 6716b0eb029b49ec08cb52ebefc23e50b19036ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771664"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>Puxar o Microsoft Defender para detecções de ponto de extremidade usando a API REST SIEM

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- [O Alerta do Microsoft Defender para Ponto](alerts.md) de Extremidade é composto por uma ou mais detecções.
>- [O Microsoft Defender para Detecção de Ponto](api-portal-mapping.md) de Extremidade é composto do evento suspeito ocorrido no Dispositivo e seus detalhes de Alerta relacionados.
>-A API de alerta do Microsoft Defender for Endpoint é a API mais recente para consumo de alerta e contém uma lista detalhada de evidências relacionadas para cada alerta. Para obter mais informações, consulte [Métodos de alerta e propriedades](alerts.md) e [Alertas de lista.](get-alerts.md)

O Microsoft Defender para Ponto de Extremidade oferece suporte ao protocolo OAuth 2.0 para puxar detecções da API.

Em geral, o protocolo OAuth 2.0 oferece suporte a quatro tipos de fluxos:
- Fluxo de concessão de autorização
- Fluxo implícito
- Fluxo de credenciais do cliente
- Fluxo do proprietário do recurso

Para obter mais informações sobre as especificações do OAuth, consulte o [site OAuth](http://www.oauth.net).

O Microsoft Defender for  Endpoint  oferece suporte ao fluxo de concessão de autorização e ao fluxo de credenciais do cliente para obter acesso a detecções de pull, com Azure Active Directory (AAD) como o servidor de autorização.

O _fluxo de concessão de_ autorização usa credenciais de usuário para obter um código de autorização, que é usado para obter um token de acesso.

O _fluxo de credenciais do cliente_ usa credenciais de cliente para autenticar na URL do ponto de extremidade do Microsoft Defender para Ponto de Extremidade. Esse fluxo é adequado para cenários em que um cliente OAuth cria solicitações para uma API que não exige credenciais de usuário.

Use o método a seguir na API do Microsoft Defender para Ponto de Extremidade para puxar detecções no formato JSON.

>[!NOTE]
>Central de Segurança do Microsoft Defender mescla detecções de alerta semelhantes em um único alerta. Essa API puxa detecções de alerta em sua forma bruta com base nos parâmetros de consulta que você definiu, permitindo que você aplique seu próprio grupo e filtragem. 

## <a name="before-you-begin"></a>Antes de você começar
- Antes de chamar o ponto de extremidade do Microsoft Defender para Endpoint para detectar, você precisará habilitar o aplicativo de integração siem no Azure Active Directory (AAD). Para obter mais informações, consulte [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).

- Anote os valores a seguir no registro do seu aplicativo Azure. Você precisa desses valores para configurar o fluxo OAuth em seu aplicativo de serviço ou daemon:
  - ID do aplicativo (exclusiva para o seu aplicativo)
  - Chave do aplicativo ou segredo (exclusiva para o seu aplicativo)
  - O ponto de extremidade de token OAuth 2.0 de seu aplicativo
    - Encontre esse valor clicando em **Exibir Pontos de Extremidade** na parte inferior do Portal de Gerenciamento do Azure, na página do seu aplicativo. O ponto de extremidade terá a seguinte aparência: `https://login.microsoftonline.com/{tenantId}/oauth2/token`.

## <a name="get-an-access-token"></a>Obter um token de acesso
Antes de criar chamadas para o ponto de extremidade, você precisará obter um token de acesso.

Você usará o token de acesso para acessar o recurso protegido, que é detecções no Microsoft Defender para Ponto de Extremidade.

Para obter um token de acesso, você precisará fazer uma solicitação POST ao ponto de extremidade de emissão de token. Aqui está uma solicitação de exemplo:

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
A resposta incluirá um token de acesso e informações sobre a expiração.

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
Agora você pode usar o valor no *campo* access_token em uma solicitação à API defender para ponto de extremidade.

## <a name="request"></a>Solicitação
Com um token de acesso, seu aplicativo pode fazer solicitações autenticadas para a API do Microsoft Defender para Ponto de Extremidade. Seu aplicativo deve anexar o token de acesso ao cabeçalho Authorization de cada solicitação.

### <a name="request-syntax"></a>Sintaxe de solicitação
Método | Solicitar URI
:---|:---|
GET| Use o URI aplicável à sua região. <br><br> **Para a UE**: `https://wdatp-alertexporter-eu.windows.com/api/alerts` </br> **Para NÓS**: `https://wdatp-alertexporter-us.windows.com/api/alerts` <br> **Para o Reino Unido**: `https://wdatp-alertexporter-uk.windows.com/api/alerts` 

### <a name="request-header"></a>Header de solicitação
Cabeçalho | Tipo | Descrição|
:--|:--|:--
Autorização | string | Obrigatório. O token de acesso do Azure AD no token **do** &lt; *portador do formulário* &gt; . |

### <a name="request-parameters"></a>Solicitar parâmetros

Use parâmetros de consulta opcionais para especificar e controlar a quantidade de dados retornados em uma resposta. Se você chamar esse método sem parâmetros, a resposta conterá todos os alertas em sua organização nas últimas 2 horas.

Nome | Valor| Descrição
:---|:---|:---
sinceTimeUtc | DateTime | Define os alertas com limite de tempo inferior dos quais os alertas são recuperados, com base no campo: <br> `LastProcessedTimeUtc` <br> O intervalo de tempo será: de sinceTimeUtc até a hora atual. <br><br> **OBSERVAÇÃO**: Quando não especificado, todos os alertas gerados nas últimas duas horas são recuperados.
untilTimeUtc | DateTime | Define que os alertas de limite de tempo superior são recuperados. <br> O intervalo de tempo será: de `sinceTimeUtc` vez em `untilTimeUtc` quando. <br><br> **OBSERVAÇÃO**: quando não especificado, o valor padrão será a hora atual.
ago | cadeia de caracteres | Puxa alertas no seguinte intervalo de tempo: de `(current_time - ago)` vez em `current_time` quando. <br><br> O valor deve ser definido de acordo com o formato de duração **iso 8601** <br> Exemplo: `ago=PT10M` puxará alertas recebidos nos últimos 10 minutos.
limite | int | Define o número de alertas a serem recuperados. Os alertas mais recentes serão recuperados com base no número definido.<br><br> **OBSERVAÇÃO**: Quando não especificado, todos os alertas disponíveis no intervalo de tempo serão recuperados.
machinegroups | cadeia de caracteres | Especifica grupos de dispositivos para puxar alertas. <br><br> **OBSERVAÇÃO**: Quando não especificado, os alertas de todos os grupos de dispositivos serão recuperados. <br><br> Exemplo: <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
DeviceCreatedMachineTags | cadeia de caracteres | Marca de dispositivo único do Registro.
CloudCreatedMachineTags | cadeia de caracteres | Marcas de dispositivo que foram criadas Central de Segurança do Microsoft Defender.

### <a name="request-example"></a>Exemplo de solicitação
O exemplo a seguir demonstra como recuperar todas as detecções em sua organização.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

O exemplo a seguir demonstra uma solicitação para obter as últimas 20 detecções desde 2016-09-12 00:00:00.

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>Resposta
O valor de retorno é uma matriz de objetos de alerta no formato JSON.

Aqui está um valor de retorno de exemplo:

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>Exemplos de código
### <a name="get-access-token"></a>Obter token de acesso
Os exemplos de código a seguir demonstram como obter um token de acesso para chamar a API SIEM do Microsoft Defender para Ponto de Extremidade.

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>Usar token para se conectar ao ponto de extremidade de detecções
Os exemplos de código a seguir demonstram como usar um token de acesso para chamar a API SIEM do Defender para Ponto de Extremidade para obter alertas.

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>Códigos de erro
A API REST do Microsoft Defender para Ponto de Extremidade retorna os seguintes códigos de erro causados por uma solicitação inválida.

Código de erro HTTP | Descrição
:---|:---
401 | Solicitação malformada ou token inválido.
403 | Exceção não autorizada - qualquer um dos domínios não é gerenciado pelo administrador do locatário ou o estado do locatário é excluído.
500 | Erro no serviço.

## <a name="related-topics"></a>Tópicos relacionados
- [Habilitar a integração do SIEM no Microsoft Defender para Endpoint](enable-siem-integration.md)
- [Configurar ArcSight para puxar o Microsoft Defender para detecções de ponto de extremidade](configure-arcsight.md)
- [Pull detections to your SIEM tools](configure-siem.md)
- [Campos de Detecção de Ponto de Extremidade do Microsoft Defender](api-portal-mapping.md)
- [Solucionar problemas de integração da ferramenta SIEM](troubleshoot-siem.md)
