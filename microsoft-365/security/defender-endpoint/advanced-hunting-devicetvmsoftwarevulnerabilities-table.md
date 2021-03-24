---
title: Tabela DeviceTvmSoftwareVulnerabilities no esquema de busca avançado
description: Saiba mais sobre vulnerabilidades de software encontradas em dispositivos e a lista de atualizações de segurança disponíveis que abordam cada vulnerabilidade na tabela DeviceTvmSoftwareVulnerabilities do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID de CVE, DEVICETvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b38297cd0fa2e931619ff9c0557d2ae868c7aa4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054344"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="4463f-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="4463f-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4463f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4463f-105">**Applies to:**</span></span>
- [<span data-ttu-id="4463f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4463f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="4463f-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4463f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4463f-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4463f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="4463f-109">A tabela no esquema de busca avançada contém a lista gerenciamento de vulnerabilidades & ameaças em `DeviceTvmSoftwareVulnerabilities` produtos de software instalados. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="4463f-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="4463f-110">Esta tabela também inclui informações sobre o sistema operacional, as IDs do CVE e as informações sobre a severidade da vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="4463f-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="4463f-111">Você pode usar essa tabela, por exemplo, para procurar eventos envolvendo dispositivos que tenham vulnerabilidades graves em seu software.</span><span class="sxs-lookup"><span data-stu-id="4463f-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="4463f-112">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="4463f-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="4463f-113">As `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` tabelas e substituíram a `DeviceTvmSoftwareInventoryVulnerabilities` tabela.</span><span class="sxs-lookup"><span data-stu-id="4463f-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="4463f-114">Juntas, as duas primeiras tabelas incluem mais colunas que você pode usar para ajudar a informar suas atividades de gerenciamento de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="4463f-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="4463f-115">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="4463f-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="4463f-116">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="4463f-116">Column name</span></span> | <span data-ttu-id="4463f-117">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="4463f-117">Data type</span></span> | <span data-ttu-id="4463f-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="4463f-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="4463f-119">string</span><span class="sxs-lookup"><span data-stu-id="4463f-119">string</span></span> | <span data-ttu-id="4463f-120">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="4463f-120">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="4463f-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4463f-121">string</span></span> | <span data-ttu-id="4463f-122">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="4463f-122">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="4463f-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4463f-123">string</span></span> | <span data-ttu-id="4463f-124">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4463f-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="4463f-125">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="4463f-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="4463f-126">string</span><span class="sxs-lookup"><span data-stu-id="4463f-126">string</span></span> | <span data-ttu-id="4463f-127">Versão do sistema operacional em execução no dispositivo</span><span class="sxs-lookup"><span data-stu-id="4463f-127">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="4463f-128">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4463f-128">string</span></span> | <span data-ttu-id="4463f-129">Arquitetura do sistema operacional em execução no dispositivo</span><span class="sxs-lookup"><span data-stu-id="4463f-129">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="4463f-130">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4463f-130">string</span></span> | <span data-ttu-id="4463f-131">Nome do fornecedor de software</span><span class="sxs-lookup"><span data-stu-id="4463f-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="4463f-132">string</span><span class="sxs-lookup"><span data-stu-id="4463f-132">string</span></span> | <span data-ttu-id="4463f-133">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="4463f-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="4463f-134">string</span><span class="sxs-lookup"><span data-stu-id="4463f-134">string</span></span> | <span data-ttu-id="4463f-135">Número da versão do produto software</span><span class="sxs-lookup"><span data-stu-id="4463f-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="4463f-136">string</span><span class="sxs-lookup"><span data-stu-id="4463f-136">string</span></span> | <span data-ttu-id="4463f-137">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="4463f-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="4463f-138">string</span><span class="sxs-lookup"><span data-stu-id="4463f-138">string</span></span> | <span data-ttu-id="4463f-139">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="4463f-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="4463f-140">string</span><span class="sxs-lookup"><span data-stu-id="4463f-140">string</span></span> | <span data-ttu-id="4463f-141">Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="4463f-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="4463f-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4463f-142">string</span></span> | <span data-ttu-id="4463f-143">Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB)</span><span class="sxs-lookup"><span data-stu-id="4463f-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="4463f-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4463f-144">Related topics</span></span>

- [<span data-ttu-id="4463f-145">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="4463f-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4463f-146">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="4463f-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4463f-147">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="4463f-147">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="4463f-148">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="4463f-148">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
