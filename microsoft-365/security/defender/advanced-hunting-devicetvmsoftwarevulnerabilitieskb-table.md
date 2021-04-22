---
title: Tabela DeviceTvmSoftwareVulnerabilitiesKB no esquema de busca avançada
description: Saiba mais sobre as vulnerabilidades do software monitoradas pelo Gerenciamento de Ameaças e Vulnerabilidades na tabela DeviceTvmSoftwareVulnerabilitiesKB do esquema de busca avançada.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, esquema, referência, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 0c9a29a75b2dc6ea2ae88f84e21ee2ab6455b2b0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933008"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="c86a0-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="c86a0-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c86a0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c86a0-105">**Applies to:**</span></span>
- <span data-ttu-id="c86a0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c86a0-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="c86a0-107">A tabela `DeviceTvmSoftwareVulnerabilitiesKB` no esquema de busca avançada contém a lista de vulnerabilidades que o [Gerenciamento de Ameaças e Vulnerabilidade](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)procura nos dispositivos. </span><span class="sxs-lookup"><span data-stu-id="c86a0-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="c86a0-108">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="c86a0-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="c86a0-109">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c86a0-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c86a0-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="c86a0-110">Column name</span></span> | <span data-ttu-id="c86a0-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="c86a0-111">Data type</span></span> | <span data-ttu-id="c86a0-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c86a0-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="c86a0-113">string</span><span class="sxs-lookup"><span data-stu-id="c86a0-113">string</span></span> | <span data-ttu-id="c86a0-114">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="c86a0-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="c86a0-115">string</span><span class="sxs-lookup"><span data-stu-id="c86a0-115">string</span></span> | <span data-ttu-id="c86a0-116">Pontuação de gravidade atribuída à vulnerabilidade de segurança no Common Vulnerability Scoring System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="c86a0-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="c86a0-117">booliano</span><span class="sxs-lookup"><span data-stu-id="c86a0-117">boolean</span></span> | <span data-ttu-id="c86a0-118">Indica se o código de exploração da vulnerabilidade está disponível publicamente</span><span class="sxs-lookup"><span data-stu-id="c86a0-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="c86a0-119">string</span><span class="sxs-lookup"><span data-stu-id="c86a0-119">string</span></span> | <span data-ttu-id="c86a0-120">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="c86a0-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="c86a0-121">datetime</span><span class="sxs-lookup"><span data-stu-id="c86a0-121">datetime</span></span> | <span data-ttu-id="c86a0-122">Data e hora em que o item ou os metadados relacionados foram modificados pela última vez</span><span class="sxs-lookup"><span data-stu-id="c86a0-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="c86a0-123">datetime</span><span class="sxs-lookup"><span data-stu-id="c86a0-123">datetime</span></span> | <span data-ttu-id="c86a0-124">Data em que a vulnerabilidade foi divulgada ao público</span><span class="sxs-lookup"><span data-stu-id="c86a0-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="c86a0-125">string</span><span class="sxs-lookup"><span data-stu-id="c86a0-125">string</span></span> | <span data-ttu-id="c86a0-126">Descrição da vulnerabilidade e riscos associados</span><span class="sxs-lookup"><span data-stu-id="c86a0-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="c86a0-127">string</span><span class="sxs-lookup"><span data-stu-id="c86a0-127">string</span></span> | <span data-ttu-id="c86a0-128">Lista de todos os produtos de software afetados pela vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="c86a0-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c86a0-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c86a0-129">Related topics</span></span>

- [<span data-ttu-id="c86a0-130">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="c86a0-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c86a0-131">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="c86a0-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c86a0-132">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="c86a0-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c86a0-133">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="c86a0-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c86a0-134">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="c86a0-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c86a0-135">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="c86a0-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="c86a0-136">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="c86a0-136">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)