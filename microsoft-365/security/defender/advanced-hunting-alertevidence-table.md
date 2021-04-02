---
title: Tabela AlertEvidence no esquema de busca avançado
description: Saiba mais sobre informações associadas a alertas na tabela AlertEvidence do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidências, arquivo, endereço IP, dispositivo, máquina, usuário, conta
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
ms.openlocfilehash: 7b1f581e1cfc8345df6e7b8053621cf46110c355
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499887"
---
# <a name="alertevidence"></a><span data-ttu-id="29f85-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="29f85-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="29f85-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="29f85-105">**Applies to:**</span></span>
- <span data-ttu-id="29f85-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29f85-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="29f85-107">A tabela no esquema de busca avançada contém informações sobre várias `AlertEvidence` entidades, arquivos, endereços IP, URLs, usuários ou dispositivos, associados a alertas do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365, Segurança de Aplicativos na Nuvem da [](advanced-hunting-overview.md) Microsoft e Microsoft Defender para Identidade.</span><span class="sxs-lookup"><span data-stu-id="29f85-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="29f85-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="29f85-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="29f85-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="29f85-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="29f85-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="29f85-110">Column name</span></span> | <span data-ttu-id="29f85-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="29f85-111">Data type</span></span> | <span data-ttu-id="29f85-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="29f85-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="29f85-113">datetime</span><span class="sxs-lookup"><span data-stu-id="29f85-113">datetime</span></span> | <span data-ttu-id="29f85-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="29f85-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="29f85-115">string</span><span class="sxs-lookup"><span data-stu-id="29f85-115">string</span></span> | <span data-ttu-id="29f85-116">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="29f85-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="29f85-117">string</span><span class="sxs-lookup"><span data-stu-id="29f85-117">string</span></span> | <span data-ttu-id="29f85-118">Produto ou serviço que forneceu as informações de alerta</span><span class="sxs-lookup"><span data-stu-id="29f85-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="29f85-119">string</span><span class="sxs-lookup"><span data-stu-id="29f85-119">string</span></span> | <span data-ttu-id="29f85-120">Tipo de objeto, como um arquivo, um processo, um dispositivo ou um usuário</span><span class="sxs-lookup"><span data-stu-id="29f85-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="29f85-121">string</span><span class="sxs-lookup"><span data-stu-id="29f85-121">string</span></span> | <span data-ttu-id="29f85-122">Como a entidade está envolvida em um alerta, indicando se ela foi impactada ou está meramente relacionada</span><span class="sxs-lookup"><span data-stu-id="29f85-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="29f85-123">string</span><span class="sxs-lookup"><span data-stu-id="29f85-123">string</span></span> | <span data-ttu-id="29f85-124">Indica se a entidade é a origem ou o destino de uma conexão de rede</span><span class="sxs-lookup"><span data-stu-id="29f85-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="29f85-125">string</span><span class="sxs-lookup"><span data-stu-id="29f85-125">string</span></span> | <span data-ttu-id="29f85-126">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="29f85-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="29f85-127">string</span><span class="sxs-lookup"><span data-stu-id="29f85-127">string</span></span> | <span data-ttu-id="29f85-128">Pasta que contém o arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="29f85-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="29f85-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29f85-129">string</span></span> | <span data-ttu-id="29f85-130">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="29f85-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="29f85-131">string</span><span class="sxs-lookup"><span data-stu-id="29f85-131">string</span></span> | <span data-ttu-id="29f85-132">SHA-256 do arquivo ao qual a ação gravada foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="29f85-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="29f85-133">Esse campo geralmente não é preenchido— use a coluna SHA1 quando disponível.</span><span class="sxs-lookup"><span data-stu-id="29f85-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="29f85-134">int</span><span class="sxs-lookup"><span data-stu-id="29f85-134">int</span></span> | <span data-ttu-id="29f85-135">Tamanho do arquivo em bytes</span><span class="sxs-lookup"><span data-stu-id="29f85-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="29f85-136">string</span><span class="sxs-lookup"><span data-stu-id="29f85-136">string</span></span> | <span data-ttu-id="29f85-137">Família de malware em que o arquivo ou processo suspeito ou mal-intencionado foi classificado</span><span class="sxs-lookup"><span data-stu-id="29f85-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="29f85-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29f85-138">string</span></span> | <span data-ttu-id="29f85-139">Endereço IP que estava sendo conectado ao</span><span class="sxs-lookup"><span data-stu-id="29f85-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="29f85-140">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29f85-140">string</span></span> | <span data-ttu-id="29f85-141">URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à</span><span class="sxs-lookup"><span data-stu-id="29f85-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="29f85-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29f85-142">string</span></span> | <span data-ttu-id="29f85-143">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="29f85-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="29f85-144">string</span><span class="sxs-lookup"><span data-stu-id="29f85-144">string</span></span> | <span data-ttu-id="29f85-145">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="29f85-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="29f85-146">string</span><span class="sxs-lookup"><span data-stu-id="29f85-146">string</span></span> | <span data-ttu-id="29f85-147">Identificador de Segurança (SID) da conta</span><span class="sxs-lookup"><span data-stu-id="29f85-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="29f85-148">string</span><span class="sxs-lookup"><span data-stu-id="29f85-148">string</span></span> | <span data-ttu-id="29f85-149">Identificador exclusivo da conta no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="29f85-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountUpn` | <span data-ttu-id="29f85-150">string</span><span class="sxs-lookup"><span data-stu-id="29f85-150">string</span></span> | <span data-ttu-id="29f85-151">Nome principal do usuário (UPN) da conta</span><span class="sxs-lookup"><span data-stu-id="29f85-151">User principal name (UPN) of the account</span></span> |
| `DeviceId` | <span data-ttu-id="29f85-152">string</span><span class="sxs-lookup"><span data-stu-id="29f85-152">string</span></span> | <span data-ttu-id="29f85-153">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="29f85-153">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="29f85-154">string</span><span class="sxs-lookup"><span data-stu-id="29f85-154">string</span></span> | <span data-ttu-id="29f85-155">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="29f85-155">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="29f85-156">string</span><span class="sxs-lookup"><span data-stu-id="29f85-156">string</span></span> | <span data-ttu-id="29f85-157">Endereço IP atribuído ao dispositivo local usado durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="29f85-157">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="29f85-158">string</span><span class="sxs-lookup"><span data-stu-id="29f85-158">string</span></span> | <span data-ttu-id="29f85-159">Identificador exclusivo do email, gerado pelo Office 365</span><span class="sxs-lookup"><span data-stu-id="29f85-159">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="29f85-160">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29f85-160">string</span></span> | <span data-ttu-id="29f85-161">Assunto do email</span><span class="sxs-lookup"><span data-stu-id="29f85-161">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="29f85-162">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29f85-162">string</span></span> | <span data-ttu-id="29f85-163">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="29f85-163">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="29f85-164">string</span><span class="sxs-lookup"><span data-stu-id="29f85-164">string</span></span> | <span data-ttu-id="29f85-165">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="29f85-165">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="29f85-166">string</span><span class="sxs-lookup"><span data-stu-id="29f85-166">string</span></span> | <span data-ttu-id="29f85-167">Linha de comando usada para criar o novo processo</span><span class="sxs-lookup"><span data-stu-id="29f85-167">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="29f85-168">string</span><span class="sxs-lookup"><span data-stu-id="29f85-168">string</span></span> | <span data-ttu-id="29f85-169">Informações adicionais sobre o evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="29f85-169">Additional information about the event in JSON array format</span></span> |
| `RegistryKey` |<span data-ttu-id="29f85-170">string</span><span class="sxs-lookup"><span data-stu-id="29f85-170">string</span></span> | <span data-ttu-id="29f85-171">Chave do Registro a que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="29f85-171">Registry key that the recorded action was applied to</span></span> |
| `RegistryValueName` |<span data-ttu-id="29f85-172">string</span><span class="sxs-lookup"><span data-stu-id="29f85-172">string</span></span> | <span data-ttu-id="29f85-173">Nome do valor do Registro ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="29f85-173">Name of the registry value that the recorded action was applied to</span></span> |
| `RegistryValueData` |<span data-ttu-id="29f85-174">string</span><span class="sxs-lookup"><span data-stu-id="29f85-174">string</span></span> | <span data-ttu-id="29f85-175">Dados do valor do Registro ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="29f85-175">Data of the registry value that the recorded action was applied to</span></span> |

## <a name="related-topics"></a><span data-ttu-id="29f85-176">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="29f85-176">Related topics</span></span>
- [<span data-ttu-id="29f85-177">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="29f85-177">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="29f85-178">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="29f85-178">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="29f85-179">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="29f85-179">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="29f85-180">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="29f85-180">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="29f85-181">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="29f85-181">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="29f85-182">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="29f85-182">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
