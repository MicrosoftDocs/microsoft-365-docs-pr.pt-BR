---
title: APIs de incidentes do Microsoft 365 defender e o tipo de recurso de incidente
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
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719329"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>API de incidentes do Microsoft 365 defender e tipo de recurso de incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Um [incidente](incidents-overview.md) é uma coleção de alertas relacionados que ajudam a descrever um ataque. Eventos de diferentes entidades em sua organização são agregados automaticamente pelo Microsoft 365 defender. Você pode usar a API de incidentes para acessar programaticamente os incidentes da sua organização e alertas relacionados.

## <a name="quotas-and-resource-allocation"></a>Cotas e alocação de recursos

Você pode solicitar até 50 chamadas por minuto ou 1500 de chamadas por hora. Cada método também tem suas próprias cotas. Para obter mais informações sobre cotas específicas de método, consulte o respectivo artigo referente ao método que você deseja usar.

Um `429` código de resposta http indica que você atingiu uma cota, seja pelo número de solicitações enviadas ou pelo tempo de execução alocado. O corpo da resposta incluirá o tempo até que a cota que você atingiu seja redefinida.

## <a name="permissions"></a>Permissões

A API de incidentes requer diferentes tipos de permissões para cada um de seus métodos. Para obter mais informações sobre as permissões necessárias, consulte o artigo do respectivo método.

## <a name="methods"></a>Métodos

Método | Tipo de retorno | Descrição
-|-|-
[Listar incidentes](api-list-incidents.md) | Lista de [incidentes](api-incident.md) | Obter uma lista de incidentes.
[Atualizar incidente](api-update-incidents.md) | [Incidente](api-incident.md) | Atualize um incidente específico.

## <a name="request-body-response-and-examples"></a>Corpo, resposta e exemplos de solicitação

Consulte os respectivos artigos do método para obter mais detalhes sobre como criar uma solicitação ou analisar uma resposta e exemplos práticos.

## <a name="common-properties"></a>Propriedades comuns

Propriedade | Tipo | Descrição
-|-|-
incidentalid | long | ID exclusiva do incidente.
redirectIncidentId | Long anulável | A ID de incidente à qual o incidente atual foi mesclado.
incidentalname | string | O nome do incidente.
createdtime | DateTimeOffset | A data e a hora (em UTC) que o incidente foi criado.
lastUpdateTime | DateTimeOffset | A data e a hora (em UTC) que o incidente foi atualizado pela última vez.
assignedTo | string | Proprietário do incidente.
severity | Enum | Gravidade do incidente. Os valores possíveis são: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` e ```High``` .
status | Enum | Especifica o status atual do incidente. Os valores possíveis são: ```Active``` , ```Resolved``` , e ```Redirected``` .
classificação | Enum | Especificação do incidente. Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.
determinação | Enum | Especifica a determinação do incidente. Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | Lista de cadeia de caracteres | Lista de marcas de incidente.
alerts | Lista de alerta | Lista de alertas relacionados. Consulte exemplos na documentação da API de [incidentes de lista](api-list-incidents.md) .

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 defender](api-overview.md)
- [Visão geral dos incidentes](incidents-overview.md)
- [Listar a API de incidentes](api-list-incidents.md)
- [Atualizar a API de incidente](api-update-incidents.md)
