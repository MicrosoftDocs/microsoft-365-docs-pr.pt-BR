---
title: Tabela CloudAppEvents no esquema de busca avançada
description: Saiba mais sobre eventos de aplicativos e serviços em nuvem na tabela CloudAppEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928445"
---
# <a name="cloudappevents"></a><span data-ttu-id="4c5eb-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="4c5eb-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4c5eb-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4c5eb-105">**Applies to:**</span></span>
- <span data-ttu-id="4c5eb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c5eb-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="4c5eb-107">Disponível atualmente na visualização, a tabela no esquema de busca avançada contém informações sobre atividades em vários aplicativos e serviços de nuvem, especificamente `CloudAppEvents` Microsoft Teams e Exchange Online. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4c5eb-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="4c5eb-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="4c5eb-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="4c5eb-109">Esta tabela será expandida para incluir mais atividades monitoradas pelo Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4c5eb-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="4c5eb-110">Eventualmente, esta tabela incluirá a atividade de arquivo atualmente armazenada na [tabela AppFileEvents.](advanced-hunting-appfileevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="4c5eb-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="4c5eb-111">A Microsoft fornecerá orientações adicionais à medida que mais dados se moverem para esta tabela.</span><span class="sxs-lookup"><span data-stu-id="4c5eb-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="4c5eb-112">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="4c5eb-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4c5eb-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="4c5eb-113">Column name</span></span> | <span data-ttu-id="4c5eb-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4c5eb-114">Data type</span></span> | <span data-ttu-id="4c5eb-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="4c5eb-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4c5eb-116">datetime</span><span class="sxs-lookup"><span data-stu-id="4c5eb-116">datetime</span></span> | <span data-ttu-id="4c5eb-117">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="4c5eb-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="4c5eb-118">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-118">string</span></span> | <span data-ttu-id="4c5eb-119">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="4c5eb-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="4c5eb-120">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-120">string</span></span> | <span data-ttu-id="4c5eb-121">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="4c5eb-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="4c5eb-122">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-122">string</span></span> | <span data-ttu-id="4c5eb-123">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="4c5eb-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="4c5eb-124">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-124">string</span></span> | <span data-ttu-id="4c5eb-125">Identificador exclusivo da conta no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4c5eb-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="4c5eb-126">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-126">string</span></span> | <span data-ttu-id="4c5eb-127">Nome do usuário da conta exibido no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="4c5eb-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="4c5eb-128">Normalmente, uma combinação de um nome ou nome determinado, uma iniciação do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="4c5eb-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="4c5eb-129">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-129">string</span></span> | <span data-ttu-id="4c5eb-130">Indica se a atividade foi executada por um administrador</span><span class="sxs-lookup"><span data-stu-id="4c5eb-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="4c5eb-131">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-131">string</span></span> | <span data-ttu-id="4c5eb-132">Tipo de dispositivo com base em finalidade e funcionalidade, como "Dispositivo de rede", "Estação de trabalho", "Servidor", "Celular", "Console de jogos" ou "Impressora"</span><span class="sxs-lookup"><span data-stu-id="4c5eb-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="4c5eb-133">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-133">string</span></span> | <span data-ttu-id="4c5eb-134">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c5eb-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="4c5eb-135">Esta coluna indica sistemas operacionais específicos, incluindo variações dentro da mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="4c5eb-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="4c5eb-136">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-136">string</span></span> | <span data-ttu-id="4c5eb-137">Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="4c5eb-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="4c5eb-138">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-138">string</span></span> | <span data-ttu-id="4c5eb-139">Indica se o endereço IP pertence a um proxy anônimo conhecido</span><span class="sxs-lookup"><span data-stu-id="4c5eb-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="4c5eb-140">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-140">string</span></span> | <span data-ttu-id="4c5eb-141">Código de duas letras indicando o país onde o endereço IP do cliente está geolocalado</span><span class="sxs-lookup"><span data-stu-id="4c5eb-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="4c5eb-142">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-142">string</span></span> | <span data-ttu-id="4c5eb-143">Cidade onde o endereço IP do cliente está geolocaltado</span><span class="sxs-lookup"><span data-stu-id="4c5eb-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="4c5eb-144">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-144">string</span></span> | <span data-ttu-id="4c5eb-145">Provedor de serviços de Internet (ISP) associado ao endereço IP</span><span class="sxs-lookup"><span data-stu-id="4c5eb-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="4c5eb-146">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-146">string</span></span> | <span data-ttu-id="4c5eb-147">Informações do agente do usuário do navegador da Web ou de outro aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="4c5eb-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="4c5eb-148">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-148">string</span></span> | <span data-ttu-id="4c5eb-149">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="4c5eb-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="4c5eb-150">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-150">string</span></span> | <span data-ttu-id="4c5eb-151">Lista de objetos, como arquivos ou pastas, que estavam envolvidos na atividade gravada</span><span class="sxs-lookup"><span data-stu-id="4c5eb-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="4c5eb-152">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-152">string</span></span> | <span data-ttu-id="4c5eb-153">Nome do objeto ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="4c5eb-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="4c5eb-154">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-154">string</span></span> | <span data-ttu-id="4c5eb-155">Tipo de objeto, como um arquivo ou uma pasta, ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="4c5eb-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="4c5eb-156">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-156">string</span></span> | <span data-ttu-id="4c5eb-157">Identificador exclusivo do objeto ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="4c5eb-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="4c5eb-158">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-158">string</span></span> | <span data-ttu-id="4c5eb-159">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="4c5eb-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="4c5eb-160">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-160">string</span></span> | <span data-ttu-id="4c5eb-161">Informações de evento brutas do aplicativo ou serviço de origem no formato JSON</span><span class="sxs-lookup"><span data-stu-id="4c5eb-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="4c5eb-162">string</span><span class="sxs-lookup"><span data-stu-id="4c5eb-162">string</span></span> | <span data-ttu-id="4c5eb-163">Informações adicionais sobre a entidade ou evento</span><span class="sxs-lookup"><span data-stu-id="4c5eb-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4c5eb-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4c5eb-164">Related topics</span></span>
- [<span data-ttu-id="4c5eb-165">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="4c5eb-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4c5eb-166">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="4c5eb-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4c5eb-167">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="4c5eb-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4c5eb-168">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="4c5eb-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4c5eb-169">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="4c5eb-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4c5eb-170">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="4c5eb-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
