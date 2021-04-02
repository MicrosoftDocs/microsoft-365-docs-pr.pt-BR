---
title: Tabela CloudAppEvents no esquema de busca avançado
description: Saiba mais sobre eventos de aplicativos e serviços de nuvem na tabela CloudAppEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 2aa592e70bce7bb469f851bedc542ee58cac0037
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498672"
---
# <a name="cloudappevents"></a><span data-ttu-id="fe9ae-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="fe9ae-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fe9ae-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="fe9ae-105">**Applies to:**</span></span>
- <span data-ttu-id="fe9ae-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe9ae-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="fe9ae-107">A tabela no esquema de busca avançada contém informações sobre atividades em vários aplicativos e serviços de nuvem cobertos pelo Microsoft Cloud App Security, especificamente `CloudAppEvents` Dropbox, Exchange Online, OneDrive, Microsoft Teams e SharePoint. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="fe9ae-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security, specifically Dropbox, Exchange Online, OneDrive, Microsoft Teams, and SharePoint.</span></span> <span data-ttu-id="fe9ae-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-108">Use this reference to construct queries that return information from this table.</span></span>

>[!IMPORTANT]
><span data-ttu-id="fe9ae-109">Esta tabela inclui informações que costumavam estar disponíveis na `AppFileEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-109">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="fe9ae-110">A partir de 7 de março de 2021, os usuários que pesquisam atividades relacionadas a arquivos em serviços de nuvem dentro e fora dessa data devem usar a `CloudAppEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-110">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="fe9ae-111">Procure por consultas e regras de detecção personalizadas que ainda usem a tabela e `AppFileEvents` edite-as para usar a `CloudAppEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-111">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="fe9ae-112">Mais orientações sobre a conversão de consultas afetadas podem ser encontradas em [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span><span class="sxs-lookup"><span data-stu-id="fe9ae-112">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="fe9ae-113">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="fe9ae-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="fe9ae-114">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="fe9ae-114">Column name</span></span> | <span data-ttu-id="fe9ae-115">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="fe9ae-115">Data type</span></span> | <span data-ttu-id="fe9ae-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe9ae-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="fe9ae-117">datetime</span><span class="sxs-lookup"><span data-stu-id="fe9ae-117">datetime</span></span> | <span data-ttu-id="fe9ae-118">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="fe9ae-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="fe9ae-119">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-119">string</span></span> | <span data-ttu-id="fe9ae-120">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="fe9ae-120">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="fe9ae-121">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-121">string</span></span> | <span data-ttu-id="fe9ae-122">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="fe9ae-122">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="fe9ae-123">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-123">string</span></span> | <span data-ttu-id="fe9ae-124">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="fe9ae-124">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="fe9ae-125">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-125">string</span></span> | <span data-ttu-id="fe9ae-126">Identificador exclusivo da conta no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fe9ae-126">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="fe9ae-127">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-127">string</span></span> | <span data-ttu-id="fe9ae-128">Nome do usuário da conta exibido no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-128">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="fe9ae-129">Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-129">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="fe9ae-130">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-130">string</span></span> | <span data-ttu-id="fe9ae-131">Indica se a atividade foi executada por um administrador</span><span class="sxs-lookup"><span data-stu-id="fe9ae-131">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="fe9ae-132">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-132">string</span></span> | <span data-ttu-id="fe9ae-133">Tipo de dispositivo com base na finalidade e funcionalidade, como "Dispositivo de rede", "Estação de Trabalho", "Servidor", "Mobile", "Console de Jogos" ou "Impressora"</span><span class="sxs-lookup"><span data-stu-id="fe9ae-133">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="fe9ae-134">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-134">string</span></span> | <span data-ttu-id="fe9ae-135">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-135">Platform of the operating system running on the device.</span></span> <span data-ttu-id="fe9ae-136">Esta coluna indica sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="fe9ae-136">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="fe9ae-137">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-137">string</span></span> | <span data-ttu-id="fe9ae-138">Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="fe9ae-138">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="fe9ae-139">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-139">string</span></span> | <span data-ttu-id="fe9ae-140">Indica se o endereço IP pertence a um proxy anônimo conhecido</span><span class="sxs-lookup"><span data-stu-id="fe9ae-140">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="fe9ae-141">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-141">string</span></span> | <span data-ttu-id="fe9ae-142">Código de duas letras indicando o país onde o endereço IP do cliente está geolocado</span><span class="sxs-lookup"><span data-stu-id="fe9ae-142">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="fe9ae-143">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-143">string</span></span> | <span data-ttu-id="fe9ae-144">Cidade onde o endereço IP do cliente está geolocado</span><span class="sxs-lookup"><span data-stu-id="fe9ae-144">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="fe9ae-145">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-145">string</span></span> | <span data-ttu-id="fe9ae-146">Provedor de serviços de Internet (ISP) associado ao endereço IP</span><span class="sxs-lookup"><span data-stu-id="fe9ae-146">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="fe9ae-147">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-147">string</span></span> | <span data-ttu-id="fe9ae-148">Informações do agente do usuário do navegador da Web ou de outro aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="fe9ae-148">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="fe9ae-149">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-149">string</span></span> | <span data-ttu-id="fe9ae-150">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="fe9ae-150">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="fe9ae-151">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-151">string</span></span> | <span data-ttu-id="fe9ae-152">Lista de objetos, como arquivos ou pastas, que estavam envolvidos na atividade gravada</span><span class="sxs-lookup"><span data-stu-id="fe9ae-152">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="fe9ae-153">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-153">string</span></span> | <span data-ttu-id="fe9ae-154">Nome do objeto ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="fe9ae-154">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="fe9ae-155">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-155">string</span></span> | <span data-ttu-id="fe9ae-156">Tipo de objeto, como um arquivo ou uma pasta, ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="fe9ae-156">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="fe9ae-157">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-157">string</span></span> | <span data-ttu-id="fe9ae-158">Identificador exclusivo do objeto ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="fe9ae-158">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="fe9ae-159">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-159">string</span></span> | <span data-ttu-id="fe9ae-160">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="fe9ae-160">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="fe9ae-161">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-161">string</span></span> | <span data-ttu-id="fe9ae-162">Informações de evento brutos do aplicativo ou serviço de origem no formato JSON</span><span class="sxs-lookup"><span data-stu-id="fe9ae-162">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="fe9ae-163">string</span><span class="sxs-lookup"><span data-stu-id="fe9ae-163">string</span></span> | <span data-ttu-id="fe9ae-164">Informações adicionais sobre a entidade ou evento</span><span class="sxs-lookup"><span data-stu-id="fe9ae-164">Additional information about the entity or event</span></span> |


## <a name="related-topics"></a><span data-ttu-id="fe9ae-165">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fe9ae-165">Related topics</span></span>
- [<span data-ttu-id="fe9ae-166">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="fe9ae-166">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fe9ae-167">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="fe9ae-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fe9ae-168">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="fe9ae-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fe9ae-169">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="fe9ae-169">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fe9ae-170">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="fe9ae-170">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fe9ae-171">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="fe9ae-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
