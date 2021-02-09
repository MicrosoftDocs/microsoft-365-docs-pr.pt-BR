---
title: Tabela DeviceFileEvents no esquema de busca avançada
description: Saiba mais sobre eventos relacionados a arquivos na tabela DeviceFileEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, filecreationevents, DeviceFileEvents, arquivos, caminho, hash, sha1, sha256, md5
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
ms.openlocfilehash: cccbd268c8f69d6623df1ef4c8208d20ead2e9f5
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145286"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém informações sobre a `DeviceFileEvents` criação, modificação e outros eventos do sistema de arquivos. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

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
| `FileOriginUrl` | string | URL da qual o arquivo foi baixado |
| `FileOriginReferrerUrl` | string | URL da página da Web que se vincula ao arquivo baixado |
| `FileOriginIP` | string | Endereço IP do qual o arquivo foi baixado |
| `PreviousFolderPath` | string | Pasta original que contém o arquivo antes da ação gravada ser aplicada |
| `PreviousFileName` | string | Nome original do arquivo que foi renomeado como resultado da ação |
| `FileSize` | long | Tamanho do arquivo em bytes |
| `InitiatingProcessAccountDomain` | string | Domínio da conta que fez o processo responsável pelo evento |
| `InitiatingProcessAccountName` | string | Nome de usuário da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | string | Identificador de segurança (SID) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountUpn` | string | Nome UPN da conta que fez a correção do processo responsável pelo evento |
| `InitiatingProcessMD5` | string | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA1` | string | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | string | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `InitiatingProcessFolderPath` | string | Pasta que contém o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFileName` | string | Nome do processo que iniciou o evento |
| `InitiatingProcessId` | int | ID do processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | string | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessIntegrityLevel` | string | Nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se eles fossem lançados em um download da Internet. Esses níveis de integridade influenciam as permissões para recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token indicando a presença ou ausência da elevação de privilégio do Controle de Acesso de Usuário (UAC) aplicada ao processo que iniciou o evento |
| `InitiatingProcessParentId` | int | ID do processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | string | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `RequestProtocol` | string | Protocolo de rede, se aplicável, usado para iniciar a atividade: Desconhecido, Local, SMB ou NFS |
| `ShareName` | string | Nome da pasta compartilhada que contém o arquivo |
| `RequestSourceIP` | string | Endereço IPv4 ou IPv6 do dispositivo remoto que iniciou a atividade |
| `RequestSourcePort` | string | Porta de origem no dispositivo remoto que iniciou a atividade |
| `RequestAccountName` | string | Nome de usuário da conta usada para iniciar remotamente a atividade |
| `RequestAccountDomain` | string | Domínio da conta usada para iniciar remotamente a atividade |
| `RequestAccountSid` | string | Identificador de segurança (SID) da conta usada para iniciar remotamente a atividade |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp. |
| `AppGuardContainerId` | string | Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |
| `AdditionalFields` | string | Informações adicionais sobre a entidade ou evento |
| `InitiatingProcessFileSize` | long | Tamanho do arquivo que fez o processo responsável pelo evento |
| `SensitivityLabel` | string | Rótulo aplicado a um email, arquivo ou outro conteúdo para classificá-lo para proteção de informações |
| `SensitivitySubLabel` | string | Sub-rótulo aplicado a um email, arquivo ou outro conteúdo para classificá-lo para proteção de informações; os sub-rótulos de sensibilidade são agrupados em rótulos de sensibilidade, mas são tratados de forma independente |
| `IsAzureInfoProtectionApplied` | booliano | Indica se o arquivo é criptografado pela Proteção de Informações do Azure |

>[!NOTE]
> As informações de hash do arquivo sempre serão mostradas quando disponíveis. No entanto, há vários motivos possíveis pelos quais um SHA1, SHA256 ou MD5 não pode ser calculado. Por exemplo, o arquivo pode estar localizado no armazenamento remoto, bloqueado por outro processo, compactado ou marcado como virtual. Nesses cenários, as informações de hash do arquivo aparecem vazias.

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
