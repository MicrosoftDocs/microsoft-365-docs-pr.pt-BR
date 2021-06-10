---
title: Tabela CloudAppEvents no esquema de busca avançado
description: Saiba mais sobre eventos de aplicativos e serviços de nuvem na tabela CloudAppEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935864"
---
# <a name="cloudappevents"></a><span data-ttu-id="d9028-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="d9028-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d9028-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d9028-105">**Applies to:**</span></span>
- <span data-ttu-id="d9028-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9028-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="d9028-107">A tabela no esquema de busca avançado contém informações sobre atividades em vários aplicativos e serviços de nuvem `CloudAppEvents` cobertos por [](advanced-hunting-overview.md) Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="d9028-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="d9028-108">Para uma lista completa, pule para [Aplicativos e serviços abordados](#apps-and-services-covered).</span><span class="sxs-lookup"><span data-stu-id="d9028-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="d9028-109">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="d9028-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="d9028-110">Esta tabela inclui informações que costumavam estar disponíveis na `AppFileEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="d9028-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="d9028-111">A partir de 7 de março de 2021, os usuários que pesquisam atividades relacionadas a arquivos em serviços de nuvem dentro e fora dessa data devem usar a `CloudAppEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="d9028-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="d9028-112">Procure por consultas e regras de detecção personalizadas que ainda usem a tabela e `AppFileEvents` edite-as para usar a `CloudAppEvents` tabela.</span><span class="sxs-lookup"><span data-stu-id="d9028-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="d9028-113">Mais orientações sobre a conversão de consultas afetadas podem ser encontradas em [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span><span class="sxs-lookup"><span data-stu-id="d9028-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="d9028-114">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d9028-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d9028-115">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="d9028-115">Column name</span></span> | <span data-ttu-id="d9028-116">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="d9028-116">Data type</span></span> | <span data-ttu-id="d9028-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="d9028-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d9028-118">datetime</span><span class="sxs-lookup"><span data-stu-id="d9028-118">datetime</span></span> | <span data-ttu-id="d9028-119">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="d9028-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="d9028-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-120">string</span></span> | <span data-ttu-id="d9028-121">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="d9028-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="d9028-122">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-122">string</span></span> | <span data-ttu-id="d9028-123">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="d9028-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="d9028-124">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-124">string</span></span> | <span data-ttu-id="d9028-125">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="d9028-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="d9028-126">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-126">string</span></span> | <span data-ttu-id="d9028-127">Identificador exclusivo da conta no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d9028-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="d9028-128">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-128">string</span></span> | <span data-ttu-id="d9028-129">Nome do usuário da conta exibido no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="d9028-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="d9028-130">Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="d9028-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="d9028-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-131">string</span></span> | <span data-ttu-id="d9028-132">Indica se a atividade foi executada por um administrador</span><span class="sxs-lookup"><span data-stu-id="d9028-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="d9028-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-133">string</span></span> | <span data-ttu-id="d9028-134">Tipo de dispositivo com base na finalidade e funcionalidade, como "Dispositivo de rede", "Estação de Trabalho", "Servidor", "Mobile", "Console de Jogos" ou "Impressora"</span><span class="sxs-lookup"><span data-stu-id="d9028-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="d9028-135">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-135">string</span></span> | <span data-ttu-id="d9028-136">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9028-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="d9028-137">Esta coluna indica sistemas operacionais específicos, incluindo variações na mesma família, como Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="d9028-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="d9028-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-138">string</span></span> | <span data-ttu-id="d9028-139">Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="d9028-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="d9028-140">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-140">string</span></span> | <span data-ttu-id="d9028-141">Indica se o endereço IP pertence a um proxy anônimo conhecido</span><span class="sxs-lookup"><span data-stu-id="d9028-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="d9028-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-142">string</span></span> | <span data-ttu-id="d9028-143">Código de duas letras indicando o país onde o endereço IP do cliente está geolocado</span><span class="sxs-lookup"><span data-stu-id="d9028-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="d9028-144">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-144">string</span></span> | <span data-ttu-id="d9028-145">Cidade onde o endereço IP do cliente está geolocado</span><span class="sxs-lookup"><span data-stu-id="d9028-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="d9028-146">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-146">string</span></span> | <span data-ttu-id="d9028-147">Provedor de serviços de Internet (ISP) associado ao endereço IP</span><span class="sxs-lookup"><span data-stu-id="d9028-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="d9028-148">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-148">string</span></span> | <span data-ttu-id="d9028-149">Informações do agente do usuário do navegador da Web ou de outro aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="d9028-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="d9028-150">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-150">string</span></span> | <span data-ttu-id="d9028-151">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="d9028-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="d9028-152">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-152">string</span></span> | <span data-ttu-id="d9028-153">Lista de objetos, como arquivos ou pastas, que estavam envolvidos na atividade gravada</span><span class="sxs-lookup"><span data-stu-id="d9028-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="d9028-154">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-154">string</span></span> | <span data-ttu-id="d9028-155">Nome do objeto ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="d9028-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="d9028-156">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-156">string</span></span> | <span data-ttu-id="d9028-157">Tipo de objeto, como um arquivo ou uma pasta, ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="d9028-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="d9028-158">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-158">string</span></span> | <span data-ttu-id="d9028-159">Identificador exclusivo do objeto ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="d9028-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="d9028-160">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-160">string</span></span> | <span data-ttu-id="d9028-161">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="d9028-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="d9028-162">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-162">string</span></span> | <span data-ttu-id="d9028-163">Informações de evento brutos do aplicativo ou serviço de origem no formato JSON</span><span class="sxs-lookup"><span data-stu-id="d9028-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="d9028-164">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d9028-164">string</span></span> | <span data-ttu-id="d9028-165">Informações adicionais sobre a entidade ou evento</span><span class="sxs-lookup"><span data-stu-id="d9028-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="d9028-166">Aplicativos e serviços cobertos</span><span class="sxs-lookup"><span data-stu-id="d9028-166">Apps and services covered</span></span>

- <span data-ttu-id="d9028-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="d9028-167">Dropbox</span></span>
- <span data-ttu-id="d9028-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="d9028-168">Dynamics 365</span></span>
- <span data-ttu-id="d9028-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d9028-169">Exchange Online</span></span>
- <span data-ttu-id="d9028-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d9028-170">Microsoft Teams</span></span>
- <span data-ttu-id="d9028-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d9028-171">OneDrive for Business</span></span>
- <span data-ttu-id="d9028-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="d9028-172">Power Automate</span></span>
- <span data-ttu-id="d9028-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="d9028-173">Power BI</span></span>
- <span data-ttu-id="d9028-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d9028-174">SharePoint Online</span></span>
- <span data-ttu-id="d9028-175">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d9028-175">Skype for Business</span></span>
- <span data-ttu-id="d9028-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="d9028-176">Office 365</span></span>
- <span data-ttu-id="d9028-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="d9028-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d9028-178">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d9028-178">Related topics</span></span>
- [<span data-ttu-id="d9028-179">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="d9028-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d9028-180">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="d9028-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d9028-181">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="d9028-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d9028-182">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="d9028-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d9028-183">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="d9028-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d9028-184">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="d9028-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
