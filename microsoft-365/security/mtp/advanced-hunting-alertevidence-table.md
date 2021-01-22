---
title: Tabela AlertEvidence no esquema de busca avançada
description: Saiba mais sobre as informações associadas a alertas na tabela AlertEvidence do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AlertInfo, alerta, entidades, evidências, arquivo, endereço IP, dispositivo, computador, usuário, conta
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c01b0aae1eff3d9b4add632aff0f13cb56941a30
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932293"
---
# <a name="alertevidence"></a><span data-ttu-id="6009d-104">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="6009d-104">AlertEvidence</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6009d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6009d-105">**Applies to:**</span></span>
- <span data-ttu-id="6009d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6009d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6009d-107">A tabela no esquema de busca avançada contém informações sobre várias entidades ( arquivos, endereços IP, URLs, usuários ou dispositivos ) associadas a alertas do Microsoft Defender para Ponto de `AlertEvidence` Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6009d-107">The `AlertEvidence` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about various entities—files, IP addresses, URLs, users, or devices—associated with alerts from Microsoft  Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity.</span></span> <span data-ttu-id="6009d-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="6009d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="6009d-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6009d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6009d-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="6009d-110">Column name</span></span> | <span data-ttu-id="6009d-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="6009d-111">Data type</span></span> | <span data-ttu-id="6009d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="6009d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6009d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="6009d-113">datetime</span></span> | <span data-ttu-id="6009d-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="6009d-114">Date and time when the event was recorded</span></span> |
| `AlertId` | <span data-ttu-id="6009d-115">string</span><span class="sxs-lookup"><span data-stu-id="6009d-115">string</span></span> | <span data-ttu-id="6009d-116">Identificador exclusivo do alerta.</span><span class="sxs-lookup"><span data-stu-id="6009d-116">Unique identifier for the alert</span></span> |
| `ServiceSource` | <span data-ttu-id="6009d-117">string</span><span class="sxs-lookup"><span data-stu-id="6009d-117">string</span></span> | <span data-ttu-id="6009d-118">Produto ou serviço que forneceu as informações de alerta</span><span class="sxs-lookup"><span data-stu-id="6009d-118">Product or service that provided the alert information</span></span> |
| `EntityType` | <span data-ttu-id="6009d-119">string</span><span class="sxs-lookup"><span data-stu-id="6009d-119">string</span></span> | <span data-ttu-id="6009d-120">Tipo de objeto, como um arquivo, um processo, um dispositivo ou um usuário</span><span class="sxs-lookup"><span data-stu-id="6009d-120">Type of object, such as a file, a process, a device, or a user</span></span> |
| `EvidenceRole` | <span data-ttu-id="6009d-121">string</span><span class="sxs-lookup"><span data-stu-id="6009d-121">string</span></span> | <span data-ttu-id="6009d-122">Como a entidade está envolvida em um alerta, indicando se ela é impactada ou está simplesmente relacionada</span><span class="sxs-lookup"><span data-stu-id="6009d-122">How the entity is involved in an alert, indicating whether it is impacted or is merely related</span></span> |
| `EvidenceDirection` | <span data-ttu-id="6009d-123">string</span><span class="sxs-lookup"><span data-stu-id="6009d-123">string</span></span> | <span data-ttu-id="6009d-124">Indica se a entidade é a origem ou o destino de uma conexão de rede</span><span class="sxs-lookup"><span data-stu-id="6009d-124">Indicates whether the entity is the source or the destination of a network connection</span></span> |
| `FileName` | <span data-ttu-id="6009d-125">string</span><span class="sxs-lookup"><span data-stu-id="6009d-125">string</span></span> | <span data-ttu-id="6009d-126">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="6009d-126">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="6009d-127">string</span><span class="sxs-lookup"><span data-stu-id="6009d-127">string</span></span> | <span data-ttu-id="6009d-128">Pasta que contém o arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="6009d-128">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="6009d-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6009d-129">string</span></span> | <span data-ttu-id="6009d-130">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="6009d-130">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="6009d-131">string</span><span class="sxs-lookup"><span data-stu-id="6009d-131">string</span></span> | <span data-ttu-id="6009d-132">SHA-256 do arquivo ao qual a ação gravada foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="6009d-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="6009d-133">Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível.</span><span class="sxs-lookup"><span data-stu-id="6009d-133">This field is usually not populated—use the SHA1 column when available.</span></span> |
| `FileSize` | <span data-ttu-id="6009d-134">int</span><span class="sxs-lookup"><span data-stu-id="6009d-134">int</span></span> | <span data-ttu-id="6009d-135">Tamanho do arquivo em bytes</span><span class="sxs-lookup"><span data-stu-id="6009d-135">Size of the file in bytes</span></span> |
| `ThreatFamily` | <span data-ttu-id="6009d-136">string</span><span class="sxs-lookup"><span data-stu-id="6009d-136">string</span></span> | <span data-ttu-id="6009d-137">Família de malware em que o arquivo ou processo suspeito ou mal-intencionado foi classificado</span><span class="sxs-lookup"><span data-stu-id="6009d-137">Malware family that the suspicious or malicious file or process has been classified under</span></span> |
| `RemoteIP` | <span data-ttu-id="6009d-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6009d-138">string</span></span> | <span data-ttu-id="6009d-139">Endereço IP que estava sendo conectado ao</span><span class="sxs-lookup"><span data-stu-id="6009d-139">IP address that was being connected to</span></span> |
| `RemoteUrl` | <span data-ttu-id="6009d-140">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6009d-140">string</span></span> | <span data-ttu-id="6009d-141">URL ou FQDN (nome de domínio totalmente qualificado) que estava sendo conectado à</span><span class="sxs-lookup"><span data-stu-id="6009d-141">URL or fully qualified domain name (FQDN) that was being connected to</span></span> |
| `AccountName` | <span data-ttu-id="6009d-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6009d-142">string</span></span> | <span data-ttu-id="6009d-143">Nome de usuário da conta</span><span class="sxs-lookup"><span data-stu-id="6009d-143">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6009d-144">string</span><span class="sxs-lookup"><span data-stu-id="6009d-144">string</span></span> | <span data-ttu-id="6009d-145">Domínio da conta</span><span class="sxs-lookup"><span data-stu-id="6009d-145">Domain of the account</span></span> |
| `AccountSid` | <span data-ttu-id="6009d-146">string</span><span class="sxs-lookup"><span data-stu-id="6009d-146">string</span></span> | <span data-ttu-id="6009d-147">Sid (Identificador de Segurança) da conta</span><span class="sxs-lookup"><span data-stu-id="6009d-147">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6009d-148">string</span><span class="sxs-lookup"><span data-stu-id="6009d-148">string</span></span> | <span data-ttu-id="6009d-149">Identificador exclusivo da conta no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6009d-149">Unique identifier for the account in Azure Active Directory</span></span> |
| `DeviceId` | <span data-ttu-id="6009d-150">string</span><span class="sxs-lookup"><span data-stu-id="6009d-150">string</span></span> | <span data-ttu-id="6009d-151">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="6009d-151">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="6009d-152">string</span><span class="sxs-lookup"><span data-stu-id="6009d-152">string</span></span> | <span data-ttu-id="6009d-153">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="6009d-153">Fully qualified domain name (FQDN) of the machine</span></span> |
| `LocalIP` | <span data-ttu-id="6009d-154">string</span><span class="sxs-lookup"><span data-stu-id="6009d-154">string</span></span> | <span data-ttu-id="6009d-155">Endereço IP atribuído ao dispositivo local usado durante a comunicação</span><span class="sxs-lookup"><span data-stu-id="6009d-155">IP address assigned to the local device used during communication</span></span> |
| `NetworkMessageId` | <span data-ttu-id="6009d-156">string</span><span class="sxs-lookup"><span data-stu-id="6009d-156">string</span></span> | <span data-ttu-id="6009d-157">Identificador exclusivo do email, gerado pelo Office 365</span><span class="sxs-lookup"><span data-stu-id="6009d-157">Unique identifier for the email, generated by Office 365</span></span> |
| `EmailSubject` | <span data-ttu-id="6009d-158">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6009d-158">string</span></span> | <span data-ttu-id="6009d-159">Assunto do email</span><span class="sxs-lookup"><span data-stu-id="6009d-159">Subject of the email</span></span> |
| `ApplicationId` | <span data-ttu-id="6009d-160">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6009d-160">string</span></span> | <span data-ttu-id="6009d-161">Identificador exclusivo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="6009d-161">Unique identifier for the application</span></span> |
| `Application` | <span data-ttu-id="6009d-162">string</span><span class="sxs-lookup"><span data-stu-id="6009d-162">string</span></span> | <span data-ttu-id="6009d-163">Aplicativo que realizou a ação gravada</span><span class="sxs-lookup"><span data-stu-id="6009d-163">Application that performed the recorded action</span></span> |
| `ProcessCommandLine` | <span data-ttu-id="6009d-164">string</span><span class="sxs-lookup"><span data-stu-id="6009d-164">string</span></span> | <span data-ttu-id="6009d-165">Linha de comando usada para criar o novo processo</span><span class="sxs-lookup"><span data-stu-id="6009d-165">Command line used to create the new process</span></span> |
| `AdditionalFields` | <span data-ttu-id="6009d-166">string</span><span class="sxs-lookup"><span data-stu-id="6009d-166">string</span></span> | <span data-ttu-id="6009d-167">Informações adicionais sobre o evento no formato de matriz JSON</span><span class="sxs-lookup"><span data-stu-id="6009d-167">Additional information about the event in JSON array format</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6009d-168">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6009d-168">Related topics</span></span>
- [<span data-ttu-id="6009d-169">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="6009d-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6009d-170">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="6009d-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6009d-171">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="6009d-171">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6009d-172">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="6009d-172">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6009d-173">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="6009d-173">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6009d-174">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="6009d-174">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
