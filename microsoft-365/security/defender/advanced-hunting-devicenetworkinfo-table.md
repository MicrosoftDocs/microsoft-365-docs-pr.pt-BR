---
title: Tabela DeviceNetworkInfo no esquema de busca avançado
description: Saiba mais sobre informações de configuração de rede na tabela DeviceNetworkInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, mac, ip, adaptador, dns, dhcp, gateway, túnel
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
ms.openlocfilehash: 6d860e20bdd116d579b3cb178e3352825c60fe44
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500898"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A tabela no esquema de busca avançada contém informações sobre a configuração de rede de computadores, incluindo adaptadores de rede, endereços IP e MAC e redes `DeviceNetworkInfo` ou domínios [](advanced-hunting-overview.md) conectados. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `NetworkAdapterName` | string | Nome do adaptador de rede |
| `MacAddress` | string | Endereço MAC do adaptador de rede |
| `NetworkAdapterType` | string | Tipo de adaptador de rede. Para os valores possíveis, consulte [esta enumeração](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | string | Status operacional do adaptador de rede. Para os valores possíveis, consulte [esta enumeração](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | string | Protocolo de túnel, se a interface for usada para essa finalidade, por exemplo, 6to4, Teredo, ISATAP, PPTP, SSTP e SSH |
| `ConnectedNetworks` | string | Redes às que o adaptador está conectado. Cada matriz JSON contém o nome da rede, categoria (público, privado ou domínio), uma descrição e um sinalizador indicando se ela está conectada publicamente à Internet |
| `DnsAddresses` | string | Endereços de servidor DNS no formato de matriz JSON |
| `IPv4Dhcp` | string | Endereço IPv4 do servidor DHCP |
| `IPv6Dhcp` | string | Endereço IPv6 do servidor DHCP |
| `DefaultGateways` | string | Endereços de gateway padrão no formato de matriz JSON |
| `IPAddresses` | string | Matriz JSON contendo todos os endereços IP atribuídos ao adaptador, juntamente com seu respectivo prefixo de sub-rede e espaço de endereço IP, como público, privado ou link-local |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)