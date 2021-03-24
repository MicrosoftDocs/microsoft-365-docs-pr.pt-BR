---
title: Tabela DeviceTvmSoftwareVulnerabilitiesKB no esquema de busca avançada
description: Saiba mais sobre as vulnerabilidades do software monitoradas pelo Gerenciamento de Ameaças e Vulnerabilidades na tabela DeviceTvmSoftwareVulnerabilitiesKB do esquema de busca avançada.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID de CVE, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 772a287097f0b204eb329d066cdd81c4eef7a755
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053055"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a><span data-ttu-id="926b4-104">DeviceTvmSoftwareVulnerabilitiesKB</span><span class="sxs-lookup"><span data-stu-id="926b4-104">DeviceTvmSoftwareVulnerabilitiesKB</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="926b4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="926b4-105">**Applies to:**</span></span>
- [<span data-ttu-id="926b4-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="926b4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="926b4-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="926b4-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="926b4-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="926b4-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="926b4-109">A tabela `DeviceTvmSoftwareVulnerabilitiesKB` no esquema de busca avançada contém a lista de vulnerabilidades que o [Gerenciamento de Ameaças e Vulnerabilidade](next-gen-threat-and-vuln-mgt.md)procura nos dispositivos. </span><span class="sxs-lookup"><span data-stu-id="926b4-109">The `DeviceTvmSoftwareVulnerabilitiesKB` table in the advanced hunting schema contains the list of vulnerabilities [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) assesses devices for.</span></span> <span data-ttu-id="926b4-110">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="926b4-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="926b4-111">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="926b4-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="926b4-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="926b4-112">Column name</span></span> | <span data-ttu-id="926b4-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="926b4-113">Data type</span></span> | <span data-ttu-id="926b4-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="926b4-114">Description</span></span> |
|-------------|-----------|-------------|
| `CveId` | <span data-ttu-id="926b4-115">string</span><span class="sxs-lookup"><span data-stu-id="926b4-115">string</span></span> | <span data-ttu-id="926b4-116">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="926b4-116">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `CvssScore` | <span data-ttu-id="926b4-117">string</span><span class="sxs-lookup"><span data-stu-id="926b4-117">string</span></span> | <span data-ttu-id="926b4-118">Pontuação de gravidade atribuída à vulnerabilidade de segurança no Common Vulnerability Scoring System (CVSS)</span><span class="sxs-lookup"><span data-stu-id="926b4-118">Severity score assigned to the security vulnerability under th Common Vulnerability Scoring System (CVSS)</span></span> |
| `IsExploitAvailable` | <span data-ttu-id="926b4-119">booliano</span><span class="sxs-lookup"><span data-stu-id="926b4-119">boolean</span></span> | <span data-ttu-id="926b4-120">Indica se o código de exploração da vulnerabilidade está disponível publicamente</span><span class="sxs-lookup"><span data-stu-id="926b4-120">Indicates whether exploit code for the vulnerability is publicly available</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="926b4-121">string</span><span class="sxs-lookup"><span data-stu-id="926b4-121">string</span></span> | <span data-ttu-id="926b4-122">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="926b4-122">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `LastModifiedTime` | <span data-ttu-id="926b4-123">datetime</span><span class="sxs-lookup"><span data-stu-id="926b4-123">datetime</span></span> | <span data-ttu-id="926b4-124">Data e hora em que o item ou os metadados relacionados foram modificados pela última vez</span><span class="sxs-lookup"><span data-stu-id="926b4-124">Date and time the item or related metadata was last modified</span></span> |
| `PublishedDate` | <span data-ttu-id="926b4-125">datetime</span><span class="sxs-lookup"><span data-stu-id="926b4-125">datetime</span></span> | <span data-ttu-id="926b4-126">Data em que a vulnerabilidade foi divulgada ao público</span><span class="sxs-lookup"><span data-stu-id="926b4-126">Date vulnerability was disclosed to public</span></span> |
| `VulnerabilityDescription` | <span data-ttu-id="926b4-127">string</span><span class="sxs-lookup"><span data-stu-id="926b4-127">string</span></span> | <span data-ttu-id="926b4-128">Descrição da vulnerabilidade e riscos associados</span><span class="sxs-lookup"><span data-stu-id="926b4-128">Description of vulnerability and associated risks</span></span> |
| `AffectedSoftware` | <span data-ttu-id="926b4-129">string</span><span class="sxs-lookup"><span data-stu-id="926b4-129">string</span></span> | <span data-ttu-id="926b4-130">Lista de todos os produtos de software afetados pela vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="926b4-130">List of all software products affected by the vulnerability</span></span> |

## <a name="related-topics"></a><span data-ttu-id="926b4-131">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="926b4-131">Related topics</span></span>

- [<span data-ttu-id="926b4-132">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="926b4-132">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="926b4-133">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="926b4-133">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="926b4-134">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="926b4-134">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="926b4-135">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="926b4-135">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
