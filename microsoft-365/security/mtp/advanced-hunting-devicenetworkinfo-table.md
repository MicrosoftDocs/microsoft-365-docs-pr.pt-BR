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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 0fd6000f4d3a4b9fafb0eede74cbbe4e6c3d494e
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899238"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="0994e-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="0994e-104">DeviceNetworkInfo</span></span>

<span data-ttu-id="0994e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0994e-105">**Applies to:**</span></span>
- <span data-ttu-id="0994e-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0994e-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="0994e-107">A `DeviceNetworkInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre a configuração de rede de computadores, incluindo adaptadores de rede, endereços IP e Mac e redes ou domínios conectados.</span><span class="sxs-lookup"><span data-stu-id="0994e-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="0994e-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="0994e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0994e-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0994e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0994e-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="0994e-110">Column name</span></span> | <span data-ttu-id="0994e-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0994e-111">Data type</span></span> | <span data-ttu-id="0994e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="0994e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0994e-113">datetime</span><span class="sxs-lookup"><span data-stu-id="0994e-113">datetime</span></span> | <span data-ttu-id="0994e-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="0994e-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="0994e-115">string</span><span class="sxs-lookup"><span data-stu-id="0994e-115">string</span></span> | <span data-ttu-id="0994e-116">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="0994e-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="0994e-117">string</span><span class="sxs-lookup"><span data-stu-id="0994e-117">string</span></span> | <span data-ttu-id="0994e-118">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="0994e-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="0994e-119">long</span><span class="sxs-lookup"><span data-stu-id="0994e-119">long</span></span> | <span data-ttu-id="0994e-120">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="0994e-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="0994e-121">Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp</span><span class="sxs-lookup"><span data-stu-id="0994e-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="0994e-122">string</span><span class="sxs-lookup"><span data-stu-id="0994e-122">string</span></span> | <span data-ttu-id="0994e-123">Nome do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="0994e-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="0994e-124">string</span><span class="sxs-lookup"><span data-stu-id="0994e-124">string</span></span> | <span data-ttu-id="0994e-125">Endereço MAC do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="0994e-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="0994e-126">string</span><span class="sxs-lookup"><span data-stu-id="0994e-126">string</span></span> | <span data-ttu-id="0994e-127">Tipo de adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="0994e-127">Network adapter type.</span></span> <span data-ttu-id="0994e-128">Para obter os valores possíveis, consulte [essa enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="0994e-128">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="0994e-129">string</span><span class="sxs-lookup"><span data-stu-id="0994e-129">string</span></span> | <span data-ttu-id="0994e-130">Status operacional do adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="0994e-130">Operational status of the network adapter.</span></span> <span data-ttu-id="0994e-131">Para obter os valores possíveis, consulte [essa enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="0994e-131">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="0994e-132">string</span><span class="sxs-lookup"><span data-stu-id="0994e-132">string</span></span> | <span data-ttu-id="0994e-133">Protocolo de encapsulamento, se a interface for usada para essa finalidade, por exemplo, 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="0994e-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="0994e-134">string</span><span class="sxs-lookup"><span data-stu-id="0994e-134">string</span></span> | <span data-ttu-id="0994e-135">Redes às quais o adaptador está conectado.</span><span class="sxs-lookup"><span data-stu-id="0994e-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="0994e-136">Cada matriz JSON contém o nome da rede, a categoria (público, privado ou domínio), uma descrição e um sinalizador que indica se ele está conectado publicamente à Internet</span><span class="sxs-lookup"><span data-stu-id="0994e-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="0994e-137">string</span><span class="sxs-lookup"><span data-stu-id="0994e-137">string</span></span> | <span data-ttu-id="0994e-138">Endereços de servidor DNS no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="0994e-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="0994e-139">string</span><span class="sxs-lookup"><span data-stu-id="0994e-139">string</span></span> | <span data-ttu-id="0994e-140">Endereço IPv4 do servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="0994e-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="0994e-141">string</span><span class="sxs-lookup"><span data-stu-id="0994e-141">string</span></span> | <span data-ttu-id="0994e-142">Endereço IPv6 do servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="0994e-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="0994e-143">string</span><span class="sxs-lookup"><span data-stu-id="0994e-143">string</span></span> | <span data-ttu-id="0994e-144">Endereços de gateway padrão no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="0994e-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="0994e-145">string</span><span class="sxs-lookup"><span data-stu-id="0994e-145">string</span></span> | <span data-ttu-id="0994e-146">Matriz JSON que contém todos os endereços IP atribuídos ao adaptador, juntamente com seus respectivos prefixo de sub-rede e espaço de endereço IP, como Public, Private ou link-local</span><span class="sxs-lookup"><span data-stu-id="0994e-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0994e-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0994e-147">Related topics</span></span>
- [<span data-ttu-id="0994e-148">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="0994e-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0994e-149">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="0994e-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0994e-150">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="0994e-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0994e-151">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="0994e-151">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0994e-152">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="0994e-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0994e-153">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="0994e-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
