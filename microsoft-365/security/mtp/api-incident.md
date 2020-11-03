---
title: Tipo de recurso de incidente na API do Microsoft 365 defender
description: Saiba mais sobre os métodos e as propriedades do tipo de recurso incidente no Microsoft 365 defender
keywords: incidente, incidentes, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844015"
---
# <a name="incident-resource-type"></a>Tipo de recurso incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>Métodos

Método |Tipo de retorno |Descrição
:---|:---|:---
[Listar incidentes](api-list-incidents.md) | Lista de [incidentes](api-incident.md) | Obter uma lista de incidentes.
[Atualizar incidente](api-update-incidents.md) | [Incidente](api-incident.md) | Atualize o incidente específico.


## <a name="properties"></a>Propriedades

Propriedade |    Tipo    |    Descrição
:---|:---|:---
incidentalid | long | ID exclusiva do incidente.
redirectIncidentId | Long anulável | A ID de incidente à qual o incidente atual foi mesclado.
incidentalname | string | O nome do incidente.
createdtime | DateTimeOffset | A data e a hora (em UTC) que o incidente foi criado.
lastUpdateTime | DateTimeOffset | A data e a hora (em UTC) que o incidente foi atualizado pela última vez.
assignedTo | string | Proprietário do incidente.
severity | Enum | Gravidade do incidente. Os valores possíveis são: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` e ```High``` .
status | Enum | Especifica o status atual do incidente. Os valores possíveis são ```Active``` : ```Resolved``` e ```Redirected``` .
classificação | Enum | Especificação do incidente. Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.
determinação | Enum | Especifica a determinação do incidente. Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
categorias | Lista de cadeia de caracteres | Lista de marcas de incidente.
alerts | Lista de alerta | Lista de alertas relacionados. Consulte exemplos na documentação da API de [incidentes de lista](api-list-incidents.md) .
