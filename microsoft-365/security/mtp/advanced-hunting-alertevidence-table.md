---
title: Tabela AlertEvidence no esquema de busca avançada
description: Saiba mais sobre arquivo, endereço de rede, usuário ou informações de dispositivo associadas a alertas gerados na tabela AlertEvidence do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidência, arquivo, endereço IP, dispositivo, máquina, usuário, conta
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
ms.openlocfilehash: 8fc713db33b0e40adcd0975d26c10daece636ab1
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649506"
---
# <a name="alertevidence"></a><span data-ttu-id="9fc3f-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="9fc3f-104">AlertEvidence</span></span>

<span data-ttu-id="9fc3f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9fc3f-105">**Applies to:**</span></span>
- <span data-ttu-id="9fc3f-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9fc3f-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="9fc3f-107">A `AlertEvidence` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre várias entidades (arquivos, endereços IP, URLs, usuários ou dispositivos) associados a alertas do Microsoft defender ATP, Office 365 ATP, Microsoft Cloud app Security e Azure ATP.</span><span class="sxs-lookup"><span data-stu-id="9fc3f-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities — files, IP addresses, URLs, users, or devices — associated with alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP.</span></span> <span data-ttu-id="9fc3f-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="9fc3f-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="9fc3f-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9fc3f-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9fc3f-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="9fc3f-110">Column name</span></span> | <span data-ttu-id="9fc3f-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="9fc3f-111">Data type</span></span> | <span data-ttu-id="9fc3f-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="9fc3f-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9fc3f-113">datetime</span><span class="sxs-lookup"><span data-stu-id="9fc3f-113">datetime</span></span> | <span data-ttu-id="9fc3f-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="9fc3f-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="9fc3f-115">string</span><span class="sxs-lookup"><span data-stu-id="9fc3f-115">string</span></span> | <span data-ttu-id="9fc3f-116">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="9fc3f-116">Unique identifier for the alert</span></span> |
| `EntityType` | <span data-ttu-id="9fc3f-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-117">string</span></span> | <span data-ttu-id="9fc3f-118">Tipo de objeto, como um arquivo, um processo, um dispositivo ou um usuário</span><span class="sxs-lookup"><span data-stu-id="9fc3f-118">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="9fc3f-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-119">string</span></span> | <span data-ttu-id="9fc3f-120">Como a entidade está envolvida em um alerta, indicando se é impactada ou se é meramente relacionada</span><span class="sxs-lookup"><span data-stu-id="9fc3f-120">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `SHA1` | <span data-ttu-id="9fc3f-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-121">string</span></span> | <span data-ttu-id="9fc3f-122">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="9fc3f-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="9fc3f-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-123">string</span></span> | <span data-ttu-id="9fc3f-124">SHA-256 do arquivo ao qual a ação gravada foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="9fc3f-124">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="9fc3f-125">Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível.</span><span class="sxs-lookup"><span data-stu-id="9fc3f-125">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `RemoteIP` | <span data-ttu-id="9fc3f-126">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-126">string</span></span> | <span data-ttu-id="9fc3f-127">Endereço IP que estava sendo conectado ao</span><span class="sxs-lookup"><span data-stu-id="9fc3f-127">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="9fc3f-128">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-128">string</span></span> | <span data-ttu-id="9fc3f-129">URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à</span><span class="sxs-lookup"><span data-stu-id="9fc3f-129">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="9fc3f-130">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-130">string</span></span> | <span data-ttu-id="9fc3f-131">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="9fc3f-131">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="9fc3f-132">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-132">string</span></span> | <span data-ttu-id="9fc3f-133">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="9fc3f-133">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="9fc3f-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-134">string</span></span> | <span data-ttu-id="9fc3f-135">Identificador de segurança (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="9fc3f-135">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="9fc3f-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-136">string</span></span> | <span data-ttu-id="9fc3f-137">Identificador exclusivo da conta no Azure AD</span><span class="sxs-lookup"><span data-stu-id="9fc3f-137">Unique identifier for the account in Azure AD</span></span> |
| `DeviceId` | <span data-ttu-id="9fc3f-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-138">string</span></span> | <span data-ttu-id="9fc3f-139">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="9fc3f-139">Unique identifier for the machine in the service</span></span> |
| `ThreatFamily` | <span data-ttu-id="9fc3f-140">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-140">string</span></span> | <span data-ttu-id="9fc3f-141">Família de malware que o arquivo ou processo suspeito ou mal-intencionado foi classificado em</span><span class="sxs-lookup"><span data-stu-id="9fc3f-141">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `EvidenceDirection` | <span data-ttu-id="9fc3f-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-142">string</span></span> | <span data-ttu-id="9fc3f-143">Indica se a entidade é a origem ou o destino de uma conexão de rede</span><span class="sxs-lookup"><span data-stu-id="9fc3f-143">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `AdditionalFields` | <span data-ttu-id="9fc3f-144">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fc3f-144">string</span></span> | <span data-ttu-id="9fc3f-145">Informações adicionais sobre o evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="9fc3f-145">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9fc3f-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9fc3f-146">Related topics</span></span>
- [<span data-ttu-id="9fc3f-147">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="9fc3f-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9fc3f-148">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="9fc3f-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9fc3f-149">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="9fc3f-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9fc3f-150">Procurar por dispositivos, emails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="9fc3f-150">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9fc3f-151">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="9fc3f-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9fc3f-152">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="9fc3f-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
