---
title: Tabela DeviceTvmSoftwareInventory no esquema de busca avançado
description: Saiba mais sobre o inventário de software em seus dispositivos na tabela DeviceTvmSoftwareInventory do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, ameaça & Gerenciamento de Vulnerabilidades, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID de CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: 5f82684ebb10b72ff83a6789c010f5ec9fa099e7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024224"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="7bffa-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="7bffa-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7bffa-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7bffa-105">**Applies to:**</span></span>
- <span data-ttu-id="7bffa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7bffa-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="7bffa-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7bffa-107">Microsoft Defender for Endpoint</span></span>

>[!IMPORTANT]
> <span data-ttu-id="7bffa-108">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="7bffa-108">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7bffa-109">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="7bffa-109">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="7bffa-110">A tabela no esquema de busca avançada contém o inventário de Gerenciamento de Vulnerabilidades & Ameaças do software atualmente instalado em dispositivos em sua rede, incluindo informações de fim `DeviceTvmSoftwareInventory` do suporte. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="7bffa-110">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="7bffa-111">Você pode, por exemplo, procurar eventos envolvendo dispositivos instalados com uma versão de software vulnerável no momento.</span><span class="sxs-lookup"><span data-stu-id="7bffa-111">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="7bffa-112">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="7bffa-112">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="7bffa-113">As `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` tabelas e substituíram a `DeviceTvmSoftwareInventoryVulnerabilities` tabela.</span><span class="sxs-lookup"><span data-stu-id="7bffa-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="7bffa-114">Juntas, as duas primeiras tabelas incluem mais colunas que você pode usar para ajudar a informar suas atividades de gerenciamento de vulnerabilidade ou a procurar dispositivos vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="7bffa-114">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="7bffa-115">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="7bffa-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="7bffa-116">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="7bffa-116">Column name</span></span> | <span data-ttu-id="7bffa-117">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="7bffa-117">Data type</span></span> | <span data-ttu-id="7bffa-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="7bffa-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="7bffa-119">string</span><span class="sxs-lookup"><span data-stu-id="7bffa-119">string</span></span> | <span data-ttu-id="7bffa-120">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="7bffa-120">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="7bffa-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="7bffa-121">string</span></span> | <span data-ttu-id="7bffa-122">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="7bffa-122">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="7bffa-123">string</span><span class="sxs-lookup"><span data-stu-id="7bffa-123">string</span></span> | <span data-ttu-id="7bffa-124">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="7bffa-124">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="7bffa-125">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="7bffa-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="7bffa-126">string</span><span class="sxs-lookup"><span data-stu-id="7bffa-126">string</span></span> | <span data-ttu-id="7bffa-127">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="7bffa-127">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="7bffa-128">string</span><span class="sxs-lookup"><span data-stu-id="7bffa-128">string</span></span> | <span data-ttu-id="7bffa-129">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="7bffa-129">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="7bffa-130">string</span><span class="sxs-lookup"><span data-stu-id="7bffa-130">string</span></span> | <span data-ttu-id="7bffa-131">Nome do fornecedor de software</span><span class="sxs-lookup"><span data-stu-id="7bffa-131">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="7bffa-132">string</span><span class="sxs-lookup"><span data-stu-id="7bffa-132">string</span></span> | <span data-ttu-id="7bffa-133">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="7bffa-133">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="7bffa-134">string</span><span class="sxs-lookup"><span data-stu-id="7bffa-134">string</span></span> | <span data-ttu-id="7bffa-135">Número da versão do produto software</span><span class="sxs-lookup"><span data-stu-id="7bffa-135">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="7bffa-136">string</span><span class="sxs-lookup"><span data-stu-id="7bffa-136">string</span></span> | <span data-ttu-id="7bffa-137">Indica o estágio de ciclo de vida do produto de software em relação à data especificada de fim de suporte (EOS) ou fim da vida útil (EOL)</span><span class="sxs-lookup"><span data-stu-id="7bffa-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="7bffa-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="7bffa-138">string</span></span> | <span data-ttu-id="7bffa-139">Data de fim de suporte (EOS) ou fim da vida útil (EOL) do produto de software</span><span class="sxs-lookup"><span data-stu-id="7bffa-139">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="7bffa-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7bffa-140">Related topics</span></span>

- [<span data-ttu-id="7bffa-141">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="7bffa-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7bffa-142">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="7bffa-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7bffa-143">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="7bffa-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="7bffa-144">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="7bffa-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="7bffa-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="7bffa-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7bffa-146">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="7bffa-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7bffa-147">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="7bffa-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)