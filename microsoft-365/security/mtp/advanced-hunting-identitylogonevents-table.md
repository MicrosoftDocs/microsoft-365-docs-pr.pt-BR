---
title: Tabela IdentityLogonEvents no esquema de busca avançada
description: Saiba mais sobre eventos de autenticação registrados pelo Active Directory na tabela IdentityLogonEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, identidades
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
ms.openlocfilehash: 17e12e9095219b7ad7923f7b5664946fff6ce724
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899370"
---
# <a name="identitylogonevents"></a><span data-ttu-id="ceba9-104">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="ceba9-104">IdentityLogonEvents</span></span>

<span data-ttu-id="ceba9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ceba9-105">**Applies to:**</span></span>
- <span data-ttu-id="ceba9-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ceba9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ceba9-107">A `IdentityLogonEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre as atividades de autenticação registradas pelo Azure Active Directory e outros aplicativos e serviços do Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="ceba9-107">The `IdentityLogonEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about authentication activities recorded by Azure Active Directory and other Microsoft cloud apps and services.</span></span> <span data-ttu-id="ceba9-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="ceba9-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="ceba9-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ceba9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ceba9-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="ceba9-110">Column name</span></span> | <span data-ttu-id="ceba9-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ceba9-111">Data type</span></span> | <span data-ttu-id="ceba9-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="ceba9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ceba9-113">datetime</span><span class="sxs-lookup"><span data-stu-id="ceba9-113">datetime</span></span> | <span data-ttu-id="ceba9-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="ceba9-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="ceba9-115">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-115">string</span></span> | <span data-ttu-id="ceba9-116">Tipo de atividade que disparou o evento</span><span class="sxs-lookup"><span data-stu-id="ceba9-116">Type of activity that triggered the event</span></span> |
| `LogonType` | <span data-ttu-id="ceba9-117">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-117">string</span></span> | <span data-ttu-id="ceba9-118">Tipo de sessão de logon, especificamente:</span><span class="sxs-lookup"><span data-stu-id="ceba9-118">Type of logon session, specifically:</span></span><br><br> <span data-ttu-id="ceba9-119">- **Interativo** -o usuário interage fisicamente com o computador usando o teclado e a tela locais</span><span class="sxs-lookup"><span data-stu-id="ceba9-119">- **Interactive** - User physically interacts with the machine using the local keyboard and screen</span></span><br><br> <span data-ttu-id="ceba9-120">- **Logons interativos (RDP) remotos** -o usuário interage com o computador remotamente usando a área de trabalho remota, serviços de terminal, assistência remota ou outros clientes RDP</span><span class="sxs-lookup"><span data-stu-id="ceba9-120">- **Remote interactive (RDP) logons** - User interacts with the machine remotely using Remote Desktop, Terminal Services, Remote Assistance, or other RDP clients</span></span><br><br> <span data-ttu-id="ceba9-121">- **Rede** -sessão iniciada quando a máquina é acessada usando o PsExec ou quando recursos compartilhados na máquina, como impressoras e pastas compartilhadas, são acessados</span><span class="sxs-lookup"><span data-stu-id="ceba9-121">- **Network** - Session initiated when the machine is accessed using PsExec or when shared resources on the machine, such as printers and shared folders, are accessed</span></span><br><br> <span data-ttu-id="ceba9-122">- Sessão **em lote** iniciada por tarefas agendadas</span><span class="sxs-lookup"><span data-stu-id="ceba9-122">- **Batch** - Session initiated by scheduled tasks</span></span><br><br> <span data-ttu-id="ceba9-123">- **Serviço** -sessão iniciada pelos serviços à medida que eles são iniciados</span><span class="sxs-lookup"><span data-stu-id="ceba9-123">- **Service** - Session initiated by services as they start</span></span> |
| `Application` | <span data-ttu-id="ceba9-124">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-124">string</span></span> | <span data-ttu-id="ceba9-125">Aplicativo que executou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="ceba9-125">Application that performed the recorded action</span></span> |
| `Protocol` | <span data-ttu-id="ceba9-126">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-126">string</span></span> | <span data-ttu-id="ceba9-127">Protocolo usado durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="ceba9-127">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="ceba9-128">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-128">string</span></span> | <span data-ttu-id="ceba9-129">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="ceba9-129">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="ceba9-130">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-130">string</span></span> | <span data-ttu-id="ceba9-131">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="ceba9-131">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="ceba9-132">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-132">string</span></span> | <span data-ttu-id="ceba9-133">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="ceba9-133">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="ceba9-134">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-134">string</span></span> | <span data-ttu-id="ceba9-135">Identificador de segurança (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="ceba9-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="ceba9-136">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-136">string</span></span> | <span data-ttu-id="ceba9-137">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="ceba9-137">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="ceba9-138">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-138">string</span></span> | <span data-ttu-id="ceba9-139">Nome do usuário da conta exibido no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="ceba9-139">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="ceba9-140">Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="ceba9-140">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="ceba9-141">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ceba9-141">string</span></span> | <span data-ttu-id="ceba9-142">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="ceba9-142">Fully qualified domain name (FQDN) of the machine</span></span> |
| `DeviceType` | <span data-ttu-id="ceba9-143">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ceba9-143">string</span></span> | <span data-ttu-id="ceba9-144">Tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ceba9-144">Type of device</span></span> |
| `OSPlatform` | <span data-ttu-id="ceba9-145">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-145">string</span></span> | <span data-ttu-id="ceba9-146">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="ceba9-146">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="ceba9-147">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="ceba9-147">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="ceba9-148">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-148">string</span></span> | <span data-ttu-id="ceba9-149">Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas</span><span class="sxs-lookup"><span data-stu-id="ceba9-149">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="ceba9-150">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-150">string</span></span> | <span data-ttu-id="ceba9-151">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="ceba9-151">City, country, or other geographic location associated with the event</span></span> |
| `Isp` | <span data-ttu-id="ceba9-152">string</span><span class="sxs-lookup"><span data-stu-id="ceba9-152">string</span></span> | <span data-ttu-id="ceba9-153">Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="ceba9-153">Internet service provider (ISP) associated with the endpoint IP address</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ceba9-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ceba9-154">Related topics</span></span>
- [<span data-ttu-id="ceba9-155">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="ceba9-155">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ceba9-156">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="ceba9-156">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ceba9-157">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="ceba9-157">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ceba9-158">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="ceba9-158">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ceba9-159">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="ceba9-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ceba9-160">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="ceba9-160">Apply query best practices</span></span>](advanced-hunting-best-practices.md)