---
title: Tabela DeviceFileCertificateInfo no esquema de busca avançado
description: Saiba mais sobre informações de assinatura de arquivo na tabela DeviceFileCertificateInfo do esquema de busca avançado
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 00e10c84c4bcb20f2e018bf05033b5b2235fd9ae
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053218"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="f3d0b-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="f3d0b-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f3d0b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f3d0b-105">**Applies to:**</span></span>
- <span data-ttu-id="f3d0b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3d0b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f3d0b-107">A `DeviceFileCertificateInfo` tabela no esquema de busca [avançada](advanced-hunting-overview.md) contém informações sobre certificados de assinatura de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f3d0b-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="f3d0b-108">Esta tabela usa dados obtidos de atividades de verificação de certificado regularmente executadas em arquivos nos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f3d0b-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="f3d0b-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f3d0b-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f3d0b-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="f3d0b-110">Column name</span></span> | <span data-ttu-id="f3d0b-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f3d0b-111">Data type</span></span> | <span data-ttu-id="f3d0b-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3d0b-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f3d0b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f3d0b-113">datetime</span></span> | <span data-ttu-id="f3d0b-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="f3d0b-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="f3d0b-115">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3d0b-115">string</span></span> | <span data-ttu-id="f3d0b-116">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="f3d0b-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f3d0b-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3d0b-117">string</span></span> | <span data-ttu-id="f3d0b-118">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="f3d0b-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="f3d0b-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3d0b-119">string</span></span> | <span data-ttu-id="f3d0b-120">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="f3d0b-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="f3d0b-121">booliano</span><span class="sxs-lookup"><span data-stu-id="f3d0b-121">boolean</span></span> | <span data-ttu-id="f3d0b-122">Indica se o arquivo está assinado</span><span class="sxs-lookup"><span data-stu-id="f3d0b-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="f3d0b-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3d0b-123">string</span></span> | <span data-ttu-id="f3d0b-124">Indica se as informações de assinatura foram lidas como conteúdo incorporado no próprio arquivo ou leitura de um arquivo de catálogo externo</span><span class="sxs-lookup"><span data-stu-id="f3d0b-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="f3d0b-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3d0b-125">string</span></span> | <span data-ttu-id="f3d0b-126">Informações sobre o signante do arquivo</span><span class="sxs-lookup"><span data-stu-id="f3d0b-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="f3d0b-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3d0b-127">string</span></span> | <span data-ttu-id="f3d0b-128">Valor de hash exclusivo que identifica o signante</span><span class="sxs-lookup"><span data-stu-id="f3d0b-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="f3d0b-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3d0b-129">string</span></span> | <span data-ttu-id="f3d0b-130">Informações sobre a autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="f3d0b-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="f3d0b-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3d0b-131">string</span></span> | <span data-ttu-id="f3d0b-132">Valor de hash exclusivo identificando a autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="f3d0b-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="f3d0b-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3d0b-133">string</span></span> | <span data-ttu-id="f3d0b-134">Identificador do certificado exclusivo da autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="f3d0b-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="f3d0b-135">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3d0b-135">string</span></span> |  <span data-ttu-id="f3d0b-136">Matriz JSON listando as URLs de compartilhamentos de rede que contêm certificados e listas de revogação de certificados (CRLs)</span><span class="sxs-lookup"><span data-stu-id="f3d0b-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="f3d0b-137">datetime</span><span class="sxs-lookup"><span data-stu-id="f3d0b-137">datetime</span></span> | <span data-ttu-id="f3d0b-138">Data e hora em que o certificado foi criado</span><span class="sxs-lookup"><span data-stu-id="f3d0b-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="f3d0b-139">datetime</span><span class="sxs-lookup"><span data-stu-id="f3d0b-139">datetime</span></span> | <span data-ttu-id="f3d0b-140">Data e hora em que o certificado está definido para expirar</span><span class="sxs-lookup"><span data-stu-id="f3d0b-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="f3d0b-141">datetime</span><span class="sxs-lookup"><span data-stu-id="f3d0b-141">datetime</span></span> | <span data-ttu-id="f3d0b-142">Data e hora em que o certificado foi contra-assinado</span><span class="sxs-lookup"><span data-stu-id="f3d0b-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="f3d0b-143">booliano</span><span class="sxs-lookup"><span data-stu-id="f3d0b-143">boolean</span></span> | <span data-ttu-id="f3d0b-144">Indica se o arquivo é confiável com base nos resultados da função WinVerifyTrust, que verifica se há informações de certificado raiz desconhecidas, assinaturas inválidas, certificados revogados e outros atributos questionáveis</span><span class="sxs-lookup"><span data-stu-id="f3d0b-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="f3d0b-145">booliano</span><span class="sxs-lookup"><span data-stu-id="f3d0b-145">boolean</span></span> | <span data-ttu-id="f3d0b-146">Indica se o signante do certificado raiz é a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f3d0b-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="f3d0b-147">long</span><span class="sxs-lookup"><span data-stu-id="f3d0b-147">long</span></span> | <span data-ttu-id="f3d0b-148">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="f3d0b-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="f3d0b-149">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="f3d0b-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="f3d0b-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f3d0b-150">Related topics</span></span>
- [<span data-ttu-id="f3d0b-151">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="f3d0b-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f3d0b-152">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="f3d0b-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f3d0b-153">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="f3d0b-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f3d0b-154">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="f3d0b-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f3d0b-155">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="f3d0b-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f3d0b-156">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="f3d0b-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
