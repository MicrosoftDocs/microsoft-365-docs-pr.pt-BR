---
title: Tabela DeviceLogonEvents no esquema de busca avançado
description: Saiba mais sobre eventos de autenticação ou entrada na tabela DeviceLogonEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, devicelogonevents, autenticação, logon, entrar, LogonEvents
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
ms.openlocfilehash: 7bc6e655d3a423b45f70210e53fca9713427355a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054110"
---
# <a name="devicelogonevents"></a>DeviceLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

A `DeviceLogonEvents` tabela no esquema de busca [avançada](advanced-hunting-overview.md) contém informações sobre logons do usuário e outros eventos de autenticação. Use esta referência para criar consultas quer retiram informações desta tabela.

> [!NOTE]
> A coleção deviceLogonEvents não é suportada no Windows 7 ou no Windows Server 2008 R2.
> Recomendamos a atualização para o Windows 10 ou o Windows Server 2019 para obter uma visibilidade ideal da atividade de logon do usuário.

Para obter informações sobre outras tabelas no esquema de busca avançado, consulte [a referência avançada do esquema de busca](advanced-hunting-schema-reference.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `ActionType` | cadeia de caracteres |Tipo de atividade que disparou o evento |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta |
| `LogonType` | cadeia de caracteres | Tipo de sessão de logon, especificamente:<br><br> - **Interativo** - O usuário interage fisicamente com o dispositivo usando o teclado e a tela locais<br><br> - **Logons interativos remotos (RDP)** - O usuário interage com o dispositivo remotamente usando Área de Trabalho Remota, Serviços de Terminal, Assistência Remota ou outros clientes RDP<br><br> - **Rede** - Sessão iniciada quando o dispositivo é acessado usando PsExec ou quando os recursos compartilhados no dispositivo, como impressoras e pastas compartilhadas, são acessados<br><br> - **Batch** - Sessão iniciada por tarefas agendadas<br><br> - **Serviço** - Sessão iniciada pelos serviços à medida que eles iniciam<br> |
| `LogonId` | cadeia de caracteres | Identificador de uma sessão de logon. Esse identificador é exclusivo no mesmo dispositivo somente entre reinicializações |
| `RemoteDeviceName` | cadeia de caracteres | Nome do dispositivo que realizou uma operação remota no dispositivo afetado. Dependendo do evento relatado, esse nome pode ser um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um nome de host sem informações de domínio |
| `RemoteIP` | cadeia de caracteres | Endereço IP que estava sendo conectado ao |
| `RemoteIPType` | cadeia de caracteres | Tipo de endereço IP, por exemplo, Público, Privado, Reservado, Loopback, Teredo, FourToSixMapping e Broadcast |
| `RemotePort` | int | Porta TCP no dispositivo remoto que estava sendo conectado |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre o evento no formato de matriz JSON |
| `InitiatingProcessAccountDomain` | cadeia de caracteres | Domínio da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountName` | cadeia de caracteres | Nome de usuário da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessIntegrityLevel` | cadeia de caracteres | Nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se eles foram lançados a partir de um download da Internet. Esses níveis de integridade influenciam permissões para recursos |
| `InitiatingProcessTokenElevation` | cadeia de caracteres | Tipo de token que indica a presença ou ausência da elevação de privilégio de Controle de Acesso para Usuário (UAC) aplicada ao processo que iniciou o evento |
| `InitiatingProcessSHA1` | cadeia de caracteres | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | cadeia de caracteres | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Esse campo geralmente não é preenchido— use a coluna SHA1 quando disponível |
| `InitiatingProcessMD5` | cadeia de caracteres | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFileName` | cadeia de caracteres | Nome do processo que iniciou o evento |
| `InitiatingProcessId` | int | ID do processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | cadeia de caracteres | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessFolderPath` | cadeia de caracteres | Pasta contendo o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessParentId` | int | ID do processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | cadeia de caracteres | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com `DeviceName` as `Timestamp` colunas e |
| `AppGuardContainerId` | cadeia de caracteres | Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |
| `IsLocalAdmin` | booliano | Indicador booleano de se o usuário é um administrador local no dispositivo |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
