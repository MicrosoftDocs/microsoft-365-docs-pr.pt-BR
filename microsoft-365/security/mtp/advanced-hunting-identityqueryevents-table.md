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
ms.openlocfilehash: cf2038a15242139817eb073ec2a6408905824123
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649314"
---
# <a name="identityqueryevents"></a><span data-ttu-id="29e6a-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="29e6a-104">IdentityQueryEvents</span></span>

<span data-ttu-id="29e6a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="29e6a-105">**Applies to:**</span></span>
- <span data-ttu-id="29e6a-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="29e6a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="29e6a-107">A `IdentityQueryEvents` tabela no esquema de [caça avançada](advanced-hunting-overview.md) contém informações sobre consultas realizadas em objetos do Active Directory, como usuários, grupos, dispositivos e domínios.</span><span class="sxs-lookup"><span data-stu-id="29e6a-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="29e6a-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="29e6a-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="29e6a-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="29e6a-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="29e6a-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="29e6a-110">Column name</span></span> | <span data-ttu-id="29e6a-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="29e6a-111">Data type</span></span> | <span data-ttu-id="29e6a-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="29e6a-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="29e6a-113">datetime</span><span class="sxs-lookup"><span data-stu-id="29e6a-113">datetime</span></span> | <span data-ttu-id="29e6a-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="29e6a-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="29e6a-115">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-115">string</span></span> | <span data-ttu-id="29e6a-116">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="29e6a-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="29e6a-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-117">string</span></span> | <span data-ttu-id="29e6a-118">Aplicativo que executou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="29e6a-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="29e6a-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-119">string</span></span> | <span data-ttu-id="29e6a-120">Tipo de consulta, como o QueryUser ou o EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="29e6a-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="29e6a-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-121">string</span></span> | <span data-ttu-id="29e6a-122">Nome do usuário, grupo, dispositivo, domínio ou qualquer outro tipo de entidade sendo consultado</span><span class="sxs-lookup"><span data-stu-id="29e6a-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="29e6a-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-123">string</span></span> | <span data-ttu-id="29e6a-124">Cadeia de caracteres usada para executar a consulta</span><span class="sxs-lookup"><span data-stu-id="29e6a-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="29e6a-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-125">string</span></span> | <span data-ttu-id="29e6a-126">Protocolo usado durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="29e6a-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="29e6a-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-127">string</span></span> | <span data-ttu-id="29e6a-128">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="29e6a-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="29e6a-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-129">string</span></span> | <span data-ttu-id="29e6a-130">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="29e6a-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="29e6a-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-131">string</span></span> | <span data-ttu-id="29e6a-132">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="29e6a-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="29e6a-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-133">string</span></span> | <span data-ttu-id="29e6a-134">Identificador de segurança (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="29e6a-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="29e6a-135">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-135">string</span></span> | <span data-ttu-id="29e6a-136">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="29e6a-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="29e6a-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-137">string</span></span> | <span data-ttu-id="29e6a-138">Nome do usuário da conta exibido no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="29e6a-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="29e6a-139">Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="29e6a-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="29e6a-140">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-140">string</span></span> | <span data-ttu-id="29e6a-141">FQDN (nome de domínio totalmente qualificado) do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="29e6a-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="29e6a-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-142">string</span></span> | <span data-ttu-id="29e6a-143">Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="29e6a-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="29e6a-144">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-144">string</span></span> | <span data-ttu-id="29e6a-145">Nome do dispositivo que executa o aplicativo de servidor que processou a ação registrada</span><span class="sxs-lookup"><span data-stu-id="29e6a-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="29e6a-146">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-146">string</span></span> | <span data-ttu-id="29e6a-147">Endereço IP do dispositivo que está executando o aplicativo de servidor que processou a ação registrada</span><span class="sxs-lookup"><span data-stu-id="29e6a-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="29e6a-148">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-148">string</span></span> | <span data-ttu-id="29e6a-149">FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="29e6a-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="29e6a-150">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-150">string</span></span> | <span data-ttu-id="29e6a-151">Nome principal do usuário (UPN) da conta à qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="29e6a-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="29e6a-152">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-152">string</span></span> | <span data-ttu-id="29e6a-153">Nome para exibição da conta à qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="29e6a-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="29e6a-154">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-154">string</span></span> | <span data-ttu-id="29e6a-155">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="29e6a-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="29e6a-156">long</span><span class="sxs-lookup"><span data-stu-id="29e6a-156">long</span></span> | <span data-ttu-id="29e6a-157">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="29e6a-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="29e6a-158">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29e6a-158">string</span></span> | <span data-ttu-id="29e6a-159">Informações adicionais sobre a entidade ou o evento</span><span class="sxs-lookup"><span data-stu-id="29e6a-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="29e6a-160">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="29e6a-160">Related topics</span></span>
- [<span data-ttu-id="29e6a-161">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="29e6a-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="29e6a-162">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="29e6a-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="29e6a-163">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="29e6a-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="29e6a-164">Procurar por dispositivos, emails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="29e6a-164">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="29e6a-165">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="29e6a-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="29e6a-166">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="29e6a-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
