---
title: Tabela DeviceLogonEvents no esquema de busca avançada
description: Saiba mais sobre eventos de autenticação ou entrada na tabela DeviceLogonEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, logonevents, DeviceLogonEvents, autenticação, logon, entrar
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
ms.openlocfilehash: 3a5666cc106365876956c8e313f9cd2f5a996e6f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931225"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A `DeviceLogonEvents` tabela no esquema de busca [avançada](advanced-hunting-overview.md) contém informações sobre logons do usuário e outros eventos de autenticação em dispositivos. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos (valores) com suporte em uma tabela, use a referência de esquema interna disponível na `ActionType` central de segurança. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ActionType` | string |Tipo de atividade que disparou o evento |
| `AccountDomain` | string | Domínio da conta |
| `AccountName` | string | Nome de usuário da conta |
| `AccountSid` | string | Sid (Identificador de Segurança) da conta |
| `LogonType` | string | Tipo de sessão de logon, especificamente:<br><br> - **Interativo** - o usuário interage fisicamente com o computador usando o teclado local e a tela<br><br> - **Logons interativos remotos (RDP)** – o usuário interage com o computador remotamente usando a Área de Trabalho Remota, Serviços de Terminal, Assistência Remota ou outros clientes RDP<br><br> - **Rede** - Sessão iniciada quando o computador é acessado usando PsExec ou quando os recursos compartilhados no computador, como impressoras e pastas compartilhadas, são acessados<br><br> - **Lote** - Sessão iniciada por tarefas agendadas<br><br> - **Serviço** - Sessão iniciada pelos serviços ao iniciar<br> |
| `LogonId` | string | Identificador de uma sessão de logon. Esse identificador é exclusivo no mesmo computador somente entre reinicializações |
| `RemoteDeviceName` | string | Nome do computador que realizou uma operação remota no computador afetado. Dependendo do evento relatado, esse nome pode ser um nome de domínio totalmente qualificado (FQDN), um nome NetBIOS ou um nome de host sem informações de domínio |
| `RemoteIP` | cadeia de caracteres | Endereço IP que estava sendo conectado ao |
| `RemoteIPType` | string | Tipo de endereço IP, por exemplo, Public, Private, Reserved, Loopback, Teredo, FourToSixMapping e Broadcast |
| `RemotePort` | int | Porta TCP no dispositivo remoto que estava sendo conectado |
| `AdditionalFields` | string | Informações adicionais sobre o evento no formato de matriz JSON |
| `InitiatingProcessAccountDomain` | string | Domínio da conta que fez o processo responsável pelo evento |
| `InitiatingProcessAccountName` | string | Nome de usuário da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | string | Identificador de segurança (SID) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessIntegrityLevel` | string | Nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se eles fossem lançados em um download da Internet. Esses níveis de integridade influenciam as permissões para recursos |
| `InitiatingProcessTokenElevation` | string | Tipo de token indicando a presença ou ausência da elevação de privilégio do Controle de Acesso de Usuário (UAC) aplicada ao processo que iniciou o evento |
| `InitiatingProcessSHA1` | string | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | string | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível |
| `InitiatingProcessMD5` | string | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFileName` | string | Nome do processo que iniciou o evento |
| `InitiatingProcessId` | int | ID do processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | string | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessFolderPath` | string | Pasta que contém o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessParentId` | int | ID do processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | string | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp |
| `AppGuardContainerId` | string | Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |
| `IsLocalAdmin` | booliano | Indicador booleano de se o usuário é um administrador local no computador |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
