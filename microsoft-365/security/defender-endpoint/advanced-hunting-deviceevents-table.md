---
title: Tabela DeviceEvents no esquema de busca avançado
description: Saiba mais sobre antivírus, firewall e outros tipos de evento na tabela eventos de dispositivo diversos (DeviceEvents) do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, eventos de segurança, antivírus, firewall, exploit guard, MiscEvents
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
ms.openlocfilehash: 49a0b608caa6d759f58889e6f831f84d2b4b90d3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053430"
---
# <a name="deviceevents"></a>Eventos do dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

A tabela ou eventos de dispositivo diversos no esquema de busca avançada contém informações sobre vários tipos de eventos, incluindo eventos disparados por controles de segurança, como o Microsoft Defender Antivírus e a proteção `DeviceEvents` contra exploração. [](advanced-hunting-overview.md) Use esta referência para criar consultas quer retiram informações desta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançado, consulte [a referência avançada do esquema de busca](advanced-hunting-schema-reference.md).

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
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountName` |cadeia de caracteres | Nome de usuário da conta |
| `AccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta |
| `RemoteUrl` | cadeia de caracteres | URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à |
| `RemoteDeviceName` | cadeia de caracteres | Nome do dispositivo que realizou uma operação remota no dispositivo afetado. Dependendo do evento relatado, esse nome pode ser um FQDN (nome de domínio totalmente qualificado), um nome NetBIOS ou um nome de host sem informações de domínio |
| `ProcessId` | int | ID do processo (PID) do processo recém-criado |
| `ProcessCommandLine` | cadeia de caracteres | Linha de comando usada para criar o novo processo |
| `ProcessCreationTime` | datetime | Data e hora em que o processo foi criado |
| `ProcessTokenElevation` | cadeia de caracteres | Tipo de token que indica a presença ou ausência da elevação de privilégio de Controle de Acesso para Usuário (UAC) aplicada ao processo recém-criado |
| `LogonId` | cadeia de caracteres | Identificador de uma sessão de logon. Esse identificador é exclusivo no mesmo dispositivo somente entre reinicializações |
| `RegistryKey` | cadeia de caracteres | Chave do Registro a que a ação gravada foi aplicada |
| `RegistryValueName` | cadeia de caracteres | Nome do valor do Registro ao que a ação gravada foi aplicada |
| `RegistryValueData` | cadeia de caracteres | Dados do valor do Registro ao que a ação gravada foi aplicada |
| `RemoteIP` | cadeia de caracteres | Endereço IP que estava sendo conectado ao |
| `RemotePort` | int | Porta TCP no dispositivo remoto que estava sendo conectado |
| `LocalIP` | cadeia de caracteres | Endereço IP atribuído ao dispositivo local usado durante a comunicação |
| `LocalPort` | int | Porta TCP no dispositivo local usado durante a comunicação |
| `FileOriginUrl` | cadeia de caracteres | URL da qual o arquivo foi baixado |
| `FileOriginIP` | cadeia de caracteres | Endereço IP de onde o arquivo foi baixado |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre o evento no formato de matriz JSON |
| `InitiatingProcessSHA1` | cadeia de caracteres | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessSHA256` | cadeia de caracteres | SHA-256 do processo (arquivo de imagem) que iniciou o evento. Esse campo geralmente não é preenchido— use a coluna SHA1 quando disponível |
| `InitiatingProcessFileName` | cadeia de caracteres | Nome do processo que iniciou o evento |
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
| `InitiatingProcessLogonId` | cadeia de caracteres | Identificador de uma sessão de logon do processo que iniciou o evento. Esse identificador é exclusivo no mesmo dispositivo somente entre reinicializações |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com `DeviceName` as `Timestamp` colunas e |
| `AppGuardContainerId` | cadeia de caracteres | Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
