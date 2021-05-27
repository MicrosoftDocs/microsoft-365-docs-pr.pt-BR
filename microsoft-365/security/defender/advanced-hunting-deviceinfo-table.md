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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689104"
---
# <a name="deviceinfo"></a><span data-ttu-id="39304-104">DeviceInfo</span><span class="sxs-lookup"><span data-stu-id="39304-104">DeviceInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="39304-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="39304-105">**Applies to:**</span></span>
- <span data-ttu-id="39304-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39304-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="39304-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="39304-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="39304-108">A tabela no esquema de busca avançada contém informações sobre dispositivos na organização, incluindo a versão do sistema operacional, usuários `DeviceInfo` ativos e nome do computador. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="39304-108">The `DeviceInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about devices in the organization, including OS version, active users, and computer name.</span></span> <span data-ttu-id="39304-109">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="39304-109">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="39304-110">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="39304-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="39304-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="39304-111">Column name</span></span> | <span data-ttu-id="39304-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="39304-112">Data type</span></span> | <span data-ttu-id="39304-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="39304-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="39304-114">datetime</span><span class="sxs-lookup"><span data-stu-id="39304-114">datetime</span></span> | <span data-ttu-id="39304-115">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="39304-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="39304-116">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-116">string</span></span> | <span data-ttu-id="39304-117">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="39304-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="39304-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-118">string</span></span> | <span data-ttu-id="39304-119">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="39304-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ClientVersion` | <span data-ttu-id="39304-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-120">string</span></span> | <span data-ttu-id="39304-121">Versão do agente de ponto de extremidade ou sensor em execução no computador</span><span class="sxs-lookup"><span data-stu-id="39304-121">Version of the endpoint agent or sensor running on the machine</span></span> |
| `PublicIP` | <span data-ttu-id="39304-122">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-122">string</span></span> | <span data-ttu-id="39304-123">Endereço IP público usado pelo computador interno para se conectar ao serviço Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="39304-123">Public IP address used by the onboarded machine to connect to the Microsoft  Defender for Endpoint service.</span></span> <span data-ttu-id="39304-124">Esse pode ser o endereço IP do próprio computador, um dispositivo NAT ou um proxy</span><span class="sxs-lookup"><span data-stu-id="39304-124">This could be the IP address of the machine itself, a NAT device, or a proxy</span></span> |
| `OSArchitecture` | <span data-ttu-id="39304-125">string</span><span class="sxs-lookup"><span data-stu-id="39304-125">string</span></span> | <span data-ttu-id="39304-126">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="39304-126">Architecture of the operating system running on the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="39304-127">string</span><span class="sxs-lookup"><span data-stu-id="39304-127">string</span></span> | <span data-ttu-id="39304-128">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="39304-128">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="39304-129">Isso indica sistemas operacionais específicos, incluindo variações na mesma família, como Windows 10 e Windows 7</span><span class="sxs-lookup"><span data-stu-id="39304-129">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7</span></span> |
| `OSBuild` | <span data-ttu-id="39304-130">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-130">string</span></span> | <span data-ttu-id="39304-131">Versão de com build do sistema operacional em execução no computador</span><span class="sxs-lookup"><span data-stu-id="39304-131">Build version of the operating system running on the machine</span></span> |
| `IsAzureADJoined` | <span data-ttu-id="39304-132">booliano</span><span class="sxs-lookup"><span data-stu-id="39304-132">boolean</span></span> | <span data-ttu-id="39304-133">Indicador booleano de se o computador está ingressado no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="39304-133">Boolean indicator of whether machine is joined to the Azure Active Directory</span></span> |
| `AadObjectId` | <span data-ttu-id="39304-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-134">string</span></span> | <span data-ttu-id="39304-135">Identificador exclusivo do dispositivo no Azure AD</span><span class="sxs-lookup"><span data-stu-id="39304-135">Unique identifier for the device in Azure AD</span></span> |
| `LoggedOnUsers` | <span data-ttu-id="39304-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-136">string</span></span> | <span data-ttu-id="39304-137">Lista de todos os usuários que estão conectados no computador no momento do evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="39304-137">List of all users that are logged on the machine at the time of the event in JSON array format</span></span> |
| `RegistryDeviceTag` | <span data-ttu-id="39304-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-138">string</span></span> | <span data-ttu-id="39304-139">Marca de máquina adicionada por meio do Registro</span><span class="sxs-lookup"><span data-stu-id="39304-139">Machine tag added through the registry</span></span> |
| `OSVersion` | <span data-ttu-id="39304-140">string</span><span class="sxs-lookup"><span data-stu-id="39304-140">string</span></span> | <span data-ttu-id="39304-141">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="39304-141">Version of the operating system running on the machine</span></span> |
| `MachineGroup` | <span data-ttu-id="39304-142">string</span><span class="sxs-lookup"><span data-stu-id="39304-142">string</span></span> | <span data-ttu-id="39304-143">Grupo de máquinas do computador.</span><span class="sxs-lookup"><span data-stu-id="39304-143">Machine group of the machine.</span></span> <span data-ttu-id="39304-144">Esse grupo é usado pelo controle de acesso baseado em função para determinar o acesso ao computador</span><span class="sxs-lookup"><span data-stu-id="39304-144">This group is used by role-based access control to determine access to the machine</span></span> |
| `ReportId` | <span data-ttu-id="39304-145">long</span><span class="sxs-lookup"><span data-stu-id="39304-145">long</span></span> | <span data-ttu-id="39304-146">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="39304-146">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="39304-147">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp</span><span class="sxs-lookup"><span data-stu-id="39304-147">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns</span></span> |
| `OnboardingStatus` | <span data-ttu-id="39304-148">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-148">string</span></span> | <span data-ttu-id="39304-149">Indica se o dispositivo está atualmente conectado ou não ao Microsoft Defender Para Ponto de Extremidade ou se o dispositivo não tem suporte</span><span class="sxs-lookup"><span data-stu-id="39304-149">Indicates whether the device is currently onboarded or not to Microsoft Defender For Endpoint or if the device is not supported</span></span> |
|`AdditionalFields` | <span data-ttu-id="39304-150">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-150">string</span></span> | <span data-ttu-id="39304-151">Informações adicionais sobre o evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="39304-151">Additional information about the event in JSON array format</span></span> |
|`DeviceCategory` | <span data-ttu-id="39304-152">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-152">string</span></span> | <span data-ttu-id="39304-153">Classificação mais ampla que grupos determinados tipos de dispositivo nas seguintes categorias: Ponto de Extremidade, Dispositivo de rede, IoT, Desconhecido</span><span class="sxs-lookup"><span data-stu-id="39304-153">Broader classification that groups certain device types under the following categories: Endpoint, Network device, IoT, Unknown</span></span> |
|`DeviceType` | <span data-ttu-id="39304-154">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-154">string</span></span> | <span data-ttu-id="39304-155">Tipo de dispositivo com base na finalidade e funcionalidade, como dispositivo de rede, estação de trabalho, servidor, celular, console de jogos ou impressora</span><span class="sxs-lookup"><span data-stu-id="39304-155">Type of device based on purpose and functionality, such as network device, workstation, server, mobile, gaming console, or printer</span></span> |
|`DeviceSubType` | <span data-ttu-id="39304-156">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-156">string</span></span> | <span data-ttu-id="39304-157">Modificador adicional para determinados tipos de dispositivos, por exemplo, um dispositivo móvel pode ser um tablet ou um smartphone</span><span class="sxs-lookup"><span data-stu-id="39304-157">Additional modifier for certain types of devices, for example, a mobile device can be a tablet or a smartphone</span></span> |
|`Model` | <span data-ttu-id="39304-158">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-158">string</span></span> | <span data-ttu-id="39304-159">Nome do modelo ou número do produto do fornecedor ou fabricante</span><span class="sxs-lookup"><span data-stu-id="39304-159">Model name or number of the product from the vendor or manufacturer</span></span> |
|`Vendor` | <span data-ttu-id="39304-160">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-160">string</span></span> | <span data-ttu-id="39304-161">Nome do fornecedor ou fabricante do produto</span><span class="sxs-lookup"><span data-stu-id="39304-161">Name of the product vendor or manufacturer</span></span> |
|`OSDistribution` | <span data-ttu-id="39304-162">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-162">string</span></span> | <span data-ttu-id="39304-163">Distribuição da plataforma do sistema operacional, como Ubuntu ou RedHat para plataformas Linux</span><span class="sxs-lookup"><span data-stu-id="39304-163">Distribution of the OS platform, such as Ubuntu or RedHat for Linux platforms</span></span> |
|`OSVersionInfo` | <span data-ttu-id="39304-164">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-164">string</span></span> | <span data-ttu-id="39304-165">Informações adicionais sobre a versão do sistema operacional, como o nome popular, o nome do código ou o número da versão</span><span class="sxs-lookup"><span data-stu-id="39304-165">Additional information about the OS version, such as the popular name, code name, or version number</span></span> |
|`MergedDeviceIds` | <span data-ttu-id="39304-166">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-166">string</span></span> | <span data-ttu-id="39304-167">IDs de dispositivo anteriores que foram atribuídas ao mesmo dispositivo</span><span class="sxs-lookup"><span data-stu-id="39304-167">Previous device IDs that have been assigned to the same device</span></span> |
|`MergedToDeviceId` | <span data-ttu-id="39304-168">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="39304-168">string</span></span> | <span data-ttu-id="39304-169">A ID de dispositivo mais recente atribuída a um dispositivo</span><span class="sxs-lookup"><span data-stu-id="39304-169">The most recent device ID assigned to a device</span></span> |

<span data-ttu-id="39304-170">A `DeviceInfo` tabela fornece informações do dispositivo com base em pulsações, que são relatórios periódicos ou sinais de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="39304-170">The `DeviceInfo` table provides device information based on heartbeats, which are periodic reports or signals from a device.</span></span> <span data-ttu-id="39304-171">A cada quinze minutos, o dispositivo envia uma pulsação parcial que contém atributos que mudam com frequência, como `LoggedOnUsers` .</span><span class="sxs-lookup"><span data-stu-id="39304-171">Every fifteen minutes, the device sends a partial heartbeat that contains frequently changing attributes like `LoggedOnUsers`.</span></span> <span data-ttu-id="39304-172">Uma vez por dia, uma pulsação completa que contém os atributos do dispositivo é enviada.</span><span class="sxs-lookup"><span data-stu-id="39304-172">Once a day, a full heartbeat containing the device's attributes is sent.</span></span>

<span data-ttu-id="39304-173">Você pode usar a seguinte consulta de exemplo para obter o estado mais recente de um dispositivo:</span><span class="sxs-lookup"><span data-stu-id="39304-173">You can use the following sample query to get the latest state of a device:</span></span>

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a><span data-ttu-id="39304-174">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="39304-174">Related topics</span></span>
- [<span data-ttu-id="39304-175">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="39304-175">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="39304-176">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="39304-176">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="39304-177">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="39304-177">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="39304-178">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="39304-178">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="39304-179">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="39304-179">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="39304-180">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="39304-180">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
