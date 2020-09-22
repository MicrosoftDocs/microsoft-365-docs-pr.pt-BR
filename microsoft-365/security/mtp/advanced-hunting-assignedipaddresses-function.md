---
title: Função AssignedIPAddresses () em busca avançada para a proteção contra ameaças da Microsoft
description: Saiba como usar a função AssignedIPAddresses () para obter os endereços IP mais recentes atribuídos a um dispositivo
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, fileprofile, perfil de arquivo, função, enriquecimento
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
ms.openlocfilehash: 685132e3f5c303f21fde3702725a84e24383e679
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198238"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Use a `AssignedIPAddresses()` função para obter rapidamente os endereços IP mais recentes que foram atribuídos a um dispositivo. Se você especificar um argumento timestamp, essa função obterá os endereços IP mais recentes no horário especificado. 

Essa função retorna uma tabela com as seguintes colunas:

| Coluna | Tipo de dados | Descrição |
|------------|-------------|-------------|
| `Timestamp` | datetime | Última hora em que o dispositivo foi observado usando o endereço IP |
| `IPAddress` | string | Endereço IP usado pelo dispositivo |
| `IPType` | string | Indica se o endereço IP é um endereço público ou privado |
| `NetworkAdapterType` | int | Tipo de adaptador de rede usado pelo dispositivo que foi atribuído ao endereço IP. Para obter os valores possíveis, consulte [essa enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Redes às quais o adaptador com o endereço IP atribuído está conectado. Cada matriz JSON contém o nome da rede, a categoria (pública, particular ou o domínio), uma descrição e um sinalizador que indica se ele está conectado publicamente à Internet |

## <a name="syntax"></a>Sintaxe

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumentos

- **x**— `DeviceId` ou `DeviceName` Value identificando o dispositivo
- valor **y**– `Timestamp` (DateTime) instruindo a função para obter os endereços IP atribuídos mais recentes de um horário específico. Se não for especificado, a função retornará os endereços IP mais recentes.

## <a name="examples"></a>Exemplos

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Obter a lista de endereços IP usados por um dispositivo 24 horas atrás

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Obter endereços IP usados por um dispositivo e encontrar dispositivos se comunicando com ele
Essa consulta usa a `AssignedIPAddresses()` função para obter endereços IP atribuídos para o dispositivo ( `example-device-name` ) em ou antes de uma data específica ( `example-date` ). Em seguida, ele usa os endereços IP para localizar conexões com o dispositivo iniciado por outros dispositivos. 

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
