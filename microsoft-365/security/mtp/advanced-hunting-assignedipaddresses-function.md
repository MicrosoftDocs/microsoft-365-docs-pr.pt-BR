---
title: Função AssignedIPAddresses() em busca avançada do Microsoft 365 Defender
description: Saiba como usar a função AssignedIPAddresses() para obter os endereços IP mais recentes atribuídos a um dispositivo
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, FileProfile, perfil de arquivo, função, enriquecimento
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
ms.openlocfilehash: d16cd7efc49cc2498eff3f705bb43fa62f37d975
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933013"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Use a função nas consultas de busca avançada para obter rapidamente os endereços IP mais recentes `AssignedIPAddresses()` que foram atribuídos a um dispositivo. [](advanced-hunting-overview.md) Se você especificar um argumento timestamp, essa função obterá os endereços IP mais recentes no horário especificado. 

Esta função retorna uma tabela com as seguintes colunas:

| Coluna | Tipo de dados | Descrição |
|------------|-------------|-------------|
| `Timestamp` | datetime | Hora mais recente em que o dispositivo foi observado usando o endereço IP |
| `IPAddress` | string | Endereço IP usado pelo dispositivo |
| `IPType` | string | Indica se o endereço IP é um endereço público ou privado |
| `NetworkAdapterType` | int | Tipo de adaptador de rede usado pelo dispositivo ao qual foi atribuído o endereço IP. Para os valores possíveis, consulte [esta enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Redes às que o adaptador com o endereço IP atribuído está conectado. Cada matriz JSON contém o nome da rede, categoria (público, privado ou domínio), uma descrição e um sinalizador indicando se ele está conectado publicamente à Internet |

## <a name="syntax"></a>Sintaxe

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumentos

- **x**— `DeviceId` ou valor que identifica o `DeviceName` dispositivo
- **y**— valor (datetime) instruindo a função a obter os endereços IP atribuídos mais `Timestamp` recentes de um horário específico. Se não for especificada, a função retornará os endereços IP mais recentes.

## <a name="examples"></a>Exemplos

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Obter a lista de endereços IP usados por um dispositivo há 24 horas

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Obter endereços IP usados por um dispositivo e encontrar dispositivos se comunicando com ele
Essa consulta usa a função para obter endereços IP atribuídos para o dispositivo `AssignedIPAddresses()` ( ) em ou antes de uma data específica ( `example-device-name` `example-date` ). Em seguida, ele usa os endereços IP para encontrar conexões com o dispositivo iniciadas por outros dispositivos. 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
