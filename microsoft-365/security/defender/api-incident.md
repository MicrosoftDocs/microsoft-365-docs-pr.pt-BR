---
title: Microsoft 365 APIs de incidentes do Defender e o tipo de recurso de incidentes
description: Saiba mais sobre os métodos e propriedades do tipo de recurso Incidentes no Microsoft 365 Defender
keywords: incidentes, incidentes, api
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
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888428"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a>Microsoft 365 API de incidentes do Defender e o tipo de recurso de incidentes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

Um [incidente](incidents-overview.md) é uma coleção de alertas relacionados que ajudam a descrever um ataque. Eventos de entidades diferentes em sua organização são automaticamente agregados pelo Microsoft 365 Defender. Você pode usar a API de incidentes para acessar programaticamente os incidentes e alertas relacionados da sua organização.

## <a name="quotas-and-resource-allocation"></a>Cotas e alocação de recursos

Você pode solicitar até 50 chamadas por minuto ou 1500 chamadas por hora. Cada método também tem suas próprias cotas. Para obter mais informações sobre cotas específicas do método, consulte o artigo respectivo para o método que você deseja usar.

Um código de resposta HTTP indica que você atingiu uma cota, por número de solicitações enviadas ou pelo tempo de `429` execução alocado. O corpo da resposta incluirá o tempo até que a cota atingida seja redefinida.

## <a name="permissions"></a>Permissões

A API de incidentes requer diferentes tipos de permissões para cada um de seus métodos. Para obter mais informações sobre permissões necessárias, consulte o artigo do método respectivo.

## <a name="methods"></a>Métodos

Método | Tipo de retorno | Descrição
-|-|-
[Listar incidentes](api-list-incidents.md) | [Lista de](api-incident.md) incidentes | Obter uma lista de incidentes.
[Atualizar incidente](api-update-incidents.md) | [Incidente](api-incident.md) | Atualize um incidente específico.
[Obter incidente](api-get-incident.md) | [Incidente](api-incident.md) | Obter um único incidente.

## <a name="request-body-response-and-examples"></a>Solicitar corpo, resposta e exemplos

Consulte os respectivos artigos de método para obter mais detalhes sobre como construir uma solicitação ou analisar uma resposta e para obter exemplos práticos.

## <a name="common-properties"></a>Propriedades comuns

Propriedade | Tipo | Descrição
-|-|-
incidentId | long | ID exclusiva do incidente.
redirectIncidentId | nullable long | A ID do Incidente à que o Incidente atual foi mesclado.
incidentName | string | O nome do Incidente.
createdTime | DateTimeOffset | A data e a hora (em UTC) que o Incidente foi criado.
lastUpdateTime | DateTimeOffset | A data e a hora (em UTC) que o Incidente foi atualizado pela última vez.
assignedTo | string | Proprietário do Incidente.
severity | Enum | Gravidade do Incidente. Os valores possíveis são: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .
status | Enum | Especifica o status atual do incidente. Os valores possíveis são: ```Active``` ```Resolved``` , e ```Redirected``` .
classificação | Enum | Especificação do incidente. Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.
determinação | Enum | Especifica a determinação do incidente. Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.
categorias | string List | Lista de marcas de incidente.
comentários | Lista de comentários de incidentes | O objeto Comentário de Incidente contém: cadeia de caracteres de comentários, createdBy string e createTime date time.
alerts | Lista de alertas | Lista de alertas relacionados. Consulte exemplos na documentação da API [de incidentes](api-list-incidents.md) de lista.

## <a name="related-articles"></a>Artigos relacionados

- [Microsoft 365 Visão geral das APIs do Defender](api-overview.md)
- [Visão geral dos incidentes](incidents-overview.md)
- [Api de incidentes de lista](api-list-incidents.md)
- [Atualizar API de incidentes](api-update-incidents.md)
