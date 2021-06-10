---
title: Tabela DeviceFileCertificateInfo no esquema de busca avançado
description: Saiba mais sobre informações de assinatura de arquivo na tabela DeviceFileCertificateInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, assinatura digital, certificado, assinatura de arquivo, DeviceFileCertificateInfo
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
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023208"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="ad7c6-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="ad7c6-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ad7c6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ad7c6-105">**Applies to:**</span></span>
- <span data-ttu-id="ad7c6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad7c6-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="ad7c6-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ad7c6-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="ad7c6-108">A `DeviceFileCertificateInfo` tabela no esquema de busca [avançada](advanced-hunting-overview.md) contém informações sobre certificados de assinatura de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-108">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="ad7c6-109">Esta tabela usa dados obtidos de atividades de verificação de certificado regularmente executadas em arquivos nos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-109">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="ad7c6-110">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ad7c6-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ad7c6-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="ad7c6-111">Column name</span></span> | <span data-ttu-id="ad7c6-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ad7c6-112">Data type</span></span> | <span data-ttu-id="ad7c6-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="ad7c6-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ad7c6-114">datetime</span><span class="sxs-lookup"><span data-stu-id="ad7c6-114">datetime</span></span> | <span data-ttu-id="ad7c6-115">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="ad7c6-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="ad7c6-116">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ad7c6-116">string</span></span> | <span data-ttu-id="ad7c6-117">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="ad7c6-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ad7c6-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ad7c6-118">string</span></span> | <span data-ttu-id="ad7c6-119">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="ad7c6-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="ad7c6-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ad7c6-120">string</span></span> | <span data-ttu-id="ad7c6-121">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="ad7c6-121">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="ad7c6-122">booliano</span><span class="sxs-lookup"><span data-stu-id="ad7c6-122">boolean</span></span> | <span data-ttu-id="ad7c6-123">Indica se o arquivo está assinado</span><span class="sxs-lookup"><span data-stu-id="ad7c6-123">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="ad7c6-124">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ad7c6-124">string</span></span> | <span data-ttu-id="ad7c6-125">Indica se as informações de assinatura foram lidas como conteúdo incorporado no próprio arquivo ou leitura de um arquivo de catálogo externo</span><span class="sxs-lookup"><span data-stu-id="ad7c6-125">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="ad7c6-126">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ad7c6-126">string</span></span> | <span data-ttu-id="ad7c6-127">Informações sobre o signante do arquivo</span><span class="sxs-lookup"><span data-stu-id="ad7c6-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="ad7c6-128">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ad7c6-128">string</span></span> | <span data-ttu-id="ad7c6-129">Valor de hash exclusivo que identifica o signante</span><span class="sxs-lookup"><span data-stu-id="ad7c6-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="ad7c6-130">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ad7c6-130">string</span></span> | <span data-ttu-id="ad7c6-131">Informações sobre a autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="ad7c6-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="ad7c6-132">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ad7c6-132">string</span></span> | <span data-ttu-id="ad7c6-133">Valor de hash exclusivo identificando a autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="ad7c6-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="ad7c6-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ad7c6-134">string</span></span> | <span data-ttu-id="ad7c6-135">Identificador do certificado exclusivo da autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="ad7c6-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="ad7c6-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ad7c6-136">string</span></span> |  <span data-ttu-id="ad7c6-137">Matriz JSON listando as URLs de compartilhamentos de rede que contêm certificados e listas de revogação de certificados (CRLs)</span><span class="sxs-lookup"><span data-stu-id="ad7c6-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="ad7c6-138">datetime</span><span class="sxs-lookup"><span data-stu-id="ad7c6-138">datetime</span></span> | <span data-ttu-id="ad7c6-139">Data e hora em que o certificado foi criado</span><span class="sxs-lookup"><span data-stu-id="ad7c6-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="ad7c6-140">datetime</span><span class="sxs-lookup"><span data-stu-id="ad7c6-140">datetime</span></span> | <span data-ttu-id="ad7c6-141">Data e hora em que o certificado está definido para expirar</span><span class="sxs-lookup"><span data-stu-id="ad7c6-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="ad7c6-142">datetime</span><span class="sxs-lookup"><span data-stu-id="ad7c6-142">datetime</span></span> | <span data-ttu-id="ad7c6-143">Data e hora em que o certificado foi contra-assinado</span><span class="sxs-lookup"><span data-stu-id="ad7c6-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="ad7c6-144">booliano</span><span class="sxs-lookup"><span data-stu-id="ad7c6-144">boolean</span></span> | <span data-ttu-id="ad7c6-145">Indica se o arquivo é confiável com base nos resultados da função WinVerifyTrust, que verifica se há informações de certificado raiz desconhecidas, assinaturas inválidas, certificados revogados e outros atributos questionáveis</span><span class="sxs-lookup"><span data-stu-id="ad7c6-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="ad7c6-146">booliano</span><span class="sxs-lookup"><span data-stu-id="ad7c6-146">boolean</span></span> | <span data-ttu-id="ad7c6-147">Indica se o signante do certificado raiz é a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ad7c6-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="ad7c6-148">long</span><span class="sxs-lookup"><span data-stu-id="ad7c6-148">long</span></span> | <span data-ttu-id="ad7c6-149">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="ad7c6-150">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="ad7c6-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="ad7c6-151">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ad7c6-151">Related topics</span></span>
- [<span data-ttu-id="ad7c6-152">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="ad7c6-152">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ad7c6-153">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="ad7c6-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ad7c6-154">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="ad7c6-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ad7c6-155">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="ad7c6-155">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ad7c6-156">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="ad7c6-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ad7c6-157">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="ad7c6-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
