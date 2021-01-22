---
title: Tabela DeviceTvmSoftwareInventoryVulnerabilities no esquema de busca avançada
description: Saiba mais sobre o inventário de software em seus dispositivos e suas vulnerabilidades na tabela DeviceTvmSoftwareInventoryVulnerabilities do esquema de busca avançada.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades do &, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 517f974657032a1a4b7fee5888b0c681ec8063d7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931069"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="f8f9e-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="f8f9e-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f8f9e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f8f9e-105">**Applies to:**</span></span>
- <span data-ttu-id="f8f9e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8f9e-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="f8f9e-107">A tabela`DeviceTvmSoftwareInventoryVulnerabilities`no esquema de busca avançado contém o inventário de software para [Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) em seus dispositivos, bem como quaisquer vulnerabilidades conhecidas nesses produtos de software.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="f8f9e-108">Esta tabela também inclui informações sobre o sistema operacional, as IDs do CVE e as informações sobre a severidade da vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="f8f9e-109">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="f8f9e-110">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f8f9e-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f8f9e-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="f8f9e-111">Column name</span></span> | <span data-ttu-id="f8f9e-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f8f9e-112">Data type</span></span> | <span data-ttu-id="f8f9e-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f8f9e-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="f8f9e-114">string</span><span class="sxs-lookup"><span data-stu-id="f8f9e-114">string</span></span> | <span data-ttu-id="f8f9e-115">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="f8f9e-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f8f9e-116">string</span><span class="sxs-lookup"><span data-stu-id="f8f9e-116">string</span></span> | <span data-ttu-id="f8f9e-117">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="f8f9e-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="f8f9e-118">string</span><span class="sxs-lookup"><span data-stu-id="f8f9e-118">string</span></span> | <span data-ttu-id="f8f9e-119">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="f8f9e-120">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="f8f9e-121">string</span><span class="sxs-lookup"><span data-stu-id="f8f9e-121">string</span></span> | <span data-ttu-id="f8f9e-122">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="f8f9e-123">string</span><span class="sxs-lookup"><span data-stu-id="f8f9e-123">string</span></span> | <span data-ttu-id="f8f9e-124">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="f8f9e-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="f8f9e-125">string</span><span class="sxs-lookup"><span data-stu-id="f8f9e-125">string</span></span> | <span data-ttu-id="f8f9e-126">Nome do fornecedor do software</span><span class="sxs-lookup"><span data-stu-id="f8f9e-126">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="f8f9e-127">string</span><span class="sxs-lookup"><span data-stu-id="f8f9e-127">string</span></span> | <span data-ttu-id="f8f9e-128">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="f8f9e-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="f8f9e-129">string</span><span class="sxs-lookup"><span data-stu-id="f8f9e-129">string</span></span> | <span data-ttu-id="f8f9e-130">Número da versão do produto software</span><span class="sxs-lookup"><span data-stu-id="f8f9e-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="f8f9e-131">string</span><span class="sxs-lookup"><span data-stu-id="f8f9e-131">string</span></span> | <span data-ttu-id="f8f9e-132">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="f8f9e-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="f8f9e-133">string</span><span class="sxs-lookup"><span data-stu-id="f8f9e-133">string</span></span> | <span data-ttu-id="f8f9e-134">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="f8f9e-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="f8f9e-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f8f9e-135">Related topics</span></span>

- [<span data-ttu-id="f8f9e-136">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="f8f9e-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f8f9e-137">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="f8f9e-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f8f9e-138">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="f8f9e-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f8f9e-139">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="f8f9e-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f8f9e-140">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="f8f9e-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f8f9e-141">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="f8f9e-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="f8f9e-142">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="f8f9e-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
