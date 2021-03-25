---
title: Tabela DeviceFileEvents no esquema de busca avançado
description: Saiba mais sobre eventos relacionados a arquivos na tabela DeviceFileEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, filecreationevents, DeviceFileEvents, arquivos, caminho, hash, sha1, sha256, md5
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
ms.openlocfilehash: 10009edab33d04ca01da9459c394634d0622cf3d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053219"
---
# <a name="devicefileevents"></a><span data-ttu-id="a89c6-104">DeviceFileEvents</span><span class="sxs-lookup"><span data-stu-id="a89c6-104">DeviceFileEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a89c6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a89c6-105">**Applies to:**</span></span>
- <span data-ttu-id="a89c6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a89c6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="a89c6-107">A tabela no esquema de busca avançada contém informações sobre a criação, modificação e outros eventos do sistema `DeviceFileEvents` de arquivos. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a89c6-107">The `DeviceFileEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file creation, modification, and other file system events.</span></span> <span data-ttu-id="a89c6-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="a89c6-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="a89c6-109">Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.</span><span class="sxs-lookup"><span data-stu-id="a89c6-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="a89c6-110">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a89c6-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a89c6-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="a89c6-111">Column name</span></span> | <span data-ttu-id="a89c6-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="a89c6-112">Data type</span></span> | <span data-ttu-id="a89c6-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="a89c6-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="a89c6-114">datetime</span><span class="sxs-lookup"><span data-stu-id="a89c6-114">datetime</span></span> | <span data-ttu-id="a89c6-115">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="a89c6-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="a89c6-116">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-116">string</span></span> | <span data-ttu-id="a89c6-117">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="a89c6-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="a89c6-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-118">string</span></span> | <span data-ttu-id="a89c6-119">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="a89c6-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `ActionType` | <span data-ttu-id="a89c6-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-120">string</span></span> | <span data-ttu-id="a89c6-121">Tipo de atividade que disparou o evento.</span><span class="sxs-lookup"><span data-stu-id="a89c6-121">Type of activity that triggered the event.</span></span> <span data-ttu-id="a89c6-122">Consulte a [referência de esquema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) no portal para obter detalhes</span><span class="sxs-lookup"><span data-stu-id="a89c6-122">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `FileName` | <span data-ttu-id="a89c6-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-123">string</span></span> | <span data-ttu-id="a89c6-124">Nome do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="a89c6-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="a89c6-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-125">string</span></span> | <span data-ttu-id="a89c6-126">Pasta que contém o arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="a89c6-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="a89c6-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-127">string</span></span> | <span data-ttu-id="a89c6-128">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="a89c6-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="a89c6-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-129">string</span></span> | <span data-ttu-id="a89c6-130">SHA-256 do arquivo ao qual a ação gravada foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="a89c6-130">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="a89c6-131">Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível.</span><span class="sxs-lookup"><span data-stu-id="a89c6-131">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `MD5` | <span data-ttu-id="a89c6-132">string</span><span class="sxs-lookup"><span data-stu-id="a89c6-132">string</span></span> | <span data-ttu-id="a89c6-133">Hash MD5 do arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="a89c6-133">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileOriginUrl` | <span data-ttu-id="a89c6-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-134">string</span></span> | <span data-ttu-id="a89c6-135">URL da qual o arquivo foi baixado</span><span class="sxs-lookup"><span data-stu-id="a89c6-135">URL where the file was downloaded from</span></span> |
| `FileOriginReferrerUrl` | <span data-ttu-id="a89c6-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-136">string</span></span> | <span data-ttu-id="a89c6-137">URL da página da Web que se vincula ao arquivo baixado</span><span class="sxs-lookup"><span data-stu-id="a89c6-137">URL of the web page that links to the downloaded file</span></span> |
| `FileOriginIP` | <span data-ttu-id="a89c6-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-138">string</span></span> | <span data-ttu-id="a89c6-139">Endereço IP de onde o arquivo foi baixado</span><span class="sxs-lookup"><span data-stu-id="a89c6-139">IP address where the file was downloaded from</span></span> |
| `PreviousFolderPath` | <span data-ttu-id="a89c6-140">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-140">string</span></span> | <span data-ttu-id="a89c6-141">Pasta original que contém o arquivo antes da ação gravada ser aplicada</span><span class="sxs-lookup"><span data-stu-id="a89c6-141">Original folder containing the file before the recorded action was applied</span></span> |
| `PreviousFileName` | <span data-ttu-id="a89c6-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-142">string</span></span> | <span data-ttu-id="a89c6-143">Nome original do arquivo que foi renomeado como resultado da ação</span><span class="sxs-lookup"><span data-stu-id="a89c6-143">Original name of the file that was renamed as a result of the action</span></span> |
| `FileSize` | <span data-ttu-id="a89c6-144">long</span><span class="sxs-lookup"><span data-stu-id="a89c6-144">long</span></span> | <span data-ttu-id="a89c6-145">Tamanho do arquivo em bytes</span><span class="sxs-lookup"><span data-stu-id="a89c6-145">Size of the file in bytes</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="a89c6-146">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-146">string</span></span> | <span data-ttu-id="a89c6-147">Domínio da conta que correu o processo responsável pelo evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-147">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="a89c6-148">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-148">string</span></span> | <span data-ttu-id="a89c6-149">Nome de usuário da conta que correu o processo responsável pelo evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-149">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="a89c6-150">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-150">string</span></span> | <span data-ttu-id="a89c6-151">Identificador de Segurança (SID) da conta que correu o processo responsável pelo evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-151">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountUpn` | <span data-ttu-id="a89c6-152">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-152">string</span></span> | <span data-ttu-id="a89c6-153">Nome principal do usuário (UPN) da conta que correu o processo responsável pelo evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-153">User principal name (UPN) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="a89c6-154">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-154">string</span></span> | <span data-ttu-id="a89c6-155">Hash MD5 do processo (arquivo de imagem) que iniciou o evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-155">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="a89c6-156">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-156">string</span></span> | <span data-ttu-id="a89c6-157">SHA-1 do processo (arquivo de imagem) que iniciou o evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-157">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessSHA256` | <span data-ttu-id="a89c6-158">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-158">string</span></span> | <span data-ttu-id="a89c6-159">SHA-256 do processo (arquivo de imagem) que iniciou o evento.</span><span class="sxs-lookup"><span data-stu-id="a89c6-159">SHA-256 of the process (image file) that initiated the event.</span></span> <span data-ttu-id="a89c6-160">Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível.</span><span class="sxs-lookup"><span data-stu-id="a89c6-160">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="a89c6-161">string</span><span class="sxs-lookup"><span data-stu-id="a89c6-161">string</span></span> | <span data-ttu-id="a89c6-162">Pasta contendo o processo (arquivo de imagem) que iniciou o evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-162">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="a89c6-163">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-163">string</span></span> | <span data-ttu-id="a89c6-164">Nome do processo que iniciou o evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-164">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="a89c6-165">int</span><span class="sxs-lookup"><span data-stu-id="a89c6-165">int</span></span> | <span data-ttu-id="a89c6-166">ID do processo (PID) do processo que iniciou o evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-166">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="a89c6-167">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-167">string</span></span> | <span data-ttu-id="a89c6-168">Linha de comando usada para executar o processo que iniciou o evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-168">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="a89c6-169">datetime</span><span class="sxs-lookup"><span data-stu-id="a89c6-169">datetime</span></span> | <span data-ttu-id="a89c6-170">Data e hora em que o processo que iniciou o evento foi iniciado</span><span class="sxs-lookup"><span data-stu-id="a89c6-170">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="a89c6-171">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-171">string</span></span> | <span data-ttu-id="a89c6-172">Nível de integridade do processo que iniciou o evento.</span><span class="sxs-lookup"><span data-stu-id="a89c6-172">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="a89c6-173">O Windows atribui níveis de integridade a processos com base em determinadas características, como se eles foram lançados a partir de um download da Internet.</span><span class="sxs-lookup"><span data-stu-id="a89c6-173">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="a89c6-174">Esses níveis de integridade influenciam permissões para recursos</span><span class="sxs-lookup"><span data-stu-id="a89c6-174">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="a89c6-175">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-175">string</span></span> | <span data-ttu-id="a89c6-176">Tipo de token que indica a presença ou ausência da elevação de privilégio de Controle de Acesso para Usuário (UAC) aplicada ao processo que iniciou o evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-176">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="a89c6-177">int</span><span class="sxs-lookup"><span data-stu-id="a89c6-177">int</span></span> | <span data-ttu-id="a89c6-178">ID do processo (PID) do processo pai que gerou o processo responsável pelo evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-178">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="a89c6-179">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-179">string</span></span> | <span data-ttu-id="a89c6-180">Nome do processo pai que gerou o processo responsável pelo evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-180">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="a89c6-181">datetime</span><span class="sxs-lookup"><span data-stu-id="a89c6-181">datetime</span></span> | <span data-ttu-id="a89c6-182">Data e hora em que o pai do processo responsável pelo evento foi iniciado</span><span class="sxs-lookup"><span data-stu-id="a89c6-182">Date and time when the parent of the process responsible for the event was started</span></span> |
| `RequestProtocol` | <span data-ttu-id="a89c6-183">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-183">string</span></span> | <span data-ttu-id="a89c6-184">Protocolo de rede, se aplicável, usado para iniciar a atividade: Desconhecido, Local, SMB ou NFS</span><span class="sxs-lookup"><span data-stu-id="a89c6-184">Network protocol, if applicable, used to initiate the activity: Unknown, Local, SMB, or NFS</span></span> |
| `ShareName` | <span data-ttu-id="a89c6-185">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-185">string</span></span> | <span data-ttu-id="a89c6-186">Nome da pasta compartilhada que contém o arquivo</span><span class="sxs-lookup"><span data-stu-id="a89c6-186">Name of shared folder containing the file</span></span> |
| `RequestSourceIP` | <span data-ttu-id="a89c6-187">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-187">string</span></span> | <span data-ttu-id="a89c6-188">Endereço IPv4 ou IPv6 do dispositivo remoto que iniciou a atividade</span><span class="sxs-lookup"><span data-stu-id="a89c6-188">IPv4 or IPv6 address of the remote device that initiated the activity</span></span> |
| `RequestSourcePort` | <span data-ttu-id="a89c6-189">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-189">string</span></span> | <span data-ttu-id="a89c6-190">Porta de origem no dispositivo remoto que iniciou a atividade</span><span class="sxs-lookup"><span data-stu-id="a89c6-190">Source port on the remote device that initiated the activity</span></span> |
| `RequestAccountName` | <span data-ttu-id="a89c6-191">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-191">string</span></span> | <span data-ttu-id="a89c6-192">Nome de usuário da conta usada para iniciar remotamente a atividade</span><span class="sxs-lookup"><span data-stu-id="a89c6-192">User name of account used to remotely initiate the activity</span></span> |
| `RequestAccountDomain` | <span data-ttu-id="a89c6-193">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-193">string</span></span> | <span data-ttu-id="a89c6-194">Domínio da conta usada para iniciar remotamente a atividade</span><span class="sxs-lookup"><span data-stu-id="a89c6-194">Domain of the account used to remotely initiate the activity</span></span> |
| `RequestAccountSid` | <span data-ttu-id="a89c6-195">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-195">string</span></span> | <span data-ttu-id="a89c6-196">Sid (Identificador de Segurança) da conta usada para iniciar remotamente a atividade</span><span class="sxs-lookup"><span data-stu-id="a89c6-196">Security Identifier (SID) of the account used to remotely initiate the activity</span></span> |
| `ReportId` | <span data-ttu-id="a89c6-197">long</span><span class="sxs-lookup"><span data-stu-id="a89c6-197">long</span></span> | <span data-ttu-id="a89c6-198">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="a89c6-198">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="a89c6-199">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="a89c6-199">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="a89c6-200">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-200">string</span></span> | <span data-ttu-id="a89c6-201">Identificador do contêiner virtualizado usado pelo Application Guard para isolar a atividade do navegador</span><span class="sxs-lookup"><span data-stu-id="a89c6-201">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |
| `AdditionalFields` | <span data-ttu-id="a89c6-202">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-202">string</span></span> | <span data-ttu-id="a89c6-203">Informações adicionais sobre a entidade ou evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-203">Additional information about the entity or event</span></span> |
| `InitiatingProcessFileSize` | <span data-ttu-id="a89c6-204">long</span><span class="sxs-lookup"><span data-stu-id="a89c6-204">long</span></span> | <span data-ttu-id="a89c6-205">Tamanho do arquivo que correu o processo responsável pelo evento</span><span class="sxs-lookup"><span data-stu-id="a89c6-205">Size of the file that ran the process responsible for the event</span></span> |
| `SensitivityLabel` | <span data-ttu-id="a89c6-206">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-206">string</span></span> | <span data-ttu-id="a89c6-207">Rótulo aplicado a um email, arquivo ou outro conteúdo para classificá-lo para proteção de informações</span><span class="sxs-lookup"><span data-stu-id="a89c6-207">Label applied to an email, file, or other content to classify it for information protection</span></span> |
| `SensitivitySubLabel` | <span data-ttu-id="a89c6-208">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a89c6-208">string</span></span> | <span data-ttu-id="a89c6-209">Sub-rótulo aplicado a um email, arquivo ou outro conteúdo para classificá-lo para proteção de informações; os sub-rótulos de sensibilidade são agrupados sob rótulos de sensibilidade, mas são tratados independentemente</span><span class="sxs-lookup"><span data-stu-id="a89c6-209">Sublabel applied to an email, file, or other content to classify it for information protection; sensitivity sublabels are grouped under sensitivity labels but are treated independently</span></span> |
| `IsAzureInfoProtectionApplied` | <span data-ttu-id="a89c6-210">booliano</span><span class="sxs-lookup"><span data-stu-id="a89c6-210">boolean</span></span> | <span data-ttu-id="a89c6-211">Indica se o arquivo é criptografado pela Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="a89c6-211">Indicates whether the file is encrypted by Azure Information Protection</span></span> |

>[!NOTE]
> <span data-ttu-id="a89c6-212">As informações de hash de arquivo sempre serão mostradas quando disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a89c6-212">File hash information will always be shown when it is available.</span></span> <span data-ttu-id="a89c6-213">No entanto, há várias razões possíveis pelas quais um SHA1, SHA256 ou MD5 não pode ser calculado.</span><span class="sxs-lookup"><span data-stu-id="a89c6-213">However, there are several possible reasons why a SHA1, SHA256, or MD5 cannot be calculated.</span></span> <span data-ttu-id="a89c6-214">Por exemplo, o arquivo pode estar localizado no armazenamento remoto, bloqueado por outro processo, compactado ou marcado como virtual.</span><span class="sxs-lookup"><span data-stu-id="a89c6-214">For instance, the file might be located in remote storage, locked by another process, compressed, or marked as virtual.</span></span> <span data-ttu-id="a89c6-215">Nesses cenários, as informações de hash de arquivo aparecem vazias.</span><span class="sxs-lookup"><span data-stu-id="a89c6-215">In these scenarios, the file hash information appears empty.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a89c6-216">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a89c6-216">Related topics</span></span>
- [<span data-ttu-id="a89c6-217">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="a89c6-217">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a89c6-218">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="a89c6-218">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a89c6-219">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="a89c6-219">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a89c6-220">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="a89c6-220">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a89c6-221">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="a89c6-221">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a89c6-222">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="a89c6-222">Apply query best practices</span></span>](advanced-hunting-best-practices.md)