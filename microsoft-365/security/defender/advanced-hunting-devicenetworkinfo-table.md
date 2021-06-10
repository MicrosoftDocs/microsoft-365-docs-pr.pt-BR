---
title: Tabela DeviceNetworkInfo no esquema de busca avançado
description: Saiba mais sobre informações de configuração de rede na tabela DeviceNetworkInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, mac, ip, adaptador, dns, dhcp, gateway, túnel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 11a6fd00524e3dd7ad456f68da6f493d74deee69
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023184"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="93dce-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="93dce-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="93dce-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="93dce-105">**Applies to:**</span></span>
- <span data-ttu-id="93dce-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93dce-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="93dce-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="93dce-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="93dce-108">A tabela no esquema de busca avançada contém informações sobre a configuração de rede de computadores, incluindo adaptadores de rede, endereços IP e MAC e redes `DeviceNetworkInfo` ou domínios [](advanced-hunting-overview.md) conectados.</span><span class="sxs-lookup"><span data-stu-id="93dce-108">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of machines, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="93dce-109">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="93dce-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="93dce-110">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="93dce-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="93dce-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="93dce-111">Column name</span></span> | <span data-ttu-id="93dce-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="93dce-112">Data type</span></span> | <span data-ttu-id="93dce-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="93dce-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="93dce-114">datetime</span><span class="sxs-lookup"><span data-stu-id="93dce-114">datetime</span></span> | <span data-ttu-id="93dce-115">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="93dce-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="93dce-116">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-116">string</span></span> | <span data-ttu-id="93dce-117">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="93dce-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="93dce-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-118">string</span></span> | <span data-ttu-id="93dce-119">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="93dce-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="93dce-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-120">string</span></span> | <span data-ttu-id="93dce-121">Nome do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="93dce-121">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="93dce-122">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-122">string</span></span> | <span data-ttu-id="93dce-123">Endereço MAC do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="93dce-123">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="93dce-124">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-124">string</span></span> | <span data-ttu-id="93dce-125">Tipo de adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="93dce-125">Network adapter type.</span></span> <span data-ttu-id="93dce-126">Para os valores possíveis, consulte [esta enumeração](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span><span class="sxs-lookup"><span data-stu-id="93dce-126">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.networkinterfacetype)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="93dce-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-127">string</span></span> | <span data-ttu-id="93dce-128">Status operacional do adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="93dce-128">Operational status of the network adapter.</span></span> <span data-ttu-id="93dce-129">Para os valores possíveis, consulte [esta enumeração](/dotnet/api/system.net.networkinformation.operationalstatus)</span><span class="sxs-lookup"><span data-stu-id="93dce-129">For the possible values, refer to [this enumeration](/dotnet/api/system.net.networkinformation.operationalstatus)</span></span> |
| `TunnelType` | <span data-ttu-id="93dce-130">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-130">string</span></span> | <span data-ttu-id="93dce-131">Protocolo de túnel, se a interface for usada para essa finalidade, por exemplo, 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="93dce-131">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="93dce-132">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-132">string</span></span> | <span data-ttu-id="93dce-133">Redes às que o adaptador está conectado.</span><span class="sxs-lookup"><span data-stu-id="93dce-133">Networks that the adapter is connected to.</span></span> <span data-ttu-id="93dce-134">Cada matriz JSON contém o nome da rede, categoria (público, privado ou domínio), uma descrição e um sinalizador indicando se ela está conectada publicamente à Internet</span><span class="sxs-lookup"><span data-stu-id="93dce-134">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="93dce-135">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-135">string</span></span> | <span data-ttu-id="93dce-136">Endereços de servidor DNS no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="93dce-136">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="93dce-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-137">string</span></span> | <span data-ttu-id="93dce-138">Endereço IPv4 do servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="93dce-138">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="93dce-139">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-139">string</span></span> | <span data-ttu-id="93dce-140">Endereço IPv6 do servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="93dce-140">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="93dce-141">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-141">string</span></span> | <span data-ttu-id="93dce-142">Endereços de gateway padrão no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="93dce-142">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="93dce-143">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="93dce-143">string</span></span> | <span data-ttu-id="93dce-144">Matriz JSON contendo todos os endereços IP atribuídos ao adaptador, juntamente com seu respectivo prefixo de sub-rede e espaço de endereço IP, como público, privado ou link-local</span><span class="sxs-lookup"><span data-stu-id="93dce-144">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |
| `ReportId` | <span data-ttu-id="93dce-145">long</span><span class="sxs-lookup"><span data-stu-id="93dce-145">long</span></span> | <span data-ttu-id="93dce-146">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="93dce-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="93dce-147">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="93dce-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |

## <a name="related-topics"></a><span data-ttu-id="93dce-148">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="93dce-148">Related topics</span></span>
- [<span data-ttu-id="93dce-149">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="93dce-149">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="93dce-150">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="93dce-150">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="93dce-151">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="93dce-151">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="93dce-152">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="93dce-152">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="93dce-153">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="93dce-153">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="93dce-154">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="93dce-154">Apply query best practices</span></span>](advanced-hunting-best-practices.md)