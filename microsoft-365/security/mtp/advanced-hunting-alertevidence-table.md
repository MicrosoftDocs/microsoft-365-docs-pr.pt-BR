---
title: Tabela AlertEvidence no esquema de busca avançada
description: Saiba mais sobre as informações associadas a alertas na tabela AlertEvidence do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidências, arquivo, endereço IP, dispositivo, computador, usuário, conta
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
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932293"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém informações sobre várias entidades ( arquivos, endereços IP, URLs, usuários ou dispositivos ) associadas a alertas do Microsoft Defender para Ponto de `AlertEvidence` Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `AlertId` | string | Identificador exclusivo do alerta. |
| `ServiceSource` | string | Produto ou serviço que forneceu as informações de alerta |
| `EntityType` | string | Tipo de objeto, como um arquivo, um processo, um dispositivo ou um usuário |
| `EvidenceRole` | string | Como a entidade está envolvida em um alerta, indicando se ela é impactada ou está simplesmente relacionada |
| `EvidenceDirection` | string | Indica se a entidade é a origem ou o destino de uma conexão de rede |
| `FileName` | string | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | string | Pasta que contém o arquivo ao que a ação gravada foi aplicada |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `SHA256` | string | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `FileSize` | int | Tamanho do arquivo em bytes |
| `ThreatFamily` | string | Família de malware em que o arquivo ou processo suspeito ou mal-intencionado foi classificado |
| `RemoteIP` | cadeia de caracteres | Endereço IP que estava sendo conectado ao |
| `RemoteUrl` | cadeia de caracteres | URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `AccountSid` | string | Sid (Identificador de Segurança) da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure Active Directory |
| `DeviceId` | string | Identificador exclusivo do dispositivo no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `LocalIP` | string | Endereço IP atribuído ao dispositivo local usado durante a comunicação |
| `NetworkMessageId` | string | Identificador exclusivo do email, gerado pelo Office 365 |
| `EmailSubject` | cadeia de caracteres | Assunto do email |
| `ApplicationId` | cadeia de caracteres | Identificador exclusivo do aplicativo |
| `Application` | string | Aplicativo que realizou a ação gravada |
| `ProcessCommandLine` | string | Linha de comando usada para criar o novo processo |
| `AdditionalFields` | string | Informações adicionais sobre o evento no formato de matriz JSON |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
