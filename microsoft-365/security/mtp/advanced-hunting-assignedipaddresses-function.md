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
# <a name="assignedipaddresses"></a><span data-ttu-id="76ce4-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="76ce4-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="76ce4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="76ce4-105">**Applies to:**</span></span>
- <span data-ttu-id="76ce4-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="76ce4-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="76ce4-107">Use a `AssignedIPAddresses()` função para obter rapidamente os endereços IP mais recentes que foram atribuídos a um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76ce4-107">Use the `AssignedIPAddresses()` function to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="76ce4-108">Se você especificar um argumento timestamp, essa função obterá os endereços IP mais recentes no horário especificado.</span><span class="sxs-lookup"><span data-stu-id="76ce4-108">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span> 

<span data-ttu-id="76ce4-109">Essa função retorna uma tabela com as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="76ce4-109">This function returns a table with the following columns:</span></span>

| <span data-ttu-id="76ce4-110">Coluna</span><span class="sxs-lookup"><span data-stu-id="76ce4-110">Column</span></span> | <span data-ttu-id="76ce4-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="76ce4-111">Data type</span></span> | <span data-ttu-id="76ce4-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="76ce4-112">Description</span></span> |
|------------|-------------|-------------|
| `Timestamp` | <span data-ttu-id="76ce4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="76ce4-113">datetime</span></span> | <span data-ttu-id="76ce4-114">Última hora em que o dispositivo foi observado usando o endereço IP</span><span class="sxs-lookup"><span data-stu-id="76ce4-114">Latest time when the device was observed using the IP address</span></span> |
| `IPAddress` | <span data-ttu-id="76ce4-115">string</span><span class="sxs-lookup"><span data-stu-id="76ce4-115">string</span></span> | <span data-ttu-id="76ce4-116">Endereço IP usado pelo dispositivo</span><span class="sxs-lookup"><span data-stu-id="76ce4-116">IP address used by the device</span></span> |
| `IPType` | <span data-ttu-id="76ce4-117">string</span><span class="sxs-lookup"><span data-stu-id="76ce4-117">string</span></span> | <span data-ttu-id="76ce4-118">Indica se o endereço IP é um endereço público ou privado</span><span class="sxs-lookup"><span data-stu-id="76ce4-118">Indicates whether the IP address is a public or private address</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="76ce4-119">int</span><span class="sxs-lookup"><span data-stu-id="76ce4-119">int</span></span> | <span data-ttu-id="76ce4-120">Tipo de adaptador de rede usado pelo dispositivo que foi atribuído ao endereço IP.</span><span class="sxs-lookup"><span data-stu-id="76ce4-120">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="76ce4-121">Para obter os valores possíveis, consulte [essa enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="76ce4-121">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="76ce4-122">int</span><span class="sxs-lookup"><span data-stu-id="76ce4-122">int</span></span> | <span data-ttu-id="76ce4-123">Redes às quais o adaptador com o endereço IP atribuído está conectado.</span><span class="sxs-lookup"><span data-stu-id="76ce4-123">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="76ce4-124">Cada matriz JSON contém o nome da rede, a categoria (pública, particular ou o domínio), uma descrição e um sinalizador que indica se ele está conectado publicamente à Internet</span><span class="sxs-lookup"><span data-stu-id="76ce4-124">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |

## <a name="syntax"></a><span data-ttu-id="76ce4-125">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="76ce4-125">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="76ce4-126">Argumentos</span><span class="sxs-lookup"><span data-stu-id="76ce4-126">Arguments</span></span>

- <span data-ttu-id="76ce4-127">**x**— `DeviceId` ou `DeviceName` Value identificando o dispositivo</span><span class="sxs-lookup"><span data-stu-id="76ce4-127">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="76ce4-128">valor **y**– `Timestamp` (DateTime) instruindo a função para obter os endereços IP atribuídos mais recentes de um horário específico.</span><span class="sxs-lookup"><span data-stu-id="76ce4-128">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="76ce4-129">Se não for especificado, a função retornará os endereços IP mais recentes.</span><span class="sxs-lookup"><span data-stu-id="76ce4-129">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="76ce4-130">Exemplos</span><span class="sxs-lookup"><span data-stu-id="76ce4-130">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="76ce4-131">Obter a lista de endereços IP usados por um dispositivo 24 horas atrás</span><span class="sxs-lookup"><span data-stu-id="76ce4-131">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="76ce4-132">Obter endereços IP usados por um dispositivo e encontrar dispositivos se comunicando com ele</span><span class="sxs-lookup"><span data-stu-id="76ce4-132">Get IP addresses used by a device and find devices communicating with it</span></span>
<span data-ttu-id="76ce4-133">Essa consulta usa a `AssignedIPAddresses()` função para obter endereços IP atribuídos para o dispositivo ( `example-device-name` ) em ou antes de uma data específica ( `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="76ce4-133">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="76ce4-134">Em seguida, ele usa os endereços IP para localizar conexões com o dispositivo iniciado por outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="76ce4-134">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="76ce4-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="76ce4-135">Related topics</span></span>
- [<span data-ttu-id="76ce4-136">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="76ce4-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="76ce4-137">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="76ce4-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="76ce4-138">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="76ce4-138">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
