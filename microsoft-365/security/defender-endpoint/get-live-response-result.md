---
title: Obter resultados de resposta ao vivo
description: Saiba como recuperar um resultado de comando de resposta ao vivo específico pelo índice.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879645"
---
#  <a name="get-live-response-results"></a>Obter resultados de resposta ao vivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>Descrição da API

Recupera um resultado de comando de resposta ao vivo específico pelo índice.

## <a name="limitations"></a>Limitações

1.  Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.

## <a name="permissions"></a>Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md).

| Tipo de permissão                    | Permissão           | Nome de exibição de permissão                   |
|------------------------------------|----------------------|-------------------------------------------|
| Aplicativo                        | Machine.LiveResponse | Executar resposta ao vivo em um computador específico |
| Delegado (conta corporativa ou de estudante) | Machine.LiveResponse | Executar resposta ao vivo em um computador específico |

## <a name="http-request"></a>Solicitação HTTP

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a>Cabeçalhos de solicitação

| Nome      | Tipo | Descrição               |
|---------------|----------|-------------------------------|
| Autorização | Cadeia de caracteres   | {token} de portador. Obrigatório. |

## <a name="request-body"></a>Corpo da solicitação

Vazio

## <a name="response"></a>Resposta

Se tiver êxito, este método retornará 200, código de resposta Ok com o objeto que contém o link para o resultado do comando na *propriedade value.* Esse link é válido por 30 minutos e deve ser usado imediatamente para baixar o pacote para um armazenamento local. Um link expirado pode ser re-criado por outra chamada e não é necessário executar a resposta ao vivo novamente.

*Propriedades de transcrição de runscript:*

| Propriedade  | Descrição                       |
|---------------|---------------------------------------|
| name          | Nome do script executado                  |
| exit_code     | Código de saída de script executado             |
| script_output | Saída padrão de script executada       |
| script_error  | Saída de erro padrão de script executada |

## <a name="example"></a>Exemplo

**Solicitação**

Este é um exemplo da solicitação.

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

**Response**

Veja a seguir um exemplo da resposta.

HTTP/1.1 200 Ok

Tipo de conteúdo: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

*Conteúdo do arquivo:* 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a>Tópicos relacionados

- [Obter API de ação de máquina](get-machineaction-object.md)
- [Cancelar ação do computador](cancel-machine-action.md)
- [Executar resposta ao vivo](run-live-response.md) 
