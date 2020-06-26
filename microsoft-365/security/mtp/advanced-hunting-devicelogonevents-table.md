---
title: Tabela DeviceLogonEvents no esquema de busca avançada
description: Saiba mais sobre autenticação ou eventos de logon na tabela DeviceLogonEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, logonevents, DeviceLogonEvents, autenticação, logon, entrar
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 07b2c2301784f378075e3c9803cebc5bcabf9cb0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899262"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft



A `DeviceLogonEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre logons de usuário e outros eventos de autenticação. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ActionType` | string |Tipo de atividade que disparou o evento |
| `AccountDomain` | string | Domínio da conta |
| `AccountName` | string | Nome de usuário da conta |
| `AccountSid` | string | Identificador de segurança (SID) da conta |
| `LogonType` | string | Tipo de sessão de logon, especificamente:<br><br> - **Interativo** -o usuário interage fisicamente com o computador usando o teclado e a tela locais<br><br> - **Logons interativos (RDP) remotos** -o usuário interage com o computador remotamente usando a área de trabalho remota, serviços de terminal, assistência remota ou outros clientes RDP<br><br> - **Rede** -sessão iniciada quando a máquina é acessada usando o PsExec ou quando recursos compartilhados na máquina, como impressoras e pastas compartilhadas, são acessados<br><br> - Sessão **em lote** iniciada por tarefas agendadas<br><br> - **Serviço** -sessão iniciada pelos serviços à medida que eles são iniciados<br> |
| `LogonId` | string | Identificador para uma sessão de logon. Este identificador é exclusivo na mesma máquina somente entre as reinicializações |
| `RemoteDeviceName` | string | Nome do computador que executou uma operação remota na máquina afetada. Dependendo do evento que está sendo relatado, esse nome poderia ser um nome de domínio totalmente qualificado (FQDN), um nome NetBIOS ou um nome de host sem informações de domínio |
| `RemoteIP` | cadeia de caracteres | Endereço IP que estava sendo conectado ao |
| `RemoteIPType` | string | Tipo de endereço IP, por exemplo público, privado, reservado, auto-retorno, Teredo, FourToSixMapping e transmissão |
| `RemotePort` | int | Porta TCP no dispositivo remoto que estava sendo conectado ao |
| `AdditionalFields` | string | Informações adicionais sobre o evento no formato de matriz JSON |
| `InitiatingProcessAccountDomain` | string | Domínio da conta que executou o processo responsável pelo evento |
| `InitiatingProcessAccountName` | string | Nome de usuário da conta que executou o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | string | Identificador de segurança (SID) da conta que executou o processo responsável pelo evento |
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
| `IsLocalAdmin` | booliano | Indicador booleano se o usuário é um administrador local no computador |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
