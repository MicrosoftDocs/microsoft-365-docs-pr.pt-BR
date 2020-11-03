---
title: Tabela AlertEvidence no esquema de busca avançada
description: Saiba mais sobre as informações associadas a alertas na tabela AlertEvidence do esquema de busca avançada
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 549eed005e06a7d52ce2f881820ae9fdeffdfea7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847675"
---
# <a name="alertevidence"></a><span data-ttu-id="c91db-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="c91db-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c91db-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c91db-105">**Applies to:**</span></span>
- <span data-ttu-id="c91db-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="c91db-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c91db-107">A `AlertEvidence` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre várias entidades — arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas do Microsoft defender para ponto de extremidade, Microsoft defender para Office 365, Microsoft Cloud app Security e Microsoft defender para identidade.</span><span class="sxs-lookup"><span data-stu-id="c91db-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="c91db-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="c91db-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c91db-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c91db-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c91db-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="c91db-110">Column name</span></span> | <span data-ttu-id="c91db-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c91db-111">Data type</span></span> | <span data-ttu-id="c91db-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c91db-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c91db-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c91db-113">datetime</span></span> | <span data-ttu-id="c91db-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="c91db-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="c91db-115">string</span><span class="sxs-lookup"><span data-stu-id="c91db-115">string</span></span> | <span data-ttu-id="c91db-116">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="c91db-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="c91db-117">string</span><span class="sxs-lookup"><span data-stu-id="c91db-117">string</span></span> | <span data-ttu-id="c91db-118">Produto ou serviço que forneceu as informações de alerta</span><span class="sxs-lookup"><span data-stu-id="c91db-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="c91db-119">string</span><span class="sxs-lookup"><span data-stu-id="c91db-119">string</span></span> | <span data-ttu-id="c91db-120">Tipo de objeto, como um arquivo, um processo, um dispositivo ou um usuário</span><span class="sxs-lookup"><span data-stu-id="c91db-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="c91db-121">string</span><span class="sxs-lookup"><span data-stu-id="c91db-121">string</span></span> | <span data-ttu-id="c91db-122">Como a entidade está envolvida em um alerta, indicando se é impactada ou se é meramente relacionada</span><span class="sxs-lookup"><span data-stu-id="c91db-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="c91db-123">string</span><span class="sxs-lookup"><span data-stu-id="c91db-123">string</span></span> | <span data-ttu-id="c91db-124">Indica se a entidade é a origem ou o destino de uma conexão de rede</span><span class="sxs-lookup"><span data-stu-id="c91db-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="c91db-125">string</span><span class="sxs-lookup"><span data-stu-id="c91db-125">string</span></span> | <span data-ttu-id="c91db-126">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="c91db-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="c91db-127">string</span><span class="sxs-lookup"><span data-stu-id="c91db-127">string</span></span> | <span data-ttu-id="c91db-128">Pasta que contém o arquivo para o qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="c91db-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="c91db-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c91db-129">string</span></span> | <span data-ttu-id="c91db-130">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="c91db-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="c91db-131">string</span><span class="sxs-lookup"><span data-stu-id="c91db-131">string</span></span> | <span data-ttu-id="c91db-132">SHA-256 do arquivo ao qual a ação gravada foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="c91db-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="c91db-133">Este campo geralmente não é preenchido: Use a coluna SHA1 quando disponível.</span><span class="sxs-lookup"><span data-stu-id="c91db-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="c91db-134">int</span><span class="sxs-lookup"><span data-stu-id="c91db-134">int</span></span> | <span data-ttu-id="c91db-135">Tamanho do arquivo em bytes</span><span class="sxs-lookup"><span data-stu-id="c91db-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="c91db-136">string</span><span class="sxs-lookup"><span data-stu-id="c91db-136">string</span></span> | <span data-ttu-id="c91db-137">Família de malware que o arquivo ou processo suspeito ou mal-intencionado foi classificado em</span><span class="sxs-lookup"><span data-stu-id="c91db-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="c91db-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c91db-138">string</span></span> | <span data-ttu-id="c91db-139">Endereço IP que estava sendo conectado ao</span><span class="sxs-lookup"><span data-stu-id="c91db-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="c91db-140">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c91db-140">string</span></span> | <span data-ttu-id="c91db-141">URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à</span><span class="sxs-lookup"><span data-stu-id="c91db-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="c91db-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c91db-142">string</span></span> | <span data-ttu-id="c91db-143">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="c91db-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="c91db-144">string</span><span class="sxs-lookup"><span data-stu-id="c91db-144">string</span></span> | <span data-ttu-id="c91db-145">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="c91db-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="c91db-146">string</span><span class="sxs-lookup"><span data-stu-id="c91db-146">string</span></span> | <span data-ttu-id="c91db-147">Identificador de segurança (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="c91db-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="c91db-148">string</span><span class="sxs-lookup"><span data-stu-id="c91db-148">string</span></span> | <span data-ttu-id="c91db-149">Identificador exclusivo para a conta no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c91db-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="c91db-150">string</span><span class="sxs-lookup"><span data-stu-id="c91db-150">string</span></span> | <span data-ttu-id="c91db-151">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="c91db-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c91db-152">string</span><span class="sxs-lookup"><span data-stu-id="c91db-152">string</span></span> | <span data-ttu-id="c91db-153">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="c91db-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="c91db-154">string</span><span class="sxs-lookup"><span data-stu-id="c91db-154">string</span></span> | <span data-ttu-id="c91db-155">Endereço IP atribuído ao dispositivo local usado durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="c91db-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="c91db-156">string</span><span class="sxs-lookup"><span data-stu-id="c91db-156">string</span></span> | <span data-ttu-id="c91db-157">Identificador exclusivo do email, gerado pelo Office 365</span><span class="sxs-lookup"><span data-stu-id="c91db-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="c91db-158">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c91db-158">string</span></span> | <span data-ttu-id="c91db-159">Assunto do email</span><span class="sxs-lookup"><span data-stu-id="c91db-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="c91db-160">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c91db-160">string</span></span> | <span data-ttu-id="c91db-161">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="c91db-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="c91db-162">string</span><span class="sxs-lookup"><span data-stu-id="c91db-162">string</span></span> | <span data-ttu-id="c91db-163">Aplicativo que executou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="c91db-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="c91db-164">string</span><span class="sxs-lookup"><span data-stu-id="c91db-164">string</span></span> | <span data-ttu-id="c91db-165">Linha de comando usada para criar o novo processo</span><span class="sxs-lookup"><span data-stu-id="c91db-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="c91db-166">string</span><span class="sxs-lookup"><span data-stu-id="c91db-166">string</span></span> | <span data-ttu-id="c91db-167">Informações adicionais sobre o evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="c91db-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c91db-168">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c91db-168">Related topics</span></span>
- [<span data-ttu-id="c91db-169">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="c91db-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c91db-170">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="c91db-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c91db-171">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="c91db-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c91db-172">Procure em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="c91db-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c91db-173">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="c91db-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c91db-174">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="c91db-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
