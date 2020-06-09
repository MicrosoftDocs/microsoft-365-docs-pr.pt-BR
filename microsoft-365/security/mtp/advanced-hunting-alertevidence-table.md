---
title: Tabela AlertEvidence no esquema de busca avançada
description: Saiba mais sobre arquivo, endereço de rede, usuário ou informações de dispositivo associadas a alertas gerados na tabela AlertEvidence do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidência, arquivo, endereço IP, dispositivo, máquina, usuário, conta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da6e84725aa391e4cb6056fadd327fdba2436214
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617081"
---
# <a name="alertevidence"></a>AlertEvidence

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `AlertEvidence` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre várias entidades (arquivos, endereços IP, URLs, usuários ou dispositivos) associados a alertas do Microsoft defender ATP, Office 365 ATP, Microsoft Cloud app Security e Azure ATP. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `AlertId` | string | Identificador exclusivo do alerta. |
| `EntityType` | string | Tipo de objeto, como um arquivo, um processo, um dispositivo ou um usuário |
| `EvidenceRole` | string | Como a entidade está envolvida em um alerta, indicando se é impactada ou se é meramente relacionada |
| `SHA1` | string | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `SHA256` | string | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `RemoteIP` | string | Endereço IP que estava sendo conectado ao |
| `RemoteUrl` | string | URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `AccountSid` | string | Identificador de segurança (SID) da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `ThreatFamily` | string | Família de malware que o arquivo ou processo suspeito ou mal-intencionado foi classificado em |
| `EvidenceDirection` | string | Indica se a entidade é a origem ou o destino de uma conexão de rede |
| `AdditionalFields` | string | Informações adicionais sobre o evento no formato de matriz JSON |

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
