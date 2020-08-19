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
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794226"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="4d694-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="4d694-104">AssignedIPAddresses()</span></span>

<span data-ttu-id="4d694-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4d694-105">**Applies to:**</span></span>
- <span data-ttu-id="4d694-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4d694-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="4d694-107">Use a `AssignedIPAddresses()` função para obter rapidamente os endereços IP mais recentes que foram atribuídos a um dispositivo ou os endereços IP mais recentes de um momento específico.</span><span class="sxs-lookup"><span data-stu-id="4d694-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device or the most recent IP addresses from a specified point in time.</span></span> <span data-ttu-id="4d694-108">Essa função retorna uma tabela com as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="4d694-108">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="4d694-109">Coluna</span><span class="sxs-lookup"><span data-stu-id="4d694-109">Column</span></span> | <span data-ttu-id="4d694-110">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4d694-110">Data type</span></span> | <span data-ttu-id="4d694-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d694-111">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="4d694-112">Carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="4d694-112">Timestamp</span></span> | <span data-ttu-id="4d694-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4d694-113">datetime</span></span> | <span data-ttu-id="4d694-114">Última hora em que o dispositivo foi observado usando o endereço IP</span><span class="sxs-lookup"><span data-stu-id="4d694-114">Latest time when the device was observed using the IP address</span></span> |
| <span data-ttu-id="4d694-115">IPAddress</span><span class="sxs-lookup"><span data-stu-id="4d694-115">IPAddress</span></span> | <span data-ttu-id="4d694-116">string</span><span class="sxs-lookup"><span data-stu-id="4d694-116">string</span></span> | <span data-ttu-id="4d694-117">Endereço IP usado pelo dispositivo</span><span class="sxs-lookup"><span data-stu-id="4d694-117">IP address used by the device</span></span> |
| <span data-ttu-id="4d694-118">IPType</span><span class="sxs-lookup"><span data-stu-id="4d694-118">IPType</span></span> | <span data-ttu-id="4d694-119">string</span><span class="sxs-lookup"><span data-stu-id="4d694-119">string</span></span> | <span data-ttu-id="4d694-120">Indica se o endereço IP é um endereço público ou privado</span><span class="sxs-lookup"><span data-stu-id="4d694-120">Indicates whether the IP address is a public or private address</span></span> |
| <span data-ttu-id="4d694-121">NetworkAdapterType</span><span class="sxs-lookup"><span data-stu-id="4d694-121">NetworkAdapterType</span></span> | <span data-ttu-id="4d694-122">int</span><span class="sxs-lookup"><span data-stu-id="4d694-122">int</span></span> | <span data-ttu-id="4d694-123">Tipo de adaptador de rede usado pelo dispositivo que foi atribuído ao endereço IP.</span><span class="sxs-lookup"><span data-stu-id="4d694-123">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="4d694-124">Para obter os valores possíveis, consulte [essa enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="4d694-124">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span>  |
| <span data-ttu-id="4d694-125">ConnectedNetworks</span><span class="sxs-lookup"><span data-stu-id="4d694-125">ConnectedNetworks</span></span> | <span data-ttu-id="4d694-126">int</span><span class="sxs-lookup"><span data-stu-id="4d694-126">int</span></span> | <span data-ttu-id="4d694-127">Redes às quais o adaptador com o endereço IP atribuído está conectado.</span><span class="sxs-lookup"><span data-stu-id="4d694-127">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="4d694-128">Cada matriz JSON contém o nome da rede, a categoria (público, privado ou domínio), uma descrição e um sinalizador que indica se ele está conectado publicamente à Internet</span><span class="sxs-lookup"><span data-stu-id="4d694-128">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |


## <a name="syntax"></a><span data-ttu-id="4d694-129">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="4d694-129">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="4d694-130">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4d694-130">Arguments</span></span>

- <span data-ttu-id="4d694-131">**x** — `DeviceId` ou `DeviceName` Value identificando o dispositivo</span><span class="sxs-lookup"><span data-stu-id="4d694-131">**x** — `DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="4d694-132">**y** – `Timestamp` o valor (DateTime) que indica o ponto específico no momento em que os endereços IP mais recentes serão obtidos.</span><span class="sxs-lookup"><span data-stu-id="4d694-132">**y** — `Timestamp` (datetime) value indicating the specific point in time where to get the most recent IP addresses.</span></span> <span data-ttu-id="4d694-133">Se não for especificado, a função retornará os endereços IP mais recentes.</span><span class="sxs-lookup"><span data-stu-id="4d694-133">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="4d694-134">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4d694-134">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a><span data-ttu-id="4d694-135">Obter a lista de endereços IP usados por um dispositivo a partir de 24 horas</span><span class="sxs-lookup"><span data-stu-id="4d694-135">Get the list of IP addresses used by a device as of 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="4d694-136">Obter endereços IP usados por um dispositivo e encontrar dispositivos se comunicando com ele</span><span class="sxs-lookup"><span data-stu-id="4d694-136">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="4d694-137">Essa consulta usa a `AssignedIPAddresses()` função para obter endereços IP atribuídos para o dispositivo ( `example-device-name` ) em ou antes de uma data específica ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="4d694-137">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="4d694-138">Em seguida, ele usa os endereços IP para localizar conexões com o dispositivo iniciado por outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4d694-138">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="4d694-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4d694-139">Related topics</span></span>
- [<span data-ttu-id="4d694-140">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="4d694-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4d694-141">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="4d694-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4d694-142">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="4d694-142">Understand the schema</span></span>](advanced-hunting-schema-tables.md)