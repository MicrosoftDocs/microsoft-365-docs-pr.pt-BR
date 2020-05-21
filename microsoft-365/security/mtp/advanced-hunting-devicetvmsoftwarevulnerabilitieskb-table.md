---
title: Tabela DeviceTvmSoftwareVulnerabilitiesKB no esquema de busca avançada
description: Saiba mais sobre as vulnerabilidades do software monitoradas pelo Gerenciamento de Ameaças e Vulnerabilidades na tabela DeviceTvmSoftwareVulnerabilitiesKB do esquema de busca avançada.
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Search, Query, telemetria, esquema, referência, Kusto, tabela, coluna, tipo de dados, descrição, ameaça & gerenciamento de vulnerabilidades, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 378ffee34a24af225b1b6deebd7cc514c62e1926
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327933"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="5bb04-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="5bb04-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

<span data-ttu-id="5bb04-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5bb04-105">**Applies to:**</span></span>
- <span data-ttu-id="5bb04-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5bb04-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="5bb04-107">A tabela `DeviceTvmSoftwareVulnerabilitiesKB` no esquema de busca avançada contém a lista de vulnerabilidades que o [Gerenciamento de Ameaças e Vulnerabilidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)procura nos dispositivos. </span><span class="sxs-lookup"><span data-stu-id="5bb04-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="5bb04-108">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="5bb04-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="5bb04-109">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5bb04-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5bb04-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="5bb04-110">Column name</span></span> | <span data-ttu-id="5bb04-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="5bb04-111">Data type</span></span> | <span data-ttu-id="5bb04-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="5bb04-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="5bb04-113">string</span><span class="sxs-lookup"><span data-stu-id="5bb04-113">string</span></span> | <span data-ttu-id="5bb04-114">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="5bb04-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="5bb04-115">string</span><span class="sxs-lookup"><span data-stu-id="5bb04-115">string</span></span> | <span data-ttu-id="5bb04-116">Pontuação de gravidade atribuída à vulnerabilidade de segurança no Common Vulnerability Scoring System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="5bb04-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="5bb04-117">booliano</span><span class="sxs-lookup"><span data-stu-id="5bb04-117">boolean</span></span> | <span data-ttu-id="5bb04-118">Indica se o código de exploração da vulnerabilidade está disponível publicamente</span><span class="sxs-lookup"><span data-stu-id="5bb04-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="5bb04-119">string</span><span class="sxs-lookup"><span data-stu-id="5bb04-119">string</span></span> | <span data-ttu-id="5bb04-120">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="5bb04-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="5bb04-121">datetime</span><span class="sxs-lookup"><span data-stu-id="5bb04-121">datetime</span></span> | <span data-ttu-id="5bb04-122">Data e hora em que o item ou os metadados relacionados foram modificados pela última vez</span><span class="sxs-lookup"><span data-stu-id="5bb04-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="5bb04-123">datetime</span><span class="sxs-lookup"><span data-stu-id="5bb04-123">datetime</span></span> | <span data-ttu-id="5bb04-124">Data em que a vulnerabilidade foi divulgada ao público</span><span class="sxs-lookup"><span data-stu-id="5bb04-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="5bb04-125">string</span><span class="sxs-lookup"><span data-stu-id="5bb04-125">string</span></span> | <span data-ttu-id="5bb04-126">Descrição da vulnerabilidade e riscos associados</span><span class="sxs-lookup"><span data-stu-id="5bb04-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="5bb04-127">string</span><span class="sxs-lookup"><span data-stu-id="5bb04-127">string</span></span> | <span data-ttu-id="5bb04-128">Lista de todos os produtos de software afetados pela vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="5bb04-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5bb04-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5bb04-129">Related topics</span></span>

- [<span data-ttu-id="5bb04-130">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="5bb04-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5bb04-131">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="5bb04-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5bb04-132">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="5bb04-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5bb04-133">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="5bb04-133">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5bb04-134">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="5bb04-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5bb04-135">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="5bb04-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5bb04-136">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="5bb04-136">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
