---
title: Tabela DeviceTvmSoftwareVulnerabilities no esquema de busca avançado
description: Saiba mais sobre as vulnerabilidades de software encontradas em dispositivos e a lista de atualizações de segurança disponíveis que abordam cada vulnerabilidade na tabela DeviceTvmSoftwareVulnerabilities do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID da CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 6911031e3caa27eff80bb83a3a88643cac2b6918
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053826"
---
# <a name="devicetvmsoftwarevulnerabilities"></a><span data-ttu-id="b4298-104">DeviceTvmSoftwareVulnerabilities</span><span class="sxs-lookup"><span data-stu-id="b4298-104">DeviceTvmSoftwareVulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b4298-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b4298-105">**Applies to:**</span></span>
- <span data-ttu-id="b4298-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4298-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="b4298-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="b4298-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b4298-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="b4298-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b4298-109">A tabela no esquema de busca avançada contém a lista gerenciamento de vulnerabilidades & ameaças em `DeviceTvmSoftwareVulnerabilities` produtos de software instalados. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="b4298-109">The `DeviceTvmSoftwareVulnerabilities` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) list of vulnerabilities in installed software products.</span></span> <span data-ttu-id="b4298-110">Esta tabela também inclui informações sobre o sistema operacional, as IDs do CVE e as informações sobre a severidade da vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="b4298-110">This table also includes operating system information, CVE IDs, and vulnerability severity information.</span></span> <span data-ttu-id="b4298-111">Você pode usar essa tabela, por exemplo, para procurar eventos envolvendo dispositivos que tenham vulnerabilidades graves em seu software.</span><span class="sxs-lookup"><span data-stu-id="b4298-111">You can use this table, for example, to hunt for events involving devices that have severe vulnerabilities in their software.</span></span> <span data-ttu-id="b4298-112">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="b4298-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="b4298-113">As `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` tabelas e substituíram a `DeviceTvmSoftwareInventoryVulnerabilities` tabela.</span><span class="sxs-lookup"><span data-stu-id="b4298-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="b4298-114">Juntas, as duas primeiras tabelas incluem mais colunas que você pode usar para ajudar a informar suas atividades de gerenciamento de vulnerabilidade ou a procurar dispositivos vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="b4298-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="b4298-115">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b4298-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b4298-116">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="b4298-116">Column name</span></span> | <span data-ttu-id="b4298-117">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b4298-117">Data type</span></span> | <span data-ttu-id="b4298-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="b4298-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="b4298-119">string</span><span class="sxs-lookup"><span data-stu-id="b4298-119">string</span></span> | <span data-ttu-id="b4298-120">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="b4298-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b4298-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4298-121">string</span></span> | <span data-ttu-id="b4298-122">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="b4298-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="b4298-123">string</span><span class="sxs-lookup"><span data-stu-id="b4298-123">string</span></span> | <span data-ttu-id="b4298-124">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="b4298-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b4298-125">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b4298-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="b4298-126">string</span><span class="sxs-lookup"><span data-stu-id="b4298-126">string</span></span> | <span data-ttu-id="b4298-127">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="b4298-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="b4298-128">string</span><span class="sxs-lookup"><span data-stu-id="b4298-128">string</span></span> | <span data-ttu-id="b4298-129">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="b4298-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="b4298-130">string</span><span class="sxs-lookup"><span data-stu-id="b4298-130">string</span></span> | <span data-ttu-id="b4298-131">Nome do fornecedor de software</span><span class="sxs-lookup"><span data-stu-id="b4298-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="b4298-132">string</span><span class="sxs-lookup"><span data-stu-id="b4298-132">string</span></span> | <span data-ttu-id="b4298-133">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="b4298-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="b4298-134">string</span><span class="sxs-lookup"><span data-stu-id="b4298-134">string</span></span> | <span data-ttu-id="b4298-135">Número da versão do produto software</span><span class="sxs-lookup"><span data-stu-id="b4298-135">Version number of the software product</span></span> |
| `CveId` | <span data-ttu-id="b4298-136">string</span><span class="sxs-lookup"><span data-stu-id="b4298-136">string</span></span> | <span data-ttu-id="b4298-137">Identificador exclusivo atribuído à vulnerabilidade de segurança sob o sistema Common Vulnerabilities and Exposures (CVE)</span><span class="sxs-lookup"><span data-stu-id="b4298-137">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system</span></span> |
| `VulnerabilitySeverityLevel` | <span data-ttu-id="b4298-138">string</span><span class="sxs-lookup"><span data-stu-id="b4298-138">string</span></span> | <span data-ttu-id="b4298-139">Nível de gravidade atribuído à vulnerabilidade de segurança com base na pontuação CVSS e fatores dinâmicos influenciados pelo cenário de ameaças</span><span class="sxs-lookup"><span data-stu-id="b4298-139">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape</span></span> |
| `RecommendedSecurityUpdate` | <span data-ttu-id="b4298-140">string</span><span class="sxs-lookup"><span data-stu-id="b4298-140">string</span></span> | <span data-ttu-id="b4298-141">Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="b4298-141">Name or description of the security update provided by the software vendor to address the vulnerability</span></span> |
| `RecommendedSecurityUpdateId` | <span data-ttu-id="b4298-142">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b4298-142">string</span></span> | <span data-ttu-id="b4298-143">Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB)</span><span class="sxs-lookup"><span data-stu-id="b4298-143">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> |



## <a name="related-topics"></a><span data-ttu-id="b4298-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b4298-144">Related topics</span></span>

- [<span data-ttu-id="b4298-145">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="b4298-145">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b4298-146">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b4298-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b4298-147">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="b4298-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b4298-148">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="b4298-148">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b4298-149">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="b4298-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b4298-150">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="b4298-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b4298-151">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="b4298-151">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)