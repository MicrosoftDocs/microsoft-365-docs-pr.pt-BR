---
title: Tabela DeviceTvmSoftwareVulnerabilitiesKB no esquema de busca avançada
description: Saiba mais sobre as vulnerabilidades do software monitoradas pelo Gerenciamento de Ameaças e Vulnerabilidades na tabela DeviceTvmSoftwareVulnerabilitiesKB do esquema de busca avançada.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, esquema, referência, kusto, tabela, coluna, tipo de dados, descrição, ameaça & Gerenciamento de Vulnerabilidades, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID de CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKBB
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
ms.openlocfilehash: afcd6bcd81e1a8635be9ced766c533ea4195334f
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023792"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="5e80f-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="5e80f-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5e80f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5e80f-105">**Applies to:**</span></span>
- <span data-ttu-id="5e80f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e80f-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="5e80f-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5e80f-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="5e80f-108">A tabela `DeviceTvmSoftwareVulnerabilitiesKB` no esquema de busca avançada contém a lista de vulnerabilidades que o [Gerenciamento de Ameaças e Vulnerabilidade](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)procura nos dispositivos. </span><span class="sxs-lookup"><span data-stu-id="5e80f-108">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="5e80f-109">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="5e80f-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="5e80f-110">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5e80f-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5e80f-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="5e80f-111">Column name</span></span> | <span data-ttu-id="5e80f-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="5e80f-112">Data type</span></span> | <span data-ttu-id="5e80f-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e80f-113">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="5e80f-114">string</span><span class="sxs-lookup"><span data-stu-id="5e80f-114">string</span></span> | <span data-ttu-id="5e80f-115">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="5e80f-115">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="5e80f-116">string</span><span class="sxs-lookup"><span data-stu-id="5e80f-116">string</span></span> | <span data-ttu-id="5e80f-117">Pontuação de gravidade atribuída à vulnerabilidade de segurança no Common Vulnerability Scoring System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="5e80f-117">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="5e80f-118">booliano</span><span class="sxs-lookup"><span data-stu-id="5e80f-118">boolean</span></span> | <span data-ttu-id="5e80f-119">Indica se o código de exploração da vulnerabilidade está disponível publicamente</span><span class="sxs-lookup"><span data-stu-id="5e80f-119">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="5e80f-120">string</span><span class="sxs-lookup"><span data-stu-id="5e80f-120">string</span></span> | <span data-ttu-id="5e80f-121">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="5e80f-121">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="5e80f-122">datetime</span><span class="sxs-lookup"><span data-stu-id="5e80f-122">datetime</span></span> | <span data-ttu-id="5e80f-123">Data e hora em que o item ou os metadados relacionados foram modificados pela última vez</span><span class="sxs-lookup"><span data-stu-id="5e80f-123">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="5e80f-124">datetime</span><span class="sxs-lookup"><span data-stu-id="5e80f-124">datetime</span></span> | <span data-ttu-id="5e80f-125">Data em que a vulnerabilidade foi divulgada ao público</span><span class="sxs-lookup"><span data-stu-id="5e80f-125">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="5e80f-126">string</span><span class="sxs-lookup"><span data-stu-id="5e80f-126">string</span></span> | <span data-ttu-id="5e80f-127">Descrição da vulnerabilidade e riscos associados</span><span class="sxs-lookup"><span data-stu-id="5e80f-127">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="5e80f-128">string</span><span class="sxs-lookup"><span data-stu-id="5e80f-128">string</span></span> | <span data-ttu-id="5e80f-129">Lista de todos os produtos de software afetados pela vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="5e80f-129">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5e80f-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5e80f-130">Related topics</span></span>

- [<span data-ttu-id="5e80f-131">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="5e80f-131">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5e80f-132">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="5e80f-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5e80f-133">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="5e80f-133">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5e80f-134">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="5e80f-134">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5e80f-135">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="5e80f-135">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5e80f-136">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="5e80f-136">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5e80f-137">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="5e80f-137">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)