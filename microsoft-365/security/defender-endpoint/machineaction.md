---
title: Tipo de recurso machineAction
description: Saiba mais sobre os métodos e propriedades do tipo de recurso MachineAction no Microsoft Defender para Ponto de Extremidade.
keywords: apis, apis com suporte, get, machineaction, recent
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
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187376"
---
# <a name="machineaction-resource-type"></a>Tipo de recurso MachineAction

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Para obter mais informações, consulte [Ações de Resposta](respond-machine-alerts.md). 

| Método                                                            | Tipo de retorno                        | Descrição                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [Listar MachineActions](get-machineactions-collection.md)           | [Ação do Computador](machineaction.md) | Listar [entidades de ação](machineaction.md) do computador.           |
| [Obter MachineAction](get-machineaction-object.md)                  | [Ação do Computador](machineaction.md) | Obter uma única [entidade ação do](machineaction.md) computador.     |
| [Coletar pacote de investigação](collect-investigation-package.md) | [Ação do Computador](machineaction.md) | Coletar pacote de investigação de um [computador](machine.md). |
| [Obter URI SAS do pacote de investigação](get-package-sas-uri.md)       | [Ação do Computador](machineaction.md) | Obter URI para baixar o pacote de investigação.          |
| [Isolar computador](isolate-machine.md)                             | [Ação do Computador](machineaction.md) | Isolar [o computador](machine.md) da rede.                 |
| [Liberar computador do isolamento](unisolate-machine.md)            | [Ação do Computador](machineaction.md) | Liberar [máquina](machine.md) do Isolamento.               |
| [Restringir execução de aplicativo](restrict-code-execution.md)              | [Ação do Computador](machineaction.md) | Restringir a execução do aplicativo.                             |
| [Remover restrição de aplicativo](unrestrict-code-execution.md)            | [Ação do Computador](machineaction.md) | Remover restrição de execução do aplicativo.                   |
| [Executar verificação de antivírus](run-av-scan.md)                              | [Ação do Computador](machineaction.md) | Execute uma verificação av usando Windows Defender (quando aplicável).    |
| [Remover computador](offboard-machine-api.md)                       | [Ação do Computador](machineaction.md) | Máquina de [offboard](machine.md) do Microsoft Defender para Ponto de Extremidade. |
| [Interromper e colocar o arquivo em quarentena](stop-and-quarantine-file.md)           | [Ação do Computador](machineaction.md) | Pare a execução de um arquivo em um computador e exclua-o.        |

<br>

## <a name="properties"></a>Propriedades

| Propriedade            | Tipo           | Descrição                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                  | Guid           | Identidade da [entidade Ação do](machineaction.md) Computador.                                                                                                                                                     |
| tipo                | Enum           | Tipo da ação. Os valores possíveis são: "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" e "UnrestrictCodeExecution" |
| escopo               | string         | Escopo da ação. "Completo" ou "Seletivo" para Isolamento, "Rápido" ou "Completo" para verificação de Antivírus.                                                                                                   |
| requestor           | Cadeia de caracteres         | Identidade da pessoa que executou a ação.                                                                                                                                                               |
| requestorComment    | Cadeia de caracteres         | Comentário que foi escrito durante a emissão da ação.                                                                                                                                                              |
| status              | Enum           | Status atual do comando. Os valores possíveis são: "Pendente", "InProgress", "Succeeded", "Failed", "TimeOut" e "Canceled".                                                                                 |
| machineId           | Cadeia de caracteres         | ID do [computador no](machine.md) qual a ação foi executada.                                                                                                                                              |
| machineId           | Cadeia de caracteres         | Nome do [computador no](machine.md) qual a ação foi executada.                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | A data e a hora em que a ação foi criada.                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | A última data e hora em que o status da ação foi atualizado.                                                                                                                                                     |
| relatedFileInfo     | Classe          | Contém duas propriedades. string ```fileIdentifier``` , Enum ```fileIdentifierType``` com os valores possíveis: "Sha1", "Sha256" e "Md5".                                                                         |


## <a name="json-representation"></a>Representação Json

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
