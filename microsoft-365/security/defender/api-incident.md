---
title: Microsoft 365 O Defender incidentes APIs e o tipo de recurso incidente
description: Conheça os métodos e propriedades do tipo de recurso incidente no Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572580"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender incidentes API e o tipo de recurso incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

Um [incidente](incidents-overview.md) é uma coleção de alertas relacionados que ajudam a descrever um ataque. Eventos de diferentes entidades em sua organização são automaticamente agregados pelo Microsoft 365 Defender. Você pode usar a API incidentes para acessar programaticamente os incidentes e alertas relacionados da sua organização.

## <a name="quotas-and-resource-allocation"></a>Cotas e alocação de recursos

Você pode solicitar até 50 chamadas por minuto ou 1500 chamadas por hora. Cada método também tem suas próprias cotas. Para obter mais informações sobre cotas específicas do método, consulte o respectivo artigo para o método que deseja usar.

Um `429` código de resposta HTTP indica que você atingiu uma cota, seja pelo número de solicitações enviadas ou pelo tempo de execução alocado. O órgão de resposta incluirá o tempo até que a cota que você alcançou seja redefinida.

## <a name="permissions"></a>Permissões

Os incidentes API requer diferentes tipos de permissões para cada um de seus métodos. Para obter mais informações sobre as permissões necessárias, consulte o artigo do respectivo método.

## <a name="methods"></a>Métodos

Método | Tipo de retorno | Descrição
-|-|-
[Listar incidentes](api-list-incidents.md) | [Lista de incidentes](api-incident.md) | Pegue uma lista de incidentes.
[Atualizar incidente](api-update-incidents.md) | [Incidente](api-incident.md) | Atualize um incidente específico.

## <a name="request-body-response-and-examples"></a>Solicitar corpo, resposta e exemplos

Consulte os respectivos artigos do método para obter mais detalhes sobre como construir uma solicitação ou analisar uma resposta e, para exemplos práticos.

## <a name="common-properties"></a>Propriedades comuns

Propriedade | Tipo | Descrição
-|-|-
incidenteId | long | ID único incidente.
redirecionarIncidentId | longa nulo | A ID do Incidente foi mesclada.
incidentName | cadeia de caracteres | O nome do Incidente.
criadoTime | DateTimeOffset | A data e a hora (em UTC) do Incidente foram criadas.
lastUpdateTime | DateTimeOffset | A data e a hora (em UTC) do Incidente foram atualizadas pela última vez.
assignedTo | cadeia de caracteres | Dono do Incidente.
severity | Enum | Gravidade do Incidente. Os valores possíveis são: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enum | Especifica o estado atual do incidente. Os valores possíveis são: ```Active``` ```Resolved``` , , e ```Redirected``` .
classificação | Enum | Especificação do incidente. Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.
determinação | Enum | Especifica a determinação do incidente. Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
tags | lista de strings | Lista de etiquetas de incidente.
comentários | Lista de comentários sobre incidentes | Objeto de comentário incidente contém: string de comentário, sequência criadapor sequência e hora de data de criação.
alerts | Lista de alerta | Lista de alertas relacionados. Veja exemplos na documentação da API [de incidentes da Lista.](api-list-incidents.md)

## <a name="related-articles"></a>Artigos relacionados

- [Microsoft 365 Visão geral do Defender APIs](api-overview.md)
- [Visão geral dos incidentes](incidents-overview.md)
- [Lista de incidentes API](api-list-incidents.md)
- [Atualizar a API incidente](api-update-incidents.md)
