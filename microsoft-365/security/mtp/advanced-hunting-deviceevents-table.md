---
title: Tabela DeviceEvents no esquema de busca avançado
description: Saiba mais sobre antivírus, firewall e outros tipos de evento na tabela eventos de dispositivo diversos (DeviceEvents) do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, eventos de segurança, antivírus, firewall, exploit guard, DeviceEvents
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
ms.openlocfilehash: 02e0caed602ffa14a756f0cc8e695fc9fb953efc
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712469"
---
# <a name="deviceevents"></a>Eventos do dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



Os diversos eventos de dispositivo ou tabela no esquema de busca avançada contêm informações sobre vários tipos de eventos, incluindo eventos disparados por controles de segurança, como Windows Defender Antivírus e proteção `DeviceEvents` de exploração. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).


| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo da máquina no serviço |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento. Consulte a [referência de esquema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) no portal para obter detalhes |
| `FileName` | cadeia de caracteres | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | cadeia de caracteres | Pasta que contém o arquivo ao que a ação gravada foi aplicada |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `SHA256` | cadeia de caracteres | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `MD5` | string | Hash MD5 do arquivo ao que a ação gravada foi aplicada |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta |
| `RemoteUrl` | cadeia de caracteres | URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à |
| `RemoteDeviceName` | cadeia de caracteres | Nome do computador que realizou uma operação remota no computador afetado. Dependendo do evento relatado, esse nome pode ser um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um nome de host sem informações de domínio |
| `ProcessId` | int | ID do processo (PID) do processo recém-criado |
| `ProcessCommandLine` | cadeia de caracteres | Linha de comando usada para criar o novo processo |
| `ProcessCreationTime` | datetime | Data e hora em que o processo foi criado |
| `ProcessTokenElevation` | cadeia de caracteres | Tipo de token que indica a presença ou ausência da elevação de privilégio de Controle de Acesso para Usuário (UAC) aplicada ao processo recém-criado |
| `LogonId` | cadeia de caracteres | Identificador de uma sessão de logon. Esse identificador é exclusivo no mesmo computador somente entre reinicializações |
| `RegistryKey` | cadeia de caracteres | Chave do Registro a que a ação gravada foi aplicada |
| `RegistryValueName` | cadeia de caracteres | Nome do valor do Registro ao que a ação gravada foi aplicada |
| `RegistryValueData` | cadeia de caracteres | Dados do valor do Registro ao que a ação gravada foi aplicada |
| `RemoteIP` | cadeia de caracteres | Endereço IP que estava sendo conectado ao |
| `RemotePort` | int | Porta TCP no dispositivo remoto que estava sendo conectado |
| `LocalIP` | cadeia de caracteres | Endereço IP atribuído à máquina local usada durante a comunicação |
| `LocalPort` | int | Porta TCP na máquina local usada durante a comunicação |
| `FileOriginUrl` | cadeia de caracteres | URL da qual o arquivo foi baixado |
| `FileOriginIP` | cadeia de caracteres | Endereço IP de onde o arquivo foi baixado |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre o evento no formato de matriz JSON |
| `InitiatingProcessFileSize` | long | Tamanho do arquivo que correu o processo responsável pelo evento |
| `FileSize` | long | Tamanho do arquivo em bytes |
| `InitiatingProcessSHA1` | cadeia de caracteres | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | cadeia de caracteres | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `InitiatingProcessFileName` | string | Nome do processo que iniciou o evento |
| `InitiatingProcessFolderPath` | cadeia de caracteres | Pasta contendo o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessId` | int | ID do processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | cadeia de caracteres | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessParentId` | int | ID do processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | cadeia de caracteres | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `InitiatingProcessMD5` | cadeia de caracteres | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessAccountDomain` | cadeia de caracteres | Domínio da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountName` | cadeia de caracteres | Nome de usuário da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountObjectId` | cadeia de caracteres | ID do objeto do Azure AD da conta de usuário que correu o processo responsável pelo evento |
| `InitiatingProcessLogonId` | cadeia de caracteres | Identificador de uma sessão de logon do processo que iniciou o evento. Esse identificador é exclusivo no mesmo computador somente entre reinicializações |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp |
| `AppGuardContainerId` | cadeia de caracteres | Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
