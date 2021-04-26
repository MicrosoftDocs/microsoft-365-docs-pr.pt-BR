---
title: Tabela DeviceInfo no esquema de busca avançado
description: Saiba mais sobre o sistema operacional, o nome do computador e outras informações do computador na tabela DeviceInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, machineinfo, DeviceInfo, dispositivo, máquina, sistema operacional, plataforma, usuários
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
ms.openlocfilehash: f97947c2c9f02720facae4f0c3c29ff702416261
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023124"
---
# <a name="deviceinfo"></a><span data-ttu-id="06af3-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="06af3-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="06af3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="06af3-105">**Applies to:**</span></span>
- <span data-ttu-id="06af3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06af3-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="06af3-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="06af3-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="06af3-108">A tabela no esquema de busca avançada contém informações sobre dispositivos na organização, incluindo a versão do sistema operacional, usuários `DeviceInfo` ativos e nome do computador. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="06af3-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="06af3-109">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="06af3-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="06af3-110">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="06af3-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="06af3-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="06af3-111">Column name</span></span> | <span data-ttu-id="06af3-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="06af3-112">Data type</span></span> | <span data-ttu-id="06af3-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="06af3-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="06af3-114">datetime</span><span class="sxs-lookup"><span data-stu-id="06af3-114">datetime</span></span> | <span data-ttu-id="06af3-115">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="06af3-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="06af3-116">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06af3-116">string</span></span> | <span data-ttu-id="06af3-117">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="06af3-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="06af3-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06af3-118">string</span></span> | <span data-ttu-id="06af3-119">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="06af3-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="06af3-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06af3-120">string</span></span> | <span data-ttu-id="06af3-121">Versão do agente de ponto de extremidade ou sensor em execução no computador</span><span class="sxs-lookup"><span data-stu-id="06af3-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="06af3-122">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06af3-122">string</span></span> | <span data-ttu-id="06af3-123">Endereço IP público usado pelo computador interno para se conectar ao serviço Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="06af3-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="06af3-124">Esse pode ser o endereço IP do próprio computador, um dispositivo NAT ou um proxy</span><span class="sxs-lookup"><span data-stu-id="06af3-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="06af3-125">string</span><span class="sxs-lookup"><span data-stu-id="06af3-125">string</span></span> | <span data-ttu-id="06af3-126">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="06af3-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="06af3-127">string</span><span class="sxs-lookup"><span data-stu-id="06af3-127">string</span></span> | <span data-ttu-id="06af3-128">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="06af3-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="06af3-129">Isso indica sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7</span><span class="sxs-lookup"><span data-stu-id="06af3-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="06af3-130">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06af3-130">string</span></span> | <span data-ttu-id="06af3-131">Versão de com build do sistema operacional em execução no computador</span><span class="sxs-lookup"><span data-stu-id="06af3-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="06af3-132">booliano</span><span class="sxs-lookup"><span data-stu-id="06af3-132">boolean</span></span> | <span data-ttu-id="06af3-133">Indicador booleano de se o computador está ingressado no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="06af3-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="06af3-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06af3-134">string</span></span> | <span data-ttu-id="06af3-135">Identificador exclusivo do dispositivo no Azure AD</span><span class="sxs-lookup"><span data-stu-id="06af3-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="06af3-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06af3-136">string</span></span> | <span data-ttu-id="06af3-137">Lista de todos os usuários que estão conectados no computador no momento do evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="06af3-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="06af3-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06af3-138">string</span></span> | <span data-ttu-id="06af3-139">Marca de máquina adicionada por meio do Registro</span><span class="sxs-lookup"><span data-stu-id="06af3-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="06af3-140">string</span><span class="sxs-lookup"><span data-stu-id="06af3-140">string</span></span> | <span data-ttu-id="06af3-141">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="06af3-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="06af3-142">string</span><span class="sxs-lookup"><span data-stu-id="06af3-142">string</span></span> | <span data-ttu-id="06af3-143">Grupo de máquinas do computador.</span><span class="sxs-lookup"><span data-stu-id="06af3-143">Machine group of the machine.</span></span> <span data-ttu-id="06af3-144">Esse grupo é usado pelo controle de acesso baseado em função para determinar o acesso ao computador</span><span class="sxs-lookup"><span data-stu-id="06af3-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="06af3-145">long</span><span class="sxs-lookup"><span data-stu-id="06af3-145">long</span></span> | <span data-ttu-id="06af3-146">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="06af3-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="06af3-147">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="06af3-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="06af3-148">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06af3-148">string</span></span> | <span data-ttu-id="06af3-149">Informações adicionais sobre o evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="06af3-149">Additional information about the event in JSON array format</span></span> |

<span data-ttu-id="06af3-150">A `DeviceInfo` tabela fornece informações do dispositivo com base em pulsações, que são relatórios periódicos ou sinais de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="06af3-150">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="06af3-151">A cada quinze minutos, o dispositivo envia uma pulsação parcial que contém atributos que mudam com frequência, como `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="06af3-151">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="06af3-152">Uma vez por dia, uma pulsação completa que contém os atributos do dispositivo é enviada.</span><span class="sxs-lookup"><span data-stu-id="06af3-152">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="06af3-153">Você pode usar a seguinte consulta de exemplo para obter o estado mais recente de um dispositivo:</span><span class="sxs-lookup"><span data-stu-id="06af3-153">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="06af3-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="06af3-154">Related topics</span></span>
- [<span data-ttu-id="06af3-155">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="06af3-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="06af3-156">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="06af3-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="06af3-157">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="06af3-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="06af3-158">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="06af3-158">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="06af3-159">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="06af3-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="06af3-160">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="06af3-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
