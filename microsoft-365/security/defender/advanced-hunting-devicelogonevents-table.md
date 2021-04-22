---
title: Tabela DeviceLogonEvents no esquema de busca avançado
description: Saiba mais sobre eventos de autenticação ou entrada na tabela DeviceLogonEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, logonevents, DeviceLogonEvents, autenticação, logon, entrar
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
ms.openlocfilehash: 62e0179f4a8c7b45d0c9743d2f133f9a10fb4c24
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934052"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A `DeviceLogonEvents` tabela no esquema de busca [avançada](advanced-hunting-overview.md) contém informações sobre logons do usuário e outros eventos de autenticação em dispositivos. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo da máquina no serviço |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ActionType` | cadeia de caracteres |Tipo de atividade que disparou o evento |
| `LogonType` | cadeia de caracteres | Tipo de sessão de logon, especificamente:<br><br> - **Interativo** - O usuário interage fisicamente com o computador usando o teclado local e a tela<br><br> - **Logons interativos remotos (RDP)** - O usuário interage com o computador remotamente usando Área de Trabalho Remota, Serviços de Terminal, Assistência Remota ou outros clientes RDP<br><br> - **Rede** - Sessão iniciada quando o computador é acessado usando PsExec ou quando os recursos compartilhados no computador, como impressoras e pastas compartilhadas, são acessados<br><br> - **Batch** - Sessão iniciada por tarefas agendadas<br><br> - **Serviço** - Sessão iniciada pelos serviços à medida que eles iniciam<br> |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta |
| `Protocol` | cadeia de caracteres | Protocolo usado durante a comunicação |
| `FailureReason` | cadeia de caracteres | Informações explicando por que a ação gravada falhou |
| `IsLocalAdmin` | booliano | Indicador booleano de se o usuário é um administrador local no computador |
| `LogonId` | cadeia de caracteres | Identificador de uma sessão de logon. Esse identificador é exclusivo no mesmo computador somente entre reinicializações |
| `RemoteDeviceName` | cadeia de caracteres | Nome do computador que realizou uma operação remota no computador afetado. Dependendo do evento relatado, esse nome pode ser um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um nome de host sem informações de domínio |
| `RemoteIP` | cadeia de caracteres | Endereço IP que estava sendo conectado ao |
| `RemoteIPType` | cadeia de caracteres | Tipo de endereço IP, por exemplo, Público, Privado, Reservado, Loopback, Teredo, FourToSixMapping e Broadcast |
| `RemotePort` | int | Porta TCP no dispositivo remoto que estava sendo conectado |
| `InitiatingProcessAccountDomain` | cadeia de caracteres | Domínio da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountName` | cadeia de caracteres | Nome de usuário da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta que correu o processo responsável pelo evento |
| ` InitiatingProcessAccountObjectId` | cadeia de caracteres | ID do objeto do Azure AD da conta de usuário que correu o processo responsável pelo evento |
| `InitiatingProcessIntegrityLevel` | cadeia de caracteres | Nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se eles foram lançados a partir de um download da Internet. Esses níveis de integridade influenciam permissões para recursos |
| `InitiatingProcessTokenElevation` | cadeia de caracteres | Tipo de token que indica a presença ou ausência da elevação de privilégio de Controle de Acesso para Usuário (UAC) aplicada ao processo que iniciou o evento |
| `InitiatingProcessSHA1` | cadeia de caracteres | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | cadeia de caracteres | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Esse campo geralmente não é preenchido— use a coluna SHA1 quando disponível |
| `InitiatingProcessMD5` | cadeia de caracteres | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFileName` | cadeia de caracteres | Nome do processo que iniciou o evento |
| `InitiatingProcessFileSize` | long | Tamanho do arquivo que correu o processo responsável pelo evento |
| `InitiatingProcessVersionInfoCompanyName` | cadeia de caracteres | Nome da empresa a partir das informações de versão do processo (arquivo de imagem) responsável pelo evento |
| `InitiatingProcessVersionInfoProductName` | cadeia de caracteres | Nome do produto das informações de versão do processo (arquivo de imagem) responsável pelo evento |
| `InitiatingProcessVersionInfoProductVersion` | cadeia de caracteres | Versão do produto das informações de versão do processo (arquivo de imagem) responsável pelo evento |
| `InitiatingProcessVersionInfoInternalFileName` | cadeia de caracteres | Nome do arquivo interno das informações de versão do processo (arquivo de imagem) responsável pelo evento |
| `InitiatingProcessVersionInfoOriginalFileName` | cadeia de caracteres | Nome do arquivo original das informações de versão do processo (arquivo de imagem) responsável pelo evento |
| `InitiatingProcessVersionInfoFileDescription` | cadeia de caracteres | Descrição das informações de versão do processo (arquivo de imagem) responsável pelo evento |
| `InitiatingProcessId` | int | ID do processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | cadeia de caracteres | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessFolderPath` | cadeia de caracteres | Pasta contendo o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessParentId` | int | ID do processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | cadeia de caracteres | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp |
| `AppGuardContainerId` | cadeia de caracteres | Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre o evento no formato de matriz JSON |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
