---
title: Tabela DeviceInfo no esquema de busca avançado
description: Saiba mais sobre o sistema operacional, o nome do computador e outras informações de dispositivo na tabela DeviceInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, deviceinfo, dispositivo, sistema operacional, plataforma, usuários, DeviceInfo
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
ms.openlocfilehash: e86cba39663e96beffc00aa94d6cbcdf7a6e1e42
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054111"
---
# <a name="deviceinfo"></a><span data-ttu-id="6f237-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="6f237-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f237-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6f237-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f237-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6f237-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="6f237-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6f237-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6f237-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6f237-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="6f237-109">A tabela no esquema de busca avançada contém informações sobre dispositivos na organização, incluindo sua versão do sistema operacional, usuários `DeviceInfo` ativos e nome do computador. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f237-109">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including their OS version, active users, and computer name.</span></span> <span data-ttu-id="6f237-110">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="6f237-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="6f237-111">Para obter informações sobre outras tabelas no esquema de busca avançado, consulte [a referência avançada do esquema de busca](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="6f237-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="6f237-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="6f237-112">Column name</span></span> | <span data-ttu-id="6f237-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="6f237-113">Data type</span></span> | <span data-ttu-id="6f237-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="6f237-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6f237-115">datetime</span><span class="sxs-lookup"><span data-stu-id="6f237-115">datetime</span></span> | <span data-ttu-id="6f237-116">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="6f237-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="6f237-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-117">string</span></span> | <span data-ttu-id="6f237-118">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="6f237-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6f237-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-119">string</span></span> | <span data-ttu-id="6f237-120">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f237-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ClientVersion` | <span data-ttu-id="6f237-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-121">string</span></span> | <span data-ttu-id="6f237-122">Versão do agente de ponto de extremidade ou sensor em execução no dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f237-122">Version of the endpoint agent or sensor running on the device</span></span> |
| `PublicIP` | <span data-ttu-id="6f237-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-123">string</span></span> | <span data-ttu-id="6f237-124">Endereço IP público usado pelo dispositivo interno para se conectar ao serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6f237-124">Public IP address used by the onboarded device to connect to the Defender for Endpoint service.</span></span> <span data-ttu-id="6f237-125">Esse pode ser o endereço IP do próprio dispositivo, um dispositivo NAT ou um proxy</span><span class="sxs-lookup"><span data-stu-id="6f237-125">This could be the IP address of the device itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="6f237-126">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-126">string</span></span> | <span data-ttu-id="6f237-127">Arquitetura do sistema operacional em execução no dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f237-127">Architecture of the operating system running on the device</span></span> |
| `OSPlatform` | <span data-ttu-id="6f237-128">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-128">string</span></span> | <span data-ttu-id="6f237-129">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f237-129">Platform of the operating system running on the device.</span></span> <span data-ttu-id="6f237-130">Isso indica sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7</span><span class="sxs-lookup"><span data-stu-id="6f237-130">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="6f237-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-131">string</span></span> | <span data-ttu-id="6f237-132">Versão de com build do sistema operacional em execução no dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f237-132">Build version of the operating system running on the device</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="6f237-133">booliano</span><span class="sxs-lookup"><span data-stu-id="6f237-133">boolean</span></span> | <span data-ttu-id="6f237-134">Indicador booleano de se o dispositivo está ingressado no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6f237-134">Boolean indicator of whether device is joined to the Azure Active Directory</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="6f237-135">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-135">string</span></span> | <span data-ttu-id="6f237-136">Lista de todos os usuários que estão conectados no dispositivo no momento do evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="6f237-136">List of all users that are logged on the device at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="6f237-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-137">string</span></span> | <span data-ttu-id="6f237-138">Marca de dispositivo adicionada por meio do Registro</span><span class="sxs-lookup"><span data-stu-id="6f237-138">Device tag added through the registry</span></span> |
| `ReportId` | <span data-ttu-id="6f237-139">long</span><span class="sxs-lookup"><span data-stu-id="6f237-139">long</span></span> | <span data-ttu-id="6f237-140">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="6f237-140">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6f237-141">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="6f237-141">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OSVersion` | <span data-ttu-id="6f237-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-142">string</span></span> | <span data-ttu-id="6f237-143">Versão do sistema operacional em execução no dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f237-143">Version of the operating system running on the device</span></span> |
| `MachineGroup` | <span data-ttu-id="6f237-144">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6f237-144">string</span></span> | <span data-ttu-id="6f237-145">Grupo de máquinas do computador.</span><span class="sxs-lookup"><span data-stu-id="6f237-145">Machine group of the machine.</span></span> <span data-ttu-id="6f237-146">Esse grupo é usado pelo controle de acesso baseado em função para determinar o acesso ao computador</span><span class="sxs-lookup"><span data-stu-id="6f237-146">This group is used by role-based access control to determine access to the machine</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6f237-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6f237-147">Related topics</span></span>
- [<span data-ttu-id="6f237-148">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="6f237-148">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6f237-149">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="6f237-149">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6f237-150">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="6f237-150">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
