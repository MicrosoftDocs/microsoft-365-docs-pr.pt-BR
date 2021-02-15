---
title: Função FileProfile() em busca avançada do Microsoft 365 Defender
description: Saiba como usar o FileProfile() para enriquecer informações sobre arquivos em seus resultados de consulta de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, FileProfile, perfil de arquivo, função, enriquecimento
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
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929545"
---
# <a name="fileprofile"></a><span data-ttu-id="65d27-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="65d27-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="65d27-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="65d27-105">**Applies to:**</span></span>
- <span data-ttu-id="65d27-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65d27-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="65d27-107">A função é uma função de enriquecimento na busca avançada que adiciona os `FileProfile()` seguintes dados aos arquivos encontrados pela consulta. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="65d27-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="65d27-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="65d27-108">Column</span></span> | <span data-ttu-id="65d27-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="65d27-109">Data type</span></span> | <span data-ttu-id="65d27-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="65d27-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="65d27-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="65d27-111">SHA1</span></span> | <span data-ttu-id="65d27-112">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="65d27-112">string</span></span> | <span data-ttu-id="65d27-113">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="65d27-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="65d27-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="65d27-114">SHA256</span></span> | <span data-ttu-id="65d27-115">string</span><span class="sxs-lookup"><span data-stu-id="65d27-115">string</span></span> | <span data-ttu-id="65d27-116">SHA-256 do arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="65d27-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="65d27-117">MD5</span><span class="sxs-lookup"><span data-stu-id="65d27-117">MD5</span></span> | <span data-ttu-id="65d27-118">string</span><span class="sxs-lookup"><span data-stu-id="65d27-118">string</span></span> | <span data-ttu-id="65d27-119">Hash MD5 do arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="65d27-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="65d27-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="65d27-120">FileSize</span></span> | <span data-ttu-id="65d27-121">int</span><span class="sxs-lookup"><span data-stu-id="65d27-121">int</span></span> | <span data-ttu-id="65d27-122">Tamanho do arquivo em bytes</span><span class="sxs-lookup"><span data-stu-id="65d27-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="65d27-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="65d27-123">GlobalPrevalence</span></span> | <span data-ttu-id="65d27-124">int</span><span class="sxs-lookup"><span data-stu-id="65d27-124">int</span></span> | <span data-ttu-id="65d27-125">Número de instâncias da entidade observada pela Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="65d27-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="65d27-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="65d27-126">GlobalFirstSeen</span></span> | <span data-ttu-id="65d27-127">datetime</span><span class="sxs-lookup"><span data-stu-id="65d27-127">datetime</span></span> | <span data-ttu-id="65d27-128">Data e hora em que a entidade foi observada pela primeira vez pela Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="65d27-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="65d27-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="65d27-129">GlobalLastSeen</span></span> | <span data-ttu-id="65d27-130">datetime</span><span class="sxs-lookup"><span data-stu-id="65d27-130">datetime</span></span> | <span data-ttu-id="65d27-131">Data e hora em que a entidade foi observada pela última vez pela Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="65d27-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="65d27-132">Signante</span><span class="sxs-lookup"><span data-stu-id="65d27-132">Signer</span></span> | <span data-ttu-id="65d27-133">string</span><span class="sxs-lookup"><span data-stu-id="65d27-133">string</span></span> | <span data-ttu-id="65d27-134">Informações sobre o signante do arquivo</span><span class="sxs-lookup"><span data-stu-id="65d27-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="65d27-135">Emissor</span><span class="sxs-lookup"><span data-stu-id="65d27-135">Issuer</span></span> | <span data-ttu-id="65d27-136">string</span><span class="sxs-lookup"><span data-stu-id="65d27-136">string</span></span> | <span data-ttu-id="65d27-137">Informações sobre a autoridade de certificação (CA) de emissão</span><span class="sxs-lookup"><span data-stu-id="65d27-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="65d27-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="65d27-138">SignerHash</span></span> | <span data-ttu-id="65d27-139">string</span><span class="sxs-lookup"><span data-stu-id="65d27-139">string</span></span> | <span data-ttu-id="65d27-140">Valor de hash exclusivo que identifica o signante</span><span class="sxs-lookup"><span data-stu-id="65d27-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="65d27-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="65d27-141">IsCertificateValid</span></span> | <span data-ttu-id="65d27-142">booliano</span><span class="sxs-lookup"><span data-stu-id="65d27-142">boolean</span></span> | <span data-ttu-id="65d27-143">Se o certificado usado para assinar o arquivo é válido</span><span class="sxs-lookup"><span data-stu-id="65d27-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="65d27-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="65d27-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="65d27-145">booliano</span><span class="sxs-lookup"><span data-stu-id="65d27-145">boolean</span></span> | <span data-ttu-id="65d27-146">Indica se o signante do certificado raiz é a Microsoft</span><span class="sxs-lookup"><span data-stu-id="65d27-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="65d27-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="65d27-147">IsExecutable</span></span> | <span data-ttu-id="65d27-148">booliano</span><span class="sxs-lookup"><span data-stu-id="65d27-148">boolean</span></span> | <span data-ttu-id="65d27-149">Se o arquivo é um arquivo PE (Portable Executable)</span><span class="sxs-lookup"><span data-stu-id="65d27-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="65d27-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="65d27-150">ThreatName</span></span> | <span data-ttu-id="65d27-151">string</span><span class="sxs-lookup"><span data-stu-id="65d27-151">string</span></span> | <span data-ttu-id="65d27-152">Nome da detecção de qualquer malware ou outras ameaças encontradas</span><span class="sxs-lookup"><span data-stu-id="65d27-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="65d27-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="65d27-153">Publisher</span></span> | <span data-ttu-id="65d27-154">string</span><span class="sxs-lookup"><span data-stu-id="65d27-154">string</span></span> | <span data-ttu-id="65d27-155">Nome da organização que publicou o arquivo</span><span class="sxs-lookup"><span data-stu-id="65d27-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="65d27-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="65d27-156">SoftwareName</span></span> | <span data-ttu-id="65d27-157">string</span><span class="sxs-lookup"><span data-stu-id="65d27-157">string</span></span> | <span data-ttu-id="65d27-158">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="65d27-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="65d27-159">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="65d27-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="65d27-160">Argumentos</span><span class="sxs-lookup"><span data-stu-id="65d27-160">Arguments</span></span>

- <span data-ttu-id="65d27-161">**x**— coluna de ID do arquivo a ser usada: , ou ; a função usa `SHA1` se não `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especificada</span><span class="sxs-lookup"><span data-stu-id="65d27-161">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="65d27-162">**y**— limite ao número de registros a enriquecer, 1 a 1000; função usa 100 se não especificado</span><span class="sxs-lookup"><span data-stu-id="65d27-162">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="65d27-163">Exemplos</span><span class="sxs-lookup"><span data-stu-id="65d27-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="65d27-164">Projetar somente a coluna SHA1 e enriqueci-la</span><span class="sxs-lookup"><span data-stu-id="65d27-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="65d27-165">Enriquecer os primeiros 500 registros e listar arquivos de baixa prevalência</span><span class="sxs-lookup"><span data-stu-id="65d27-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="65d27-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="65d27-166">Related topics</span></span>
- [<span data-ttu-id="65d27-167">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="65d27-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="65d27-168">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="65d27-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="65d27-169">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="65d27-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="65d27-170">Obter mais exemplos de consulta</span><span class="sxs-lookup"><span data-stu-id="65d27-170">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
