---
title: Tabela DeviceNetworkInfo no esquema de busca avançado
description: Saiba mais sobre informações de configuração de rede na tabela DeviceNetworkInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, mac, ip, adaptador, dns, dhcp, gateway, túnel
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1c8a3f3ab91add9e057c4661677997e658f42386
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053211"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="280d7-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="280d7-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="280d7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="280d7-105">**Applies to:**</span></span>
- <span data-ttu-id="280d7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="280d7-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="280d7-107">A tabela no esquema de busca avançada contém informações sobre a configuração de rede de computadores, incluindo adaptadores de rede, endereços IP e MAC e redes `DeviceNetworkInfo` ou domínios [](advanced-hunting-overview.md) conectados.</span><span class="sxs-lookup"><span data-stu-id="280d7-107">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="280d7-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="280d7-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="280d7-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="280d7-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="280d7-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="280d7-110">Column name</span></span> | <span data-ttu-id="280d7-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="280d7-111">Data type</span></span> | <span data-ttu-id="280d7-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="280d7-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="280d7-113">datetime</span><span class="sxs-lookup"><span data-stu-id="280d7-113">datetime</span></span> | <span data-ttu-id="280d7-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="280d7-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="280d7-115">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-115">string</span></span> | <span data-ttu-id="280d7-116">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="280d7-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="280d7-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-117">string</span></span> | <span data-ttu-id="280d7-118">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="280d7-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ReportId` | <span data-ttu-id="280d7-119">long</span><span class="sxs-lookup"><span data-stu-id="280d7-119">long</span></span> | <span data-ttu-id="280d7-120">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="280d7-120">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="280d7-121">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="280d7-121">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="280d7-122">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-122">string</span></span> | <span data-ttu-id="280d7-123">Nome do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="280d7-123">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="280d7-124">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-124">string</span></span> | <span data-ttu-id="280d7-125">Endereço MAC do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="280d7-125">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="280d7-126">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-126">string</span></span> | <span data-ttu-id="280d7-127">Tipo de adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="280d7-127">Network adapter type.</span></span> <span data-ttu-id="280d7-128">Para os valores possíveis, consulte [esta enumeração](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="280d7-128">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="280d7-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-129">string</span></span> | <span data-ttu-id="280d7-130">Status operacional do adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="280d7-130">Operational status of the network adapter.</span></span> <span data-ttu-id="280d7-131">Para os valores possíveis, consulte [esta enumeração](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span><span class="sxs-lookup"><span data-stu-id="280d7-131">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2)</span></span> |
| `TunnelType` | <span data-ttu-id="280d7-132">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-132">string</span></span> | <span data-ttu-id="280d7-133">Protocolo de túnel, se a interface for usada para essa finalidade, por exemplo, 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="280d7-133">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="280d7-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-134">string</span></span> | <span data-ttu-id="280d7-135">Redes às que o adaptador está conectado.</span><span class="sxs-lookup"><span data-stu-id="280d7-135">Networks that the adapter is connected to.</span></span> <span data-ttu-id="280d7-136">Cada matriz JSON contém o nome da rede, categoria (público, privado ou domínio), uma descrição e um sinalizador indicando se ela está conectada publicamente à Internet</span><span class="sxs-lookup"><span data-stu-id="280d7-136">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="280d7-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-137">string</span></span> | <span data-ttu-id="280d7-138">Endereços de servidor DNS no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="280d7-138">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="280d7-139">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-139">string</span></span> | <span data-ttu-id="280d7-140">Endereço IPv4 do servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="280d7-140">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="280d7-141">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-141">string</span></span> | <span data-ttu-id="280d7-142">Endereço IPv6 do servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="280d7-142">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="280d7-143">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-143">string</span></span> | <span data-ttu-id="280d7-144">Endereços de gateway padrão no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="280d7-144">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="280d7-145">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="280d7-145">string</span></span> | <span data-ttu-id="280d7-146">Matriz JSON contendo todos os endereços IP atribuídos ao adaptador, juntamente com seu respectivo prefixo de sub-rede e espaço de endereço IP, como público, privado ou link-local</span><span class="sxs-lookup"><span data-stu-id="280d7-146">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="280d7-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="280d7-147">Related topics</span></span>
- [<span data-ttu-id="280d7-148">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="280d7-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="280d7-149">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="280d7-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="280d7-150">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="280d7-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="280d7-151">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="280d7-151">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="280d7-152">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="280d7-152">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="280d7-153">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="280d7-153">Apply query best practices</span></span>](advanced-hunting-best-practices.md)