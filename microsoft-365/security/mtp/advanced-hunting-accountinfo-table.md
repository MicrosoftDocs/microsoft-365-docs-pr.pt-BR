---
title: Tabela AccountInfo no esquema de busca avançada
description: Saiba mais sobre as informações da conta de usuário na tabela AccountInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidência, arquivo, endereço IP, dispositivo, máquina, usuário, conta
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929523"
---
# <a name="accountinfo"></a><span data-ttu-id="eac5d-104">AccountInfo</span><span class="sxs-lookup"><span data-stu-id="eac5d-104">AccountInfo</span></span>

<span data-ttu-id="eac5d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="eac5d-105">**Applies to:**</span></span>
- <span data-ttu-id="eac5d-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="eac5d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="eac5d-107">A `AccountInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre contas de usuário obtidas de vários serviços, incluindo o Active Directory do Azure.</span><span class="sxs-lookup"><span data-stu-id="eac5d-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="eac5d-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="eac5d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="eac5d-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="eac5d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="eac5d-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="eac5d-110">Column name</span></span> | <span data-ttu-id="eac5d-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="eac5d-111">Data type</span></span> | <span data-ttu-id="eac5d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="eac5d-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="eac5d-113">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-113">string</span></span> | <span data-ttu-id="eac5d-114">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="eac5d-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="eac5d-115">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-115">string</span></span> | <span data-ttu-id="eac5d-116">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="eac5d-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="eac5d-117">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-117">string</span></span> | <span data-ttu-id="eac5d-118">SID (identificador de segurança) local da conta</span><span class="sxs-lookup"><span data-stu-id="eac5d-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="eac5d-119">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-119">string</span></span> | <span data-ttu-id="eac5d-120">Identificador de segurança de nuvem da conta</span><span class="sxs-lookup"><span data-stu-id="eac5d-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="eac5d-121">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-121">string</span></span> | <span data-ttu-id="eac5d-122">Nome ou nome de usuário da conta fornecido</span><span class="sxs-lookup"><span data-stu-id="eac5d-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="eac5d-123">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-123">string</span></span> | <span data-ttu-id="eac5d-124">Sobrenome, nome da família ou sobrenome do usuário da conta</span><span class="sxs-lookup"><span data-stu-id="eac5d-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="eac5d-125">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-125">string</span></span> | <span data-ttu-id="eac5d-126">Nome do usuário da conta exibido no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="eac5d-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="eac5d-127">Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="eac5d-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="eac5d-128">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-128">string</span></span> | <span data-ttu-id="eac5d-129">Nome do departamento ao qual pertence o usuário da conta</span><span class="sxs-lookup"><span data-stu-id="eac5d-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="eac5d-130">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-130">string</span></span> | <span data-ttu-id="eac5d-131">Título do trabalho da conta de usuário</span><span class="sxs-lookup"><span data-stu-id="eac5d-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="eac5d-132">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-132">string</span></span> | <span data-ttu-id="eac5d-133">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="eac5d-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="eac5d-134">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-134">string</span></span> | <span data-ttu-id="eac5d-135">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="eac5d-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="eac5d-136">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-136">string</span></span> | <span data-ttu-id="eac5d-137">Endereço SMTP da conta</span><span class="sxs-lookup"><span data-stu-id="eac5d-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="eac5d-138">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-138">string</span></span> | <span data-ttu-id="eac5d-139">Voice of IP (VOIP) endereço de protocolo de início de sessão (SIP) da conta</span><span class="sxs-lookup"><span data-stu-id="eac5d-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="eac5d-140">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-140">string</span></span> | <span data-ttu-id="eac5d-141">Cidade onde o usuário da conta está localizado</span><span class="sxs-lookup"><span data-stu-id="eac5d-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="eac5d-142">string</span><span class="sxs-lookup"><span data-stu-id="eac5d-142">string</span></span> | <span data-ttu-id="eac5d-143">País/região onde o usuário da conta está localizado</span><span class="sxs-lookup"><span data-stu-id="eac5d-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="eac5d-144">booliano</span><span class="sxs-lookup"><span data-stu-id="eac5d-144">boolean</span></span> | <span data-ttu-id="eac5d-145">Indica se a conta está habilitada ou não</span><span class="sxs-lookup"><span data-stu-id="eac5d-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="eac5d-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="eac5d-146">Related topics</span></span>
- [<span data-ttu-id="eac5d-147">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="eac5d-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="eac5d-148">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="eac5d-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="eac5d-149">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="eac5d-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="eac5d-150">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="eac5d-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="eac5d-151">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="eac5d-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="eac5d-152">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="eac5d-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
