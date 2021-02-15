---
title: Tabela DeviceFileCertificateInfo no esquema de busca avançada
description: Saiba mais sobre as informações de assinatura de arquivo na tabela DeviceFileCertificateInfo do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, assinatura digital, certificado, assinatura de arquivo, DeviceFileCertificateInfo
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
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931309"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="939d9-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="939d9-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="939d9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="939d9-105">**Applies to:**</span></span>
- <span data-ttu-id="939d9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="939d9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="939d9-107">A `DeviceFileCertificateInfo` tabela no esquema de busca [avançada](advanced-hunting-overview.md) contém informações sobre certificados de assinatura de arquivo.</span><span class="sxs-lookup"><span data-stu-id="939d9-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="939d9-108">Esta tabela usa dados obtidos de atividades de verificação de certificado executadas regularmente em arquivos nos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="939d9-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="939d9-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="939d9-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="939d9-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="939d9-110">Column name</span></span> | <span data-ttu-id="939d9-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="939d9-111">Data type</span></span> | <span data-ttu-id="939d9-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="939d9-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="939d9-113">datetime</span><span class="sxs-lookup"><span data-stu-id="939d9-113">datetime</span></span> | <span data-ttu-id="939d9-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="939d9-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="939d9-115">string</span><span class="sxs-lookup"><span data-stu-id="939d9-115">string</span></span> | <span data-ttu-id="939d9-116">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="939d9-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="939d9-117">string</span><span class="sxs-lookup"><span data-stu-id="939d9-117">string</span></span> | <span data-ttu-id="939d9-118">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="939d9-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="939d9-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="939d9-119">string</span></span> | <span data-ttu-id="939d9-120">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="939d9-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="939d9-121">booliano</span><span class="sxs-lookup"><span data-stu-id="939d9-121">boolean</span></span> | <span data-ttu-id="939d9-122">Indica se o arquivo está assinado</span><span class="sxs-lookup"><span data-stu-id="939d9-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="939d9-123">string</span><span class="sxs-lookup"><span data-stu-id="939d9-123">string</span></span> | <span data-ttu-id="939d9-124">Indica se as informações de assinatura foram lidas como conteúdo incorporado no próprio arquivo ou lidas de um arquivo de catálogo externo</span><span class="sxs-lookup"><span data-stu-id="939d9-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="939d9-125">string</span><span class="sxs-lookup"><span data-stu-id="939d9-125">string</span></span> | <span data-ttu-id="939d9-126">Informações sobre o signante do arquivo</span><span class="sxs-lookup"><span data-stu-id="939d9-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="939d9-127">string</span><span class="sxs-lookup"><span data-stu-id="939d9-127">string</span></span> | <span data-ttu-id="939d9-128">Valor de hash exclusivo identificando o signante</span><span class="sxs-lookup"><span data-stu-id="939d9-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="939d9-129">string</span><span class="sxs-lookup"><span data-stu-id="939d9-129">string</span></span> | <span data-ttu-id="939d9-130">Informações sobre a autoridade de certificação (CA) de emissão</span><span class="sxs-lookup"><span data-stu-id="939d9-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="939d9-131">string</span><span class="sxs-lookup"><span data-stu-id="939d9-131">string</span></span> | <span data-ttu-id="939d9-132">Valor de hash exclusivo identificando a autoridade de certificação (CA) de emissão</span><span class="sxs-lookup"><span data-stu-id="939d9-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="939d9-133">string</span><span class="sxs-lookup"><span data-stu-id="939d9-133">string</span></span> | <span data-ttu-id="939d9-134">Identificador do certificado que é exclusivo da autoridade de certificação (CA) de emissão</span><span class="sxs-lookup"><span data-stu-id="939d9-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="939d9-135">string</span><span class="sxs-lookup"><span data-stu-id="939d9-135">string</span></span> |  <span data-ttu-id="939d9-136">Matriz JSON listando as URLs de compartilhamentos de rede que contêm certificados e listas de certificados revogados (CRLs)</span><span class="sxs-lookup"><span data-stu-id="939d9-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="939d9-137">datetime</span><span class="sxs-lookup"><span data-stu-id="939d9-137">datetime</span></span> | <span data-ttu-id="939d9-138">Data e hora em que o certificado foi criado</span><span class="sxs-lookup"><span data-stu-id="939d9-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="939d9-139">datetime</span><span class="sxs-lookup"><span data-stu-id="939d9-139">datetime</span></span> | <span data-ttu-id="939d9-140">Data e hora em que o certificado está definido para expirar</span><span class="sxs-lookup"><span data-stu-id="939d9-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="939d9-141">datetime</span><span class="sxs-lookup"><span data-stu-id="939d9-141">datetime</span></span> | <span data-ttu-id="939d9-142">Data e hora em que o certificado foi contra-atribuído</span><span class="sxs-lookup"><span data-stu-id="939d9-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="939d9-143">booliano</span><span class="sxs-lookup"><span data-stu-id="939d9-143">boolean</span></span> | <span data-ttu-id="939d9-144">Indica se o arquivo é confiável com base nos resultados da função WinVerifyTrust, que verifica se há informações de certificado raiz desconhecidas, assinaturas inválidas, certificados revogados e outros atributos questionáveis</span><span class="sxs-lookup"><span data-stu-id="939d9-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="939d9-145">booliano</span><span class="sxs-lookup"><span data-stu-id="939d9-145">boolean</span></span> | <span data-ttu-id="939d9-146">Indica se o signante do certificado raiz é a Microsoft</span><span class="sxs-lookup"><span data-stu-id="939d9-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="939d9-147">long</span><span class="sxs-lookup"><span data-stu-id="939d9-147">long</span></span> | <span data-ttu-id="939d9-148">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="939d9-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="939d9-149">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="939d9-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="939d9-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="939d9-150">Related topics</span></span>
- [<span data-ttu-id="939d9-151">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="939d9-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="939d9-152">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="939d9-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="939d9-153">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="939d9-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="939d9-154">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="939d9-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="939d9-155">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="939d9-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="939d9-156">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="939d9-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
