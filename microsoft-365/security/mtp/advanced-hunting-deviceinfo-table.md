---
title: Tabela DeviceInfo no esquema de busca avançada
description: Saiba mais sobre o sistema operacional, o nome do computador e outras informações do computador na tabela DeviceInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, machineinfo, DeviceInfo, dispositivo, máquina, so, plataforma , os usuários
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
ms.openlocfilehash: ab7e48eaf582dbf6bc26d0393d26fea433da2253
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600438"
---
# <a name="deviceinfo"></a><span data-ttu-id="13033-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="13033-104">DeviceInfo</span></span>

<span data-ttu-id="13033-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="13033-105">**Applies to:**</span></span>
- <span data-ttu-id="13033-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="13033-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="13033-107">A `DeviceInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre as máquinas da organização, incluindo a versão do sistema operacional, usuários ativos e o nome do computador.</span><span class="sxs-lookup"><span data-stu-id="13033-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="13033-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="13033-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="13033-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="13033-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="13033-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="13033-110">Column name</span></span> | <span data-ttu-id="13033-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="13033-111">Data type</span></span> | <span data-ttu-id="13033-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="13033-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="13033-113">datetime</span><span class="sxs-lookup"><span data-stu-id="13033-113">datetime</span></span> | <span data-ttu-id="13033-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="13033-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="13033-115">string</span><span class="sxs-lookup"><span data-stu-id="13033-115">string</span></span> | <span data-ttu-id="13033-116">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="13033-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="13033-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="13033-117">string</span></span> | <span data-ttu-id="13033-118">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="13033-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="13033-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="13033-119">string</span></span> | <span data-ttu-id="13033-120">Versão do agente de ponto de extremidade ou do sensor em execução no computador</span><span class="sxs-lookup"><span data-stu-id="13033-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="13033-121">string</span><span class="sxs-lookup"><span data-stu-id="13033-121">string</span></span> | <span data-ttu-id="13033-122">Endereço IP público usado pela máquina integrada para se conectar ao serviço do Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="13033-122">Public IP address used by the onboarded machine to connect to the Microsoft Defender ATP service.</span></span> <span data-ttu-id="13033-123">Esse pode ser o endereço IP da máquina, um dispositivo NAT ou um proxy</span><span class="sxs-lookup"><span data-stu-id="13033-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="13033-124">string</span><span class="sxs-lookup"><span data-stu-id="13033-124">string</span></span> | <span data-ttu-id="13033-125">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="13033-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="13033-126">string</span><span class="sxs-lookup"><span data-stu-id="13033-126">string</span></span> | <span data-ttu-id="13033-127">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="13033-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="13033-128">Isso indica sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7</span><span class="sxs-lookup"><span data-stu-id="13033-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="13033-129">string</span><span class="sxs-lookup"><span data-stu-id="13033-129">string</span></span> | <span data-ttu-id="13033-130">Versão de compilação do sistema operacional em execução no computador</span><span class="sxs-lookup"><span data-stu-id="13033-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="13033-131">booliano</span><span class="sxs-lookup"><span data-stu-id="13033-131">boolean</span></span> | <span data-ttu-id="13033-132">Indicador booliano de que o computador ingressou no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="13033-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="13033-133">string</span><span class="sxs-lookup"><span data-stu-id="13033-133">string</span></span> | <span data-ttu-id="13033-134">Lista de todos os usuários que são registrados no computador no momento do evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="13033-134">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="13033-135">string</span><span class="sxs-lookup"><span data-stu-id="13033-135">string</span></span> | <span data-ttu-id="13033-136">Marca de máquina adicionada por meio do registro</span><span class="sxs-lookup"><span data-stu-id="13033-136">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="13033-137">long</span><span class="sxs-lookup"><span data-stu-id="13033-137">long</span></span> | <span data-ttu-id="13033-138">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="13033-138">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="13033-139">Para identificar eventos exclusivos, esta coluna deve ser usada em conjunto com as colunas DeviceName e timestamp</span><span class="sxs-lookup"><span data-stu-id="13033-139">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="13033-140">string</span><span class="sxs-lookup"><span data-stu-id="13033-140">string</span></span> | <span data-ttu-id="13033-141">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="13033-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="13033-142">string</span><span class="sxs-lookup"><span data-stu-id="13033-142">string</span></span> | <span data-ttu-id="13033-143">Grupo de computadores da máquina.</span><span class="sxs-lookup"><span data-stu-id="13033-143">Machine group of the machine.</span></span> <span data-ttu-id="13033-144">Esse grupo é usado pelo controle de acesso baseado em função para determinar o acesso ao computador</span><span class="sxs-lookup"><span data-stu-id="13033-144">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="13033-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="13033-145">Related topics</span></span>
- [<span data-ttu-id="13033-146">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="13033-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="13033-147">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="13033-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="13033-148">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="13033-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="13033-149">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="13033-149">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="13033-150">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="13033-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="13033-151">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="13033-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)