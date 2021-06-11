---
title: Executar comandos de resposta ao vivo em um dispositivo
description: Saiba como executar uma sequência de comandos de resposta ao vivo em um dispositivo.
keywords: apis, api gráfica, apis com suporte, upload na biblioteca
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879638"
---
#  <a name="run-live-response-commands-on-a-device"></a>Executar comandos de resposta ao vivo em um dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrição da API

Executa uma sequência de comandos de resposta ao vivo em um dispositivo

## <a name="limitations"></a>Limitações

1.  Limitações de taxa para essa API são 10 chamadas por minuto (solicitações adicionais são atendidas com HTTP 429).

2.  25 sessões em execução simultâneas (solicitações que excedem o limite de limitação receberão uma resposta "429 - Solicitações excessivas").

3.  Se o computador não estiver disponível, a sessão será en fila por até 3 dias.

4.  Tempo de tempo de comando RunScript após 10 minutos.

5.  Quando um comando de resposta ao vivo falhar, todas as ações seguidas não serão executadas.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md).

| Tipo de permissão                    | Permissão           | Nome de exibição de permissão                   |
|------------------------------------|----------------------|-------------------------------------------|
| Aplicativo                        | Machine.LiveResponse | Executar resposta ao vivo em um computador específico |
| Delegado (conta corporativa ou de estudante) | Machine.LiveResponse | Executar resposta ao vivo em um computador específico |

## <a name="http-request"></a>Solicitação HTTP

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

| Nome      | Tipo | Descrição                 |
|---------------|----------|---------------------------------|
| Autorização | Cadeia de caracteres   | Portador\<token>\. Obrigatório.   |
| Content-Type  | string   | application/json. Obrigatório. |

## <a name="request-body"></a>Corpo da solicitação

| Parâmetro | Tipo | Descrição                                                        |
|---------------|----------|------------------------------------------------------------------------|
| Comentário       | String   | Comentário para associar à ação.                                 |
| Comandos      | Matriz    | Comandos a executar. Os valores permitidos são PutFile, RunScript, GetFile. |

Comandos:

| Tipo de Comando | Parâmetros                                                                          | Descrição                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PutFile      | Chave: FileName  <br><br>  Valor: \<file name\>                                                                          | Coloca um arquivo da biblioteca no dispositivo. Os arquivos são salvos em uma pasta de trabalho e são excluídos quando o dispositivo é reiniciado por padrão.
| RunScript    | Chave: ScriptName<br>Valor: \<Script from library\> <br><br> Chave: Args  <br> Valor: \<Script arguments\>                          | Executa um script da biblioteca em um dispositivo.    <br><br>  O parâmetro Args é passado para seu script. <br><br> Tempo de duração após 10 minutos.     
| GetFile      | Chave: Caminho <br> Valor: \<File path\>                                                        | Coletar arquivo de um dispositivo. OBSERVAÇÃO: backslashes in path deve ser escape.                                                                      |

## <a name="response"></a>Resposta

-   Se tiver êxito, este método retornará 200, ok.
    Entidade Action. Se o computador com a ID especificada não for encontrado - 404 Não Encontrado.

## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
**JSON**

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

**Response**

Veja a seguir um exemplo da resposta.

```HTTP
HTTP/1.1 200 Ok
```

Tipo de conteúdo: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a>Tópicos relacionados
- [Obter API de ação de máquina](get-machineaction-object.md)
- [Obter resultado de resposta ao vivo](get-live-response-result.md)
- [Cancelar ação do computador](cancel-machine-action.md)
