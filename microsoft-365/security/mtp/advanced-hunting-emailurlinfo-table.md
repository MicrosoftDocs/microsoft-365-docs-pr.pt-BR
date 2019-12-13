---
title: Tabela EmailUrlInfo no esquema de busca avançada
description: Saiba mais sobre URL ou informações de link na tabela EmailUrlInfo do esquema de busca avançada
keywords: caça avançada, caça de ameaças, caça de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, EmailUrlInfo, mensagem de rede, url, link
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
ms.openlocfilehash: 10cf82667fd97eebe66c376e0539db000f20b1c2
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910729"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!include[Prerelease information](prerelease.md)]

A tabela `EmailUrlInfo` no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre URLs em emails e anexos processados na ATP do Office 365. Use esta referência para criar consultas que retornam informações desta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `EventTime` | datetime | A data e a hora em que o evento foi gravado |
| `UrlId` | string | Identificador exclusivo da URL no assunto, no corpo ou no anexo de email |
| `NetworkMessageId` | string | Identificador exclusivo do email, gerado pelo Office 365 |
| `Url` | string | URL completa no assunto, no corpo ou no anexo de email |

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)