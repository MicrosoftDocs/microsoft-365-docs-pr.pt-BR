---
title: Tabela DeviceEvents no esquema de busca avançada
description: Saiba mais sobre antivírus, firewall e outros tipos de eventos na tabela diversos eventos de dispositivo (DeviceEvents) do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema Kusto, tabela, coluna, tipo de dados, eventos de segurança, antivírus, firewall, Exploit Guard, DeviceEvents
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
ms.openlocfilehash: 26516dc4559a428880637c6cf8248d50bb802f08
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2020
ms.locfileid: "41209926"
---
# <a name="deviceevents"></a>DeviceEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Os diversos eventos de dispositivo `DeviceEvents` ou tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre vários tipos de eventos, incluindo eventos disparados por controles de segurança, como o Windows Defender Antivirus e a proteção contra Exploit. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).


| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo da máquina no serviço |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento |
| `FileName` | cadeia de caracteres | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | string | Pasta que contém o arquivo para o qual a ação registrada foi aplicada |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `SHA256` | string | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Este campo geralmente não é preenchido — use a coluna SHA1 quando disponível |
| `MD5` | cadeia de caracteres | Hash MD5 do arquivo ao qual a ação registrada foi aplicada |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountSid` | cadeia de caracteres | Identificador de segurança (SID) da conta |
| `RemoteUrl` | cadeia de caracteres | URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à |
| `RemoteDeviceName` | cadeia de caracteres | Nome do computador que executou uma operação remota na máquina afetada. Dependendo do evento que está sendo relatado, esse nome poderia ser um nome de domínio totalmente qualificado (FQDN), um nome NetBIOS ou um nome de host sem informações de domínio |
| `ProcessId` | int | ID de processo (PID) do processo recém-criado |
| `ProcessCommandLine` | cadeia de caracteres | Linha de comando usada para criar o novo processo |
| `ProcessCreationTime` | datetime | Data e hora em que o processo foi criado |
| `ProcessTokenElevation` | cadeia de caracteres | Tipo de token que indica a presença ou ausência de elevação de privilégio do controle de acesso do usuário (UAC) aplicada ao processo recém-criado |
| `LogonId` | cadeia de caracteres | Identificador para uma sessão de logon. Este identificador é exclusivo na mesma máquina somente entre as reinicializações |
| `RegistryKey` | cadeia de caracteres | Chave do registro à qual a ação registrada foi aplicada |
| `RegistryValueName` | cadeia de caracteres | Nome do valor do registro ao qual a ação registrada foi aplicada |
| `RegistryValueData` | cadeia de caracteres | Dados do valor do registro para o qual a ação registrada foi aplicada |
| `RemoteIP` | cadeia de caracteres | Endereço IP que estava sendo conectado ao |
| `RemotePort` | int | Porta TCP no dispositivo remoto que estava sendo conectado ao |
| `LocalIP` | cadeia de caracteres | Endereço IP atribuído ao computador local usado durante a comunicação |
| `LocalPort` | int | Porta TCP no computador local usado durante a comunicação |
| `FileOriginUrl` | cadeia de caracteres | URL de onde o arquivo foi baixado |
| `FileOriginIP` | cadeia de caracteres | Endereço IP de onde o arquivo foi baixado |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre o evento no formato de matriz JSON |
| `InitiatingProcessSHA1` | cadeia de caracteres | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | cadeia de caracteres | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Este campo geralmente não é preenchido — use a coluna SHA1 quando disponível |
| `InitiatingProcessFileName` | cadeia de caracteres | Nome do processo que iniciou o evento |
| `InitiatingProcessFolderPath` | cadeia de caracteres | Pasta que contém o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessId` | int | ID de processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | cadeia de caracteres | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessParentId` | int | ID de processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | cadeia de caracteres | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `InitiatingProcessMD5` | cadeia de caracteres | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessAccountDomain` | cadeia de caracteres | Domínio da conta que executou o processo responsável pelo evento |
| `InitiatingProcessAccountName` | cadeia de caracteres | Nome de usuário da conta que executou o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | cadeia de caracteres | Identificador de segurança (SID) da conta que executou o processo responsável pelo evento |
| `InitiatingProcessLogonId` | cadeia de caracteres | Identificador para uma sessão de logon do processo que iniciou o evento. Este identificador é exclusivo na mesma máquina somente entre as reinicializações |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp |
| `AppGuardContainerId` | cadeia de caracteres | Identificador para o contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
