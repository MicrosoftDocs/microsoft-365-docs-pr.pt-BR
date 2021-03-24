---
title: Função FileProfile() em busca avançada do Microsoft Defender para Ponto de Extremidade
description: Saiba como usar o FileProfile() para enriquecer informações sobre arquivos nos resultados avançados da consulta de busca
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, Microsoft Defender ATP, Microsoft Defender para Ponto de Extremidade, Windows Defender, Windows Defender ATP, Windows Defender proteção avançada contra ameaças, pesquisa, consulta, telemetria, referência de esquema, kusto, FileProfile, perfil de arquivo, função, enriquecimento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 668b3fe503268c46e4a1313f0c4cfb8a6a3dd602
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054337"
---
# <a name="fileprofile"></a><span data-ttu-id="b4d9f-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="b4d9f-104">FileProfile()</span></span>

<span data-ttu-id="b4d9f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b4d9f-105">**Applies to:**</span></span>
- [<span data-ttu-id="b4d9f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b4d9f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

<span data-ttu-id="b4d9f-107">A função é uma função de enriquecimento na busca avançada que adiciona os seguintes dados aos `FileProfile()` arquivos encontrados pela consulta. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b4d9f-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

<span data-ttu-id="b4d9f-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="b4d9f-108">Column</span></span> | <span data-ttu-id="b4d9f-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b4d9f-109">Data type</span></span> | <span data-ttu-id="b4d9f-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="b4d9f-110">Description</span></span>
-|-|-
<span data-ttu-id="b4d9f-111">SHA1</span><span class="sxs-lookup"><span data-stu-id="b4d9f-111">SHA1</span></span> | <span data-ttu-id="b4d9f-112">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4d9f-112">string</span></span> | <span data-ttu-id="b4d9f-113">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="b4d9f-113">SHA-1 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="b4d9f-114">SHA256</span><span class="sxs-lookup"><span data-stu-id="b4d9f-114">SHA256</span></span> | <span data-ttu-id="b4d9f-115">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4d9f-115">string</span></span> | <span data-ttu-id="b4d9f-116">SHA-256 do arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="b4d9f-116">SHA-256 of the file that the recorded action was applied to</span></span>
<span data-ttu-id="b4d9f-117">MD5</span><span class="sxs-lookup"><span data-stu-id="b4d9f-117">MD5</span></span> | <span data-ttu-id="b4d9f-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4d9f-118">string</span></span> | <span data-ttu-id="b4d9f-119">Hash MD5 do arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="b4d9f-119">MD5 hash of the file that the recorded action was applied to</span></span>
<span data-ttu-id="b4d9f-120">FileSize</span><span class="sxs-lookup"><span data-stu-id="b4d9f-120">FileSize</span></span> | <span data-ttu-id="b4d9f-121">int</span><span class="sxs-lookup"><span data-stu-id="b4d9f-121">int</span></span> | <span data-ttu-id="b4d9f-122">Tamanho do arquivo em bytes</span><span class="sxs-lookup"><span data-stu-id="b4d9f-122">Size of the file in bytes</span></span>
<span data-ttu-id="b4d9f-123">GlobalPrevalence</span><span class="sxs-lookup"><span data-stu-id="b4d9f-123">GlobalPrevalence</span></span> | <span data-ttu-id="b4d9f-124">int</span><span class="sxs-lookup"><span data-stu-id="b4d9f-124">int</span></span> | <span data-ttu-id="b4d9f-125">Número de instâncias da entidade observadas globalmente pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="b4d9f-125">Number of instances of the entity observed by Microsoft globally</span></span>
<span data-ttu-id="b4d9f-126">GlobalFirstSeen</span><span class="sxs-lookup"><span data-stu-id="b4d9f-126">GlobalFirstSeen</span></span> | <span data-ttu-id="b4d9f-127">datetime</span><span class="sxs-lookup"><span data-stu-id="b4d9f-127">datetime</span></span> | <span data-ttu-id="b4d9f-128">Data e hora em que a entidade foi observada pela primeira vez pela Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="b4d9f-128">Date and time when the entity was first observed by Microsoft globally</span></span>
<span data-ttu-id="b4d9f-129">GlobalLastSeen</span><span class="sxs-lookup"><span data-stu-id="b4d9f-129">GlobalLastSeen</span></span> | <span data-ttu-id="b4d9f-130">datetime</span><span class="sxs-lookup"><span data-stu-id="b4d9f-130">datetime</span></span> | <span data-ttu-id="b4d9f-131">Data e hora em que a entidade foi observada pela última vez pela Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="b4d9f-131">Date and time when the entity was last observed by Microsoft globally</span></span>
<span data-ttu-id="b4d9f-132">Signer</span><span class="sxs-lookup"><span data-stu-id="b4d9f-132">Signer</span></span> | <span data-ttu-id="b4d9f-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4d9f-133">string</span></span> | <span data-ttu-id="b4d9f-134">Informações sobre o signante do arquivo</span><span class="sxs-lookup"><span data-stu-id="b4d9f-134">Information about the signer of the file</span></span>
<span data-ttu-id="b4d9f-135">Emissor</span><span class="sxs-lookup"><span data-stu-id="b4d9f-135">Issuer</span></span> | <span data-ttu-id="b4d9f-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4d9f-136">string</span></span> | <span data-ttu-id="b4d9f-137">Informações sobre a autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="b4d9f-137">Information about the issuing certificate authority (CA)</span></span>
<span data-ttu-id="b4d9f-138">SignerHash</span><span class="sxs-lookup"><span data-stu-id="b4d9f-138">SignerHash</span></span> | <span data-ttu-id="b4d9f-139">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4d9f-139">string</span></span> | <span data-ttu-id="b4d9f-140">Valor de hash exclusivo que identifica o signante</span><span class="sxs-lookup"><span data-stu-id="b4d9f-140">Unique hash value identifying the signer</span></span>
<span data-ttu-id="b4d9f-141">IsCertificateValid</span><span class="sxs-lookup"><span data-stu-id="b4d9f-141">IsCertificateValid</span></span> | <span data-ttu-id="b4d9f-142">booliano</span><span class="sxs-lookup"><span data-stu-id="b4d9f-142">boolean</span></span> | <span data-ttu-id="b4d9f-143">Se o certificado usado para assinar o arquivo é válido</span><span class="sxs-lookup"><span data-stu-id="b4d9f-143">Whether the certificate used to sign the file is valid</span></span>
<span data-ttu-id="b4d9f-144">IsRootSignerMicrosoft</span><span class="sxs-lookup"><span data-stu-id="b4d9f-144">IsRootSignerMicrosoft</span></span> | <span data-ttu-id="b4d9f-145">booliano</span><span class="sxs-lookup"><span data-stu-id="b4d9f-145">boolean</span></span> | <span data-ttu-id="b4d9f-146">Indica se o signante do certificado raiz é a Microsoft</span><span class="sxs-lookup"><span data-stu-id="b4d9f-146">Indicates whether the signer of the root certificate is Microsoft</span></span>
<span data-ttu-id="b4d9f-147">IsExecutable</span><span class="sxs-lookup"><span data-stu-id="b4d9f-147">IsExecutable</span></span> | <span data-ttu-id="b4d9f-148">booliano</span><span class="sxs-lookup"><span data-stu-id="b4d9f-148">boolean</span></span> | <span data-ttu-id="b4d9f-149">Se o arquivo é um arquivo Executável Portátil (PE)</span><span class="sxs-lookup"><span data-stu-id="b4d9f-149">Whether the file is a Portable Executable (PE) file</span></span>
<span data-ttu-id="b4d9f-150">ThreatName</span><span class="sxs-lookup"><span data-stu-id="b4d9f-150">ThreatName</span></span> | <span data-ttu-id="b4d9f-151">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4d9f-151">string</span></span> | <span data-ttu-id="b4d9f-152">Nome da detecção de qualquer malware ou outras ameaças encontradas</span><span class="sxs-lookup"><span data-stu-id="b4d9f-152">Detection name for any malware or other threats found</span></span>
<span data-ttu-id="b4d9f-153">Publisher</span><span class="sxs-lookup"><span data-stu-id="b4d9f-153">Publisher</span></span> | <span data-ttu-id="b4d9f-154">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4d9f-154">string</span></span> | <span data-ttu-id="b4d9f-155">Nome da organização que publicou o arquivo</span><span class="sxs-lookup"><span data-stu-id="b4d9f-155">Name of the organization that published the file</span></span>
<span data-ttu-id="b4d9f-156">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="b4d9f-156">SoftwareName</span></span> | <span data-ttu-id="b4d9f-157">string</span><span class="sxs-lookup"><span data-stu-id="b4d9f-157">string</span></span> | <span data-ttu-id="b4d9f-158">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="b4d9f-158">Name of the software product</span></span>

## <a name="syntax"></a><span data-ttu-id="b4d9f-159">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b4d9f-159">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="b4d9f-160">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b4d9f-160">Arguments</span></span>

- <span data-ttu-id="b4d9f-161">**x** — coluna de ID de arquivo a ser usada: `SHA1` , ou ; a função usa se não `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especificada</span><span class="sxs-lookup"><span data-stu-id="b4d9f-161">**x** — file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1` or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="b4d9f-162">**y** — limite para o número de registros a enriquecer, 1-1000; function usa 100 se não especificado</span><span class="sxs-lookup"><span data-stu-id="b4d9f-162">**y** — limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>

## <a name="examples"></a><span data-ttu-id="b4d9f-163">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b4d9f-163">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="b4d9f-164">Projetar apenas a coluna SHA1 e a enriquecer</span><span class="sxs-lookup"><span data-stu-id="b4d9f-164">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="b4d9f-165">Enriquecer os primeiros 500 registros e listar arquivos de baixa prevalência</span><span class="sxs-lookup"><span data-stu-id="b4d9f-165">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="b4d9f-166">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b4d9f-166">Related topics</span></span>

- [<span data-ttu-id="b4d9f-167">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="b4d9f-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b4d9f-168">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b4d9f-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b4d9f-169">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="b4d9f-169">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
