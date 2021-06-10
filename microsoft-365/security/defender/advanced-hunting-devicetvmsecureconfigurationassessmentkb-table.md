---
title: Tabela DeviceTvmSecureConfigurationAssessmentKB no esquema de busca avançada
description: Saiba mais sobre as várias configurações seguras avaliadas pelo Gerenciamento de Vulnerabilidades e Ameaças na tabela DeviceTvmSecureConfigurationAssessmentKB do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, ameaça & Gerenciamento de Vulnerabilidades, TVM, gerenciamento de dispositivos, configuração de segurança, estrutura do MITRE ATT&CK, base de conhecimento, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 1dfa710b86afdcfd8a5643555564a0f34c7b4702
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024236"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="5862e-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="5862e-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5862e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5862e-105">**Applies to:**</span></span>
- <span data-ttu-id="5862e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5862e-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="5862e-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5862e-107">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="5862e-108">A tabela `DeviceTvmSecureConfigurationAssessmentKB` no esquema de busca avançada contém informações sobre as diversas configurações seguras — por exemplo, se um dispositivo possui atualizações automáticas ativadas, verificado pela [Gerenciamento de Vulnerabilidades e Ameaças](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="5862e-108">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="5862e-109">Também inclui informações de risco, benchmarks relacionados do setor e técnicas e táticas aplicáveis do MITRE ATT & CK.</span><span class="sxs-lookup"><span data-stu-id="5862e-109">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="5862e-110">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="5862e-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="5862e-111">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="5862e-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="5862e-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="5862e-112">Column name</span></span> | <span data-ttu-id="5862e-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="5862e-113">Data type</span></span> | <span data-ttu-id="5862e-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="5862e-114">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="5862e-115">string</span><span class="sxs-lookup"><span data-stu-id="5862e-115">string</span></span> | <span data-ttu-id="5862e-116">Identificador exclusivo para uma configuração específica</span><span class="sxs-lookup"><span data-stu-id="5862e-116">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="5862e-117">string</span><span class="sxs-lookup"><span data-stu-id="5862e-117">string</span></span> | <span data-ttu-id="5862e-118">Impacto avaliado da configuração na classificação total (1-10)</span><span class="sxs-lookup"><span data-stu-id="5862e-118">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="5862e-119">string</span><span class="sxs-lookup"><span data-stu-id="5862e-119">string</span></span> | <span data-ttu-id="5862e-120">Exibir o nome da configuração</span><span class="sxs-lookup"><span data-stu-id="5862e-120">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="5862e-121">string</span><span class="sxs-lookup"><span data-stu-id="5862e-121">string</span></span> | <span data-ttu-id="5862e-122">Descrição da configuração</span><span class="sxs-lookup"><span data-stu-id="5862e-122">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="5862e-123">string</span><span class="sxs-lookup"><span data-stu-id="5862e-123">string</span></span> | <span data-ttu-id="5862e-124">Descrição do risco associado</span><span class="sxs-lookup"><span data-stu-id="5862e-124">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="5862e-125">string</span><span class="sxs-lookup"><span data-stu-id="5862e-125">string</span></span> | <span data-ttu-id="5862e-126">Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança</span><span class="sxs-lookup"><span data-stu-id="5862e-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="5862e-127">string</span><span class="sxs-lookup"><span data-stu-id="5862e-127">string</span></span> |<span data-ttu-id="5862e-128">Subcategoria ou subgrupo ao qual a configuração pertence.</span><span class="sxs-lookup"><span data-stu-id="5862e-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="5862e-129">Em muitos casos, isso descreve capacidades ou recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="5862e-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="5862e-130">string</span><span class="sxs-lookup"><span data-stu-id="5862e-130">string</span></span> | <span data-ttu-id="5862e-131">Lista de benchmarks da indústria recomendando a mesma configuração ou configuração similar</span><span class="sxs-lookup"><span data-stu-id="5862e-131">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `Tags` | <span data-ttu-id="5862e-132">string</span><span class="sxs-lookup"><span data-stu-id="5862e-132">string</span></span> | <span data-ttu-id="5862e-133">Rótulos que representam vários atributos usados para identificar ou categorizar uma configuração de segurança</span><span class="sxs-lookup"><span data-stu-id="5862e-133">Labels representing various attributes used to identify or categorize a security configuration</span></span> |
| `RemediationOptions` | <span data-ttu-id="5862e-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5862e-134">string</span></span> | <span data-ttu-id="5862e-135">Ações recomendadas para reduzir ou resolver quaisquer riscos associados</span><span class="sxs-lookup"><span data-stu-id="5862e-135">Recommended actions to reduce or address any associated risks</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5862e-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5862e-136">Related topics</span></span>

- [<span data-ttu-id="5862e-137">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="5862e-137">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5862e-138">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="5862e-138">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5862e-139">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="5862e-139">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="5862e-140">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="5862e-140">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="5862e-141">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="5862e-141">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="5862e-142">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="5862e-142">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5862e-143">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="5862e-143">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)