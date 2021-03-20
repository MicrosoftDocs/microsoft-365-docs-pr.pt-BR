---
title: Tabela DeviceTvmSoftwareInventory no esquema de busca avançado
description: Saiba mais sobre o inventário de software em seus dispositivos na tabela DeviceTvmSoftwareInventory do esquema de busca avançado.
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0bdd3b8564a01b36d1c21d0f49a29ce1afd98348
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907310"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="188d7-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="188d7-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="188d7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="188d7-105">**Applies to:**</span></span>
- <span data-ttu-id="188d7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="188d7-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT]
> <span data-ttu-id="188d7-107">Algumas informações se relacionam ao produto pré-lançamento, que pode ser substancialmente modificado antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="188d7-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="188d7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="188d7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="188d7-109">A tabela no esquema de busca avançada contém o inventário de Gerenciamento de Vulnerabilidades & Ameaças do software atualmente instalado em dispositivos em sua rede, incluindo informações de fim `DeviceTvmSoftwareInventory` do suporte. [](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)</span><span class="sxs-lookup"><span data-stu-id="188d7-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="188d7-110">Você pode, por exemplo, procurar eventos envolvendo dispositivos instalados com uma versão de software vulnerável no momento.</span><span class="sxs-lookup"><span data-stu-id="188d7-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="188d7-111">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="188d7-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
> <span data-ttu-id="188d7-112">As `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` tabelas e substituíram a `DeviceTvmSoftwareInventoryVulnerabilities` tabela.</span><span class="sxs-lookup"><span data-stu-id="188d7-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="188d7-113">Juntas, as duas primeiras tabelas incluem mais colunas que você pode usar para ajudar a informar suas atividades de gerenciamento de vulnerabilidade ou a procurar dispositivos vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="188d7-113">Together, the first two tables include more columns you can use to help inform your vulnerablity management activities or hunt for vulnerable devices.</span></span>

<span data-ttu-id="188d7-114">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="188d7-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="188d7-115">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="188d7-115">Column name</span></span> | <span data-ttu-id="188d7-116">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="188d7-116">Data type</span></span> | <span data-ttu-id="188d7-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="188d7-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="188d7-118">string</span><span class="sxs-lookup"><span data-stu-id="188d7-118">string</span></span> | <span data-ttu-id="188d7-119">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="188d7-119">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="188d7-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="188d7-120">string</span></span> | <span data-ttu-id="188d7-121">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="188d7-121">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="188d7-122">string</span><span class="sxs-lookup"><span data-stu-id="188d7-122">string</span></span> | <span data-ttu-id="188d7-123">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="188d7-123">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="188d7-124">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="188d7-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="188d7-125">string</span><span class="sxs-lookup"><span data-stu-id="188d7-125">string</span></span> | <span data-ttu-id="188d7-126">Versão do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="188d7-126">Version of the operating system running on the machine</span></span> |
| `OSArchitecture` | <span data-ttu-id="188d7-127">string</span><span class="sxs-lookup"><span data-stu-id="188d7-127">string</span></span> | <span data-ttu-id="188d7-128">Arquitetura do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="188d7-128">Architecture of the operating system running on the machine</span></span> |
| `SoftwareVendor` | <span data-ttu-id="188d7-129">string</span><span class="sxs-lookup"><span data-stu-id="188d7-129">string</span></span> | <span data-ttu-id="188d7-130">Nome do fornecedor de software</span><span class="sxs-lookup"><span data-stu-id="188d7-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="188d7-131">string</span><span class="sxs-lookup"><span data-stu-id="188d7-131">string</span></span> | <span data-ttu-id="188d7-132">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="188d7-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="188d7-133">string</span><span class="sxs-lookup"><span data-stu-id="188d7-133">string</span></span> | <span data-ttu-id="188d7-134">Número da versão do produto software</span><span class="sxs-lookup"><span data-stu-id="188d7-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="188d7-135">string</span><span class="sxs-lookup"><span data-stu-id="188d7-135">string</span></span> | <span data-ttu-id="188d7-136">Indica o estágio de ciclo de vida do produto de software em relação à data especificada de fim de suporte (EOS) ou fim da vida útil (EOL)</span><span class="sxs-lookup"><span data-stu-id="188d7-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="188d7-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="188d7-137">string</span></span> | <span data-ttu-id="188d7-138">Data de fim de suporte (EOS) ou fim da vida útil (EOL) do produto de software</span><span class="sxs-lookup"><span data-stu-id="188d7-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="188d7-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="188d7-139">Related topics</span></span>

- [<span data-ttu-id="188d7-140">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="188d7-140">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="188d7-141">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="188d7-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="188d7-142">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="188d7-142">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="188d7-143">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="188d7-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="188d7-144">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="188d7-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="188d7-145">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="188d7-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="188d7-146">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="188d7-146">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)