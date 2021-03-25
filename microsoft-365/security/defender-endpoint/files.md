---
title: Tipo de recurso File
description: Recupere alertas recentes do Microsoft Defender para Endpoint relacionados a arquivos.
keywords: apis, api gráfica, apis com suporte, obter, alertas, recentes
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
ms.openlocfilehash: 9079a47dcc078b582586370b322502b74ce3838c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199976"
---
# <a name="file-resource-type"></a>Tipo de recurso File

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Represente uma entidade de arquivo no Defender para Ponto de Extremidade.

## <a name="methods"></a>Métodos
Método|Tipo de retorno |Descrição
:---|:---|:---
[Obter arquivo](get-file-information.md) | [file](files.md) | Obter um único arquivo 
[Listar alertas relacionados ao arquivo](get-file-related-alerts.md) | conjunto [alerta](alerts.md)  | Obter as [entidades](alerts.md) de alerta associadas ao arquivo.
[Listar máquinas relacionadas a arquivos](get-file-related-machines.md) | [coleção machine](machine.md) | Obter as [entidades](machine.md) do computador associadas ao alerta.
[estatísticas de arquivo](get-file-statistics.md) | Resumo de estatísticas | Recupera a prevalência do arquivo determinado.


## <a name="properties"></a>Propriedades
|Propriedade | Tipo    |   Descrição |
|:---|:---|:---|
|sha1 | Cadeia de caracteres | Hash sha1 do conteúdo do arquivo |
|sha256 | Cadeia de caracteres | Hash sha256 do conteúdo do arquivo |
|globalPrevalence | Long anulado | Prevalência de arquivo em toda a organização |
|globalFirstObserved | DateTimeOffset | Primeira vez que o arquivo foi observado |
|globalLastObserved | DateTimeOffset | Última vez que o arquivo foi observado |
|size | Long anulado | Tamanho do arquivo |
|fileType | Cadeia de caracteres | Tipo do arquivo |
|isPeFile | Booleano | true se o arquivo for executável portátil (por exemplo, "DLL", "EXE", etc.) |
|filePublisher | Cadeia de caracteres | Editor de arquivos |
|fileProductName | Cadeia de caracteres | Nome do produto |
|signer | Cadeia de caracteres | Signante de arquivo |
|emissor | Cadeia de caracteres | Emissor de arquivo |
|signerHash | Cadeia de caracteres | Hash do certificado de assinatura |
|isValidCertificate | Booleano | Foi verificado com êxito o certificado de assinatura pelo Microsoft Defender para agente do Ponto de Extremidade |
|determinationType | Cadeia de caracteres | O tipo de determinação do arquivo |
|determinationValue | Cadeia de caracteres | Valor de determinação |


## <a name="json-representation"></a>Representação Json

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
