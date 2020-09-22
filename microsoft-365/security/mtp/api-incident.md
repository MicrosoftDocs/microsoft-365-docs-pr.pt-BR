---
title: Tipo de recurso de incidente na API de proteção contra ameaças da Microsoft
description: Saiba mais sobre os métodos e as propriedades do tipo de recurso incidente no Microsoft Threat Protection
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
ms.openlocfilehash: ac149ca7263b8ef8bb37a7dd18bf0787a3114b37
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201298"
---
# <a name="incident-resource-type"></a>Tipo de recurso incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="methods"></a>Methods

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
