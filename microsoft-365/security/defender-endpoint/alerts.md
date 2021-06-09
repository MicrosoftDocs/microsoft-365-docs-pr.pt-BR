---
title: Obter API de alertas
description: Saiba mais sobre os métodos e propriedades do tipo de recurso Alerta no Microsoft Defender para Ponto de Extremidade.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c935df1abddc3d0ebee74e09280d6e3ec961ca97
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769804"
---
# <a name="alert-resource-type"></a>Tipo de recurso de alerta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>Métodos

Método |Tipo de retorno |Descrição
:---|:---|:---
[Obter alerta](get-alert-info-by-id.md) | [Alerta](alerts.md) | Obter um único [objeto de](alerts.md) alerta.
[Listar alertas](get-alerts.md) | [Coleção Alert](alerts.md) | Listar [coleção de](alerts.md) alertas.
[Atualizar alertas](update-alert.md) | [Alerta](alerts.md) | Atualizar alerta [específico](alerts.md).
[Alertas de atualização em lotes](batch-update-alerts.md) | | Atualizar um lote de [alertas](alerts.md).
[Criar alerta](create-alert-by-reference.md)|[Alerta](alerts.md)|Criar um alerta com base nos dados de evento obtidos da [Busca Avançada](run-advanced-query-api.md).
[Listar domínios relacionados](get-alert-related-domain-info.md)|Coleção Domain| Listar URLs associadas ao alerta.
[Listar arquivos relacionados](get-alert-related-files-info.md) | [Coleção File](files.md) |  Listar [as entidades](files.md) de arquivo associadas ao [alerta](alerts.md).
[Listar IPs relacionados](get-alert-related-ip-info.md) | Coleção IP | Listar IPs associados ao alerta.
[Obter máquinas relacionadas](get-alert-related-machine-info.md) | [Computador](machine.md) | O [computador](machine.md) associado ao [alerta](alerts.md).
[Obter usuários relacionados](get-alert-related-user-info.md) | [Usuário](user.md) | O [usuário](user.md) associado ao [alerta](alerts.md).


## <a name="properties"></a>Propriedades

Propriedade |    Tipo    |    Descrição
:---|:---|:---
id | Cadeia de caracteres | ID do alerta.
title | String | Título do alerta.
descrição | String | Descrição de alerta.
alertCreationTime | Nullable DateTimeOffset | A data e a hora (em UTC) em que o alerta foi criado.
lastEventTime | Nullable DateTimeOffset | A última ocorrência do evento que disparou o alerta no mesmo dispositivo.
firstEventTime | Nullable DateTimeOffset | A primeira ocorrência do evento que disparou o alerta nesse dispositivo.
lastUpdateTime | Nullable DateTimeOffset | A data e a hora (em UTC) em que o alerta foi atualizado pela última vez.
resolvedTime | Nullable DateTimeOffset | A data e a hora em que o status do alerta foi alterado para 'Resolvido'.
incidentId | Long anulado | A [](view-incidents-queue.md) ID do Incidente do Alerta.
investigationId | Long anulado | A [](automated-investigations.md) ID da Investigação relacionada ao Alerta.
investigationState | Núm anulado | O estado atual da [Investigação](automated-investigations.md). Os valores possíveis são: 'Unknown', 'Terminado', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
assignedTo | Cadeia de caracteres | Proprietário do alerta.
severity | Enum | Gravidade do alerta. Os valores possíveis são: 'UnSpecified', 'Informational', 'Low', 'Medium' e 'High'.
status | Enum | Especifica o status atual do alerta. Os valores possíveis são: 'Unknown', 'New', 'InProgress' e 'Resolved'.
classificação | Núm anulado | Especificação do alerta. Os valores possíveis são: 'Unknown', 'FalsePositive', 'TruePositive'.
determinação | Núm anulado | Especifica a determinação do alerta. Os valores possíveis são: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'.
category| Cadeia de caracteres | Categoria do alerta.
detectionSource | Cadeia de caracteres | Fonte de detecção.
threatFamilyName | Cadeia de caracteres | Família de ameaças.
threatName | Cadeia de caracteres | Nome da ameaça.
machineId | Cadeia de caracteres | ID de uma [entidade](machine.md) de máquina associada ao alerta.
computerDnsName | Cadeia de caracteres | [nome](machine.md) totalmente qualificado da máquina.
aadTenantId | Cadeia de caracteres | A Azure Active Directory ID.
detectorId | Cadeia de caracteres | A ID do detector que disparou o alerta.
comentários | Lista de comentários de alerta | O objeto Comentário de Alerta contém: cadeia de caracteres de comentários, createdBy string e createTime date time.
Evidências | Lista de evidências de alerta | Evidências relacionadas ao alerta. Veja o exemplo a seguir.

### <a name="response-example-for-getting-single-alert"></a>Exemplo de resposta para obter um único alerta:

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "MIDDLEEAST"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "eranb",
            "domainName": "MIDDLEEAST",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
