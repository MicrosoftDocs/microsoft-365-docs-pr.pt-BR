---
title: Função fileprofile () em busca avançada para a proteção contra ameaças da Microsoft
description: Saiba como usar o fileprofile () para enriquecer informações sobre arquivos em seus resultados de consulta de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, fileprofile, perfil de arquivo, função, enriquecimento
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
ms.openlocfilehash: 6465821ff1b8e8ea23cc5cf6b205f65a483bbe82
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204942"
---
# <a name="fileprofile"></a><span data-ttu-id="ec0f7-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="ec0f7-104">FileProfile()</span></span>

<span data-ttu-id="ec0f7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ec0f7-105">**Applies to:**</span></span>
- <span data-ttu-id="ec0f7-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ec0f7-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ec0f7-107">A `FileProfile()` função é uma função de enriquecimento em [busca avançada](advanced-hunting-overview.md) que adiciona os dados a seguir a arquivos encontrados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="ec0f7-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="ec0f7-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="ec0f7-108">Column</span></span> | <span data-ttu-id="ec0f7-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ec0f7-109">Data type</span></span> | <span data-ttu-id="ec0f7-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec0f7-110">Description</span></span> |
|------------|-------------|-------------|
| <span data-ttu-id="ec0f7-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="ec0f7-111">SHA1</span></span> | <span data-ttu-id="ec0f7-112">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ec0f7-112">string</span></span> | <span data-ttu-id="ec0f7-113">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="ec0f7-113">SHA-1 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="ec0f7-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="ec0f7-114">SHA256</span></span> | <span data-ttu-id="ec0f7-115">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ec0f7-115">string</span></span> | <span data-ttu-id="ec0f7-116">SHA-256 do arquivo ao qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="ec0f7-116">SHA-256 of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="ec0f7-117">MD5</span><span class="sxs-lookup"><span data-stu-id="ec0f7-117">MD5</span></span> | <span data-ttu-id="ec0f7-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ec0f7-118">string</span></span> | <span data-ttu-id="ec0f7-119">Hash MD5 do arquivo ao qual a ação registrada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="ec0f7-119">MD5 hash of the file that the recorded action was applied to</span></span> |
| <span data-ttu-id="ec0f7-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="ec0f7-120">FileSize</span></span> | <span data-ttu-id="ec0f7-121">int</span><span class="sxs-lookup"><span data-stu-id="ec0f7-121">int</span></span> | <span data-ttu-id="ec0f7-122">Tamanho do arquivo em bytes</span><span class="sxs-lookup"><span data-stu-id="ec0f7-122">Size of the file in bytes</span></span> |
| <span data-ttu-id="ec0f7-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="ec0f7-123">GlobalPrevalence</span></span> | <span data-ttu-id="ec0f7-124">int</span><span class="sxs-lookup"><span data-stu-id="ec0f7-124">int</span></span> | <span data-ttu-id="ec0f7-125">Número de instâncias da entidade observadas pela Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="ec0f7-125">Number of instances of the entity observed by Microsoft globally</span></span> |
| <span data-ttu-id="ec0f7-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="ec0f7-126">GlobalFirstSeen</span></span> | <span data-ttu-id="ec0f7-127">datetime</span><span class="sxs-lookup"><span data-stu-id="ec0f7-127">datetime</span></span> | <span data-ttu-id="ec0f7-128">Data e hora em que a entidade foi observada pela primeira vez pela Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="ec0f7-128">Date and time when the entity was first observed by Microsoft globally</span></span> |
| <span data-ttu-id="ec0f7-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="ec0f7-129">GlobalLastSeen</span></span> | <span data-ttu-id="ec0f7-130">datetime</span><span class="sxs-lookup"><span data-stu-id="ec0f7-130">datetime</span></span> | <span data-ttu-id="ec0f7-131">Data e hora da última vez em que a entidade foi observada pela Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="ec0f7-131">Date and time when the entity was last observed by Microsoft globally</span></span> |
| <span data-ttu-id="ec0f7-132">Signatário</span><span class="sxs-lookup"><span data-stu-id="ec0f7-132">Signer</span></span> | <span data-ttu-id="ec0f7-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ec0f7-133">string</span></span> | <span data-ttu-id="ec0f7-134">Informações sobre o signatário do arquivo</span><span class="sxs-lookup"><span data-stu-id="ec0f7-134">Information about the signer of the file</span></span> |
| <span data-ttu-id="ec0f7-135">Emissor</span><span class="sxs-lookup"><span data-stu-id="ec0f7-135">Issuer</span></span> | <span data-ttu-id="ec0f7-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ec0f7-136">string</span></span> | <span data-ttu-id="ec0f7-137">Informações sobre a CA (autoridade de certificação emissora)</span><span class="sxs-lookup"><span data-stu-id="ec0f7-137">Information about the issuing certificate authority (CA)</span></span> |
| <span data-ttu-id="ec0f7-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="ec0f7-138">SignerHash</span></span> | <span data-ttu-id="ec0f7-139">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ec0f7-139">string</span></span> | <span data-ttu-id="ec0f7-140">Valor de hash exclusivo que identifica o signatário</span><span class="sxs-lookup"><span data-stu-id="ec0f7-140">Unique hash value identifying the signer</span></span> |
| <span data-ttu-id="ec0f7-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="ec0f7-141">IsCertificateValid</span></span> | <span data-ttu-id="ec0f7-142">booliano</span><span class="sxs-lookup"><span data-stu-id="ec0f7-142">boolean</span></span> | <span data-ttu-id="ec0f7-143">Se o certificado usado para assinar o arquivo é válido</span><span class="sxs-lookup"><span data-stu-id="ec0f7-143">Whether the certificate used to sign the file is valid</span></span> |
| <span data-ttu-id="ec0f7-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="ec0f7-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="ec0f7-145">booliano</span><span class="sxs-lookup"><span data-stu-id="ec0f7-145">boolean</span></span> | <span data-ttu-id="ec0f7-146">Indica se o signatário do certificado raiz é o Microsoft</span><span class="sxs-lookup"><span data-stu-id="ec0f7-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| <span data-ttu-id="ec0f7-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="ec0f7-147">IsExecutable</span></span> | <span data-ttu-id="ec0f7-148">booliano</span><span class="sxs-lookup"><span data-stu-id="ec0f7-148">boolean</span></span> | <span data-ttu-id="ec0f7-149">Se o arquivo é um arquivo executável portátil (PE)</span><span class="sxs-lookup"><span data-stu-id="ec0f7-149">Whether the file is a Portable Executable (PE) file</span></span> |
| <span data-ttu-id="ec0f7-150">Threatname</span><span class="sxs-lookup"><span data-stu-id="ec0f7-150">ThreatName</span></span> | <span data-ttu-id="ec0f7-151">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ec0f7-151">string</span></span> | <span data-ttu-id="ec0f7-152">Nome da detecção de qualquer malware ou outra ameaça encontrada</span><span class="sxs-lookup"><span data-stu-id="ec0f7-152">Detection name for any malware or other threats found</span></span> |
| <span data-ttu-id="ec0f7-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="ec0f7-153">Publisher</span></span> | <span data-ttu-id="ec0f7-154">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ec0f7-154">string</span></span> | <span data-ttu-id="ec0f7-155">Nome da organização que publicou o arquivo</span><span class="sxs-lookup"><span data-stu-id="ec0f7-155">Name of the organization that published the file</span></span> |
| <span data-ttu-id="ec0f7-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="ec0f7-156">SoftwareName</span></span> | <span data-ttu-id="ec0f7-157">string</span><span class="sxs-lookup"><span data-stu-id="ec0f7-157">string</span></span> | <span data-ttu-id="ec0f7-158">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="ec0f7-158">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="ec0f7-159">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ec0f7-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="ec0f7-160">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ec0f7-160">Arguments</span></span>

- <span data-ttu-id="ec0f7-161">**x** — coluna de ID de arquivo para usar: `SHA1` , `SHA256` , `InitiatingProcessSHA1` ou `InitiatingProcessSHA256` ; função usa `SHA1` se não especificado</span><span class="sxs-lookup"><span data-stu-id="ec0f7-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="ec0f7-162">**y** – limitar o número de registros a enriquecer, 1-1000; função usa 100 se não especificado</span><span class="sxs-lookup"><span data-stu-id="ec0f7-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="ec0f7-163">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ec0f7-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="ec0f7-164">Projetar somente a coluna SHA1 e enriquecer</span><span class="sxs-lookup"><span data-stu-id="ec0f7-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="ec0f7-165">Enriquecer os primeiros 500 registros e listar os arquivos de prevalência de baixa</span><span class="sxs-lookup"><span data-stu-id="ec0f7-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="ec0f7-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ec0f7-166">Related topics</span></span>
- [<span data-ttu-id="ec0f7-167">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="ec0f7-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ec0f7-168">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="ec0f7-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ec0f7-169">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="ec0f7-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)