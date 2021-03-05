---
title: Tabela DeviceInfo no esquema de busca avançado
description: Saiba mais sobre o sistema operacional, o nome do computador e outras informações do computador na tabela DeviceInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, machineinfo, DeviceInfo, dispositivo, máquina, sistema operacional, plataforma, usuários
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
ms.openlocfilehash: 53948f3d470fb85ddfda8dbcf5b64024755ca50e
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461605"
---
# <a name="deviceinfo"></a><span data-ttu-id="7bc74-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="7bc74-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7bc74-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7bc74-105">**Applies to:**</span></span>
- <span data-ttu-id="7bc74-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bc74-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="7bc74-107">A tabela no esquema de busca avançada contém informações sobre dispositivos na organização, incluindo a versão do sistema operacional, usuários `DeviceInfo` ativos e nome do computador. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7bc74-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="7bc74-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="7bc74-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="7bc74-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7bc74-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7bc74-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="7bc74-110">Column name</span></span> | <span data-ttu-id="7bc74-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="7bc74-111">Data type</span></span> | <span data-ttu-id="7bc74-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="7bc74-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7bc74-113">datetime</span><span class="sxs-lookup"><span data-stu-id="7bc74-113">datetime</span></span> | <span data-ttu-id="7bc74-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="7bc74-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="7bc74-115">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-115">string</span></span> | <span data-ttu-id="7bc74-116">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="7bc74-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7bc74-117">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-117">string</span></span> | <span data-ttu-id="7bc74-118">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="7bc74-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="7bc74-119">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-119">string</span></span> | <span data-ttu-id="7bc74-120">Versão do agente de ponto de extremidade ou sensor em execução no computador</span><span class="sxs-lookup"><span data-stu-id="7bc74-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="7bc74-121">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-121">string</span></span> | <span data-ttu-id="7bc74-122">Endereço IP público usado pelo computador interno para se conectar ao serviço Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="7bc74-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="7bc74-123">Esse pode ser o endereço IP do próprio computador, um dispositivo NAT ou um proxy</span><span class="sxs-lookup"><span data-stu-id="7bc74-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="7bc74-124">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-124">string</span></span> | <span data-ttu-id="7bc74-125">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="7bc74-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="7bc74-126">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-126">string</span></span> | <span data-ttu-id="7bc74-127">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="7bc74-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="7bc74-128">Isso indica sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7</span><span class="sxs-lookup"><span data-stu-id="7bc74-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="7bc74-129">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-129">string</span></span> | <span data-ttu-id="7bc74-130">Versão de com build do sistema operacional em execução no computador</span><span class="sxs-lookup"><span data-stu-id="7bc74-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="7bc74-131">booliano</span><span class="sxs-lookup"><span data-stu-id="7bc74-131">boolean</span></span> | <span data-ttu-id="7bc74-132">Indicador booleano de se o computador está ingressado no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7bc74-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="7bc74-133">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-133">string</span></span> | <span data-ttu-id="7bc74-134">Identificador exclusivo do dispositivo no Azure AD</span><span class="sxs-lookup"><span data-stu-id="7bc74-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="7bc74-135">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-135">string</span></span> | <span data-ttu-id="7bc74-136">Lista de todos os usuários que estão conectados no computador no momento do evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="7bc74-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="7bc74-137">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-137">string</span></span> | <span data-ttu-id="7bc74-138">Marca de máquina adicionada por meio do Registro</span><span class="sxs-lookup"><span data-stu-id="7bc74-138">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="7bc74-139">long</span><span class="sxs-lookup"><span data-stu-id="7bc74-139">long</span></span> | <span data-ttu-id="7bc74-140">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="7bc74-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="7bc74-141">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="7bc74-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="7bc74-142">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-142">string</span></span> | <span data-ttu-id="7bc74-143">Informações adicionais sobre o evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="7bc74-143">Additional information about the event in JSON array format</span></span> |
| `OSVersion` | <span data-ttu-id="7bc74-144">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-144">string</span></span> | <span data-ttu-id="7bc74-145">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="7bc74-145">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="7bc74-146">string</span><span class="sxs-lookup"><span data-stu-id="7bc74-146">string</span></span> | <span data-ttu-id="7bc74-147">Grupo de máquinas do computador.</span><span class="sxs-lookup"><span data-stu-id="7bc74-147">Machine group of the machine.</span></span> <span data-ttu-id="7bc74-148">Esse grupo é usado pelo controle de acesso baseado em função para determinar o acesso ao computador</span><span class="sxs-lookup"><span data-stu-id="7bc74-148">This group is used by role-based access control to determine access to the machine</span></span> |

<span data-ttu-id="7bc74-149">A `DeviceInfo` tabela fornece informações do dispositivo com base em pulsações, que são relatórios periódicos ou sinais de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7bc74-149">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="7bc74-150">A cada quinze minutos, o dispositivo envia uma pulsação parcial que contém atributos que mudam com frequência, como `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="7bc74-150">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="7bc74-151">Uma vez por dia, uma pulsação completa que contém os atributos do dispositivo é enviada.</span><span class="sxs-lookup"><span data-stu-id="7bc74-151">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="7bc74-152">Você pode usar a seguinte consulta de exemplo para obter o estado mais recente de um dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7bc74-152">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="7bc74-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7bc74-153">Related topics</span></span>
- [<span data-ttu-id="7bc74-154">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="7bc74-154">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7bc74-155">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="7bc74-155">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7bc74-156">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="7bc74-156">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7bc74-157">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="7bc74-157">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7bc74-158">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="7bc74-158">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7bc74-159">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="7bc74-159">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
