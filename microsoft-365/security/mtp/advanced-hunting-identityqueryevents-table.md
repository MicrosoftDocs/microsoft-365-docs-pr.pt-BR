---
title: Tabela IdentityQueryEvents no esquema de busca avançada
description: Saiba mais sobre eventos de consulta do Active Directory na tabela IdentityQueryEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Search, Query, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identidades, consultas LDAP
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 3b2459d0d90f6160bcbac7efbb5c0cc0683ae8c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196804"
---
# <a name="identityqueryevents"></a><span data-ttu-id="98224-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="98224-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="98224-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="98224-105">**Applies to:**</span></span>
- <span data-ttu-id="98224-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="98224-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="98224-107">A `IdentityQueryEvents` tabela no esquema de [caça avançada](advanced-hunting-overview.md) contém informações sobre consultas realizadas em objetos do Active Directory, como usuários, grupos, dispositivos e domínios.</span><span class="sxs-lookup"><span data-stu-id="98224-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="98224-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="98224-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="98224-109">Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.</span><span class="sxs-lookup"><span data-stu-id="98224-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="98224-110">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="98224-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="98224-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="98224-111">Column name</span></span> | <span data-ttu-id="98224-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="98224-112">Data type</span></span> | <span data-ttu-id="98224-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="98224-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="98224-114">datetime</span><span class="sxs-lookup"><span data-stu-id="98224-114">datetime</span></span> | <span data-ttu-id="98224-115">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="98224-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="98224-116">string</span><span class="sxs-lookup"><span data-stu-id="98224-116">string</span></span> | <span data-ttu-id="98224-117">Tipo de atividade que disparou o evento.</span><span class="sxs-lookup"><span data-stu-id="98224-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="98224-118">Consulte a [referência de esquema no portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obter detalhes</span><span class="sxs-lookup"><span data-stu-id="98224-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="98224-119">string</span><span class="sxs-lookup"><span data-stu-id="98224-119">string</span></span> | <span data-ttu-id="98224-120">Aplicativo que executou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="98224-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="98224-121">string</span><span class="sxs-lookup"><span data-stu-id="98224-121">string</span></span> | <span data-ttu-id="98224-122">Tipo de consulta, como o QueryUser ou o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="98224-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="98224-123">string</span><span class="sxs-lookup"><span data-stu-id="98224-123">string</span></span> | <span data-ttu-id="98224-124">Nome do usuário, grupo, dispositivo, domínio ou qualquer outro tipo de entidade sendo consultado</span><span class="sxs-lookup"><span data-stu-id="98224-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="98224-125">string</span><span class="sxs-lookup"><span data-stu-id="98224-125">string</span></span> | <span data-ttu-id="98224-126">Cadeia de caracteres usada para executar a consulta</span><span class="sxs-lookup"><span data-stu-id="98224-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="98224-127">string</span><span class="sxs-lookup"><span data-stu-id="98224-127">string</span></span> | <span data-ttu-id="98224-128">Protocolo usado durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="98224-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="98224-129">string</span><span class="sxs-lookup"><span data-stu-id="98224-129">string</span></span> | <span data-ttu-id="98224-130">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="98224-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="98224-131">string</span><span class="sxs-lookup"><span data-stu-id="98224-131">string</span></span> | <span data-ttu-id="98224-132">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="98224-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="98224-133">string</span><span class="sxs-lookup"><span data-stu-id="98224-133">string</span></span> | <span data-ttu-id="98224-134">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="98224-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="98224-135">string</span><span class="sxs-lookup"><span data-stu-id="98224-135">string</span></span> | <span data-ttu-id="98224-136">Identificador de segurança (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="98224-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="98224-137">string</span><span class="sxs-lookup"><span data-stu-id="98224-137">string</span></span> | <span data-ttu-id="98224-138">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="98224-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="98224-139">string</span><span class="sxs-lookup"><span data-stu-id="98224-139">string</span></span> | <span data-ttu-id="98224-140">Nome do usuário da conta exibido no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="98224-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="98224-141">Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="98224-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="98224-142">string</span><span class="sxs-lookup"><span data-stu-id="98224-142">string</span></span> | <span data-ttu-id="98224-143">FQDN (nome de domínio totalmente qualificado) do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="98224-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="98224-144">string</span><span class="sxs-lookup"><span data-stu-id="98224-144">string</span></span> | <span data-ttu-id="98224-145">Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="98224-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="98224-146">string</span><span class="sxs-lookup"><span data-stu-id="98224-146">string</span></span> | <span data-ttu-id="98224-147">Nome do dispositivo que executa o aplicativo de servidor que processou a ação registrada</span><span class="sxs-lookup"><span data-stu-id="98224-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="98224-148">string</span><span class="sxs-lookup"><span data-stu-id="98224-148">string</span></span> | <span data-ttu-id="98224-149">Endereço IP do dispositivo que está executando o aplicativo de servidor que processou a ação registrada</span><span class="sxs-lookup"><span data-stu-id="98224-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="98224-150">string</span><span class="sxs-lookup"><span data-stu-id="98224-150">string</span></span> | <span data-ttu-id="98224-151">FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="98224-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="98224-152">string</span><span class="sxs-lookup"><span data-stu-id="98224-152">string</span></span> | <span data-ttu-id="98224-153">Nome principal do usuário (UPN) da conta à qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="98224-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="98224-154">string</span><span class="sxs-lookup"><span data-stu-id="98224-154">string</span></span> | <span data-ttu-id="98224-155">Nome para exibição da conta à qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="98224-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="98224-156">string</span><span class="sxs-lookup"><span data-stu-id="98224-156">string</span></span> | <span data-ttu-id="98224-157">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="98224-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="98224-158">long</span><span class="sxs-lookup"><span data-stu-id="98224-158">long</span></span> | <span data-ttu-id="98224-159">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="98224-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="98224-160">string</span><span class="sxs-lookup"><span data-stu-id="98224-160">string</span></span> | <span data-ttu-id="98224-161">Informações adicionais sobre a entidade ou o evento</span><span class="sxs-lookup"><span data-stu-id="98224-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="98224-162">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="98224-162">Related topics</span></span>
- [<span data-ttu-id="98224-163">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="98224-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="98224-164">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="98224-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="98224-165">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="98224-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="98224-166">Procure em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="98224-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="98224-167">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="98224-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="98224-168">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="98224-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
