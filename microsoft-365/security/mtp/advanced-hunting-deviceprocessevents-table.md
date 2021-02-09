---
title: Tabela DeviceProcessEvents no esquema de busca avançada
description: Saiba mais sobre o processo que gera ou cria eventos no DeviceProcessEventstable do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, processcreationevents, DeviceProcessEvents, id do processo, linha de comando, DeviceProcessEvents
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
ms.openlocfilehash: 6f94b861aa73d01f9e906d41bc52a9724552cd33
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145506"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A `DeviceProcessEvents` tabela no esquema de busca [avançada](advanced-hunting-overview.md) contém informações sobre a criação de processos e eventos relacionados. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos (valores) com suporte em uma tabela, use a referência de esquema interna disponível na `ActionType` central de segurança. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ActionType` | string | Tipo de atividade que disparou o evento. Consulte a [referência de esquema no portal para](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) obter detalhes |
| `FileName` | string | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | string | Pasta que contém o arquivo ao que a ação gravada foi aplicada |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `SHA256` | string | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `MD5` | string | Hash MD5 do arquivo ao que a ação gravada foi aplicada |
| `ProcessId` | int | ID do processo (PID) do processo recém-criado |
| `ProcessCommandLine` | string | Linha de comando usada para criar o novo processo |
| `ProcessIntegrityLevel` | string | Nível de integridade do processo recém-criado. O Windows atribui níveis de integridade a processos com base em determinadas características, como se eles fossem lançados de um download pela Internet. Esses níveis de integridade influenciam as permissões para recursos |
| `ProcessTokenElevation` | string | Indica o tipo de elevação do token aplicado ao processo recém-criado. Valores possíveis: TokenElevationTypeLimited (restrito), TokenElevationTypeDefault (padrão) e TokenElevationTypeFull (elevado) |
| `ProcessCreationTime` | datetime | Data e hora em que o processo foi criado |
| `AccountDomain` | string | Domínio da conta |
| `AccountName` | string | Nome de usuário da conta |
| `AccountSid` | string | Sid (Identificador de Segurança) da conta |
| `AccountUpn` | string | Nome UPN da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `LogonId` | string | Identificador de uma sessão de logon. Esse identificador é exclusivo no mesmo computador somente entre reinicializações |
| `InitiatingProcessAccountDomain` | string | Domínio da conta que fez o processo responsável pelo evento |
| `InitiatingProcessAccountName` | string | Nome de usuário da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | string | Identificador de segurança (SID) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountUpn` | string | Nome UPN da conta que fez a correção do processo responsável pelo evento |
| `InitiatingProcessAccountObjectId` | string | Azure AD object ID of the user account that ran the process responsible for the event |
| `InitiatingProcessLogonId` | string | Identificador de uma sessão de logon do processo que iniciou o evento. Esse identificador é exclusivo no mesmo computador somente entre reinicializações. |
| `InitiatingProcessIntegrityLevel` | string | Nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se fossem lançados em um download da Internet. Esses níveis de integridade influenciam as permissões para recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token indicando a presença ou ausência da elevação de privilégio do Controle de Acesso de Usuário (UAC) aplicada ao processo que iniciou o evento |
| `InitiatingProcessSHA1` | string | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | string | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `InitiatingProcessMD5` | string | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFileName` | string | Nome do processo que iniciou o evento |
| `InitiatingProcessFileSize` | long | Tamanho do arquivo que fez o processo responsável pelo evento |
| `InitiatingProcessId` | int | ID do processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | string | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessFolderPath` | string | Pasta que contém o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessParentId` | int | ID do processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | string | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp |
| `AppGuardContainerId` | string | Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |
| `AdditionalFields` | string | Informações adicionais sobre o evento no formato de matriz JSON |
| `FileSize` | long | Tamanho do arquivo em bytes |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
