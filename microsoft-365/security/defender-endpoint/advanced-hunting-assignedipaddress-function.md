---
title: Função AssignedIPAddresses() em busca avançada do Microsoft Defender para Ponto de Extremidade
description: Saiba como usar a função AssignedIPAddresses() para obter os endereços IP mais recentes atribuídos a um dispositivo
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, Microsoft Defender ATP, Microsoft Defender para Ponto de Extremidade, Windows Defender, Windows Defender ATP, Windows Defender proteção avançada contra ameaças, pesquisa, consulta, telemetria, referência de esquema, kusto, FileProfile, perfil de arquivo, função, enriquecimento
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
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 08ab7ff5bac917a027e4380a46ab1cb2cf0a1312
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053433"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)


Use a função em suas consultas de busca avançadas para obter rapidamente os endereços IP mais recentes `AssignedIPAddresses()` atribuídos a um dispositivo. Se você especificar um argumento timestamp, essa função obterá os endereços IP mais recentes no momento especificado.

Esta função retorna uma tabela com as seguintes colunas:

Coluna | Tipo de dados | Descrição
-|-|-
`Timestamp` | datetime | Última hora em que o dispositivo foi observado usando o endereço IP
`IPAddress` | cadeia de caracteres | Endereço IP usado pelo dispositivo
`IPType` | cadeia de caracteres | Indica se o endereço IP é um endereço público ou privado
`NetworkAdapterType` | int | Tipo de adaptador de rede usado pelo dispositivo que recebeu o endereço IP. Para os valores possíveis, consulte [esta enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)
`ConnectedNetworks` | int | Redes às que o adaptador com o endereço IP atribuído está conectado. Cada matriz JSON contém o nome da rede, categoria (público, privado ou domínio), uma descrição e um sinalizador indicando se ela está conectada publicamente à Internet

## <a name="syntax"></a>Sintaxe

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumentos

- **x**— `DeviceId` ou valor que identifica o `DeviceName` dispositivo
- **y**— (datetime) valor instruindo a função a obter os endereços IP atribuídos mais recentes `Timestamp` de uma hora específica. Se não for especificada, a função retornará os endereços IP mais recentes.

## <a name="examples"></a>Exemplos

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Obter a lista de endereços IP usados por um dispositivo 24 horas atrás

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Obter endereços IP usados por um dispositivo e encontrar dispositivos que se comunicam com ele

Essa consulta usa a função para receber endereços IP atribuídos para o dispositivo ( ) em ou `AssignedIPAddresses()` antes de uma data específica ( `example-device-name` `example-date` ). Em seguida, ele usa os endereços IP para encontrar conexões com o dispositivo iniciado por outros dispositivos. 

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
- [Compreender o esquema](advanced-hunting-schema-reference.md)
