---
title: Tabela DeviceInfo no esquema de busca avançada
description: Saiba mais sobre o sistema operacional, o nome do computador e outras informações do computador na tabela DeviceInfo do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, machineinfo, DeviceInfo, dispositivo, computador, sistema operacional, plataforma, usuários
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
ms.openlocfilehash: 6462096a6c1b44ee11299f652a54f261d0355523
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145362"
---
# <a name="deviceinfo"></a><span data-ttu-id="b5218-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="b5218-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b5218-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b5218-105">**Applies to:**</span></span>
- <span data-ttu-id="b5218-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b5218-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="b5218-107">A tabela no esquema de busca avançada contém informações sobre computadores na organização, incluindo a versão do sistema operacional, os usuários `DeviceInfo` ativos e o nome do computador. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b5218-107">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about machines in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="b5218-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="b5218-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="b5218-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b5218-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b5218-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="b5218-110">Column name</span></span> | <span data-ttu-id="b5218-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b5218-111">Data type</span></span> | <span data-ttu-id="b5218-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b5218-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="b5218-113">datetime</span><span class="sxs-lookup"><span data-stu-id="b5218-113">datetime</span></span> | <span data-ttu-id="b5218-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="b5218-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="b5218-115">string</span><span class="sxs-lookup"><span data-stu-id="b5218-115">string</span></span> | <span data-ttu-id="b5218-116">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="b5218-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b5218-117">string</span><span class="sxs-lookup"><span data-stu-id="b5218-117">string</span></span> | <span data-ttu-id="b5218-118">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="b5218-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="b5218-119">string</span><span class="sxs-lookup"><span data-stu-id="b5218-119">string</span></span> | <span data-ttu-id="b5218-120">Versão do agente de ponto de extremidade ou sensor em execução no computador</span><span class="sxs-lookup"><span data-stu-id="b5218-120">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="b5218-121">string</span><span class="sxs-lookup"><span data-stu-id="b5218-121">string</span></span> | <span data-ttu-id="b5218-122">Endereço IP público usado pelo computador onboard para se conectar ao serviço Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b5218-122">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="b5218-123">Pode ser o endereço IP do próprio computador, um dispositivo NAT ou um proxy</span><span class="sxs-lookup"><span data-stu-id="b5218-123">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="b5218-124">string</span><span class="sxs-lookup"><span data-stu-id="b5218-124">string</span></span> | <span data-ttu-id="b5218-125">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="b5218-125">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="b5218-126">string</span><span class="sxs-lookup"><span data-stu-id="b5218-126">string</span></span> | <span data-ttu-id="b5218-127">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="b5218-127">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b5218-128">Isso indica sistemas operacionais específicos, incluindo variações dentro da mesma família, como o Windows 10 e o Windows 7</span><span class="sxs-lookup"><span data-stu-id="b5218-128">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="b5218-129">string</span><span class="sxs-lookup"><span data-stu-id="b5218-129">string</span></span> | <span data-ttu-id="b5218-130">Versão de com build do sistema operacional em execução no computador</span><span class="sxs-lookup"><span data-stu-id="b5218-130">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="b5218-131">booliano</span><span class="sxs-lookup"><span data-stu-id="b5218-131">boolean</span></span> | <span data-ttu-id="b5218-132">Indicador booleano de se o computador está ingressado no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b5218-132">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `DeviceObjectId` | <span data-ttu-id="b5218-133">string</span><span class="sxs-lookup"><span data-stu-id="b5218-133">string</span></span> | <span data-ttu-id="b5218-134">Identificador exclusivo do dispositivo no Azure AD</span><span class="sxs-lookup"><span data-stu-id="b5218-134">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="b5218-135">string</span><span class="sxs-lookup"><span data-stu-id="b5218-135">string</span></span> | <span data-ttu-id="b5218-136">Lista de todos os usuários que estão conectados no computador no momento do evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="b5218-136">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="b5218-137">string</span><span class="sxs-lookup"><span data-stu-id="b5218-137">string</span></span> | <span data-ttu-id="b5218-138">Marca de computador adicionada por meio do Registro</span><span class="sxs-lookup"><span data-stu-id="b5218-138">Machine tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="b5218-139">long</span><span class="sxs-lookup"><span data-stu-id="b5218-139">long</span></span> | <span data-ttu-id="b5218-140">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="b5218-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="b5218-141">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="b5218-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
|`AdditionalFields` | <span data-ttu-id="b5218-142">string</span><span class="sxs-lookup"><span data-stu-id="b5218-142">string</span></span> | <span data-ttu-id="b5218-143">Informações adicionais sobre o evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="b5218-143">Additional information about the event in JSON array format</span></span> |
| `OSVersion` | <span data-ttu-id="b5218-144">string</span><span class="sxs-lookup"><span data-stu-id="b5218-144">string</span></span> | <span data-ttu-id="b5218-145">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="b5218-145">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="b5218-146">string</span><span class="sxs-lookup"><span data-stu-id="b5218-146">string</span></span> | <span data-ttu-id="b5218-147">Grupo de máquinas do computador.</span><span class="sxs-lookup"><span data-stu-id="b5218-147">Machine group of the machine.</span></span> <span data-ttu-id="b5218-148">Esse grupo é usado pelo controle de acesso baseado em função para determinar o acesso ao computador</span><span class="sxs-lookup"><span data-stu-id="b5218-148">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b5218-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b5218-149">Related topics</span></span>
- [<span data-ttu-id="b5218-150">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="b5218-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b5218-151">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b5218-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b5218-152">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="b5218-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b5218-153">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="b5218-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b5218-154">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="b5218-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b5218-155">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="b5218-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
