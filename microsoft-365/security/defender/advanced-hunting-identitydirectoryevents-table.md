---
title: Tabela IdentityDirectoryEvents no esquema de busca avançado
description: Saiba mais sobre o controlador de domínio e eventos do Active Directory na tabela IdentityDirectoryEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, IdentityDirectoryEvents, controlador de domínio, Active Directory, Azure ATP, identidades
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ba63bdeb215c24e68d0e507d99e026c5b2695cb0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054426"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="2556f-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="2556f-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2556f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2556f-105">**Applies to:**</span></span>
- <span data-ttu-id="2556f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2556f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2556f-107">A tabela no esquema de busca avançada contém eventos envolvendo um controlador de domínio local executando o `IdentityDirectoryEvents` Active Directory [](advanced-hunting-overview.md) (AD).</span><span class="sxs-lookup"><span data-stu-id="2556f-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="2556f-108">Esta tabela captura vários eventos relacionados à identidade, como alterações de senha, expiração de senha e alterações de nome principal do usuário (UPN).</span><span class="sxs-lookup"><span data-stu-id="2556f-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="2556f-109">Ele também captura eventos do sistema no controlador de domínio, como agendamento de tarefas e atividade do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2556f-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="2556f-110">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="2556f-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="2556f-111">Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.</span><span class="sxs-lookup"><span data-stu-id="2556f-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="2556f-112">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2556f-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2556f-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="2556f-113">Column name</span></span> | <span data-ttu-id="2556f-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2556f-114">Data type</span></span> | <span data-ttu-id="2556f-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="2556f-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2556f-116">datetime</span><span class="sxs-lookup"><span data-stu-id="2556f-116">datetime</span></span> | <span data-ttu-id="2556f-117">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="2556f-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="2556f-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-118">string</span></span> | <span data-ttu-id="2556f-119">Tipo de atividade que disparou o evento.</span><span class="sxs-lookup"><span data-stu-id="2556f-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="2556f-120">Consulte a [referência de esquema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) no portal para obter detalhes</span><span class="sxs-lookup"><span data-stu-id="2556f-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="2556f-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-121">string</span></span> | <span data-ttu-id="2556f-122">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="2556f-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="2556f-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-123">string</span></span> | <span data-ttu-id="2556f-124">Nome principal do usuário (UPN) da conta à que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="2556f-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="2556f-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-125">string</span></span> | <span data-ttu-id="2556f-126">Nome de exibição da conta à que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="2556f-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="2556f-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-127">string</span></span> | <span data-ttu-id="2556f-128">FQDN (nome de domínio totalmente qualificado) do dispositivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="2556f-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="2556f-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-129">string</span></span> | <span data-ttu-id="2556f-130">Nome do dispositivo que executa o aplicativo de servidor que processou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="2556f-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="2556f-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-131">string</span></span> | <span data-ttu-id="2556f-132">Endereço IP do dispositivo que executa o aplicativo de servidor que processou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="2556f-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="2556f-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-133">string</span></span> | <span data-ttu-id="2556f-134">Porta de destino da atividade</span><span class="sxs-lookup"><span data-stu-id="2556f-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="2556f-135">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-135">string</span></span> | <span data-ttu-id="2556f-136">Protocolo usado durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="2556f-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="2556f-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-137">string</span></span> | <span data-ttu-id="2556f-138">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="2556f-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="2556f-139">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-139">string</span></span> | <span data-ttu-id="2556f-140">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="2556f-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="2556f-141">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-141">string</span></span> | <span data-ttu-id="2556f-142">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="2556f-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="2556f-143">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-143">string</span></span> | <span data-ttu-id="2556f-144">Identificador de Segurança (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="2556f-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="2556f-145">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-145">string</span></span> | <span data-ttu-id="2556f-146">Identificador exclusivo da conta no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2556f-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="2556f-147">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-147">string</span></span> | <span data-ttu-id="2556f-148">Nome do usuário da conta exibido no livro de endereços.</span><span class="sxs-lookup"><span data-stu-id="2556f-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="2556f-149">Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome.</span><span class="sxs-lookup"><span data-stu-id="2556f-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="2556f-150">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-150">string</span></span> | <span data-ttu-id="2556f-151">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2556f-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="2556f-152">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-152">string</span></span> | <span data-ttu-id="2556f-153">Endereço IP atribuído ao dispositivo durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="2556f-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="2556f-154">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-154">string</span></span> | <span data-ttu-id="2556f-155">Porta TCP usada durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="2556f-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="2556f-156">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-156">string</span></span> | <span data-ttu-id="2556f-157">Cidade, país ou outra localização geográfica associada ao evento</span><span class="sxs-lookup"><span data-stu-id="2556f-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="2556f-158">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-158">string</span></span> | <span data-ttu-id="2556f-159">Provedor de serviços de Internet associado ao endereço IP</span><span class="sxs-lookup"><span data-stu-id="2556f-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="2556f-160">long</span><span class="sxs-lookup"><span data-stu-id="2556f-160">long</span></span> | <span data-ttu-id="2556f-161">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="2556f-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="2556f-162">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2556f-162">string</span></span> | <span data-ttu-id="2556f-163">Informações adicionais sobre a entidade ou evento</span><span class="sxs-lookup"><span data-stu-id="2556f-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2556f-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2556f-164">Related topics</span></span>
- [<span data-ttu-id="2556f-165">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="2556f-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2556f-166">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="2556f-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2556f-167">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="2556f-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2556f-168">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="2556f-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2556f-169">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="2556f-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2556f-170">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="2556f-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)