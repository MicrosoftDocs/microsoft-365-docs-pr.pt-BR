---
title: Tabela CloudAppEvents no esquema de busca avançada
description: Saiba mais sobre eventos de aplicativos e serviços em nuvem na tabela CloudAppEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, CloudAppEvents, segurança do aplicativo em nuvem, MCAS
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087758"
---
# <a name="cloudappevents"></a><span data-ttu-id="87f07-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="87f07-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="87f07-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="87f07-105">**Applies to:**</span></span>
- <span data-ttu-id="87f07-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87f07-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="87f07-107">Atualmente disponível no modo de visualização, a `CloudAppEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre as atividades em vários aplicativos e serviços de nuvem, especificamente o Microsoft Teams e o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="87f07-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="87f07-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="87f07-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="87f07-109">Esta tabela será expandida para incluir mais atividades monitoradas pelo Microsoft Cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="87f07-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="87f07-110">Eventualmente, esta tabela incluirá a atividade de arquivo atualmente armazenada na tabela [AppFileEvents](advanced-hunting-appfileevents-table.md) .</span><span class="sxs-lookup"><span data-stu-id="87f07-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="87f07-111">A Microsoft fornecerá orientações adicionais à medida que mais dados são movidos para esta tabela.</span><span class="sxs-lookup"><span data-stu-id="87f07-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="87f07-112">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="87f07-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="87f07-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="87f07-113">Column name</span></span> | <span data-ttu-id="87f07-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="87f07-114">Data type</span></span> | <span data-ttu-id="87f07-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="87f07-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="87f07-116">datetime</span><span class="sxs-lookup"><span data-stu-id="87f07-116">datetime</span></span> | <span data-ttu-id="87f07-117">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="87f07-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="87f07-118">string</span><span class="sxs-lookup"><span data-stu-id="87f07-118">string</span></span> | <span data-ttu-id="87f07-119">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="87f07-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="87f07-120">string</span><span class="sxs-lookup"><span data-stu-id="87f07-120">string</span></span> | <span data-ttu-id="87f07-121">Aplicativo que executou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="87f07-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="87f07-122">string</span><span class="sxs-lookup"><span data-stu-id="87f07-122">string</span></span> | <span data-ttu-id="87f07-123">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="87f07-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="87f07-124">string</span><span class="sxs-lookup"><span data-stu-id="87f07-124">string</span></span> | <span data-ttu-id="87f07-125">Identificador exclusivo para a conta no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="87f07-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="87f07-126">string</span><span class="sxs-lookup"><span data-stu-id="87f07-126">string</span></span> | <span data-ttu-id="87f07-127">Nome do usuário da conta exibido no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="87f07-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="87f07-128">Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="87f07-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="87f07-129">string</span><span class="sxs-lookup"><span data-stu-id="87f07-129">string</span></span> | <span data-ttu-id="87f07-130">Indica se a atividade foi executada por um administrador</span><span class="sxs-lookup"><span data-stu-id="87f07-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="87f07-131">string</span><span class="sxs-lookup"><span data-stu-id="87f07-131">string</span></span> | <span data-ttu-id="87f07-132">Tipo de dispositivo baseado no objetivo e na funcionalidade, como "dispositivo de rede", "estação de trabalho", "servidor", "celular", "console de jogos" ou "impressora"</span><span class="sxs-lookup"><span data-stu-id="87f07-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="87f07-133">string</span><span class="sxs-lookup"><span data-stu-id="87f07-133">string</span></span> | <span data-ttu-id="87f07-134">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="87f07-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="87f07-135">Esta coluna indica sistemas operacionais específicos, incluindo variações dentro da mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="87f07-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="87f07-136">string</span><span class="sxs-lookup"><span data-stu-id="87f07-136">string</span></span> | <span data-ttu-id="87f07-137">Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="87f07-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="87f07-138">string</span><span class="sxs-lookup"><span data-stu-id="87f07-138">string</span></span> | <span data-ttu-id="87f07-139">Indica se o endereço IP pertence a um proxy anônimo conhecido</span><span class="sxs-lookup"><span data-stu-id="87f07-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="87f07-140">string</span><span class="sxs-lookup"><span data-stu-id="87f07-140">string</span></span> | <span data-ttu-id="87f07-141">Código de duas letras que indica o país onde o endereço IP do cliente está geolocalizado</span><span class="sxs-lookup"><span data-stu-id="87f07-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="87f07-142">string</span><span class="sxs-lookup"><span data-stu-id="87f07-142">string</span></span> | <span data-ttu-id="87f07-143">Cidade onde o endereço IP do cliente está geolocalizado</span><span class="sxs-lookup"><span data-stu-id="87f07-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="87f07-144">string</span><span class="sxs-lookup"><span data-stu-id="87f07-144">string</span></span> | <span data-ttu-id="87f07-145">Provedor de serviços de Internet (ISP) associado ao endereço IP</span><span class="sxs-lookup"><span data-stu-id="87f07-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="87f07-146">string</span><span class="sxs-lookup"><span data-stu-id="87f07-146">string</span></span> | <span data-ttu-id="87f07-147">Informações do agente do usuário do navegador da Web ou outro aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="87f07-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="87f07-148">string</span><span class="sxs-lookup"><span data-stu-id="87f07-148">string</span></span> | <span data-ttu-id="87f07-149">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="87f07-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="87f07-150">string</span><span class="sxs-lookup"><span data-stu-id="87f07-150">string</span></span> | <span data-ttu-id="87f07-151">Lista de objetos, como arquivos ou pastas, que estavam envolvidos na atividade registrada</span><span class="sxs-lookup"><span data-stu-id="87f07-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="87f07-152">string</span><span class="sxs-lookup"><span data-stu-id="87f07-152">string</span></span> | <span data-ttu-id="87f07-153">Nome do objeto ao qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="87f07-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="87f07-154">string</span><span class="sxs-lookup"><span data-stu-id="87f07-154">string</span></span> | <span data-ttu-id="87f07-155">Tipo de objeto, como um arquivo ou uma pasta, a ação gravada foi aplicada a</span><span class="sxs-lookup"><span data-stu-id="87f07-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="87f07-156">string</span><span class="sxs-lookup"><span data-stu-id="87f07-156">string</span></span> | <span data-ttu-id="87f07-157">Identificador exclusivo do objeto ao qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="87f07-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="87f07-158">string</span><span class="sxs-lookup"><span data-stu-id="87f07-158">string</span></span> | <span data-ttu-id="87f07-159">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="87f07-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="87f07-160">string</span><span class="sxs-lookup"><span data-stu-id="87f07-160">string</span></span> | <span data-ttu-id="87f07-161">Informações de evento bruto do aplicativo de origem ou serviço no formato JSON</span><span class="sxs-lookup"><span data-stu-id="87f07-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="87f07-162">string</span><span class="sxs-lookup"><span data-stu-id="87f07-162">string</span></span> | <span data-ttu-id="87f07-163">Informações adicionais sobre a entidade ou o evento</span><span class="sxs-lookup"><span data-stu-id="87f07-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="87f07-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="87f07-164">Related topics</span></span>
- [<span data-ttu-id="87f07-165">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="87f07-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="87f07-166">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="87f07-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="87f07-167">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="87f07-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="87f07-168">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="87f07-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="87f07-169">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="87f07-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="87f07-170">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="87f07-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
