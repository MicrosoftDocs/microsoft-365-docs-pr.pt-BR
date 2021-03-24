---
title: Tabela DeviceFileEvents no esquema de busca avançado
description: Saiba mais sobre eventos relacionados a arquivos na tabela DeviceFileEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, devicefileevents, arquivos, caminho, hash, sha1, sha256, md5, FileCreationEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21a1bb17771314bc64f92009df4138e9550a7389
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054113"
---
# <a name="devicefileevents"></a>DeviceFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

A tabela no esquema de busca avançada contém informações sobre a criação, modificação e outros eventos do sistema `DeviceFileEvents` de arquivos. [](advanced-hunting-overview.md) Use esta referência para criar consultas quer retiram informações desta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançado, consulte  [a referência avançada do esquema de busca](advanced-hunting-schema-reference.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento |
| `FileName` | cadeia de caracteres | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | cadeia de caracteres | Pasta que contém o arquivo ao que a ação gravada foi aplicada |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `SHA256` | cadeia de caracteres | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido— use a coluna SHA1 quando disponível |
| `MD5` | cadeia de caracteres | Hash MD5 do arquivo ao que a ação gravada foi aplicada |
| `FileOriginUrl` | cadeia de caracteres | URL da qual o arquivo foi baixado |
| `FileOriginReferrerUrl` | cadeia de caracteres | URL da página da Web que se vincula ao arquivo baixado |
| `FileOriginIP` | cadeia de caracteres | Endereço IP de onde o arquivo foi baixado |
| `InitiatingProcessAccountDomain` | cadeia de caracteres | Domínio da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountName` | cadeia de caracteres | Nome de usuário da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessMD5` | cadeia de caracteres | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA1` | cadeia de caracteres | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFolderPath` | cadeia de caracteres | Pasta contendo o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFileName` | cadeia de caracteres | Nome do processo que iniciou o evento |
| `InitiatingProcessId` | int | ID do processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | cadeia de caracteres | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessIntegrityLevel` | cadeia de caracteres | nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se eles foram lançados a partir de um download da Internet. Esses níveis de integridade influenciam permissões para recursos |
| `InitiatingProcessTokenElevation` | cadeia de caracteres | Tipo de token que indica a presença ou ausência da elevação de privilégio de Controle de Acesso para Usuário (UAC) aplicada ao processo que iniciou o evento |
| `InitiatingProcessParentId` | int | ID do processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | cadeia de caracteres | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `RequestProtocol` | cadeia de caracteres | Protocolo de rede, se aplicável, usado para iniciar a atividade: Desconhecido, Local, SMB ou NFS |
| `ShareName` | cadeia de caracteres | Nome da pasta compartilhada que contém o arquivo |
| `RequestSourceIP` | cadeia de caracteres | Endereço IPv4 ou IPv6 do dispositivo remoto que iniciou a atividade |
| `RequestSourcePort` | cadeia de caracteres | Porta de origem no dispositivo remoto que iniciou a atividade |
| `RequestAccountName` | cadeia de caracteres | Nome de usuário da conta usada para iniciar remotamente a atividade |
| `RequestAccountDomain` | cadeia de caracteres | Domínio da conta usada para iniciar remotamente a atividade |
| `RequestAccountSid` | cadeia de caracteres | Sid (Identificador de Segurança) da conta para iniciar remotamente a atividade |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp |
| `AppGuardContainerId` | cadeia de caracteres | Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |
| `SensitivityLabel` | cadeia de caracteres | Rótulo aplicado a um email, arquivo ou outro conteúdo para classificá-lo para proteção de informações |
| `SensitivitySubLabel` | cadeia de caracteres | Sub-rótulo aplicado a um email, arquivo ou outro conteúdo para classificá-lo para proteção de informações; os sub-rótulos de sensibilidade são agrupados sob rótulos de sensibilidade, mas são tratados independentemente |
| `IsAzureInfoProtectionApplied` | booliano | Indica se o arquivo é criptografado pela Proteção de Informações do Azure |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
