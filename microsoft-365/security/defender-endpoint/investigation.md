---
title: Tipo de recurso de investigação
description: Entidade Microsoft Defender para Investigação de Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, alertas, investigações
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 252b273995d48d523604802c0c4365a613d86dbe
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771724"
---
# <a name="investigation-resource-type"></a>Tipo de recurso de investigação

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Represente uma entidade de Investigação Automatizada no Defender para Ponto de Extremidade.
<br> Confira [Visão geral das investigações automatizadas](automated-investigations.md) para obter mais informações.

## <a name="methods"></a>Métodos
Método|Tipo de retorno |Descrição
:---|:---|:---
[List Investigations](get-investigation-collection.md) | Coleção Investigation | Obter coleção de Investigação
[Obter investigação única](get-investigation-object.md) | Entidade de investigação | Obtém uma única entidade De investigação.
[Iniciar investigação](initiate-autoir-investigation.md) | Entidade de investigação | Inicia a investigação em um dispositivo.


## <a name="properties"></a>Propriedades
Propriedade |  Tipo    |   Descrição
:---|:---|:---
id | Cadeia de caracteres | Identidade da entidade de investigação. 
startTime | DateTime Nullable | A data e a hora em que a investigação foi criada. 
endTime | DateTime Nullable | A data e a hora em que a investigação foi concluída. 
cancelledBy | Cadeia de caracteres | A ID do usuário/aplicativo que cancelou essa investigação. 
investigationState | Enum | O estado atual da investigação. Os valores possíveis são: 'Unknown', 'Terminado', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
statusDetails | Cadeia de caracteres | Informações adicionais sobre o estado da investigação.
machineId | Cadeia de caracteres | A ID do dispositivo no qual a investigação é executada.
computerDnsName | Cadeia de caracteres | O nome do dispositivo no qual a investigação é executada.
triggeringAlertId | Cadeia de caracteres | A ID do alerta que disparou a investigação.


## <a name="json-representation"></a>Representação Json

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
