---
title: Tabela DeviceFileCertificateInfo no esquema de busca avançada
description: Saiba mais sobre informações de assinatura de arquivo na tabela DeviceFileCertificateInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, assinatura digital, certificado, assinatura de arquivos, DeviceFileCertificateInfo
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9291d9f113fdc1c082b38d92399c1dee646b523d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846165"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="bf881-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="bf881-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf881-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="bf881-105">**Applies to:**</span></span>
- <span data-ttu-id="bf881-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="bf881-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bf881-107">A `DeviceFileCertificateInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre certificados de assinatura de arquivo.</span><span class="sxs-lookup"><span data-stu-id="bf881-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="bf881-108">Esta tabela usa dados obtidos de atividades de verificação de certificado realizadas regularmente em arquivos de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="bf881-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="bf881-109">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="bf881-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="bf881-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="bf881-110">Column name</span></span> | <span data-ttu-id="bf881-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="bf881-111">Data type</span></span> | <span data-ttu-id="bf881-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="bf881-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="bf881-113">datetime</span><span class="sxs-lookup"><span data-stu-id="bf881-113">datetime</span></span> | <span data-ttu-id="bf881-114">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="bf881-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="bf881-115">string</span><span class="sxs-lookup"><span data-stu-id="bf881-115">string</span></span> | <span data-ttu-id="bf881-116">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="bf881-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="bf881-117">string</span><span class="sxs-lookup"><span data-stu-id="bf881-117">string</span></span> | <span data-ttu-id="bf881-118">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="bf881-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="bf881-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="bf881-119">string</span></span> | <span data-ttu-id="bf881-120">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="bf881-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="bf881-121">booliano</span><span class="sxs-lookup"><span data-stu-id="bf881-121">boolean</span></span> | <span data-ttu-id="bf881-122">Indica se o arquivo está assinado</span><span class="sxs-lookup"><span data-stu-id="bf881-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="bf881-123">string</span><span class="sxs-lookup"><span data-stu-id="bf881-123">string</span></span> | <span data-ttu-id="bf881-124">Indica se as informações de assinatura foram lidas como conteúdo incorporado no próprio arquivo ou lidas de um arquivo de catálogo externo</span><span class="sxs-lookup"><span data-stu-id="bf881-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="bf881-125">string</span><span class="sxs-lookup"><span data-stu-id="bf881-125">string</span></span> | <span data-ttu-id="bf881-126">Informações sobre o signatário do arquivo</span><span class="sxs-lookup"><span data-stu-id="bf881-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="bf881-127">string</span><span class="sxs-lookup"><span data-stu-id="bf881-127">string</span></span> | <span data-ttu-id="bf881-128">Valor de hash exclusivo que identifica o signatário</span><span class="sxs-lookup"><span data-stu-id="bf881-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="bf881-129">string</span><span class="sxs-lookup"><span data-stu-id="bf881-129">string</span></span> | <span data-ttu-id="bf881-130">Informações sobre a CA (autoridade de certificação emissora)</span><span class="sxs-lookup"><span data-stu-id="bf881-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="bf881-131">string</span><span class="sxs-lookup"><span data-stu-id="bf881-131">string</span></span> | <span data-ttu-id="bf881-132">Valor de hash exclusivo que identifica a CA (autoridade de certificação) de emissão</span><span class="sxs-lookup"><span data-stu-id="bf881-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="bf881-133">string</span><span class="sxs-lookup"><span data-stu-id="bf881-133">string</span></span> | <span data-ttu-id="bf881-134">Identificador para o certificado que é exclusivo da autoridade de certificação (CA) de emissão</span><span class="sxs-lookup"><span data-stu-id="bf881-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="bf881-135">string</span><span class="sxs-lookup"><span data-stu-id="bf881-135">string</span></span> |  <span data-ttu-id="bf881-136">Matriz JSON que lista as URLs de compartilhamentos de rede que contêm certificados e CRLs (listas de certificados revogados)</span><span class="sxs-lookup"><span data-stu-id="bf881-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="bf881-137">datetime</span><span class="sxs-lookup"><span data-stu-id="bf881-137">datetime</span></span> | <span data-ttu-id="bf881-138">Data e hora em que o certificado foi criado</span><span class="sxs-lookup"><span data-stu-id="bf881-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="bf881-139">datetime</span><span class="sxs-lookup"><span data-stu-id="bf881-139">datetime</span></span> | <span data-ttu-id="bf881-140">Data e hora em que o certificado está definido para expirar</span><span class="sxs-lookup"><span data-stu-id="bf881-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="bf881-141">datetime</span><span class="sxs-lookup"><span data-stu-id="bf881-141">datetime</span></span> | <span data-ttu-id="bf881-142">Data e hora em que o certificado foi assinado por ocasião</span><span class="sxs-lookup"><span data-stu-id="bf881-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="bf881-143">booliano</span><span class="sxs-lookup"><span data-stu-id="bf881-143">boolean</span></span> | <span data-ttu-id="bf881-144">Indica se o arquivo é confiável com base nos resultados da função WinVerifyTrust, que verifica informações de certificado raiz desconhecidas, assinaturas inválidas, certificados revogados e outros atributos questionáveis</span><span class="sxs-lookup"><span data-stu-id="bf881-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="bf881-145">booliano</span><span class="sxs-lookup"><span data-stu-id="bf881-145">boolean</span></span> | <span data-ttu-id="bf881-146">Indica se o signatário do certificado raiz é o Microsoft</span><span class="sxs-lookup"><span data-stu-id="bf881-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="bf881-147">long</span><span class="sxs-lookup"><span data-stu-id="bf881-147">long</span></span> | <span data-ttu-id="bf881-148">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="bf881-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="bf881-149">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e timestamp.</span><span class="sxs-lookup"><span data-stu-id="bf881-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="bf881-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bf881-150">Related topics</span></span>
- [<span data-ttu-id="bf881-151">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="bf881-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bf881-152">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="bf881-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bf881-153">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="bf881-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="bf881-154">Procure em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="bf881-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bf881-155">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="bf881-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bf881-156">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="bf881-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
