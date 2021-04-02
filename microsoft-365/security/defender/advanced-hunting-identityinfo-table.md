---
title: Tabela IdentityInfo no esquema de busca avançado
description: Saiba mais sobre as informações da conta de usuário na tabela IdentityInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AccountInfo, IdentityInfo, conta
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
ms.openlocfilehash: d7e1ad4d10c3b71a04421d92304dc2bfcb6147da
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498208"
---
# <a name="identityinfo"></a><span data-ttu-id="0424e-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="0424e-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0424e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0424e-105">**Applies to:**</span></span>
- <span data-ttu-id="0424e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0424e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0424e-107">A tabela no esquema de busca avançado contém informações sobre contas de usuário obtidas de vários `IdentityInfo` serviços, incluindo o Azure Active Directory. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0424e-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="0424e-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="0424e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="0424e-109">Esta tabela foi renomeada de `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="0424e-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="0424e-110">Durante os renomeados, todas as consultas salvas no portal são atualizadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0424e-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="0424e-111">Verifique consultas salvas em outro lugar.</span><span class="sxs-lookup"><span data-stu-id="0424e-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="0424e-112">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0424e-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0424e-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="0424e-113">Column name</span></span> | <span data-ttu-id="0424e-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0424e-114">Data type</span></span> | <span data-ttu-id="0424e-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="0424e-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="0424e-116">string</span><span class="sxs-lookup"><span data-stu-id="0424e-116">string</span></span> | <span data-ttu-id="0424e-117">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="0424e-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="0424e-118">string</span><span class="sxs-lookup"><span data-stu-id="0424e-118">string</span></span> | <span data-ttu-id="0424e-119">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="0424e-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="0424e-120">string</span><span class="sxs-lookup"><span data-stu-id="0424e-120">string</span></span> | <span data-ttu-id="0424e-121">Identificador de segurança local (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="0424e-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="0424e-122">string</span><span class="sxs-lookup"><span data-stu-id="0424e-122">string</span></span> | <span data-ttu-id="0424e-123">Identificador de segurança na nuvem da conta</span><span class="sxs-lookup"><span data-stu-id="0424e-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="0424e-124">string</span><span class="sxs-lookup"><span data-stu-id="0424e-124">string</span></span> | <span data-ttu-id="0424e-125">Nome ou nome do usuário da conta</span><span class="sxs-lookup"><span data-stu-id="0424e-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="0424e-126">string</span><span class="sxs-lookup"><span data-stu-id="0424e-126">string</span></span> | <span data-ttu-id="0424e-127">Sobrenome, nome da família ou sobrenome do usuário da conta</span><span class="sxs-lookup"><span data-stu-id="0424e-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0424e-128">string</span><span class="sxs-lookup"><span data-stu-id="0424e-128">string</span></span> | <span data-ttu-id="0424e-129">Nome do usuário da conta exibido no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="0424e-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0424e-130">Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="0424e-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="0424e-131">string</span><span class="sxs-lookup"><span data-stu-id="0424e-131">string</span></span> | <span data-ttu-id="0424e-132">Nome do departamento ao que o usuário da conta pertence</span><span class="sxs-lookup"><span data-stu-id="0424e-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="0424e-133">string</span><span class="sxs-lookup"><span data-stu-id="0424e-133">string</span></span> | <span data-ttu-id="0424e-134">Título de trabalho do usuário da conta</span><span class="sxs-lookup"><span data-stu-id="0424e-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="0424e-135">string</span><span class="sxs-lookup"><span data-stu-id="0424e-135">string</span></span> | <span data-ttu-id="0424e-136">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="0424e-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0424e-137">string</span><span class="sxs-lookup"><span data-stu-id="0424e-137">string</span></span> | <span data-ttu-id="0424e-138">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="0424e-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="0424e-139">string</span><span class="sxs-lookup"><span data-stu-id="0424e-139">string</span></span> | <span data-ttu-id="0424e-140">Endereço SMTP da conta</span><span class="sxs-lookup"><span data-stu-id="0424e-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="0424e-141">string</span><span class="sxs-lookup"><span data-stu-id="0424e-141">string</span></span> | <span data-ttu-id="0424e-142">Endereço SIP (Protocolo de iniciação de sessão DE VOIP) de voz sobre IP da conta</span><span class="sxs-lookup"><span data-stu-id="0424e-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="0424e-143">string</span><span class="sxs-lookup"><span data-stu-id="0424e-143">string</span></span> | <span data-ttu-id="0424e-144">Cidade onde o usuário da conta está localizado</span><span class="sxs-lookup"><span data-stu-id="0424e-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="0424e-145">string</span><span class="sxs-lookup"><span data-stu-id="0424e-145">string</span></span> | <span data-ttu-id="0424e-146">País/Região onde o usuário da conta está localizado</span><span class="sxs-lookup"><span data-stu-id="0424e-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="0424e-147">booliano</span><span class="sxs-lookup"><span data-stu-id="0424e-147">boolean</span></span> | <span data-ttu-id="0424e-148">Indica se a conta está habilitada ou não</span><span class="sxs-lookup"><span data-stu-id="0424e-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0424e-149">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0424e-149">Related topics</span></span>
- [<span data-ttu-id="0424e-150">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="0424e-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0424e-151">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="0424e-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0424e-152">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="0424e-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0424e-153">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="0424e-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0424e-154">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="0424e-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0424e-155">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="0424e-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
