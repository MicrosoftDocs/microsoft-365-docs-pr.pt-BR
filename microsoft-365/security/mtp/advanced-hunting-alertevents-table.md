---
title: Tabela AlertEvents no esquema de busca avançada
description: Aprenda sobre os eventos de geração de alerta na tabela AlertEvents do esquema de busca avançada
keywords: caça avançada, caça de ameaças, caça de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, alertevents, alerta, gravidade, categoria
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ee14dcc1c2ae0a2bc6fa3c094d757441515f00de
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807010"
---
# <a name="alertevents"></a>AlertEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

A tabela `AlertEvents` no esquema [busca avançada](advanced-hunting-overview.md) tem informações sobre os alertas do Microsoft Defender ATP. Use esta referência para criar consultas que retornam informações desta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `AlertId` | string | Identificador exclusivo do alerta. |
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo da máquina no serviço |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `Severity` | cadeia de caracteres | Indica o impacto potencial (alto, médio ou baixo) do indicador de ameaça ou da atividade de violação identificados pelo alerta |
| `Category` | cadeia de caracteres | Tipo de atividade indicadora de ameaça ou violação identificada pelo alerta |
| `Title` | cadeia de caracteres | Título do alerta |
| `FileName` | cadeia de caracteres | Nome do arquivo ao qual a ação gravada foi aplicada |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `RemoteUrl` | cadeia de caracteres | URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à |
| `RemoteIP` | cadeia de caracteres | Endereço IP que estava sendo conectado ao |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp |
| `Table` | cadeia de caracteres | Tabela que contém os detalhes do evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
