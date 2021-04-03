---
title: Tabela IdentityQueryEvents no esquema de busca avançado
description: Saiba mais sobre eventos de consulta do Active Directory na tabela IdentityQueryEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identidades, consultas LDAP
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
ms.openlocfilehash: 40383524ffe26326800369570856499d149e31c3
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500389"
---
# <a name="identityqueryevents"></a><span data-ttu-id="132a1-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="132a1-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="132a1-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="132a1-105">**Applies to:**</span></span>
- <span data-ttu-id="132a1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="132a1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="132a1-107">A tabela no esquema de busca avançada contém informações sobre consultas realizadas em objetos do Active Directory, como `IdentityQueryEvents` usuários, grupos, dispositivos e domínios. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="132a1-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="132a1-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="132a1-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="132a1-109">Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.</span><span class="sxs-lookup"><span data-stu-id="132a1-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="132a1-110">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="132a1-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="132a1-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="132a1-111">Column name</span></span> | <span data-ttu-id="132a1-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="132a1-112">Data type</span></span> | <span data-ttu-id="132a1-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="132a1-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="132a1-114">datetime</span><span class="sxs-lookup"><span data-stu-id="132a1-114">datetime</span></span> | <span data-ttu-id="132a1-115">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="132a1-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="132a1-116">string</span><span class="sxs-lookup"><span data-stu-id="132a1-116">string</span></span> | <span data-ttu-id="132a1-117">Tipo de atividade que disparou o evento.</span><span class="sxs-lookup"><span data-stu-id="132a1-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="132a1-118">Consulte a [referência de esquema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) no portal para obter detalhes</span><span class="sxs-lookup"><span data-stu-id="132a1-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="132a1-119">string</span><span class="sxs-lookup"><span data-stu-id="132a1-119">string</span></span> | <span data-ttu-id="132a1-120">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="132a1-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="132a1-121">string</span><span class="sxs-lookup"><span data-stu-id="132a1-121">string</span></span> | <span data-ttu-id="132a1-122">Tipo de consulta, como QueryGroup, QueryUser ou EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="132a1-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="132a1-123">string</span><span class="sxs-lookup"><span data-stu-id="132a1-123">string</span></span> | <span data-ttu-id="132a1-124">Nome do usuário, grupo, dispositivo, domínio ou qualquer outro tipo de entidade que está sendo consultado</span><span class="sxs-lookup"><span data-stu-id="132a1-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="132a1-125">string</span><span class="sxs-lookup"><span data-stu-id="132a1-125">string</span></span> | <span data-ttu-id="132a1-126">Cadeia de caracteres usada para executar a consulta</span><span class="sxs-lookup"><span data-stu-id="132a1-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="132a1-127">string</span><span class="sxs-lookup"><span data-stu-id="132a1-127">string</span></span> | <span data-ttu-id="132a1-128">Protocolo usado durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="132a1-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="132a1-129">string</span><span class="sxs-lookup"><span data-stu-id="132a1-129">string</span></span> | <span data-ttu-id="132a1-130">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="132a1-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="132a1-131">string</span><span class="sxs-lookup"><span data-stu-id="132a1-131">string</span></span> | <span data-ttu-id="132a1-132">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="132a1-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="132a1-133">string</span><span class="sxs-lookup"><span data-stu-id="132a1-133">string</span></span> | <span data-ttu-id="132a1-134">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="132a1-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="132a1-135">string</span><span class="sxs-lookup"><span data-stu-id="132a1-135">string</span></span> | <span data-ttu-id="132a1-136">Identificador de Segurança (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="132a1-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="132a1-137">string</span><span class="sxs-lookup"><span data-stu-id="132a1-137">string</span></span> | <span data-ttu-id="132a1-138">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="132a1-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="132a1-139">string</span><span class="sxs-lookup"><span data-stu-id="132a1-139">string</span></span> | <span data-ttu-id="132a1-140">Nome do usuário da conta exibido no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="132a1-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="132a1-141">Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="132a1-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="132a1-142">string</span><span class="sxs-lookup"><span data-stu-id="132a1-142">string</span></span> | <span data-ttu-id="132a1-143">FQDN (nome de domínio totalmente qualificado) do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="132a1-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="132a1-144">string</span><span class="sxs-lookup"><span data-stu-id="132a1-144">string</span></span> | <span data-ttu-id="132a1-145">Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="132a1-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="132a1-146">string</span><span class="sxs-lookup"><span data-stu-id="132a1-146">string</span></span> | <span data-ttu-id="132a1-147">Porta TCP usada durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="132a1-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="132a1-148">string</span><span class="sxs-lookup"><span data-stu-id="132a1-148">string</span></span> | <span data-ttu-id="132a1-149">Nome do dispositivo que executa o aplicativo de servidor que processou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="132a1-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="132a1-150">string</span><span class="sxs-lookup"><span data-stu-id="132a1-150">string</span></span> | <span data-ttu-id="132a1-151">Endereço IP do dispositivo que executa o aplicativo de servidor que processou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="132a1-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="132a1-152">string</span><span class="sxs-lookup"><span data-stu-id="132a1-152">string</span></span> | <span data-ttu-id="132a1-153">Porta de destino de comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="132a1-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="132a1-154">string</span><span class="sxs-lookup"><span data-stu-id="132a1-154">string</span></span> | <span data-ttu-id="132a1-155">FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="132a1-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="132a1-156">string</span><span class="sxs-lookup"><span data-stu-id="132a1-156">string</span></span> | <span data-ttu-id="132a1-157">Nome principal do usuário (UPN) da conta à que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="132a1-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="132a1-158">string</span><span class="sxs-lookup"><span data-stu-id="132a1-158">string</span></span> | <span data-ttu-id="132a1-159">Nome de exibição da conta à que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="132a1-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="132a1-160">string</span><span class="sxs-lookup"><span data-stu-id="132a1-160">string</span></span> | <span data-ttu-id="132a1-161">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="132a1-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="132a1-162">long</span><span class="sxs-lookup"><span data-stu-id="132a1-162">long</span></span> | <span data-ttu-id="132a1-163">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="132a1-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="132a1-164">string</span><span class="sxs-lookup"><span data-stu-id="132a1-164">string</span></span> | <span data-ttu-id="132a1-165">Informações adicionais sobre a entidade ou evento</span><span class="sxs-lookup"><span data-stu-id="132a1-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="132a1-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="132a1-166">Related topics</span></span>
- [<span data-ttu-id="132a1-167">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="132a1-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="132a1-168">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="132a1-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="132a1-169">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="132a1-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="132a1-170">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="132a1-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="132a1-171">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="132a1-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="132a1-172">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="132a1-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
