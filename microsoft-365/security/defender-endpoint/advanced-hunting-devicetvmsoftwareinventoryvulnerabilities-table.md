---
title: Tabela DeviceTvmSoftwareInventoryVulnerabilities no esquema de busca avançada
description: Saiba mais sobre o inventário de software em seus dispositivos e suas vulnerabilidades na tabela DeviceTvmSoftwareInventoryVulnerabilities do esquema de busca avançada.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID de CVE, DEVICETvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163454"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a><span data-ttu-id="24786-104">DeviceTvmSoftwareInventoryVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="24786-104">DeviceTvmSoftwareInventoryVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="24786-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="24786-105">**Applies to:**</span></span>

- [<span data-ttu-id="24786-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="24786-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="24786-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="24786-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="24786-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="24786-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="24786-109">A tabela`DeviceTvmSoftwareInventoryVulnerabilities`no esquema de busca avançado contém o inventário de software para [Gerenciamento de Vulnerabilidades e Ameaças](next-gen-threat-and-vuln-mgt.md) em seus dispositivos, bem como quaisquer vulnerabilidades conhecidas nesses produtos de software.</span><span class="sxs-lookup"><span data-stu-id="24786-109">The `DeviceTvmSoftwareInventoryVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software on your devices as well as any known vulnerabilities in these software products.</span></span> <span data-ttu-id="24786-110">Esta tabela também inclui informações sobre o sistema operacional, as IDs do CVE e as informações sobre a severidade da vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="24786-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="24786-111">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="24786-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="24786-112">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="24786-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="24786-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="24786-113">Column name</span></span> | <span data-ttu-id="24786-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="24786-114">Data type</span></span> | <span data-ttu-id="24786-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="24786-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="24786-116">string</span><span class="sxs-lookup"><span data-stu-id="24786-116">string</span></span> | <span data-ttu-id="24786-117">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="24786-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="24786-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="24786-118">string</span></span> | <span data-ttu-id="24786-119">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="24786-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="24786-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="24786-120">string</span></span> | <span data-ttu-id="24786-121">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="24786-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="24786-122">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="24786-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="24786-123">string</span><span class="sxs-lookup"><span data-stu-id="24786-123">string</span></span> | <span data-ttu-id="24786-124">Versão do sistema operacional em execução no dispositivo</span><span class="sxs-lookup"><span data-stu-id="24786-124">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="24786-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="24786-125">string</span></span> | <span data-ttu-id="24786-126">Arquitetura do sistema operacional em execução no dispositivo</span><span class="sxs-lookup"><span data-stu-id="24786-126">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="24786-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="24786-127">string</span></span> | <span data-ttu-id="24786-128">Nome do fornecedor de software</span><span class="sxs-lookup"><span data-stu-id="24786-128">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="24786-129">string</span><span class="sxs-lookup"><span data-stu-id="24786-129">string</span></span> | <span data-ttu-id="24786-130">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="24786-130">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="24786-131">string</span><span class="sxs-lookup"><span data-stu-id="24786-131">string</span></span> | <span data-ttu-id="24786-132">Número da versão do produto software</span><span class="sxs-lookup"><span data-stu-id="24786-132">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="24786-133">string</span><span class="sxs-lookup"><span data-stu-id="24786-133">string</span></span> | <span data-ttu-id="24786-134">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="24786-134">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="24786-135">string</span><span class="sxs-lookup"><span data-stu-id="24786-135">string</span></span> | <span data-ttu-id="24786-136">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="24786-136">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |



## <a name="related-topics"></a><span data-ttu-id="24786-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="24786-137">Related topics</span></span>

- [<span data-ttu-id="24786-138">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="24786-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="24786-139">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="24786-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="24786-140">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="24786-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="24786-141">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="24786-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
