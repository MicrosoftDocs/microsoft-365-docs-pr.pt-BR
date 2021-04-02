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
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 5dcc41302d797b4084c36d020908ba59131c90d4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499279"
---
# <a name="assignedipaddresses"></a><span data-ttu-id="e9582-104">AssignedIPAddresses()</span><span class="sxs-lookup"><span data-stu-id="e9582-104">AssignedIPAddresses()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

><span data-ttu-id="e9582-105">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e9582-105">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e9582-106">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e9582-106">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="e9582-107">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e9582-107">**Applies to:**</span></span>
- [<span data-ttu-id="e9582-108">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e9582-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="e9582-109">Use a função em suas consultas de busca avançadas para obter rapidamente os endereços IP mais recentes `AssignedIPAddresses()` atribuídos a um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9582-109">Use the `AssignedIPAddresses()` function in your advanced hunting queries to quickly obtain the latest IP addresses that have been assigned to a device.</span></span> <span data-ttu-id="e9582-110">Se você especificar um argumento timestamp, essa função obterá os endereços IP mais recentes no momento especificado.</span><span class="sxs-lookup"><span data-stu-id="e9582-110">If you specify a timestamp argument, this function obtains the most recent IP addresses at the specified time.</span></span>

<span data-ttu-id="e9582-111">Esta função retorna uma tabela com as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="e9582-111">This function returns a table with the following columns:</span></span>

<span data-ttu-id="e9582-112">Coluna</span><span class="sxs-lookup"><span data-stu-id="e9582-112">Column</span></span> | <span data-ttu-id="e9582-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e9582-113">Data type</span></span> | <span data-ttu-id="e9582-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="e9582-114">Description</span></span>
-|-|-
`Timestamp` | <span data-ttu-id="e9582-115">datetime</span><span class="sxs-lookup"><span data-stu-id="e9582-115">datetime</span></span> | <span data-ttu-id="e9582-116">Última hora em que o dispositivo foi observado usando o endereço IP</span><span class="sxs-lookup"><span data-stu-id="e9582-116">Latest time when the device was observed using the IP address</span></span>
`IPAddress` | <span data-ttu-id="e9582-117">string</span><span class="sxs-lookup"><span data-stu-id="e9582-117">string</span></span> | <span data-ttu-id="e9582-118">Endereço IP usado pelo dispositivo</span><span class="sxs-lookup"><span data-stu-id="e9582-118">IP address used by the device</span></span>
`IPType` | <span data-ttu-id="e9582-119">string</span><span class="sxs-lookup"><span data-stu-id="e9582-119">string</span></span> | <span data-ttu-id="e9582-120">Indica se o endereço IP é um endereço público ou privado</span><span class="sxs-lookup"><span data-stu-id="e9582-120">Indicates whether the IP address is a public or private address</span></span>
`NetworkAdapterType` | <span data-ttu-id="e9582-121">int</span><span class="sxs-lookup"><span data-stu-id="e9582-121">int</span></span> | <span data-ttu-id="e9582-122">Tipo de adaptador de rede usado pelo dispositivo que recebeu o endereço IP.</span><span class="sxs-lookup"><span data-stu-id="e9582-122">Network adapter type used by the device that has been assigned the IP address.</span></span> <span data-ttu-id="e9582-123">Para os valores possíveis, consulte [esta enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="e9582-123">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span>
`ConnectedNetworks` | <span data-ttu-id="e9582-124">int</span><span class="sxs-lookup"><span data-stu-id="e9582-124">int</span></span> | <span data-ttu-id="e9582-125">Redes às que o adaptador com o endereço IP atribuído está conectado.</span><span class="sxs-lookup"><span data-stu-id="e9582-125">Networks that the adapter with the assigned IP address is connected to.</span></span> <span data-ttu-id="e9582-126">Cada matriz JSON contém o nome da rede, categoria (público, privado ou domínio), uma descrição e um sinalizador indicando se ela está conectada publicamente à Internet</span><span class="sxs-lookup"><span data-stu-id="e9582-126">Each JSON array contains the network name, category (public, private, or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span>

## <a name="syntax"></a><span data-ttu-id="e9582-127">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="e9582-127">Syntax</span></span>

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a><span data-ttu-id="e9582-128">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e9582-128">Arguments</span></span>

- <span data-ttu-id="e9582-129">**x**— `DeviceId` ou valor que identifica o `DeviceName` dispositivo</span><span class="sxs-lookup"><span data-stu-id="e9582-129">**x**—`DeviceId` or `DeviceName` value identifying the device</span></span>
- <span data-ttu-id="e9582-130">**y**— (datetime) valor instruindo a função a obter os endereços IP atribuídos mais recentes `Timestamp` de uma hora específica.</span><span class="sxs-lookup"><span data-stu-id="e9582-130">**y**—`Timestamp` (datetime) value instructing the function to obtain the most recent assigned IP addresses from a specific time.</span></span> <span data-ttu-id="e9582-131">Se não for especificada, a função retornará os endereços IP mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e9582-131">If not specified, the function returns the latest IP addresses.</span></span>

## <a name="examples"></a><span data-ttu-id="e9582-132">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e9582-132">Examples</span></span>

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a><span data-ttu-id="e9582-133">Obter a lista de endereços IP usados por um dispositivo 24 horas atrás</span><span class="sxs-lookup"><span data-stu-id="e9582-133">Get the list of IP addresses used by a device 24 hours ago</span></span>

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a><span data-ttu-id="e9582-134">Obter endereços IP usados por um dispositivo e encontrar dispositivos que se comunicam com ele</span><span class="sxs-lookup"><span data-stu-id="e9582-134">Get IP addresses used by a device and find devices communicating with it</span></span>

<span data-ttu-id="e9582-135">Essa consulta usa a função para receber endereços IP atribuídos para o dispositivo ( ) em ou `AssignedIPAddresses()` antes de uma data específica ( `example-device-name` `example-date` ).</span><span class="sxs-lookup"><span data-stu-id="e9582-135">This query uses the `AssignedIPAddresses()` function to get assigned IP addresses for the device (`example-device-name`) on or before a specific date (`example-date`).</span></span> <span data-ttu-id="e9582-136">Em seguida, ele usa os endereços IP para encontrar conexões com o dispositivo iniciado por outros dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e9582-136">It then uses the IP addresses to find connections to the device initiated by other devices.</span></span> 

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

## <a name="related-topics"></a><span data-ttu-id="e9582-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e9582-137">Related topics</span></span>

- [<span data-ttu-id="e9582-138">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="e9582-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e9582-139">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="e9582-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e9582-140">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="e9582-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
