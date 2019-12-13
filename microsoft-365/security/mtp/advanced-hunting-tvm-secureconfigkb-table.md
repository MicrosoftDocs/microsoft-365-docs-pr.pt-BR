---
title: Tabela DeviceTvmSecureConfigurationAssessmentKB no esquema de busca avançada
description: Saiba mais sobre as várias configurações seguras avaliadas pelo Gerenciamento de Vulnerabilidades e Ameaças na tabela DeviceTvmSecureConfigurationAssessmentKB do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de ameaças e vulnerabilidades, TVM, gerenciamento de dispositivos, configuração de segurança, estrutura MITRE ATT&CK, knowledge base KB, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 62c21545be31c7332fba28348b7159a0d46aa4b3
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910685"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="ea033-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="ea033-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

<span data-ttu-id="ea033-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ea033-105">**Applies to:**</span></span>
- <span data-ttu-id="ea033-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ea033-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="ea033-107">A tabela `DeviceTvmSecureConfigurationAssessmentKB` no esquema de busca avançada contém informações sobre as diversas configurações seguras — por exemplo, se um dispositivo possui atualizações automáticas ativadas, verificado pela [Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="ea033-107">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="ea033-108">Também inclui informações de risco, benchmarks relacionados do setor e técnicas e táticas aplicáveis do MITRE ATT & CK.</span><span class="sxs-lookup"><span data-stu-id="ea033-108">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="ea033-109">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="ea033-109">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="ea033-110">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ea033-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ea033-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="ea033-111">Column name</span></span> | <span data-ttu-id="ea033-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ea033-112">Data type</span></span> | <span data-ttu-id="ea033-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="ea033-113">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="ea033-114">string</span><span class="sxs-lookup"><span data-stu-id="ea033-114">string</span></span> | <span data-ttu-id="ea033-115">Identificador exclusivo para uma configuração específica</span><span class="sxs-lookup"><span data-stu-id="ea033-115">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="ea033-116">string</span><span class="sxs-lookup"><span data-stu-id="ea033-116">string</span></span> | <span data-ttu-id="ea033-117">Impacto avaliado da configuração na classificação total (1-10)</span><span class="sxs-lookup"><span data-stu-id="ea033-117">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="ea033-118">string</span><span class="sxs-lookup"><span data-stu-id="ea033-118">string</span></span> | <span data-ttu-id="ea033-119">Exibir o nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ea033-119">Display name of the user.</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="ea033-120">string</span><span class="sxs-lookup"><span data-stu-id="ea033-120">string</span></span> | <span data-ttu-id="ea033-121">Descrição da configuração</span><span class="sxs-lookup"><span data-stu-id="ea033-121">Description of the task.</span></span> |
| `RiskDescription` | <span data-ttu-id="ea033-122">string</span><span class="sxs-lookup"><span data-stu-id="ea033-122">string</span></span> | <span data-ttu-id="ea033-123">Descrição do risco associado</span><span class="sxs-lookup"><span data-stu-id="ea033-123">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="ea033-124">string</span><span class="sxs-lookup"><span data-stu-id="ea033-124">string</span></span> | <span data-ttu-id="ea033-125">Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança</span><span class="sxs-lookup"><span data-stu-id="ea033-125">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="ea033-126">string</span><span class="sxs-lookup"><span data-stu-id="ea033-126">string</span></span> |<span data-ttu-id="ea033-127">Subcategoria ou subgrupo ao qual a configuração pertence.</span><span class="sxs-lookup"><span data-stu-id="ea033-127">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="ea033-128">Em muitos casos, isso descreve capacidades ou recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="ea033-128">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="ea033-129">string</span><span class="sxs-lookup"><span data-stu-id="ea033-129">string</span></span> | <span data-ttu-id="ea033-130">Lista de benchmarks da indústria recomendando a mesma configuração ou configuração similar</span><span class="sxs-lookup"><span data-stu-id="ea033-130">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="ea033-131">string</span><span class="sxs-lookup"><span data-stu-id="ea033-131">string</span></span> | <span data-ttu-id="ea033-132">Lista de técnicas de estrutura Mitre ATT e CK relacionadas à configuração</span><span class="sxs-lookup"><span data-stu-id="ea033-132">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="ea033-133">string</span><span class="sxs-lookup"><span data-stu-id="ea033-133">string</span></span> | <span data-ttu-id="ea033-134">Lista de táticas de estrutura Mitre ATT e CK relacionadas à configuração</span><span class="sxs-lookup"><span data-stu-id="ea033-134">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ea033-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ea033-135">Related topics</span></span>

- [<span data-ttu-id="ea033-136">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="ea033-136">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ea033-137">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="ea033-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ea033-138">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="ea033-138">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ea033-139">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="ea033-139">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ea033-140">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="ea033-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ea033-141">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="ea033-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ea033-142">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="ea033-142">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
