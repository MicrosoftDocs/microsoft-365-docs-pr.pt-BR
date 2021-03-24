---
title: Tabela AlertEvidence no esquema de busca avançado
description: Saiba mais sobre informações associadas a alertas na tabela AlertEvidence do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidências, arquivo, endereço IP, dispositivo, máquina, usuário, conta
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3e4a8c9bffd285d45c7a4002b1ecd96e6dda40b9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053236"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém informações sobre várias `AlertEvidence` entidades, arquivos, endereços IP, URLs, usuários ou dispositivos, associados a alertas do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365, Segurança de Aplicativos na Nuvem da [](advanced-hunting-overview.md) Microsoft e Microsoft Defender para Identidade. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `AlertId` | string | Identificador exclusivo do alerta. |
| `ServiceSource` | cadeia de caracteres | Produto ou serviço que forneceu as informações de alerta |
| `EntityType` | cadeia de caracteres | Tipo de objeto, como um arquivo, um processo, um dispositivo ou um usuário |
| `EvidenceRole` | cadeia de caracteres | Como a entidade está envolvida em um alerta, indicando se ela foi impactada ou está meramente relacionada |
| `EvidenceDirection` | cadeia de caracteres | Indica se a entidade é a origem ou o destino de uma conexão de rede |
| `FileName` | cadeia de caracteres | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | cadeia de caracteres | Pasta que contém o arquivo ao que a ação gravada foi aplicada |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `SHA256` | cadeia de caracteres | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido— use a coluna SHA1 quando disponível. |
| `FileSize` | int | Tamanho do arquivo em bytes |
| `ThreatFamily` | cadeia de caracteres | Família de malware em que o arquivo ou processo suspeito ou mal-intencionado foi classificado |
| `RemoteIP` | cadeia de caracteres | Endereço IP que estava sendo conectado ao |
| `RemoteUrl` | cadeia de caracteres | URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta |
| `AccountObjectId` | cadeia de caracteres | Identificador exclusivo da conta no Azure Active Directory |
| `AccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `LocalIP` | cadeia de caracteres | Endereço IP atribuído ao dispositivo local usado durante a comunicação |
| `NetworkMessageId` | cadeia de caracteres | Identificador exclusivo do email, gerado pelo Office 365 |
| `EmailSubject` | cadeia de caracteres | Assunto do email |
| `ApplicationId` | cadeia de caracteres | Identificador exclusivo do aplicativo |
| `Application` | cadeia de caracteres | Aplicativo que realizou a ação gravada |
| `ProcessCommandLine` | cadeia de caracteres | Linha de comando usada para criar o novo processo |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre o evento no formato de matriz JSON |
| `RegistryKey` |cadeia de caracteres | Chave do Registro a que a ação gravada foi aplicada |
| `RegistryValueName` |cadeia de caracteres | Nome do valor do Registro ao que a ação gravada foi aplicada |
| `RegistryValueData` |cadeia de caracteres | Dados do valor do Registro ao que a ação gravada foi aplicada |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
