---
title: Tabela DeviceFileEvents no esquema de busca avançada
description: Saiba mais sobre eventos relacionados a arquivos na tabela DeviceFileEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, filecreationevents, DeviceFileEvents, arquivos, caminho, hash, SHA1, SHA256, MD5
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
ms.openlocfilehash: 4b815afbe8e3ca1f7967d13f6482b90f7c64e362
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617157"
---
# <a name="devicefileevents"></a>DeviceFileEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `DeviceFileEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre a criação de arquivos, modificação e outros eventos do sistema de arquivos. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ActionType` | string | Tipo de atividade que disparou o evento |
| `FileName` | string | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | string | Pasta que contém o arquivo para o qual a ação registrada foi aplicada |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `SHA256` | string | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `MD5` | string | Hash MD5 do arquivo ao qual a ação registrada foi aplicada |
| `FileOriginUrl` | string | URL de onde o arquivo foi baixado |
| `FileOriginReferrerUrl` | string | URL da página da Web que vincula ao arquivo baixado |
| `FileOriginIP` | string | Endereço IP de onde o arquivo foi baixado |
| `InitiatingProcessAccountDomain` | string | Domínio da conta que executou o processo responsável pelo evento |
| `InitiatingProcessAccountName` | string | Nome de usuário da conta que executou o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | string | Identificador de segurança (SID) da conta que executou o processo responsável pelo evento |
| `InitiatingProcessMD5` | string | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA1` | string | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | string | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `InitiatingProcessFolderPath` | string | Pasta que contém o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFileName` | string | Nome do processo que iniciou o evento |
| `InitiatingProcessId` | int | ID de processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | string | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessIntegrityLevel` | string | Nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se foram iniciados a partir de um download da Internet. Estes níveis de integridade influenciam permissões para recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token que indica a presença ou ausência de elevação de privilégio do controle de acesso do usuário (UAC) aplicada ao processo que iniciou o evento |
| `InitiatingProcessParentId` | int | ID de processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | string | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `RequestProtocol` | string | Protocolo de rede, se aplicável, usado para iniciar a atividade: desconhecido, local, SMB ou NFS |
| `ShareName` | string | Nome da pasta compartilhada que contém o arquivo |
| `RequestSourceIP` | string | Endereço IPv4 ou IPv6 do dispositivo remoto que iniciou a atividade |
| `RequestSourcePort` | string | Porta de origem no dispositivo remoto que iniciou a atividade |
| `RequestAccountName` | string | Nome de usuário da conta usada para iniciar remotamente a atividade |
| `RequestAccountDomain` | string | Domínio da conta usada para iniciar remotamente a atividade |
| `RequestAccountSid` | string | Identificador de segurança (SID) da conta usada para iniciar remotamente a atividade |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp |
| `AppGuardContainerId` | string | Identificador para o contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |
| `SensitivityLabel` | string | Rótulo aplicado a um email, arquivo ou outro conteúdo para classificá-lo para proteção de informações |
| `SensitivitySubLabel` | string | Subrótulo aplicado a um email, arquivo ou outro conteúdo para classificá-lo para proteção de informações; subrótulos de sensibilidade são agrupados em rótulos de confidencialidade, mas são tratados de forma independente |
| `IsAzureInfoProtectionApplied` | booliano | Indica se o arquivo está criptografado pela proteção de informações do Azure |

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)