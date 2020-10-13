---
title: Tabela DeviceImageLoadEvents no esquema de busca avançada
description: Saiba mais sobre os eventos de carregamento de DLL na tabela DeviceImageLoadEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, imageloadevents, DeviceImageLoadEvents, carregamento de DLL, biblioteca, imagem de arquivo
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: adcfe0bb3cf42c5890e6ccc063bbaf3ba21827af
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431094"
---
# <a name="deviceimageloadevents"></a>DeviceImageLoadEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft



A `DeviceImageLoadEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre eventos de carregamento de dll. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ActionType` | string | Tipo de atividade que disparou o evento. Consulte a [referência de esquema no portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obter detalhes |
| `FileName` | string | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | string | Pasta que contém o arquivo para o qual a ação registrada foi aplicada |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `SHA256` | string | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `MD5` | string | Hash MD5 do arquivo ao qual a ação registrada foi aplicada |
| `InitiatingProcessAccountDomain` | string | Domínio da conta que executou o processo responsável pelo evento |
| `InitiatingProcessAccountName` | string | Nome de usuário da conta que executou o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | string | Identificador de segurança (SID) da conta que executou o processo responsável pelo evento |
| `InitiatingProcessIntegrityLevel` | string | Nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se foram iniciados a partir de um download da Internet. Estes níveis de integridade influenciam permissões para recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token que indica a presença ou ausência de elevação de privilégio do controle de acesso do usuário (UAC) aplicada ao processo que iniciou o evento |
| `InitiatingProcessSHA1` | string | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | string | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
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
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procure em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
