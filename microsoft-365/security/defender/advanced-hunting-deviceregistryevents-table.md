---
title: Tabela DeviceRegistryEvents no esquema de busca avançado
description: Saiba mais sobre eventos do Registro que você pode consultar na tabela DeviceRegistryEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, registroeventos, registro, DeviceRegistryEvents, chave, sub-chave, valor
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0eef71a7ab88d24c1f9d0b3ebdba16b13c855355
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024248"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender
- Microsoft Defender para Ponto de Extremidade

A tabela no esquema de busca avançada contém informações sobre a criação e modificação de `DeviceRegistryEvents` entradas do Registro. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo da máquina no serviço |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento. Consulte a [referência de esquema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) no portal para obter detalhes |
| `RegistryKey` | cadeia de caracteres | Chave do Registro a que a ação gravada foi aplicada |
| `RegistryValueType` | cadeia de caracteres | Tipo de dados, como binário ou cadeia de caracteres, do valor do Registro ao qual a ação gravada foi aplicada |
| `RegistryValueName` | cadeia de caracteres | Nome do valor do Registro ao que a ação gravada foi aplicada |
| `RegistryValueData` | cadeia de caracteres | Dados do valor do Registro ao que a ação gravada foi aplicada |
| `PreviousRegistryKey` | cadeia de caracteres | Chave do Registro original do valor do Registro antes de ser modificada |
| `PreviousRegistryValueName` | cadeia de caracteres | Nome original do valor do Registro antes de ser modificado |
| `PreviousRegistryValueData` | cadeia de caracteres | Dados originais do valor do Registro antes de ser modificado |
| `InitiatingProcessAccountDomain` | cadeia de caracteres | Domínio da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountName` | cadeia de caracteres | Nome de usuário da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountObjectId` | cadeia de caracteres | ID do objeto do Azure AD da conta de usuário que correu o processo responsável pelo evento |
| `InitiatingProcessSHA1` | cadeia de caracteres | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | cadeia de caracteres | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `InitiatingProcessMD5` | string | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFileName` | cadeia de caracteres | Nome do processo que iniciou o evento |
| `InitiatingProcessFileSize` | long | Tamanho do arquivo que correu o processo responsável pelo evento |
| `InitiatingProcessVersionInfoCompanyName` | cadeia de caracteres | Nome da empresa a partir das informações de versão do processo (arquivo de imagem) responsável pelo evento |
| `InitiatingProcessVersionInfoProductName` | cadeia de caracteres | Nome do produto das informações de versão do processo (arquivo de imagem) responsável pelo evento |
|` InitiatingProcessVersionInfoProductVersion` | cadeia de caracteres | Versão do produto das informações de versão do processo (arquivo de imagem) responsável pelo evento |
|` InitiatingProcessVersionInfoInternalFileName` | cadeia de caracteres | Nome do arquivo interno das informações de versão do processo (arquivo de imagem) responsável pelo evento |
| `InitiatingProcessVersionInfoOriginalFileName` | cadeia de caracteres | Nome do arquivo original das informações de versão do processo (arquivo de imagem) responsável pelo evento |
| `InitiatingProcessVersionInfoFileDescription` | cadeia de caracteres | Descrição das informações de versão do processo (arquivo de imagem) responsável pelo evento |
| `InitiatingProcessId` | int | ID do processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | cadeia de caracteres | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessFolderPath` | cadeia de caracteres | Pasta contendo o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessParentId` | int | ID do processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | cadeia de caracteres | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `InitiatingProcessIntegrityLevel` | cadeia de caracteres | Nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se eles foram lançados a partir de um download da Internet. Esses níveis de integridade influenciam permissões para recursos |
| `InitiatingProcessTokenElevation` | cadeia de caracteres | Tipo de token que indica a presença ou ausência da elevação de privilégio de Controle de Acesso para Usuário (UAC) aplicada ao processo que iniciou o evento |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp |
| `AppGuardContainerId` | cadeia de caracteres | Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
