---
title: Tabela DeviceRegistryEvents no esquema de busca avançado
description: Saiba mais sobre eventos do Registro que você pode consultar na tabela DeviceRegistryEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, deviceregistryevents, Registro, chave, subkey, valor, RegistryEvents
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
ms.openlocfilehash: 39ea04e2faa43d230ecdc281967b6a9e8f8c9abe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054098"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

A tabela no esquema de busca avançada contém informações sobre a criação e modificação de `DeviceRegistryEvents` entradas do Registro. [](advanced-hunting-overview.md) Use esta referência para criar consultas quer retiram informações desta tabela.

Para obter informações sobre outras tabelas no esquema de busca avançado, consulte [a referência avançada do esquema de busca](advanced-hunting-schema-reference.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento |
| `RegistryKey` | cadeia de caracteres | Chave do Registro a que a ação gravada foi aplicada |
| `RegistryValueType` | cadeia de caracteres | Tipo de dados, como binário ou cadeia de caracteres, do valor do Registro ao qual a ação gravada foi aplicada |
| `RegistryValueName` | cadeia de caracteres | Nome do valor do Registro ao que a ação gravada foi aplicada |
| `RegistryValueData` | cadeia de caracteres | Dados do valor do Registro ao que a ação gravada foi aplicada |
| `PreviousRegistryValueName` | cadeia de caracteres | Nome original do valor do Registro antes de ser modificado |
| `PreviousRegistryValueData` | cadeia de caracteres | Dados originais do valor do Registro antes de ser modificado |
| `InitiatingProcessAccountDomain` | cadeia de caracteres | Domínio da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountName` | cadeia de caracteres | Nome de usuário da conta que correu o processo responsável pelo evento |
| `InitiatingProcessAccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta que correu o processo responsável pelo evento |
| `InitiatingProcessSHA1` | cadeia de caracteres | SHA-1 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessMD5` | cadeia de caracteres | Hash MD5 do processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessFileName` | cadeia de caracteres | Nome do processo que iniciou o evento |
| `InitiatingProcessId` | int | ID do processo (PID) do processo que iniciou o evento |
| `InitiatingProcessCommandLine` | cadeia de caracteres | Linha de comando usada para executar o processo que iniciou o evento |
| `InitiatingProcessCreationTime` | datetime | Data e hora em que o processo que iniciou o evento foi iniciado |
| `InitiatingProcessFolderPath` | cadeia de caracteres | Pasta contendo o processo (arquivo de imagem) que iniciou o evento |
| `InitiatingProcessParentId` | int | ID do processo (PID) do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentFileName` | cadeia de caracteres | Nome do processo pai que gerou o processo responsável pelo evento |
| `InitiatingProcessParentCreationTime` | datetime | Data e hora em que o pai do processo responsável pelo evento foi iniciado |
| `InitiatingProcessIntegrityLevel` | cadeia de caracteres | Nível de integridade do processo que iniciou o evento. O Windows atribui níveis de integridade a processos com base em determinadas características, como se eles foram lançados a partir de um download da Internet. Esses níveis de integridade influenciam permissões para recursos |
| `InitiatingProcessTokenElevation` | cadeia de caracteres | Tipo de token que indica a presença ou ausência da elevação de privilégio de Controle de Acesso para Usuário (UAC) aplicada ao processo que iniciou o evento |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com `DeviceName` as `Timestamp` colunas e |
| `AppGuardContainerId` | cadeia de caracteres | Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
