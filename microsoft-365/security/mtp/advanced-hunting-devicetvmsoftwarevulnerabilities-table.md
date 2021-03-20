---
title: Tabela DeviceTvmSoftwareVulnerabilities no esquema de busca avançado
description: Saiba mais sobre as vulnerabilidades de software encontradas em dispositivos e a lista de atualizações de segurança disponíveis que abordam cada vulnerabilidade na tabela DeviceTvmSoftwareVulnerabilities do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID da CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: dfa0c74757a5403573a9300002b92e4b2b109ebb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907247"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="fedd4-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="fedd4-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fedd4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="fedd4-105">**Applies to:**</span></span>
- <span data-ttu-id="fedd4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fedd4-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="fedd4-107">Algumas informações se relacionam ao produto pré-lançamento, que pode ser substancialmente modificado antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="fedd4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="fedd4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="fedd4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="fedd4-109">A tabela no esquema de busca avançada contém a lista gerenciamento de vulnerabilidades & ameaças em `DeviceTvmSoftwareVulnerabilities` produtos de software instalados. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="fedd4-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="fedd4-110">Esta tabela também inclui informações sobre o sistema operacional, as IDs do CVE e as informações sobre a severidade da vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="fedd4-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="fedd4-111">Você pode usar essa tabela, por exemplo, para procurar eventos envolvendo dispositivos que tenham vulnerabilidades graves em seu software.</span><span class="sxs-lookup"><span data-stu-id="fedd4-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="fedd4-112">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="fedd4-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="fedd4-113">As `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` tabelas e substituíram a `DeviceTvmSoftwareInventoryVulnerabilities` tabela.</span><span class="sxs-lookup"><span data-stu-id="fedd4-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="fedd4-114">Juntas, as duas primeiras tabelas incluem mais colunas que você pode usar para ajudar a informar suas atividades de gerenciamento de vulnerabilidade ou a procurar dispositivos vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="fedd4-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="fedd4-115">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="fedd4-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="fedd4-116">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="fedd4-116">Column name</span></span> | <span data-ttu-id="fedd4-117">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="fedd4-117">Data type</span></span> | <span data-ttu-id="fedd4-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="fedd4-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="fedd4-119">string</span><span class="sxs-lookup"><span data-stu-id="fedd4-119">string</span></span> | <span data-ttu-id="fedd4-120">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="fedd4-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="fedd4-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fedd4-121">string</span></span> | <span data-ttu-id="fedd4-122">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="fedd4-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="fedd4-123">string</span><span class="sxs-lookup"><span data-stu-id="fedd4-123">string</span></span> | <span data-ttu-id="fedd4-124">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="fedd4-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="fedd4-125">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="fedd4-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="fedd4-126">string</span><span class="sxs-lookup"><span data-stu-id="fedd4-126">string</span></span> | <span data-ttu-id="fedd4-127">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="fedd4-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="fedd4-128">string</span><span class="sxs-lookup"><span data-stu-id="fedd4-128">string</span></span> | <span data-ttu-id="fedd4-129">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="fedd4-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="fedd4-130">string</span><span class="sxs-lookup"><span data-stu-id="fedd4-130">string</span></span> | <span data-ttu-id="fedd4-131">Nome do fornecedor de software</span><span class="sxs-lookup"><span data-stu-id="fedd4-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="fedd4-132">string</span><span class="sxs-lookup"><span data-stu-id="fedd4-132">string</span></span> | <span data-ttu-id="fedd4-133">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="fedd4-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="fedd4-134">string</span><span class="sxs-lookup"><span data-stu-id="fedd4-134">string</span></span> | <span data-ttu-id="fedd4-135">Número da versão do produto software</span><span class="sxs-lookup"><span data-stu-id="fedd4-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="fedd4-136">string</span><span class="sxs-lookup"><span data-stu-id="fedd4-136">string</span></span> | <span data-ttu-id="fedd4-137">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="fedd4-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="fedd4-138">string</span><span class="sxs-lookup"><span data-stu-id="fedd4-138">string</span></span> | <span data-ttu-id="fedd4-139">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="fedd4-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="fedd4-140">string</span><span class="sxs-lookup"><span data-stu-id="fedd4-140">string</span></span> | <span data-ttu-id="fedd4-141">Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="fedd4-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="fedd4-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fedd4-142">string</span></span> | <span data-ttu-id="fedd4-143">Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB)</span><span class="sxs-lookup"><span data-stu-id="fedd4-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="fedd4-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fedd4-144">Related topics</span></span>

- [<span data-ttu-id="fedd4-145">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="fedd4-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fedd4-146">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="fedd4-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fedd4-147">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="fedd4-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fedd4-148">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="fedd4-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fedd4-149">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="fedd4-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fedd4-150">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="fedd4-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="fedd4-151">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="fedd4-151">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)