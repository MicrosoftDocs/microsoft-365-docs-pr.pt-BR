---
title: Tabela DeviceTvmSoftwareVulnerabilities no esquema de busca avançado
description: Saiba mais sobre as vulnerabilidades de software encontradas em dispositivos e a lista de atualizações de segurança disponíveis que abordam cada vulnerabilidade na tabela DeviceTvmSoftwareVulnerabilities do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, ameaça & Gerenciamento de Vulnerabilidades, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID de CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 17faffc45cfd1f472dec3f423681aaa3f64944a3
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023804"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="954f4-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="954f4-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="954f4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="954f4-105">**Applies to:**</span></span>
- <span data-ttu-id="954f4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="954f4-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="954f4-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="954f4-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="954f4-108">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="954f4-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="954f4-109">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="954f4-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="954f4-110">A tabela no esquema de busca avançada contém a lista gerenciamento de vulnerabilidades & ameaças em `DeviceTvmSoftwareVulnerabilities` produtos de software instalados. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="954f4-110">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="954f4-111">Esta tabela também inclui informações sobre o sistema operacional, as IDs do CVE e as informações sobre a severidade da vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="954f4-111">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="954f4-112">Você pode usar essa tabela, por exemplo, para procurar eventos envolvendo dispositivos que tenham vulnerabilidades graves em seu software.</span><span class="sxs-lookup"><span data-stu-id="954f4-112">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="954f4-113">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="954f4-113">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="954f4-114">As `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` tabelas e substituíram a `DeviceTvmSoftwareInventoryVulnerabilities` tabela.</span><span class="sxs-lookup"><span data-stu-id="954f4-114">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="954f4-115">Juntas, as duas primeiras tabelas incluem mais colunas que você pode usar para ajudar a informar suas atividades de gerenciamento de vulnerabilidade ou a procurar dispositivos vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="954f4-115">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="954f4-116">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="954f4-116">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="954f4-117">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="954f4-117">Column name</span></span> | <span data-ttu-id="954f4-118">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="954f4-118">Data type</span></span> | <span data-ttu-id="954f4-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="954f4-119">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="954f4-120">string</span><span class="sxs-lookup"><span data-stu-id="954f4-120">string</span></span> | <span data-ttu-id="954f4-121">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="954f4-121">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="954f4-122">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="954f4-122">string</span></span> | <span data-ttu-id="954f4-123">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="954f4-123">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="954f4-124">string</span><span class="sxs-lookup"><span data-stu-id="954f4-124">string</span></span> | <span data-ttu-id="954f4-125">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="954f4-125">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="954f4-126">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="954f4-126">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="954f4-127">string</span><span class="sxs-lookup"><span data-stu-id="954f4-127">string</span></span> | <span data-ttu-id="954f4-128">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="954f4-128">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="954f4-129">string</span><span class="sxs-lookup"><span data-stu-id="954f4-129">string</span></span> | <span data-ttu-id="954f4-130">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="954f4-130">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="954f4-131">string</span><span class="sxs-lookup"><span data-stu-id="954f4-131">string</span></span> | <span data-ttu-id="954f4-132">Nome do fornecedor de software</span><span class="sxs-lookup"><span data-stu-id="954f4-132">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="954f4-133">string</span><span class="sxs-lookup"><span data-stu-id="954f4-133">string</span></span> | <span data-ttu-id="954f4-134">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="954f4-134">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="954f4-135">string</span><span class="sxs-lookup"><span data-stu-id="954f4-135">string</span></span> | <span data-ttu-id="954f4-136">Número da versão do produto software</span><span class="sxs-lookup"><span data-stu-id="954f4-136">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="954f4-137">string</span><span class="sxs-lookup"><span data-stu-id="954f4-137">string</span></span> | <span data-ttu-id="954f4-138">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="954f4-138">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="954f4-139">string</span><span class="sxs-lookup"><span data-stu-id="954f4-139">string</span></span> | <span data-ttu-id="954f4-140">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="954f4-140">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="954f4-141">string</span><span class="sxs-lookup"><span data-stu-id="954f4-141">string</span></span> | <span data-ttu-id="954f4-142">Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="954f4-142">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="954f4-143">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="954f4-143">string</span></span> | <span data-ttu-id="954f4-144">Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB)</span><span class="sxs-lookup"><span data-stu-id="954f4-144">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="954f4-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="954f4-145">Related topics</span></span>

- [<span data-ttu-id="954f4-146">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="954f4-146">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="954f4-147">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="954f4-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="954f4-148">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="954f4-148">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="954f4-149">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="954f4-149">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="954f4-150">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="954f4-150">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="954f4-151">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="954f4-151">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="954f4-152">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="954f4-152">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)