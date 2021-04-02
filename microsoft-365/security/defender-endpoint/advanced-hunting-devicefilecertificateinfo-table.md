---
title: Tabela DeviceFileCertificateInfo no esquema de busca avançado
description: Saiba mais sobre informações de assinatura de arquivo na tabela DeviceFileCertificateInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, assinatura digital, certificado, assinatura de arquivo, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499175"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="7d043-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="7d043-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7d043-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7d043-105">**Applies to:**</span></span>
- [<span data-ttu-id="7d043-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7d043-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="7d043-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="7d043-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7d043-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="7d043-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="7d043-109">A `DeviceFileCertificateInfo` tabela no esquema de busca [avançada](advanced-hunting-overview.md) contém informações sobre certificados de assinatura de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7d043-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="7d043-110">Esta tabela usa dados obtidos de atividades de verificação de certificado regularmente executadas em arquivos nos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="7d043-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="7d043-111">Para obter informações sobre outras tabelas no esquema de busca avançado, consulte [a referência avançada do esquema de busca](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="7d043-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="7d043-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="7d043-112">Column name</span></span> | <span data-ttu-id="7d043-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="7d043-113">Data type</span></span> | <span data-ttu-id="7d043-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d043-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="7d043-115">datetime</span><span class="sxs-lookup"><span data-stu-id="7d043-115">datetime</span></span> | <span data-ttu-id="7d043-116">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="7d043-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="7d043-117">string</span><span class="sxs-lookup"><span data-stu-id="7d043-117">string</span></span> | <span data-ttu-id="7d043-118">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="7d043-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7d043-119">string</span><span class="sxs-lookup"><span data-stu-id="7d043-119">string</span></span> | <span data-ttu-id="7d043-120">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="7d043-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="7d043-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="7d043-121">string</span></span> | <span data-ttu-id="7d043-122">SHA-1 do arquivo ao qual a ação gravada foi aplicada</span><span class="sxs-lookup"><span data-stu-id="7d043-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="7d043-123">booliano</span><span class="sxs-lookup"><span data-stu-id="7d043-123">boolean</span></span> | <span data-ttu-id="7d043-124">Indica se o arquivo está assinado</span><span class="sxs-lookup"><span data-stu-id="7d043-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="7d043-125">string</span><span class="sxs-lookup"><span data-stu-id="7d043-125">string</span></span> | <span data-ttu-id="7d043-126">Indica se as informações de assinatura foram lidas como conteúdo incorporado no próprio arquivo ou leitura de um arquivo de catálogo externo</span><span class="sxs-lookup"><span data-stu-id="7d043-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="7d043-127">string</span><span class="sxs-lookup"><span data-stu-id="7d043-127">string</span></span> | <span data-ttu-id="7d043-128">Informações sobre o signante do arquivo</span><span class="sxs-lookup"><span data-stu-id="7d043-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="7d043-129">string</span><span class="sxs-lookup"><span data-stu-id="7d043-129">string</span></span> | <span data-ttu-id="7d043-130">Valor de hash exclusivo que identifica o signante</span><span class="sxs-lookup"><span data-stu-id="7d043-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="7d043-131">string</span><span class="sxs-lookup"><span data-stu-id="7d043-131">string</span></span> | <span data-ttu-id="7d043-132">Informações sobre a autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="7d043-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="7d043-133">string</span><span class="sxs-lookup"><span data-stu-id="7d043-133">string</span></span> | <span data-ttu-id="7d043-134">Valor de hash exclusivo identificando a autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="7d043-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="7d043-135">string</span><span class="sxs-lookup"><span data-stu-id="7d043-135">string</span></span> | <span data-ttu-id="7d043-136">Identificador do certificado exclusivo da autoridade de certificação de emissão (CA)</span><span class="sxs-lookup"><span data-stu-id="7d043-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="7d043-137">string</span><span class="sxs-lookup"><span data-stu-id="7d043-137">string</span></span> |  <span data-ttu-id="7d043-138">Matriz JSON listando as URLs de compartilhamentos de rede que contêm certificados e listas de revogação de certificados (CRLs)</span><span class="sxs-lookup"><span data-stu-id="7d043-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="7d043-139">datetime</span><span class="sxs-lookup"><span data-stu-id="7d043-139">datetime</span></span> | <span data-ttu-id="7d043-140">Data e hora em que o certificado foi criado</span><span class="sxs-lookup"><span data-stu-id="7d043-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="7d043-141">datetime</span><span class="sxs-lookup"><span data-stu-id="7d043-141">datetime</span></span> | <span data-ttu-id="7d043-142">Data e hora em que o certificado está definido para expirar</span><span class="sxs-lookup"><span data-stu-id="7d043-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="7d043-143">datetime</span><span class="sxs-lookup"><span data-stu-id="7d043-143">datetime</span></span> | <span data-ttu-id="7d043-144">Data e hora em que o certificado foi contra-assinado</span><span class="sxs-lookup"><span data-stu-id="7d043-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="7d043-145">booliano</span><span class="sxs-lookup"><span data-stu-id="7d043-145">boolean</span></span> | <span data-ttu-id="7d043-146">Indica se o arquivo é confiável com base nos resultados da função WinVerifyTrust, que verifica se há informações de certificado raiz desconhecidas, assinaturas inválidas, certificados revogados e outros atributos questionáveis</span><span class="sxs-lookup"><span data-stu-id="7d043-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="7d043-147">booliano</span><span class="sxs-lookup"><span data-stu-id="7d043-147">boolean</span></span> | <span data-ttu-id="7d043-148">Indica se o signante do certificado raiz é a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7d043-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="7d043-149">long</span><span class="sxs-lookup"><span data-stu-id="7d043-149">long</span></span> | <span data-ttu-id="7d043-150">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="7d043-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="7d043-151">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="7d043-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="7d043-152">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7d043-152">Related topics</span></span>
- [<span data-ttu-id="7d043-153">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="7d043-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7d043-154">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="7d043-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7d043-155">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="7d043-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
