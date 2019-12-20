---
title: Tabela DeviceTvmSoftwareInventoryVulnerabilities no esquema de busca avançada
description: Saiba mais sobre o inventário de software em seus dispositivos e suas vulnerabilidades na tabela DeviceTvmSoftwareInventoryVulnerabilities do esquema de busca avançada.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, esquema, referência, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de ameaças e vulnerabilidades, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID de CVE, OS, DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 6aca41e46af8ba94f87e7ee91059c3d11a4fbe9e
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808626"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="04add-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="04add-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

<span data-ttu-id="04add-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="04add-105">**Applies to:**</span></span>
- <span data-ttu-id="04add-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="04add-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="04add-107">A tabela`DeviceTvmSoftwareInventoryVulnerabilities`no esquema de busca avançado contém o inventário de software para [Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) em seus dispositivos, bem como quaisquer vulnerabilidades conhecidas nesses produtos de software.</span><span class="sxs-lookup"><span data-stu-id="04add-107">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="04add-108">Esta tabela também inclui informações sobre o sistema operacional, as IDs do CVE e as informações sobre a severidade da vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="04add-108">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="04add-109">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="04add-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="04add-110">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="04add-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="04add-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="04add-111">Column name</span></span> | <span data-ttu-id="04add-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="04add-112">Data type</span></span> | <span data-ttu-id="04add-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="04add-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="04add-114">string</span><span class="sxs-lookup"><span data-stu-id="04add-114">string</span></span> | <span data-ttu-id="04add-115">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="04add-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="04add-116">string</span><span class="sxs-lookup"><span data-stu-id="04add-116">string</span></span> | <span data-ttu-id="04add-117">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="04add-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="04add-118">string</span><span class="sxs-lookup"><span data-stu-id="04add-118">string</span></span> | <span data-ttu-id="04add-119">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="04add-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="04add-120">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="04add-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="04add-121">string</span><span class="sxs-lookup"><span data-stu-id="04add-121">string</span></span> | <span data-ttu-id="04add-122">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="04add-122">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="04add-123">string</span><span class="sxs-lookup"><span data-stu-id="04add-123">string</span></span> | <span data-ttu-id="04add-124">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="04add-124">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="04add-125">string</span><span class="sxs-lookup"><span data-stu-id="04add-125">string</span></span> | <span data-ttu-id="04add-126">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="04add-126">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `SoftwareName` | <span data-ttu-id="04add-127">string</span><span class="sxs-lookup"><span data-stu-id="04add-127">string</span></span> | <span data-ttu-id="04add-128">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="04add-128">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="04add-129">string</span><span class="sxs-lookup"><span data-stu-id="04add-129">string</span></span> | <span data-ttu-id="04add-130">Número da versão do produto software</span><span class="sxs-lookup"><span data-stu-id="04add-130">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="04add-131">string</span><span class="sxs-lookup"><span data-stu-id="04add-131">string</span></span> | <span data-ttu-id="04add-132">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="04add-132">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="04add-133">string</span><span class="sxs-lookup"><span data-stu-id="04add-133">string</span></span> | <span data-ttu-id="04add-134">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="04add-134">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="04add-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="04add-135">Related topics</span></span>

- [<span data-ttu-id="04add-136">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="04add-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="04add-137">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="04add-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="04add-138">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="04add-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="04add-139">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="04add-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="04add-140">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="04add-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="04add-141">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="04add-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="04add-142">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="04add-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
