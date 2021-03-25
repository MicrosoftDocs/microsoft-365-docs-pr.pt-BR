---
title: Tabela DeviceTvmSoftwareVulnerabilitiesKB no esquema de busca avançada
description: Saiba mais sobre as vulnerabilidades do software monitoradas pelo Gerenciamento de Ameaças e Vulnerabilidades na tabela DeviceTvmSoftwareVulnerabilitiesKB do esquema de busca avançada.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, esquema, referência, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: a7042ac24822c8f4d866640e005ecd3176bb6409
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052857"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="b48dd-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="b48dd-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b48dd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b48dd-105">**Applies to:**</span></span>
- <span data-ttu-id="b48dd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b48dd-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="b48dd-107">A tabela `DeviceTvmSoftwareVulnerabilitiesKB` no esquema de busca avançada contém a lista de vulnerabilidades que o [Gerenciamento de Ameaças e Vulnerabilidade](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)procura nos dispositivos. </span><span class="sxs-lookup"><span data-stu-id="b48dd-107">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) assesses devices for.</span></span> <span data-ttu-id="b48dd-108">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="b48dd-108">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="b48dd-109">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b48dd-109">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b48dd-110">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="b48dd-110">Column name</span></span> | <span data-ttu-id="b48dd-111">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b48dd-111">Data type</span></span> | <span data-ttu-id="b48dd-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b48dd-112">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="b48dd-113">string</span><span class="sxs-lookup"><span data-stu-id="b48dd-113">string</span></span> | <span data-ttu-id="b48dd-114">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="b48dd-114">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="b48dd-115">string</span><span class="sxs-lookup"><span data-stu-id="b48dd-115">string</span></span> | <span data-ttu-id="b48dd-116">Pontuação de gravidade atribuída à vulnerabilidade de segurança no Common Vulnerability Scoring System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="b48dd-116">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="b48dd-117">booliano</span><span class="sxs-lookup"><span data-stu-id="b48dd-117">boolean</span></span> | <span data-ttu-id="b48dd-118">Indica se o código de exploração da vulnerabilidade está disponível publicamente</span><span class="sxs-lookup"><span data-stu-id="b48dd-118">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="b48dd-119">string</span><span class="sxs-lookup"><span data-stu-id="b48dd-119">string</span></span> | <span data-ttu-id="b48dd-120">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="b48dd-120">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="b48dd-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b48dd-121">datetime</span></span> | <span data-ttu-id="b48dd-122">Data e hora em que o item ou os metadados relacionados foram modificados pela última vez</span><span class="sxs-lookup"><span data-stu-id="b48dd-122">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="b48dd-123">datetime</span><span class="sxs-lookup"><span data-stu-id="b48dd-123">datetime</span></span> | <span data-ttu-id="b48dd-124">Data em que a vulnerabilidade foi divulgada ao público</span><span class="sxs-lookup"><span data-stu-id="b48dd-124">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="b48dd-125">string</span><span class="sxs-lookup"><span data-stu-id="b48dd-125">string</span></span> | <span data-ttu-id="b48dd-126">Descrição da vulnerabilidade e riscos associados</span><span class="sxs-lookup"><span data-stu-id="b48dd-126">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="b48dd-127">string</span><span class="sxs-lookup"><span data-stu-id="b48dd-127">string</span></span> | <span data-ttu-id="b48dd-128">Lista de todos os produtos de software afetados pela vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="b48dd-128">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b48dd-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b48dd-129">Related topics</span></span>

- [<span data-ttu-id="b48dd-130">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="b48dd-130">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b48dd-131">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b48dd-131">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b48dd-132">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="b48dd-132">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b48dd-133">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="b48dd-133">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b48dd-134">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="b48dd-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b48dd-135">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="b48dd-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b48dd-136">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="b48dd-136">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)