---
title: Tabela IdentityDirectoryEvents no esquema de busca avançada
description: Saiba mais sobre o controlador de domínio e eventos do Active Directory na tabela IdentityDirectoryEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Search, Query, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, IdentityDirectoryEvents, controlador de domínio, Active Directory, Azure ATP, identidades
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
ms.openlocfilehash: 4a698bc0d6a7c1ebadec44357b932e9b56dc0a3c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196840"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="4acde-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="4acde-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4acde-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4acde-105">**Applies to:**</span></span>
- <span data-ttu-id="4acde-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="4acde-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="4acde-107">A `IdentityDirectoryEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém eventos que envolvem um controlador de domínio local executando o Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="4acde-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="4acde-108">Esta tabela captura vários eventos relacionados à identidade, como alterações de senha, expiração de senha e alterações de nome de usuário principal (UPN).</span><span class="sxs-lookup"><span data-stu-id="4acde-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="4acde-109">Ele também captura eventos do sistema no controlador de domínio, como agendamento de tarefas e atividade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4acde-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="4acde-110">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="4acde-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="4acde-111">Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.</span><span class="sxs-lookup"><span data-stu-id="4acde-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="4acde-112">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="4acde-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="4acde-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="4acde-113">Column name</span></span> | <span data-ttu-id="4acde-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4acde-114">Data type</span></span> | <span data-ttu-id="4acde-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="4acde-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="4acde-116">datetime</span><span class="sxs-lookup"><span data-stu-id="4acde-116">datetime</span></span> | <span data-ttu-id="4acde-117">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="4acde-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="4acde-118">string</span><span class="sxs-lookup"><span data-stu-id="4acde-118">string</span></span> | <span data-ttu-id="4acde-119">Tipo de atividade que disparou o evento.</span><span class="sxs-lookup"><span data-stu-id="4acde-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="4acde-120">Consulte a [referência de esquema no portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obter detalhes</span><span class="sxs-lookup"><span data-stu-id="4acde-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="4acde-121">string</span><span class="sxs-lookup"><span data-stu-id="4acde-121">string</span></span> | <span data-ttu-id="4acde-122">Aplicativo que executou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="4acde-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="4acde-123">string</span><span class="sxs-lookup"><span data-stu-id="4acde-123">string</span></span> | <span data-ttu-id="4acde-124">Nome principal do usuário (UPN) da conta à qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="4acde-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="4acde-125">string</span><span class="sxs-lookup"><span data-stu-id="4acde-125">string</span></span> | <span data-ttu-id="4acde-126">Nome para exibição da conta à qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="4acde-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="4acde-127">string</span><span class="sxs-lookup"><span data-stu-id="4acde-127">string</span></span> | <span data-ttu-id="4acde-128">FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="4acde-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="4acde-129">string</span><span class="sxs-lookup"><span data-stu-id="4acde-129">string</span></span> | <span data-ttu-id="4acde-130">Nome do dispositivo que executa o aplicativo de servidor que processou a ação registrada</span><span class="sxs-lookup"><span data-stu-id="4acde-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="4acde-131">string</span><span class="sxs-lookup"><span data-stu-id="4acde-131">string</span></span> | <span data-ttu-id="4acde-132">Endereço IP do dispositivo que está executando o aplicativo de servidor que processou a ação registrada</span><span class="sxs-lookup"><span data-stu-id="4acde-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="4acde-133">string</span><span class="sxs-lookup"><span data-stu-id="4acde-133">string</span></span> | <span data-ttu-id="4acde-134">Porta de destino da atividade</span><span class="sxs-lookup"><span data-stu-id="4acde-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="4acde-135">string</span><span class="sxs-lookup"><span data-stu-id="4acde-135">string</span></span> | <span data-ttu-id="4acde-136">Protocolo usado durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="4acde-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="4acde-137">string</span><span class="sxs-lookup"><span data-stu-id="4acde-137">string</span></span> | <span data-ttu-id="4acde-138">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="4acde-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="4acde-139">string</span><span class="sxs-lookup"><span data-stu-id="4acde-139">string</span></span> | <span data-ttu-id="4acde-140">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="4acde-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="4acde-141">string</span><span class="sxs-lookup"><span data-stu-id="4acde-141">string</span></span> | <span data-ttu-id="4acde-142">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="4acde-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="4acde-143">string</span><span class="sxs-lookup"><span data-stu-id="4acde-143">string</span></span> | <span data-ttu-id="4acde-144">Identificador de segurança (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="4acde-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="4acde-145">string</span><span class="sxs-lookup"><span data-stu-id="4acde-145">string</span></span> | <span data-ttu-id="4acde-146">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="4acde-146">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="4acde-147">string</span><span class="sxs-lookup"><span data-stu-id="4acde-147">string</span></span> | <span data-ttu-id="4acde-148">Nome do usuário da conta exibido no catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="4acde-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="4acde-149">Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="4acde-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="4acde-150">string</span><span class="sxs-lookup"><span data-stu-id="4acde-150">string</span></span> | <span data-ttu-id="4acde-151">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="4acde-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="4acde-152">string</span><span class="sxs-lookup"><span data-stu-id="4acde-152">string</span></span> | <span data-ttu-id="4acde-153">Endereço IP atribuído ao dispositivo durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="4acde-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="4acde-154">string</span><span class="sxs-lookup"><span data-stu-id="4acde-154">string</span></span> | <span data-ttu-id="4acde-155">Porta TCP usada durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="4acde-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="4acde-156">string</span><span class="sxs-lookup"><span data-stu-id="4acde-156">string</span></span> | <span data-ttu-id="4acde-157">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="4acde-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="4acde-158">string</span><span class="sxs-lookup"><span data-stu-id="4acde-158">string</span></span> | <span data-ttu-id="4acde-159">Provedor de serviços de Internet associado ao endereço IP</span><span class="sxs-lookup"><span data-stu-id="4acde-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="4acde-160">long</span><span class="sxs-lookup"><span data-stu-id="4acde-160">long</span></span> | <span data-ttu-id="4acde-161">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="4acde-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="4acde-162">string</span><span class="sxs-lookup"><span data-stu-id="4acde-162">string</span></span> | <span data-ttu-id="4acde-163">Informações adicionais sobre a entidade ou o evento</span><span class="sxs-lookup"><span data-stu-id="4acde-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4acde-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4acde-164">Related topics</span></span>
- [<span data-ttu-id="4acde-165">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="4acde-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4acde-166">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="4acde-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4acde-167">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="4acde-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4acde-168">Procure em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="4acde-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="4acde-169">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="4acde-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4acde-170">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="4acde-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
