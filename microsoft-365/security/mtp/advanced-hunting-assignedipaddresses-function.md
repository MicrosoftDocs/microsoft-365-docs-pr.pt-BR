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
ms.openlocfilehash: c52f7b8bf5a93a75b3330a3377f3fab34b8e7837
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922915"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="75911-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="75911-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="75911-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="75911-105">**Applies to:**</span></span>
- <span data-ttu-id="75911-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75911-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="75911-107">Use a função em suas consultas de busca avançadas para obter rapidamente os endereços IP mais recentes `AssignedIPAddresses()` atribuídos a um dispositivo. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="75911-107">Use the `AssignedIPAddresses()` function in your [advanced hunting](advanced-hunting-overview.md) queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="75911-108">Se você especificar um argumento timestamp, essa função obterá os endereços IP mais recentes no momento especificado.</span><span class="sxs-lookup"><span data-stu-id="75911-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="75911-109">Esta função retorna uma tabela com as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="75911-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="75911-110">Coluna</span><span class="sxs-lookup"><span data-stu-id="75911-110">Column</span></span> | <span data-ttu-id="75911-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="75911-111">Data type</span></span> | <span data-ttu-id="75911-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="75911-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="75911-113">datetime</span><span class="sxs-lookup"><span data-stu-id="75911-113">datetime</span></span> | <span data-ttu-id="75911-114">Última hora em que o dispositivo foi observado usando o endereço IP</span><span class="sxs-lookup"><span data-stu-id="75911-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="75911-115">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="75911-115">string</span></span> | <span data-ttu-id="75911-116">Endereço IP usado pelo dispositivo</span><span class="sxs-lookup"><span data-stu-id="75911-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="75911-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="75911-117">string</span></span> | <span data-ttu-id="75911-118">Indica se o endereço IP é um endereço público ou privado</span><span class="sxs-lookup"><span data-stu-id="75911-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="75911-119">int</span><span class="sxs-lookup"><span data-stu-id="75911-119">int</span></span> | <span data-ttu-id="75911-120">Tipo de adaptador de rede usado pelo dispositivo que recebeu o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="75911-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="75911-121">Para os valores possíveis, consulte [esta enumeração](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="75911-121">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="75911-122">int</span><span class="sxs-lookup"><span data-stu-id="75911-122">int</span></span> | <span data-ttu-id="75911-123">Redes às que o adaptador com o endereço IP atribuído está conectado.</span><span class="sxs-lookup"><span data-stu-id="75911-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="75911-124">Cada matriz JSON contém o nome da rede, categoria (público, privado ou domínio), uma descrição e um sinalizador indicando se ela está conectada publicamente à Internet</span><span class="sxs-lookup"><span data-stu-id="75911-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="75911-125">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="75911-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="75911-126">Argumentos</span><span class="sxs-lookup"><span data-stu-id="75911-126">Arguments</span></span>

- <span data-ttu-id="75911-127">**x**— `DeviceId` ou valor que identifica o `DeviceName` dispositivo</span><span class="sxs-lookup"><span data-stu-id="75911-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="75911-128">**y**— (datetime) valor instruindo a função a obter os endereços IP atribuídos mais recentes `Timestamp` de uma hora específica.</span><span class="sxs-lookup"><span data-stu-id="75911-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="75911-129">Se não for especificada, a função retornará os endereços IP mais recentes.</span><span class="sxs-lookup"><span data-stu-id="75911-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="75911-130">Exemplos</span><span class="sxs-lookup"><span data-stu-id="75911-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="75911-131">Obter a lista de endereços IP usados por um dispositivo 24 horas atrás</span><span class="sxs-lookup"><span data-stu-id="75911-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="75911-132">Obter endereços IP usados por um dispositivo e encontrar dispositivos que se comunicam com ele</span><span class="sxs-lookup"><span data-stu-id="75911-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="75911-133">Essa consulta usa a função para receber endereços IP atribuídos para o dispositivo ( ) em ou `AssignedIPAddresses()` antes de uma data específica ( `example-device-name` `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="75911-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="75911-134">Em seguida, ele usa os endereços IP para encontrar conexões com o dispositivo iniciado por outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="75911-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="75911-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="75911-135">Related topics</span></span>
- [<span data-ttu-id="75911-136">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="75911-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="75911-137">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="75911-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="75911-138">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="75911-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)