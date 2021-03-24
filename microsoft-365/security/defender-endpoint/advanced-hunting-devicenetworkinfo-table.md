---
title: Tabela DeviceNetworkInfo no esquema de busca avançado
description: Saiba mais sobre informações de configuração de rede na tabela DeviceNetworkInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, devicenetworkinfo, dispositivo, dispositivo, mac, ip, adaptador, dns, dhcp, gateway, túnel, DeviceNetworkInfo
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
ms.technology: mde
ms.openlocfilehash: 4ba3e81163cdbba54bf718dca929e2df3b39a1c3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054108"
---
# <a name="devicenetworkinfo"></a><span data-ttu-id="50c92-104">DeviceNetworkInfo</span><span class="sxs-lookup"><span data-stu-id="50c92-104">DeviceNetworkInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="50c92-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="50c92-105">**Applies to:**</span></span>
- [<span data-ttu-id="50c92-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="50c92-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="50c92-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="50c92-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="50c92-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="50c92-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="50c92-109">A tabela no esquema de busca avançada contém informações sobre a configuração de rede de dispositivos, incluindo adaptadores de rede, endereços IP e MAC e redes `DeviceNetworkInfo` ou domínios [](advanced-hunting-overview.md) conectados.</span><span class="sxs-lookup"><span data-stu-id="50c92-109">The `DeviceNetworkInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about networking configuration of devices, including network adapters, IP and MAC addresses, and connected networks or domains.</span></span> <span data-ttu-id="50c92-110">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="50c92-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="50c92-111">Para obter informações sobre outras tabelas no esquema de busca avançado, consulte [a referência avançada do esquema de busca](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="50c92-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="50c92-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="50c92-112">Column name</span></span> | <span data-ttu-id="50c92-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="50c92-113">Data type</span></span> | <span data-ttu-id="50c92-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="50c92-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="50c92-115">datetime</span><span class="sxs-lookup"><span data-stu-id="50c92-115">datetime</span></span> | <span data-ttu-id="50c92-116">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="50c92-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="50c92-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-117">string</span></span> | <span data-ttu-id="50c92-118">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="50c92-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="50c92-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-119">string</span></span> | <span data-ttu-id="50c92-120">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="50c92-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ReportId` | <span data-ttu-id="50c92-121">long</span><span class="sxs-lookup"><span data-stu-id="50c92-121">long</span></span> | <span data-ttu-id="50c92-122">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="50c92-122">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="50c92-123">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com `DeviceName` as `Timestamp` colunas e</span><span class="sxs-lookup"><span data-stu-id="50c92-123">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `NetworkAdapterName` | <span data-ttu-id="50c92-124">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-124">string</span></span> | <span data-ttu-id="50c92-125">Nome do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="50c92-125">Name of the network adapter</span></span> |
| `MacAddress` | <span data-ttu-id="50c92-126">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-126">string</span></span> | <span data-ttu-id="50c92-127">Endereço MAC do adaptador de rede</span><span class="sxs-lookup"><span data-stu-id="50c92-127">MAC address of the network adapter</span></span> |
| `NetworkAdapterType` | <span data-ttu-id="50c92-128">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-128">string</span></span> | <span data-ttu-id="50c92-129">Tipo de adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="50c92-129">Network adapter type.</span></span> <span data-ttu-id="50c92-130">Para os valores possíveis, consulte [esta enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="50c92-130">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `NetworkAdapterStatus` | <span data-ttu-id="50c92-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-131">string</span></span> | <span data-ttu-id="50c92-132">Status operacional do adaptador de rede.</span><span class="sxs-lookup"><span data-stu-id="50c92-132">Operational status of the network adapter.</span></span> <span data-ttu-id="50c92-133">Para os valores possíveis, consulte [esta enumeração](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="50c92-133">For the possible values, refer to [this enumeration](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true)</span></span> |
| `TunnelType` | <span data-ttu-id="50c92-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-134">string</span></span> | <span data-ttu-id="50c92-135">Protocolo de túnel, se a interface for usada para essa finalidade, por exemplo, 6to4, Teredo, ISATAP, PPTP, SSTP e SSH</span><span class="sxs-lookup"><span data-stu-id="50c92-135">Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH</span></span> |
| `ConnectedNetworks` | <span data-ttu-id="50c92-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-136">string</span></span> | <span data-ttu-id="50c92-137">Redes às que o adaptador está conectado.</span><span class="sxs-lookup"><span data-stu-id="50c92-137">Networks that the adapter is connected to.</span></span> <span data-ttu-id="50c92-138">Cada matriz JSON contém o nome da rede, categoria (público, privado ou domínio), uma descrição e um sinalizador indicando se ela está conectada publicamente à Internet</span><span class="sxs-lookup"><span data-stu-id="50c92-138">Each JSON array contains the network name, category (public, private or domain), a description, and a flag indicating if it's connected publicly to the internet</span></span> |
| `DnsAddresses` | <span data-ttu-id="50c92-139">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-139">string</span></span> | <span data-ttu-id="50c92-140">Endereços de servidor DNS no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="50c92-140">DNS server addresses in JSON array format</span></span> |
| `IPv4Dhcp` | <span data-ttu-id="50c92-141">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-141">string</span></span> | <span data-ttu-id="50c92-142">Endereço IPv4 do servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="50c92-142">IPv4 address of DHCP server</span></span> |
| `IPv6Dhcp` | <span data-ttu-id="50c92-143">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-143">string</span></span> | <span data-ttu-id="50c92-144">Endereço IPv6 do servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="50c92-144">IPv6 address of DHCP server</span></span> |
| `DefaultGateways` | <span data-ttu-id="50c92-145">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-145">string</span></span> | <span data-ttu-id="50c92-146">Endereços de gateway padrão no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="50c92-146">Default gateway addresses in JSON array format</span></span> |
| `IPAddresses` | <span data-ttu-id="50c92-147">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50c92-147">string</span></span> | <span data-ttu-id="50c92-148">Matriz JSON contendo todos os endereços IP atribuídos ao adaptador, juntamente com seu respectivo prefixo de sub-rede e espaço de endereço IP, como público, privado ou link-local</span><span class="sxs-lookup"><span data-stu-id="50c92-148">JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and IP address space, such as public, private, or link-local</span></span> |

## <a name="related-topics"></a><span data-ttu-id="50c92-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="50c92-149">Related topics</span></span>
- [<span data-ttu-id="50c92-150">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="50c92-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="50c92-151">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="50c92-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="50c92-152">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="50c92-152">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
