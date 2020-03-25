---
title: Tabela IdentityQueryEvents no esquema de busca avançada
description: Saiba mais sobre eventos de consulta do Active Directory na tabela IdentityQueryEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identidades, consultas LDAP
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
ms.openlocfilehash: b2fc94d6ac6606c97b4824bc556b7299a2bd8ec7
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929080"
---
# <a name="identityqueryevents"></a><span data-ttu-id="316df-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="316df-104">IdentityQueryEvents</span></span>

<span data-ttu-id="316df-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="316df-105">**Applies to:**</span></span>
- <span data-ttu-id="316df-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="316df-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="316df-107">A `IdentityQueryEvents` tabela no esquema de [caça avançada](advanced-hunting-overview.md) contém informações sobre consultas realizadas em objetos do Active Directory, como usuários, grupos, dispositivos e domínios.</span><span class="sxs-lookup"><span data-stu-id="316df-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="316df-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="316df-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="316df-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="316df-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="316df-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="316df-110">Column name</span></span> | <span data-ttu-id="316df-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="316df-111">Data type</span></span> | <span data-ttu-id="316df-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="316df-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="316df-113">datetime</span><span class="sxs-lookup"><span data-stu-id="316df-113">datetime</span></span> | <span data-ttu-id="316df-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="316df-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="316df-115">string</span><span class="sxs-lookup"><span data-stu-id="316df-115">string</span></span> | <span data-ttu-id="316df-116">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="316df-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="316df-117">string</span><span class="sxs-lookup"><span data-stu-id="316df-117">string</span></span> | <span data-ttu-id="316df-118">Aplicativo que executou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="316df-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="316df-119">string</span><span class="sxs-lookup"><span data-stu-id="316df-119">string</span></span> | <span data-ttu-id="316df-120">Tipo de consulta: QueryUser ou EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="316df-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="316df-121">string</span><span class="sxs-lookup"><span data-stu-id="316df-121">string</span></span> | <span data-ttu-id="316df-122">Nome do usuário, grupo, dispositivo, domínio ou qualquer outro tipo de entidade sendo consultado</span><span class="sxs-lookup"><span data-stu-id="316df-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="316df-123">string</span><span class="sxs-lookup"><span data-stu-id="316df-123">string</span></span> | <span data-ttu-id="316df-124">Protocolo usado durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="316df-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="316df-125">string</span><span class="sxs-lookup"><span data-stu-id="316df-125">string</span></span> | <span data-ttu-id="316df-126">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="316df-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="316df-127">string</span><span class="sxs-lookup"><span data-stu-id="316df-127">string</span></span> | <span data-ttu-id="316df-128">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="316df-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="316df-129">string</span><span class="sxs-lookup"><span data-stu-id="316df-129">string</span></span> | <span data-ttu-id="316df-130">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="316df-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="316df-131">string</span><span class="sxs-lookup"><span data-stu-id="316df-131">string</span></span> | <span data-ttu-id="316df-132">Identificador de segurança (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="316df-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="316df-133">string</span><span class="sxs-lookup"><span data-stu-id="316df-133">string</span></span> | <span data-ttu-id="316df-134">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="316df-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="316df-135">string</span><span class="sxs-lookup"><span data-stu-id="316df-135">string</span></span> | <span data-ttu-id="316df-136">Nome do usuário da conta exibido no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="316df-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="316df-137">Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="316df-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="316df-138">string</span><span class="sxs-lookup"><span data-stu-id="316df-138">string</span></span> | <span data-ttu-id="316df-139">FQDN (nome de domínio totalmente qualificado) do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="316df-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="316df-140">string</span><span class="sxs-lookup"><span data-stu-id="316df-140">string</span></span> | <span data-ttu-id="316df-141">Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="316df-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="316df-142">string</span><span class="sxs-lookup"><span data-stu-id="316df-142">string</span></span> | <span data-ttu-id="316df-143">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="316df-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="316df-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="316df-144">Related topics</span></span>
- [<span data-ttu-id="316df-145">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="316df-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="316df-146">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="316df-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="316df-147">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="316df-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="316df-148">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="316df-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="316df-149">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="316df-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="316df-150">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="316df-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
