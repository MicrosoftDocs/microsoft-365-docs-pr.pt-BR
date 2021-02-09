---
title: Tabela AppFileEvents no esquema de busca avançada
description: Saiba mais sobre eventos relacionados a arquivos associados a aplicativos e serviços de nuvem na tabela AppFileEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 8406d1f9e3d56555b1699d191933c6f9735c9574
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145482"
---
# <a name="appfileevents"></a><span data-ttu-id="69062-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="69062-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="69062-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="69062-105">**Applies to:**</span></span>
- <span data-ttu-id="69062-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69062-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="69062-107">A tabela no esquema de busca avançada contém informações sobre atividades relacionadas a arquivos em aplicativos e serviços de nuvem `AppFileEvents` monitorados pelo Microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="69062-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="69062-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="69062-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="69062-109">Para obter informações detalhadas sobre os tipos de eventos (valores) com suporte em uma tabela, use a referência de esquema interna disponível na `ActionType` central de segurança. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="69062-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="69062-110">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="69062-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="69062-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="69062-111">Column name</span></span> | <span data-ttu-id="69062-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="69062-112">Data type</span></span> | <span data-ttu-id="69062-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="69062-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="69062-114">datetime</span><span class="sxs-lookup"><span data-stu-id="69062-114">datetime</span></span> | <span data-ttu-id="69062-115">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="69062-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="69062-116">string</span><span class="sxs-lookup"><span data-stu-id="69062-116">string</span></span> | <span data-ttu-id="69062-117">Tipo de atividade que disparou o evento.</span><span class="sxs-lookup"><span data-stu-id="69062-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="69062-118">Consulte a [referência de esquema no portal para](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) obter detalhes</span><span class="sxs-lookup"><span data-stu-id="69062-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="69062-119">string</span><span class="sxs-lookup"><span data-stu-id="69062-119">string</span></span> | <span data-ttu-id="69062-120">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="69062-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="69062-121">string</span><span class="sxs-lookup"><span data-stu-id="69062-121">string</span></span> | <span data-ttu-id="69062-122">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="69062-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="69062-123">string</span><span class="sxs-lookup"><span data-stu-id="69062-123">string</span></span> | <span data-ttu-id="69062-124">Pasta que contém o arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="69062-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="69062-125">string</span><span class="sxs-lookup"><span data-stu-id="69062-125">string</span></span> | <span data-ttu-id="69062-126">Nome original do arquivo que foi renomeado como resultado da ação</span><span class="sxs-lookup"><span data-stu-id="69062-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="69062-127">string</span><span class="sxs-lookup"><span data-stu-id="69062-127">string</span></span> | <span data-ttu-id="69062-128">Pasta original que contém o arquivo antes da ação gravada ser aplicada</span><span class="sxs-lookup"><span data-stu-id="69062-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="69062-129">string</span><span class="sxs-lookup"><span data-stu-id="69062-129">string</span></span> | <span data-ttu-id="69062-130">Protocolo de rede usado</span><span class="sxs-lookup"><span data-stu-id="69062-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="69062-131">string</span><span class="sxs-lookup"><span data-stu-id="69062-131">string</span></span> | <span data-ttu-id="69062-132">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="69062-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="69062-133">string</span><span class="sxs-lookup"><span data-stu-id="69062-133">string</span></span> | <span data-ttu-id="69062-134">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="69062-134">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="69062-135">string</span><span class="sxs-lookup"><span data-stu-id="69062-135">string</span></span> | <span data-ttu-id="69062-136">Sid (Identificador de Segurança) da conta</span><span class="sxs-lookup"><span data-stu-id="69062-136">Security Identifier (SID) of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="69062-137">string</span><span class="sxs-lookup"><span data-stu-id="69062-137">string</span></span> | <span data-ttu-id="69062-138">Nome UPN da conta</span><span class="sxs-lookup"><span data-stu-id="69062-138">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="69062-139">string</span><span class="sxs-lookup"><span data-stu-id="69062-139">string</span></span> | <span data-ttu-id="69062-140">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="69062-140">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="69062-141">string</span><span class="sxs-lookup"><span data-stu-id="69062-141">string</span></span> | <span data-ttu-id="69062-142">Nome do usuário da conta exibido no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="69062-142">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="69062-143">Normalmente, uma combinação de um nome ou nome determinado, uma iniciação do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="69062-143">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="69062-144">string</span><span class="sxs-lookup"><span data-stu-id="69062-144">string</span></span> | <span data-ttu-id="69062-145">Nome de domínio totalmente qualificado (FQDN) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="69062-145">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="69062-146">string</span><span class="sxs-lookup"><span data-stu-id="69062-146">string</span></span> | <span data-ttu-id="69062-147">Tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="69062-147">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="69062-148">string</span><span class="sxs-lookup"><span data-stu-id="69062-148">string</span></span> | <span data-ttu-id="69062-149">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="69062-149">Platform of the operating system running on the device.</span></span> <span data-ttu-id="69062-150">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="69062-150">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="69062-151">string</span><span class="sxs-lookup"><span data-stu-id="69062-151">string</span></span> | <span data-ttu-id="69062-152">Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="69062-152">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="69062-153">string</span><span class="sxs-lookup"><span data-stu-id="69062-153">string</span></span> | <span data-ttu-id="69062-154">Porta TCP usada durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="69062-154">TCP port used during communication</span></span>  |
| `DestinationDeviceName` | <span data-ttu-id="69062-155">string</span><span class="sxs-lookup"><span data-stu-id="69062-155">string</span></span> | <span data-ttu-id="69062-156">Nome do dispositivo que executa o aplicativo servidor que processou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="69062-156">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="69062-157">string</span><span class="sxs-lookup"><span data-stu-id="69062-157">string</span></span> | <span data-ttu-id="69062-158">Endereço IP do dispositivo que executa o aplicativo servidor que processou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="69062-158">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="69062-159">string</span><span class="sxs-lookup"><span data-stu-id="69062-159">string</span></span> | <span data-ttu-id="69062-160">Porta de destino de comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="69062-160">Destination port of related network communications</span></span> |
| `Location` | <span data-ttu-id="69062-161">string</span><span class="sxs-lookup"><span data-stu-id="69062-161">string</span></span> | <span data-ttu-id="69062-162">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="69062-162">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="69062-163">string</span><span class="sxs-lookup"><span data-stu-id="69062-163">string</span></span> | <span data-ttu-id="69062-164">Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="69062-164">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="69062-165">long</span><span class="sxs-lookup"><span data-stu-id="69062-165">long</span></span> | <span data-ttu-id="69062-166">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="69062-166">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="69062-167">string</span><span class="sxs-lookup"><span data-stu-id="69062-167">string</span></span> | <span data-ttu-id="69062-168">Informações adicionais sobre a entidade ou evento</span><span class="sxs-lookup"><span data-stu-id="69062-168">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="69062-169">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="69062-169">Related topics</span></span>
- [<span data-ttu-id="69062-170">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="69062-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="69062-171">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="69062-171">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="69062-172">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="69062-172">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="69062-173">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="69062-173">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="69062-174">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="69062-174">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="69062-175">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="69062-175">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
