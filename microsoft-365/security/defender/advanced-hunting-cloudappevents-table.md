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
ms.openlocfilehash: 83b9eec37648ba48aa8e6931e836e8a5e22458c8
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51760021"
---
# <a name="cloudappevents"></a><span data-ttu-id="d4a89-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="d4a89-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d4a89-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d4a89-105">**Applies to:**</span></span>
- <span data-ttu-id="d4a89-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4a89-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="d4a89-107">A tabela no esquema de busca avançado contém informações sobre atividades em vários aplicativos e serviços de nuvem `CloudAppEvents` cobertos pelo Microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d4a89-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="d4a89-108">Para uma lista completa, pule para [Aplicativos e serviços abordados](#apps-and-services-covered).</span><span class="sxs-lookup"><span data-stu-id="d4a89-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="d4a89-109">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="d4a89-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="d4a89-110">Esta tabela inclui informações que costumavam estar disponíveis na `AppFileEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="d4a89-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="d4a89-111">A partir de 7 de março de 2021, os usuários que pesquisam atividades relacionadas a arquivos em serviços de nuvem dentro e fora dessa data devem usar a `CloudAppEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="d4a89-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="d4a89-112">Procure por consultas e regras de detecção personalizadas que ainda usem a tabela e `AppFileEvents` edite-as para usar a `CloudAppEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="d4a89-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="d4a89-113">Mais orientações sobre a conversão de consultas afetadas podem ser encontradas em [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span><span class="sxs-lookup"><span data-stu-id="d4a89-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="d4a89-114">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d4a89-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d4a89-115">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="d4a89-115">Column name</span></span> | <span data-ttu-id="d4a89-116">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="d4a89-116">Data type</span></span> | <span data-ttu-id="d4a89-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4a89-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d4a89-118">datetime</span><span class="sxs-lookup"><span data-stu-id="d4a89-118">datetime</span></span> | <span data-ttu-id="d4a89-119">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="d4a89-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="d4a89-120">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-120">string</span></span> | <span data-ttu-id="d4a89-121">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="d4a89-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="d4a89-122">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-122">string</span></span> | <span data-ttu-id="d4a89-123">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="d4a89-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="d4a89-124">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-124">string</span></span> | <span data-ttu-id="d4a89-125">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d4a89-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="d4a89-126">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-126">string</span></span> | <span data-ttu-id="d4a89-127">Identificador exclusivo da conta no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d4a89-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="d4a89-128">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-128">string</span></span> | <span data-ttu-id="d4a89-129">Nome do usuário da conta exibido no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="d4a89-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="d4a89-130">Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="d4a89-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="d4a89-131">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-131">string</span></span> | <span data-ttu-id="d4a89-132">Indica se a atividade foi executada por um administrador</span><span class="sxs-lookup"><span data-stu-id="d4a89-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="d4a89-133">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-133">string</span></span> | <span data-ttu-id="d4a89-134">Tipo de dispositivo com base na finalidade e funcionalidade, como "Dispositivo de rede", "Estação de Trabalho", "Servidor", "Mobile", "Console de Jogos" ou "Impressora"</span><span class="sxs-lookup"><span data-stu-id="d4a89-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="d4a89-135">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-135">string</span></span> | <span data-ttu-id="d4a89-136">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4a89-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="d4a89-137">Esta coluna indica sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d4a89-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="d4a89-138">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-138">string</span></span> | <span data-ttu-id="d4a89-139">Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="d4a89-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="d4a89-140">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-140">string</span></span> | <span data-ttu-id="d4a89-141">Indica se o endereço IP pertence a um proxy anônimo conhecido</span><span class="sxs-lookup"><span data-stu-id="d4a89-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="d4a89-142">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-142">string</span></span> | <span data-ttu-id="d4a89-143">Código de duas letras indicando o país onde o endereço IP do cliente está geolocado</span><span class="sxs-lookup"><span data-stu-id="d4a89-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="d4a89-144">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-144">string</span></span> | <span data-ttu-id="d4a89-145">Cidade onde o endereço IP do cliente está geolocado</span><span class="sxs-lookup"><span data-stu-id="d4a89-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="d4a89-146">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-146">string</span></span> | <span data-ttu-id="d4a89-147">Provedor de serviços de Internet (ISP) associado ao endereço IP</span><span class="sxs-lookup"><span data-stu-id="d4a89-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="d4a89-148">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-148">string</span></span> | <span data-ttu-id="d4a89-149">Informações do agente do usuário do navegador da Web ou de outro aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="d4a89-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="d4a89-150">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-150">string</span></span> | <span data-ttu-id="d4a89-151">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="d4a89-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="d4a89-152">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-152">string</span></span> | <span data-ttu-id="d4a89-153">Lista de objetos, como arquivos ou pastas, que estavam envolvidos na atividade gravada</span><span class="sxs-lookup"><span data-stu-id="d4a89-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="d4a89-154">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-154">string</span></span> | <span data-ttu-id="d4a89-155">Nome do objeto ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="d4a89-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="d4a89-156">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-156">string</span></span> | <span data-ttu-id="d4a89-157">Tipo de objeto, como um arquivo ou uma pasta, ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="d4a89-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="d4a89-158">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-158">string</span></span> | <span data-ttu-id="d4a89-159">Identificador exclusivo do objeto ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="d4a89-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="d4a89-160">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-160">string</span></span> | <span data-ttu-id="d4a89-161">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="d4a89-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="d4a89-162">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-162">string</span></span> | <span data-ttu-id="d4a89-163">Informações de evento brutos do aplicativo ou serviço de origem no formato JSON</span><span class="sxs-lookup"><span data-stu-id="d4a89-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="d4a89-164">string</span><span class="sxs-lookup"><span data-stu-id="d4a89-164">string</span></span> | <span data-ttu-id="d4a89-165">Informações adicionais sobre a entidade ou evento</span><span class="sxs-lookup"><span data-stu-id="d4a89-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="d4a89-166">Aplicativos e serviços cobertos</span><span class="sxs-lookup"><span data-stu-id="d4a89-166">Apps and services covered</span></span>

- <span data-ttu-id="d4a89-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="d4a89-167">Dropbox</span></span>
- <span data-ttu-id="d4a89-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d4a89-168">Dynamics 365</span></span>
- <span data-ttu-id="d4a89-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d4a89-169">Exchange Online</span></span>
- <span data-ttu-id="d4a89-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d4a89-170">Microsoft Teams</span></span>
- <span data-ttu-id="d4a89-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d4a89-171">OneDrive for Business</span></span>
- <span data-ttu-id="d4a89-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="d4a89-172">Power Automate</span></span>
- <span data-ttu-id="d4a89-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="d4a89-173">Power BI</span></span>
- <span data-ttu-id="d4a89-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d4a89-174">SharePoint Online</span></span>
- <span data-ttu-id="d4a89-175">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d4a89-175">Skype for Business</span></span>
- <span data-ttu-id="d4a89-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="d4a89-176">Office 365</span></span>
- <span data-ttu-id="d4a89-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="d4a89-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d4a89-178">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d4a89-178">Related topics</span></span>
- [<span data-ttu-id="d4a89-179">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="d4a89-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d4a89-180">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="d4a89-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d4a89-181">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="d4a89-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d4a89-182">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="d4a89-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d4a89-183">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="d4a89-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d4a89-184">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="d4a89-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
