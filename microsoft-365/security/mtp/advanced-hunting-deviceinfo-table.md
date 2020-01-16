---
title: Tabela DeviceInfo no esquema de busca avançada
description: Saiba mais sobre o sistema operacional, o nome do computador e outras informações do computador na tabela DeviceInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, machineinfo, DeviceInfo, dispositivo, máquina, so, plataforma , os usuários
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4c8c5cef3ba99339176086ada055d266f92c30cf
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210443"
---
# <a name="deviceinfo"></a>DeviceInfo

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

A `DeviceInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre as máquinas da organização, incluindo a versão do sistema operacional, usuários ativos e o nome do computador. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | cadeia de caracteres | Identificador exclusivo da máquina no serviço |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ClientVersion` | cadeia de caracteres | Versão do agente de ponto de extremidade ou do sensor em execução no computador |
| `PublicIP` | cadeia de caracteres | Endereço IP público usado pela máquina integrada para se conectar ao serviço do Microsoft defender ATP. Esse pode ser o endereço IP da máquina, um dispositivo NAT ou um proxy |
| `OSArchitecture` | string | Arquitetura do sistema operacional em execução no computador. |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7 |
| `OSBuild` | cadeia de caracteres | Versão de compilação do sistema operacional em execução no computador |
| `IsAzureADJoined` | booliano | Indicador booliano de que o computador ingressou no Azure Active Directory |
| `LoggedOnUsers` | cadeia de caracteres | Lista de todos os usuários que são registrados no computador no momento do evento no formato de matriz JSON |
| `RegistryDeviceTag` | cadeia de caracteres | Marca de máquina adicionada por meio do registro |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp |
| `OSVersion` | cadeia de caracteres | Versão do sistema operacional em execução no computador. |
| `MachineGroup` | cadeia de caracteres | Grupo de computadores da máquina. Esse grupo é usado pelo controle de acesso baseado em função para determinar o acesso ao computador |

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)