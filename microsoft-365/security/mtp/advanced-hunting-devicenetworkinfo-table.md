---
title: Tabela DeviceNetworkInfo no esquema de busca avançada
description: Saiba mais sobre as informações de configuração de rede na tabela DeviceNetworkInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças na cyber, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, Mac, IP, adaptador, DNS, DHCP, gateway, túnel
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
ms.openlocfilehash: e0d183dd762aba7f11ee46acc81a89b453dc70cb
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809217"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

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
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
