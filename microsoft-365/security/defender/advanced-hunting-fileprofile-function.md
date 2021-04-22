---
title: Função FileProfile() em busca avançada do Microsoft 365 Defender
description: Saiba como usar o FileProfile() para enriquecer informações sobre arquivos nos resultados avançados da consulta de busca
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, FileProfile, perfil de arquivo, função, enriquecimento
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
ms.openlocfilehash: 67295529cdb7b8a3e93e663f2a8a28d27a8f6737
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935840"
---
# <a name="fileprofile"></a><span data-ttu-id="932ab-104">FileProfile()</span><span class="sxs-lookup"><span data-stu-id="932ab-104">FileProfile()</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="932ab-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="932ab-105">**Applies to:**</span></span>
- <span data-ttu-id="932ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="932ab-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="932ab-107">A função é uma função de enriquecimento na busca avançada que adiciona os seguintes dados aos `FileProfile()` arquivos encontrados pela consulta. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="932ab-107">The `FileProfile()` function is an enrichment function in [advanced hunting](advanced-hunting-overview.md) that adds the following data to files found by the query.</span></span>

| <span data-ttu-id="932ab-108">Coluna</span><span class="sxs-lookup"><span data-stu-id="932ab-108">Column</span></span> | <span data-ttu-id="932ab-109">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="932ab-109">Data type</span></span> | <span data-ttu-id="932ab-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="932ab-110">Description</span></span> |
|------------|---------------|-------------|
| `SHA1` | <span data-ttu-id="932ab-111">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="932ab-111">string</span></span> | <span data-ttu-id="932ab-112">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="932ab-112">SHA-1 of the file that the recorded action was applied to</span></span> |
| `SHA256` | <span data-ttu-id="932ab-113">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="932ab-113">string</span></span> | <span data-ttu-id="932ab-114">SHA-256 do arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="932ab-114">SHA-256 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="932ab-115">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="932ab-115">string</span></span> | <span data-ttu-id="932ab-116">Hash MD5 do arquivo ao que a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="932ab-116">MD5 hash of the file that the recorded action was applied to</span></span> |
| `FileSize` | <span data-ttu-id="932ab-117">int</span><span class="sxs-lookup"><span data-stu-id="932ab-117">int</span></span> | <span data-ttu-id="932ab-118">Tamanho do arquivo em bytes</span><span class="sxs-lookup"><span data-stu-id="932ab-118">Size of the file in bytes</span></span> |
| `GlobalPrevalence` | <span data-ttu-id="932ab-119">int</span><span class="sxs-lookup"><span data-stu-id="932ab-119">int</span></span> | <span data-ttu-id="932ab-120">Número de instâncias da entidade observadas globalmente pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="932ab-120">Number of instances of the entity observed by Microsoft globally</span></span> |
| `GlobalFirstSeen` | <span data-ttu-id="932ab-121">datetime</span><span class="sxs-lookup"><span data-stu-id="932ab-121">datetime</span></span> | <span data-ttu-id="932ab-122">Data e hora em que a entidade foi observada pela primeira vez pela Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="932ab-122">Date and time when the entity was first observed by Microsoft globally</span></span> |
| `GlobalLastSeen` | <span data-ttu-id="932ab-123">datetime</span><span class="sxs-lookup"><span data-stu-id="932ab-123">datetime</span></span> | <span data-ttu-id="932ab-124">Data e hora em que a entidade foi observada pela última vez pela Microsoft globalmente</span><span class="sxs-lookup"><span data-stu-id="932ab-124">Date and time when the entity was last observed by Microsoft globally</span></span> |
| `Signer` | <span data-ttu-id="932ab-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="932ab-125">string</span></span> | <span data-ttu-id="932ab-126">Informações sobre o signante do arquivo</span><span class="sxs-lookup"><span data-stu-id="932ab-126">Information about the signer of the file</span></span> |
| `Issuer` | <span data-ttu-id="932ab-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="932ab-127">string</span></span> | <span data-ttu-id="932ab-128">Informações sobre a autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="932ab-128">Information about the issuing certificate authority (CA)</span></span> |
| `SignerHash` | <span data-ttu-id="932ab-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="932ab-129">string</span></span> | <span data-ttu-id="932ab-130">Valor de hash exclusivo que identifica o signante</span><span class="sxs-lookup"><span data-stu-id="932ab-130">Unique hash value identifying the signer</span></span> |
| `IsCertificateValid` | <span data-ttu-id="932ab-131">booliano</span><span class="sxs-lookup"><span data-stu-id="932ab-131">boolean</span></span> | <span data-ttu-id="932ab-132">Se o certificado usado para assinar o arquivo é válido</span><span class="sxs-lookup"><span data-stu-id="932ab-132">Whether the certificate used to sign the file is valid</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="932ab-133">booliano</span><span class="sxs-lookup"><span data-stu-id="932ab-133">boolean</span></span> | <span data-ttu-id="932ab-134">Indica se o signante do certificado raiz é a Microsoft</span><span class="sxs-lookup"><span data-stu-id="932ab-134">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `SignatureState` | <span data-ttu-id="932ab-135">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="932ab-135">string</span></span> | <span data-ttu-id="932ab-136">Estado da assinatura do arquivo: SignedValid - o arquivo é assinado com uma assinatura válida, SignedInvalid - o arquivo é assinado, mas o certificado é inválido, não assinado - o arquivo não está assinado, Unknown - as informações sobre o arquivo não podem ser recuperadas</span><span class="sxs-lookup"><span data-stu-id="932ab-136">State of the file signature: SignedValid - the file is signed with a valid signature, SignedInvalid - the file is signed but the certificate is invalid, Unsigned - the file is not signed, Unknown - information about the file cannot be retrieved</span></span>
| `IsExecutable` | <span data-ttu-id="932ab-137">booliano</span><span class="sxs-lookup"><span data-stu-id="932ab-137">boolean</span></span> | <span data-ttu-id="932ab-138">Se o arquivo é um arquivo Executável Portátil (PE)</span><span class="sxs-lookup"><span data-stu-id="932ab-138">Whether the file is a Portable Executable (PE) file</span></span> |
| `ThreatName` | <span data-ttu-id="932ab-139">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="932ab-139">string</span></span> | <span data-ttu-id="932ab-140">Nome da detecção de qualquer malware ou outras ameaças encontradas</span><span class="sxs-lookup"><span data-stu-id="932ab-140">Detection name for any malware or other threats found</span></span> |
| `Publisher` | <span data-ttu-id="932ab-141">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="932ab-141">string</span></span> | <span data-ttu-id="932ab-142">Nome da organização que publicou o arquivo</span><span class="sxs-lookup"><span data-stu-id="932ab-142">Name of the organization that published the file</span></span> |
| `SoftwareName` | <span data-ttu-id="932ab-143">string</span><span class="sxs-lookup"><span data-stu-id="932ab-143">string</span></span> | <span data-ttu-id="932ab-144">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="932ab-144">Name of the software product</span></span> |

## <a name="syntax"></a><span data-ttu-id="932ab-145">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="932ab-145">Syntax</span></span>

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a><span data-ttu-id="932ab-146">Argumentos</span><span class="sxs-lookup"><span data-stu-id="932ab-146">Arguments</span></span>

- <span data-ttu-id="932ab-147">**x**— coluna ID de arquivo a ser usada: `SHA1` , , ou ; a função usa se não `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especificado</span><span class="sxs-lookup"><span data-stu-id="932ab-147">**x**—file ID column to use: `SHA1`, `SHA256`, `InitiatingProcessSHA1`, or `InitiatingProcessSHA256`; function uses `SHA1` if unspecified</span></span>
- <span data-ttu-id="932ab-148">**y**— limite para o número de registros a enriquecer, 1-1000; function usa 100 se não especificado</span><span class="sxs-lookup"><span data-stu-id="932ab-148">**y**—limit to the number of records to enrich, 1-1000; function uses 100 if unspecified</span></span>


>[!TIP]
> <span data-ttu-id="932ab-149">As funções de enriquecimento mostrarão informações complementares somente quando elas estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="932ab-149">Enrichment functions will show supplemental information only when they are available.</span></span> <span data-ttu-id="932ab-150">A disponibilidade de informações é variada e depende de muitos fatores.</span><span class="sxs-lookup"><span data-stu-id="932ab-150">Availability of information is varied and depends on a lot of factors.</span></span> <span data-ttu-id="932ab-151">Considere isso ao usar FileProfile() em suas consultas ou na criação de detecções personalizadas.</span><span class="sxs-lookup"><span data-stu-id="932ab-151">Make sure to consider this when using FileProfile() in your queries or in creating custom detections.</span></span> <span data-ttu-id="932ab-152">Para melhores resultados, recomendamos usar a função FileProfile() com SHA1.</span><span class="sxs-lookup"><span data-stu-id="932ab-152">For best results, we recommend using the FileProfile() function with SHA1.</span></span>

## <a name="examples"></a><span data-ttu-id="932ab-153">Exemplos</span><span class="sxs-lookup"><span data-stu-id="932ab-153">Examples</span></span>

### <a name="project-only-the-sha1-column-and-enrich-it"></a><span data-ttu-id="932ab-154">Projetar apenas a coluna SHA1 e a enriquecer</span><span class="sxs-lookup"><span data-stu-id="932ab-154">Project only the SHA1 column and enrich it</span></span>

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a><span data-ttu-id="932ab-155">Enriquecer os primeiros 500 registros e listar arquivos de baixa prevalência</span><span class="sxs-lookup"><span data-stu-id="932ab-155">Enrich the first 500 records and list low-prevalence files</span></span>

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a><span data-ttu-id="932ab-156">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="932ab-156">Related topics</span></span>
- [<span data-ttu-id="932ab-157">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="932ab-157">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="932ab-158">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="932ab-158">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="932ab-159">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="932ab-159">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="932ab-160">Obter mais exemplos de consulta</span><span class="sxs-lookup"><span data-stu-id="932ab-160">Get more query examples</span></span>](advanced-hunting-shared-queries.md)
