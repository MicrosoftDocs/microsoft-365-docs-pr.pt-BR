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
# <a name="assignedipaddresses"></a><span data-ttu-id="e07ac-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="e07ac-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e07ac-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e07ac-105">**Applies to:**</span></span>
- <span data-ttu-id="e07ac-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e07ac-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e07ac-107">Use a função nas consultas de busca avançada para obter rapidamente os endereços IP mais recentes `AssignedIPAddresses()` que foram atribuídos a um dispositivo. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e07ac-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="e07ac-108">Se você especificar um argumento timestamp, essa função obterá os endereços IP mais recentes no horário especificado.</span><span class="sxs-lookup"><span data-stu-id="e07ac-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="e07ac-109">Esta função retorna uma tabela com as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="e07ac-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="e07ac-110">Coluna</span><span class="sxs-lookup"><span data-stu-id="e07ac-110">Column</span></span> | <span data-ttu-id="e07ac-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e07ac-111">Data type</span></span> | <span data-ttu-id="e07ac-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="e07ac-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="e07ac-113">datetime</span><span class="sxs-lookup"><span data-stu-id="e07ac-113">datetime</span></span> | <span data-ttu-id="e07ac-114">Hora mais recente em que o dispositivo foi observado usando o endereço IP</span><span class="sxs-lookup"><span data-stu-id="e07ac-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="e07ac-115">string</span><span class="sxs-lookup"><span data-stu-id="e07ac-115">string</span></span> | <span data-ttu-id="e07ac-116">Endereço IP usado pelo dispositivo</span><span class="sxs-lookup"><span data-stu-id="e07ac-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="e07ac-117">string</span><span class="sxs-lookup"><span data-stu-id="e07ac-117">string</span></span> | <span data-ttu-id="e07ac-118">Indica se o endereço IP é um endereço público ou privado</span><span class="sxs-lookup"><span data-stu-id="e07ac-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="e07ac-119">int</span><span class="sxs-lookup"><span data-stu-id="e07ac-119">int</span></span> | <span data-ttu-id="e07ac-120">Tipo de adaptador de rede usado pelo dispositivo ao qual foi atribuído o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="e07ac-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="e07ac-121">Para os valores possíveis, consulte [esta enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="e07ac-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="e07ac-122">int</span><span class="sxs-lookup"><span data-stu-id="e07ac-122">int</span></span> | <span data-ttu-id="e07ac-123">Redes às que o adaptador com o endereço IP atribuído está conectado.</span><span class="sxs-lookup"><span data-stu-id="e07ac-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="e07ac-124">Cada matriz JSON contém o nome da rede, categoria (público, privado ou domínio), uma descrição e um sinalizador indicando se ele está conectado publicamente à Internet</span><span class="sxs-lookup"><span data-stu-id="e07ac-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="e07ac-125">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e07ac-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="e07ac-126">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e07ac-126">Arguments</span></span>

- <span data-ttu-id="e07ac-127">**x**— `DeviceId` ou valor que identifica o `DeviceName` dispositivo</span><span class="sxs-lookup"><span data-stu-id="e07ac-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="e07ac-128">**y**— valor (datetime) instruindo a função a obter os endereços IP atribuídos mais `Timestamp` recentes de um horário específico.</span><span class="sxs-lookup"><span data-stu-id="e07ac-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="e07ac-129">Se não for especificada, a função retornará os endereços IP mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e07ac-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="e07ac-130">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e07ac-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="e07ac-131">Obter a lista de endereços IP usados por um dispositivo há 24 horas</span><span class="sxs-lookup"><span data-stu-id="e07ac-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="e07ac-132">Obter endereços IP usados por um dispositivo e encontrar dispositivos se comunicando com ele</span><span class="sxs-lookup"><span data-stu-id="e07ac-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="e07ac-133">Essa consulta usa a função para obter endereços IP atribuídos para o dispositivo `AssignedIPAddresses()` ( ) em ou antes de uma data específica ( `example-device-name` `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="e07ac-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="e07ac-134">Em seguida, ele usa os endereços IP para encontrar conexões com o dispositivo iniciadas por outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e07ac-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="e07ac-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e07ac-135">Related topics</span></span>
- [<span data-ttu-id="e07ac-136">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="e07ac-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e07ac-137">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="e07ac-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e07ac-138">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="e07ac-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
