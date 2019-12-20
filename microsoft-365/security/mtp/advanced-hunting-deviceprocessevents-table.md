---
title: Tabela DeviceProcessEvents no esquema de busca avançada
description: Saiba mais sobre o processo de geração ou criação de eventos no DeviceProcessEventstable do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças de cyber, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, processcreationevents, DeviceProcessEvents, ID de processo, linha de comando, DeviceProcessEvents
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
ms.openlocfilehash: 4e7899d06d9107ed5fdbaf67d507ed69a034329b
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809215"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

A `DeviceProcessEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre a criação de processos e eventos relacionados. Use essa referência para criar consultas que retornam informações dessa tabela.

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
| `SHA256` | string | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Este campo geralmente não é preenchido: Use a coluna SHA1 quando disponível. |
| `MD5` | string | Hash MD5 do arquivo ao qual a ação registrada foi aplicada |
| `ProcessId` | int | ID de processo (PID) do processo recém-criado |
| `ProcessCommandLine` | string | Linha de comando usada para criar o novo processo |
| `ProcessIntegrityLevel` | string | Nível de integridade do processo recém-criado. O Windows atribui níveis de integridade a processos com base em determinadas características, como se foram iniciados a partir de uma Internet baixada. Estes níveis de integridade influenciam permissões para recursos |
| `ProcessTokenElevation` | string | Tipo de token que indica a presença ou ausência de elevação de privilégio do controle de acesso do usuário (UAC) aplicada ao processo recém-criado |
| `ProcessCreationTime` | datetime | Data e hora em que o processo foi criado |
| `AccountDomain` | string | Domínio da conta |
| `AccountName` | string | Nome de usuário da conta |
| `AccountSid` | string | Identificador de segurança (SID) da conta |
| `LogonId` | string | Identificador para uma sessão de logon. Este identificador é exclusivo na mesma máquina somente entre as reinicializações |
| `InitiatingProcessAccountDomain` | string | Domínio da conta que executou o processo responsável pelo evento |
| `InitiatingProcessAccountName` | string | Nome de usuário da conta que executou o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | string | Identificador de segurança (SID) da conta que executou o processo responsável pelo evento |
| `InitiatingProcessLogonId` | string | Identificador para uma sessão de logon do processo que iniciou o evento. Este identificador é exclusivo na mesma máquina somente entre as reinicializações. |
| `InitiatingProcessIntegrityLevel` | string | Nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se foram iniciados a partir de um download da Internet. Estes níveis de integridade influenciam permissões para recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token que indica a presença ou ausência de elevação de privilégio do controle de acesso do usuário (UAC) aplicada ao processo que iniciou o evento |
| `InitiatingProcessSHA1` | string | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | string | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Este campo geralmente não é preenchido — use a coluna SHA1 quando disponível |
| `InitiatingProcessMD5` | string | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFileName` | string | Nome do processo que iniciou o evento |
| `InitiatingProcessId` | int | ID de processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | string | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessFolderPath` | string | Pasta que contém o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessParentId` | int | ID de processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | string | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp |
| `AppGuardContainerId` | string | Identificador para o contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
