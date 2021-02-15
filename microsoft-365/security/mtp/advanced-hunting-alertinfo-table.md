---
title: Tabela AlertInfo no esquema de busca avançada
description: Saiba mais sobre eventos de geração de alertas na tabela AlertInfo do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, gravidade, categoria, MITRE, ATT&CK, Microsoft Defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS e Azure ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ac1e28987a944a8f7786af4f10a85362f2f92a80
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929965"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A tabela no esquema de busca avançada contém informações sobre alertas do Microsoft Defender para Ponto de `AlertInfo` Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `AlertId` | string | Identificador exclusivo do alerta. |
| `Title` | cadeia de caracteres | Título do alerta |
| `Category` | cadeia de caracteres | Tipo de atividade indicadora de ameaça ou violação identificada pelo alerta |
| `Severity` | cadeia de caracteres | Indica o impacto potencial (alto, médio ou baixo) do indicador de ameaça ou da atividade de violação identificados pelo alerta |
| `ServiceSource` | cadeia de caracteres | Produto ou serviço que forneceu as informações de alerta |
| `DetectionSource` | string | Tecnologia ou sensor de detecção que identificou o componente ou atividade notável |
| `AttackTechniques` | string | MITRE ATT&CK associadas à atividade que disparou o alerta |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
