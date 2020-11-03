---
title: Tabela DeviceNetworkInfo no esquema de busca avançada
description: Saiba mais sobre as informações de configuração de rede na tabela DeviceNetworkInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Search, Query, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, Mac, IP, adaptador, DNS, DHCP, gateway, túnel
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
ms.openlocfilehash: 92856d3f077d3bfe49a3b25f50965aa1c03ebdb0
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842649"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender



A `DeviceNetworkInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre a configuração de rede de computadores, incluindo adaptadores de rede, endereços IP e Mac e redes ou domínios conectados. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp |
| `NetworkAdapterName` | string | Nome do adaptador de rede |
| `MacAddress` | string | Endereço MAC do adaptador de rede |
| `NetworkAdapterType` | string | Tipo de adaptador de rede. Para obter os valores possíveis, consulte [essa enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | string | Status operacional do adaptador de rede. Para obter os valores possíveis, consulte [essa enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | string | Protocolo de encapsulamento, se a interface for usada para essa finalidade, por exemplo, 6to4, Teredo, ISATAP, PPTP, SSTP e SSH |
| `ConnectedNetworks` | string | Redes às quais o adaptador está conectado. Cada matriz JSON contém o nome da rede, a categoria (público, privado ou domínio), uma descrição e um sinalizador que indica se ele está conectado publicamente à Internet |
| `DnsAddresses` | string | Endereços de servidor DNS no formato de matriz JSON |
| `IPv4Dhcp` | string | Endereço IPv4 do servidor DHCP |
| `IPv6Dhcp` | string | Endereço IPv6 do servidor DHCP |
| `DefaultGateways` | string | Endereços de gateway padrão no formato de matriz JSON |
| `IPAddresses` | string | Matriz JSON que contém todos os endereços IP atribuídos ao adaptador, juntamente com seus respectivos prefixo de sub-rede e espaço de endereço IP, como Public, Private ou link-local |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procure em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
