---
title: Tabela DeviceNetworkInfo no esquema de busca avançada
description: Saiba mais sobre as informações de configuração de rede na tabela DeviceNetworkInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Search, Query, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, Mac, IP, adaptador, DNS, DHCP, gateway, túnel
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 92856d3f077d3bfe49a3b25f50965aa1c03ebdb0
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842649"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="65ced-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="65ced-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="65ced-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="65ced-105">**Applies to:**</span></span>
- <span data-ttu-id="65ced-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="65ced-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="65ced-107">A `DeviceNetworkInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre a configuração de rede de computadores, incluindo adaptadores de rede, endereços IP e Mac e redes ou domínios conectados.</span><span class="sxs-lookup"><span data-stu-id="65ced-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="65ced-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="65ced-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="65ced-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="65ced-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="65ced-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="65ced-110">Column name</span></span> | <span data-ttu-id="65ced-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="65ced-111">Data type</span></span> | <span data-ttu-id="65ced-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="65ced-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="65ced-113">datetime</span><span class="sxs-lookup"><span data-stu-id="65ced-113">datetime</span></span> | <span data-ttu-id="65ced-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="65ced-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="65ced-115">string</span><span class="sxs-lookup"><span data-stu-id="65ced-115">string</span></span> | <span data-ttu-id="65ced-116">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="65ced-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="65ced-117">string</span><span class="sxs-lookup"><span data-stu-id="65ced-117">string</span></span> | <span data-ttu-id="65ced-118">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="65ced-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="65ced-119">long</span><span class="sxs-lookup"><span data-stu-id="65ced-119">long</span></span> | <span data-ttu-id="65ced-120">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="65ced-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="65ced-121">Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp</span><span class="sxs-lookup"><span data-stu-id="65ced-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="65ced-122">string</span><span class="sxs-lookup"><span data-stu-id="65ced-122">string</span></span> | <span data-ttu-id="65ced-123">Nome do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="65ced-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="65ced-124">string</span><span class="sxs-lookup"><span data-stu-id="65ced-124">string</span></span> | <span data-ttu-id="65ced-125">Endereço MAC do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="65ced-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="65ced-126">string</span><span class="sxs-lookup"><span data-stu-id="65ced-126">string</span></span> | <span data-ttu-id="65ced-127">Tipo de adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="65ced-127">Network adapter type.</span></span> <span data-ttu-id="65ced-128">Para obter os valores possíveis, consulte [essa enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="65ced-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="65ced-129">string</span><span class="sxs-lookup"><span data-stu-id="65ced-129">string</span></span> | <span data-ttu-id="65ced-130">Status operacional do adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="65ced-130">Operational status of the network adapter.</span></span> <span data-ttu-id="65ced-131">Para obter os valores possíveis, consulte [essa enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="65ced-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="65ced-132">string</span><span class="sxs-lookup"><span data-stu-id="65ced-132">string</span></span> | <span data-ttu-id="65ced-133">Protocolo de encapsulamento, se a interface for usada para essa finalidade, por exemplo, 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="65ced-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="65ced-134">string</span><span class="sxs-lookup"><span data-stu-id="65ced-134">string</span></span> | <span data-ttu-id="65ced-135">Redes às quais o adaptador está conectado.</span><span class="sxs-lookup"><span data-stu-id="65ced-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="65ced-136">Cada matriz JSON contém o nome da rede, a categoria (público, privado ou domínio), uma descrição e um sinalizador que indica se ele está conectado publicamente à Internet</span><span class="sxs-lookup"><span data-stu-id="65ced-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="65ced-137">string</span><span class="sxs-lookup"><span data-stu-id="65ced-137">string</span></span> | <span data-ttu-id="65ced-138">Endereços de servidor DNS no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="65ced-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="65ced-139">string</span><span class="sxs-lookup"><span data-stu-id="65ced-139">string</span></span> | <span data-ttu-id="65ced-140">Endereço IPv4 do servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="65ced-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="65ced-141">string</span><span class="sxs-lookup"><span data-stu-id="65ced-141">string</span></span> | <span data-ttu-id="65ced-142">Endereço IPv6 do servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="65ced-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="65ced-143">string</span><span class="sxs-lookup"><span data-stu-id="65ced-143">string</span></span> | <span data-ttu-id="65ced-144">Endereços de gateway padrão no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="65ced-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="65ced-145">string</span><span class="sxs-lookup"><span data-stu-id="65ced-145">string</span></span> | <span data-ttu-id="65ced-146">Matriz JSON que contém todos os endereços IP atribuídos ao adaptador, juntamente com seus respectivos prefixo de sub-rede e espaço de endereço IP, como Public, Private ou link-local</span><span class="sxs-lookup"><span data-stu-id="65ced-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="65ced-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="65ced-147">Related topics</span></span>
- [<span data-ttu-id="65ced-148">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="65ced-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="65ced-149">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="65ced-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="65ced-150">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="65ced-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="65ced-151">Procure em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="65ced-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="65ced-152">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="65ced-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="65ced-153">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="65ced-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
