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
ms.openlocfilehash: 59e9affc53398f2a1b06fbab9774e4b53e146425
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932869"
---
# <a name="appfileevents"></a><span data-ttu-id="df3b3-104">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="df3b3-104">AppFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="df3b3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="df3b3-105">**Applies to:**</span></span>
- <span data-ttu-id="df3b3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df3b3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="df3b3-107">A tabela no esquema de busca avançada contém informações sobre atividades relacionadas a arquivos em aplicativos e serviços de nuvem `AppFileEvents` monitorados pelo Microsoft Cloud App Security. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="df3b3-107">The `AppFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file-related activities in cloud apps and services monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="df3b3-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="df3b3-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="df3b3-109">Para obter informações detalhadas sobre os tipos de eventos (valores) com suporte em uma tabela, use a referência de esquema interna disponível na `ActionType` central de segurança. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="df3b3-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="df3b3-110">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="df3b3-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="df3b3-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="df3b3-111">Column name</span></span> | <span data-ttu-id="df3b3-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="df3b3-112">Data type</span></span> | <span data-ttu-id="df3b3-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="df3b3-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="df3b3-114">datetime</span><span class="sxs-lookup"><span data-stu-id="df3b3-114">datetime</span></span> | <span data-ttu-id="df3b3-115">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="df3b3-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="df3b3-116">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-116">string</span></span> | <span data-ttu-id="df3b3-117">Tipo de atividade que disparou o evento.</span><span class="sxs-lookup"><span data-stu-id="df3b3-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="df3b3-118">Consulte a [referência de esquema no portal para](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) obter detalhes</span><span class="sxs-lookup"><span data-stu-id="df3b3-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="df3b3-119">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-119">string</span></span> | <span data-ttu-id="df3b3-120">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="df3b3-120">Application that performed the recorded action</span></span> |
| `FileName` | <span data-ttu-id="df3b3-121">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-121">string</span></span> | <span data-ttu-id="df3b3-122">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="df3b3-122">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="df3b3-123">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-123">string</span></span> | <span data-ttu-id="df3b3-124">Pasta que contém o arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="df3b3-124">Folder containing the file that the recorded action was applied to</span></span> |
| `PreviousFileName` | <span data-ttu-id="df3b3-125">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-125">string</span></span> | <span data-ttu-id="df3b3-126">Nome original do arquivo que foi renomeado como resultado da ação</span><span class="sxs-lookup"><span data-stu-id="df3b3-126">Original name of the file that was renamed as a result of the action</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="df3b3-127">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-127">string</span></span> | <span data-ttu-id="df3b3-128">Pasta original que contém o arquivo antes da ação gravada ser aplicada</span><span class="sxs-lookup"><span data-stu-id="df3b3-128">Original folder containing the file before the recorded action was applied</span></span> |
| `Protocol` | <span data-ttu-id="df3b3-129">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-129">string</span></span> | <span data-ttu-id="df3b3-130">Protocolo de rede usado</span><span class="sxs-lookup"><span data-stu-id="df3b3-130">Network protocol used</span></span> |
| `AccountName` | <span data-ttu-id="df3b3-131">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-131">string</span></span> | <span data-ttu-id="df3b3-132">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="df3b3-132">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="df3b3-133">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-133">string</span></span> | <span data-ttu-id="df3b3-134">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="df3b3-134">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="df3b3-135">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-135">string</span></span> | <span data-ttu-id="df3b3-136">Nome UPN da conta</span><span class="sxs-lookup"><span data-stu-id="df3b3-136">User principal name (UPN) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="df3b3-137">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-137">string</span></span> | <span data-ttu-id="df3b3-138">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="df3b3-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="df3b3-139">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-139">string</span></span> | <span data-ttu-id="df3b3-140">Nome do usuário da conta exibido no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="df3b3-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="df3b3-141">Normalmente, uma combinação de um nome ou nome determinado, uma iniciação do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="df3b3-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="df3b3-142">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-142">string</span></span> | <span data-ttu-id="df3b3-143">Nome de domínio totalmente qualificado (FQDN) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="df3b3-143">Fully qualified domain name (FQDN) of the device</span></span> |
| `DeviceType` | <span data-ttu-id="df3b3-144">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-144">string</span></span> | <span data-ttu-id="df3b3-145">Tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="df3b3-145">Type of device</span></span> | 
| `OSPlatform` | <span data-ttu-id="df3b3-146">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-146">string</span></span> | <span data-ttu-id="df3b3-147">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="df3b3-147">Platform of the operating system running on the device.</span></span> <span data-ttu-id="df3b3-148">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="df3b3-148">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="df3b3-149">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-149">string</span></span> | <span data-ttu-id="df3b3-150">Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="df3b3-150">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="df3b3-151">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-151">string</span></span> | <span data-ttu-id="df3b3-152">Nome do dispositivo que executa o aplicativo servidor que processou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="df3b3-152">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="df3b3-153">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-153">string</span></span> | <span data-ttu-id="df3b3-154">Endereço IP do dispositivo que executa o aplicativo servidor que processou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="df3b3-154">IP address of the device running the server application that processed the recorded action</span></span> |
| `Location` | <span data-ttu-id="df3b3-155">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-155">string</span></span> | <span data-ttu-id="df3b3-156">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="df3b3-156">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="df3b3-157">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-157">string</span></span> | <span data-ttu-id="df3b3-158">Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="df3b3-158">Internet service provider (ISP) associated with the endpoint IP address</span></span> |
| `ReportId` | <span data-ttu-id="df3b3-159">long</span><span class="sxs-lookup"><span data-stu-id="df3b3-159">long</span></span> | <span data-ttu-id="df3b3-160">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="df3b3-160">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="df3b3-161">string</span><span class="sxs-lookup"><span data-stu-id="df3b3-161">string</span></span> | <span data-ttu-id="df3b3-162">Informações adicionais sobre a entidade ou evento</span><span class="sxs-lookup"><span data-stu-id="df3b3-162">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="df3b3-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="df3b3-163">Related topics</span></span>
- [<span data-ttu-id="df3b3-164">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="df3b3-164">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="df3b3-165">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="df3b3-165">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="df3b3-166">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="df3b3-166">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="df3b3-167">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="df3b3-167">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="df3b3-168">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="df3b3-168">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="df3b3-169">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="df3b3-169">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
