---
title: APIs de incidentes do Microsoft 365 Defender e o tipo de recurso de incidente
description: Saiba mais sobre os métodos e as propriedades do tipo de recurso Incident no Microsoft 365 Defender
keywords: incidente, incidentes, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928349"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>API de incidentes do Microsoft 365 Defender e o tipo de recurso de incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Um [incidente](incidents-overview.md) é uma coleção de alertas relacionados que ajudam a descrever um ataque. Eventos de entidades diferentes em sua organização são automaticamente agregados pelo Microsoft 365 Defender. Você pode usar a API de incidentes para acessar programaticamente os incidentes e alertas relacionados da sua organização.

## <a name="quotas-and-resource-allocation"></a>Cotas e alocação de recursos

Você pode solicitar até 50 chamadas por minuto ou 1500 chamadas por hora. Cada método também tem suas próprias cotas. Para obter mais informações sobre cotas específicas do método, consulte o respectivo artigo sobre o método que você deseja usar.

Um código de resposta HTTP indica que você atingiu uma cota, por número de solicitações enviadas ou por tempo `429` de execução alocado. O corpo da resposta incluirá o tempo até que a cota alcançada seja redefinida.

## <a name="permissions"></a>Permissions

A API de incidentes requer diferentes tipos de permissões para cada um de seus métodos. Para obter mais informações sobre as permissões necessárias, consulte o artigo do respectivo método.

## <a name="methods"></a>Métodos

Método | Tipo de retorno | Descrição
-|-|-
[Listar incidentes](api-list-incidents.md) | [Lista de](api-incident.md) incidentes | Obter uma lista de incidentes.
[Atualizar incidente](api-update-incidents.md) | [Incidente](api-incident.md) | Atualizar um incidente específico.

## <a name="request-body-response-and-examples"></a>Solicitar corpo, resposta e exemplos

Consulte os respectivos artigos de método para obter mais detalhes sobre como construir uma solicitação ou analisar uma resposta e para obter exemplos práticos.

## <a name="common-properties"></a>Propriedades comuns

Propriedade | Tipo | Descrição
-|-|-
incidentId | long | ID exclusiva do incidente.
redirectIncidentId | nullable long | A ID do incidente ao que o incidente atual foi mesclado.
incidentName | string | O nome do incidente.
createdTime | DateTimeOffset | A data e a hora (em UTC) em que o incidente foi criado.
lastUpdateTime | DateTimeOffset | A data e a hora (em UTC) em que o incidente foi atualizado pela última vez.
assignedTo | string | Proprietário do incidente.
severity | Enum | Gravidade do incidente. Os valores possíveis ```UnSpecified``` são: ```Informational``` , , e ```Low``` ```Medium``` ```High``` .
status | Enum | Especifica o status atual do incidente. Os valores possíveis ```Active``` são: ```Resolved``` , e ```Redirected``` .
classificação | Enum | Especificação do incidente. Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.
determinação | Enum | Especifica a determinação do incidente. Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | string List | Lista de marcas de incidente.
alerts | Lista de alertas | Lista de alertas relacionados. Veja exemplos na documentação da API [de incidentes](api-list-incidents.md) de lista.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 Defender](api-overview.md)
- [Visão geral dos incidentes](incidents-overview.md)
- [Listar API de incidentes](api-list-incidents.md)
- [Atualizar API de incidentes](api-update-incidents.md)
