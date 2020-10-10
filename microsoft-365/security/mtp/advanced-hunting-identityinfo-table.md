---
title: Tabela IdentityInfo no esquema de busca avançada
description: Saiba mais sobre as informações da conta de usuário na tabela IdentityInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, AccountInfo, IdentityInfo, conta
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 94afa9e36ca75491511338297f02e8031333e53f
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412737"
---
# <a name="identityinfo"></a><span data-ttu-id="cf474-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="cf474-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="cf474-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cf474-105">**Applies to:**</span></span>
- <span data-ttu-id="cf474-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="cf474-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cf474-107">A `IdentityInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre contas de usuário obtidas de vários serviços, incluindo o Active Directory do Azure.</span><span class="sxs-lookup"><span data-stu-id="cf474-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="cf474-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="cf474-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="cf474-109">Esta tabela foi renomeada de `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="cf474-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="cf474-110">Durante a renomeação, todas as consultas salvas no portal são atualizadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cf474-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="cf474-111">Verifique as consultas que você salvou em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="cf474-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="cf474-112">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="cf474-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="cf474-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="cf474-113">Column name</span></span> | <span data-ttu-id="cf474-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="cf474-114">Data type</span></span> | <span data-ttu-id="cf474-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="cf474-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="cf474-116">string</span><span class="sxs-lookup"><span data-stu-id="cf474-116">string</span></span> | <span data-ttu-id="cf474-117">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="cf474-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="cf474-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-118">string</span></span> | <span data-ttu-id="cf474-119">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="cf474-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="cf474-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-120">string</span></span> | <span data-ttu-id="cf474-121">SID (identificador de segurança) local da conta</span><span class="sxs-lookup"><span data-stu-id="cf474-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="cf474-122">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-122">string</span></span> | <span data-ttu-id="cf474-123">Identificador de segurança de nuvem da conta</span><span class="sxs-lookup"><span data-stu-id="cf474-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="cf474-124">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-124">string</span></span> | <span data-ttu-id="cf474-125">Nome ou nome de usuário da conta fornecido</span><span class="sxs-lookup"><span data-stu-id="cf474-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="cf474-126">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-126">string</span></span> | <span data-ttu-id="cf474-127">Sobrenome, nome da família ou sobrenome do usuário da conta</span><span class="sxs-lookup"><span data-stu-id="cf474-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="cf474-128">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-128">string</span></span> | <span data-ttu-id="cf474-129">Nome do usuário da conta exibido no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="cf474-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="cf474-130">Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="cf474-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="cf474-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-131">string</span></span> | <span data-ttu-id="cf474-132">Nome do departamento ao qual pertence o usuário da conta</span><span class="sxs-lookup"><span data-stu-id="cf474-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="cf474-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-133">string</span></span> | <span data-ttu-id="cf474-134">Título do trabalho da conta de usuário</span><span class="sxs-lookup"><span data-stu-id="cf474-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="cf474-135">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-135">string</span></span> | <span data-ttu-id="cf474-136">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="cf474-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="cf474-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-137">string</span></span> | <span data-ttu-id="cf474-138">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="cf474-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="cf474-139">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-139">string</span></span> | <span data-ttu-id="cf474-140">Endereço SMTP da conta</span><span class="sxs-lookup"><span data-stu-id="cf474-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="cf474-141">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-141">string</span></span> | <span data-ttu-id="cf474-142">Endereço SIP (protocolo de iniciação de sessão) de voz sobre IP (VOIP) da conta</span><span class="sxs-lookup"><span data-stu-id="cf474-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="cf474-143">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-143">string</span></span> | <span data-ttu-id="cf474-144">Cidade onde o usuário da conta está localizado</span><span class="sxs-lookup"><span data-stu-id="cf474-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="cf474-145">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cf474-145">string</span></span> | <span data-ttu-id="cf474-146">País/região onde o usuário da conta está localizado</span><span class="sxs-lookup"><span data-stu-id="cf474-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="cf474-147">booliano</span><span class="sxs-lookup"><span data-stu-id="cf474-147">boolean</span></span> | <span data-ttu-id="cf474-148">Indica se a conta está habilitada ou não</span><span class="sxs-lookup"><span data-stu-id="cf474-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cf474-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cf474-149">Related topics</span></span>
- [<span data-ttu-id="cf474-150">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="cf474-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cf474-151">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="cf474-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cf474-152">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="cf474-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="cf474-153">Procure em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="cf474-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cf474-154">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="cf474-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cf474-155">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="cf474-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
