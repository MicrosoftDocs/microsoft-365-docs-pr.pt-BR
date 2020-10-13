---
title: Tabela AppFileEvents no esquema de busca avançada
description: Saiba mais sobre eventos relacionados a arquivos associados a serviços e aplicativos em nuvem na tabela AppFileEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, AppFileEvents, segurança do aplicativo em nuvem, MCAS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 5cab6e3fe7a3b4b74989dde360c03d58e0bad46f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430146"
---
# <a name="appfileevents"></a><span data-ttu-id="33fe6-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="33fe6-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="33fe6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="33fe6-105">**Applies to:**</span></span>
- <span data-ttu-id="33fe6-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="33fe6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="33fe6-107">A `AppFileEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre atividades relacionadas a arquivos em aplicativos de nuvem e serviços monitorados pelo Microsoft Cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="33fe6-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="33fe6-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="33fe6-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="33fe6-109">Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.</span><span class="sxs-lookup"><span data-stu-id="33fe6-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="33fe6-110">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="33fe6-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="33fe6-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="33fe6-111">Column name</span></span> | <span data-ttu-id="33fe6-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="33fe6-112">Data type</span></span> | <span data-ttu-id="33fe6-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="33fe6-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="33fe6-114">datetime</span><span class="sxs-lookup"><span data-stu-id="33fe6-114">datetime</span></span> | <span data-ttu-id="33fe6-115">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="33fe6-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="33fe6-116">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-116">string</span></span> | <span data-ttu-id="33fe6-117">Tipo de atividade que disparou o evento.</span><span class="sxs-lookup"><span data-stu-id="33fe6-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="33fe6-118">Consulte a [referência de esquema no portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obter detalhes</span><span class="sxs-lookup"><span data-stu-id="33fe6-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="33fe6-119">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-119">string</span></span> | <span data-ttu-id="33fe6-120">Aplicativo que executou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="33fe6-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="33fe6-121">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-121">string</span></span> | <span data-ttu-id="33fe6-122">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="33fe6-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="33fe6-123">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-123">string</span></span> | <span data-ttu-id="33fe6-124">Pasta que contém o arquivo para o qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="33fe6-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="33fe6-125">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-125">string</span></span> | <span data-ttu-id="33fe6-126">O nome original do arquivo que foi renomeado como resultado da ação</span><span class="sxs-lookup"><span data-stu-id="33fe6-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="33fe6-127">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-127">string</span></span> | <span data-ttu-id="33fe6-128">Pasta original contendo o arquivo antes da aplicação da ação gravada</span><span class="sxs-lookup"><span data-stu-id="33fe6-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="33fe6-129">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-129">string</span></span> | <span data-ttu-id="33fe6-130">Protocolo de rede usado</span><span class="sxs-lookup"><span data-stu-id="33fe6-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="33fe6-131">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-131">string</span></span> | <span data-ttu-id="33fe6-132">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="33fe6-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="33fe6-133">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-133">string</span></span> | <span data-ttu-id="33fe6-134">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="33fe6-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="33fe6-135">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-135">string</span></span> | <span data-ttu-id="33fe6-136">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="33fe6-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="33fe6-137">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-137">string</span></span> | <span data-ttu-id="33fe6-138">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="33fe6-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="33fe6-139">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-139">string</span></span> | <span data-ttu-id="33fe6-140">Nome do usuário da conta exibido no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="33fe6-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="33fe6-141">Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="33fe6-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="33fe6-142">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-142">string</span></span> | <span data-ttu-id="33fe6-143">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="33fe6-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="33fe6-144">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-144">string</span></span> | <span data-ttu-id="33fe6-145">Tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="33fe6-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="33fe6-146">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-146">string</span></span> | <span data-ttu-id="33fe6-147">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33fe6-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="33fe6-148">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="33fe6-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="33fe6-149">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-149">string</span></span> | <span data-ttu-id="33fe6-150">Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="33fe6-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="33fe6-151">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-151">string</span></span> | <span data-ttu-id="33fe6-152">Nome do dispositivo que executa o aplicativo de servidor que processou a ação registrada</span><span class="sxs-lookup"><span data-stu-id="33fe6-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="33fe6-153">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-153">string</span></span> | <span data-ttu-id="33fe6-154">Endereço IP do dispositivo que está executando o aplicativo de servidor que processou a ação registrada</span><span class="sxs-lookup"><span data-stu-id="33fe6-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="33fe6-155">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-155">string</span></span> | <span data-ttu-id="33fe6-156">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="33fe6-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="33fe6-157">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-157">string</span></span> | <span data-ttu-id="33fe6-158">Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="33fe6-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="33fe6-159">long</span><span class="sxs-lookup"><span data-stu-id="33fe6-159">long</span></span> | <span data-ttu-id="33fe6-160">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="33fe6-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="33fe6-161">string</span><span class="sxs-lookup"><span data-stu-id="33fe6-161">string</span></span> | <span data-ttu-id="33fe6-162">Informações adicionais sobre a entidade ou o evento</span><span class="sxs-lookup"><span data-stu-id="33fe6-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="33fe6-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="33fe6-163">Related topics</span></span>
- [<span data-ttu-id="33fe6-164">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="33fe6-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="33fe6-165">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="33fe6-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="33fe6-166">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="33fe6-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="33fe6-167">Procure em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="33fe6-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="33fe6-168">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="33fe6-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="33fe6-169">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="33fe6-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
