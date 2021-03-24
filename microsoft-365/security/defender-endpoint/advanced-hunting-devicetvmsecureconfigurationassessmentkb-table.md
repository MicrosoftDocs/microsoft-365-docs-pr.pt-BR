---
title: Tabela DeviceTvmSecureConfigurationAssessmentKB no esquema de busca avançada
description: Saiba mais sobre as várias configurações seguras avaliadas pelo Gerenciamento de Vulnerabilidades & Ameaça na tabela DeviceTvmSecureConfigurationAssessmentKB do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, configuração de segurança, estrutura de CK do MITRE AT&T, base de conhecimento, KB, DeviceTvmSecureConfigurationAssessmentKB
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
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054096"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a><span data-ttu-id="7fe9f-104">DeviceTvmSecureConfigurationAssessmentKB</span><span class="sxs-lookup"><span data-stu-id="7fe9f-104">DeviceTvmSecureConfigurationAssessmentKB</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7fe9f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7fe9f-105">**Applies to:**</span></span>
- [<span data-ttu-id="7fe9f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7fe9f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="7fe9f-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="7fe9f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7fe9f-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="7fe9f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="7fe9f-109">A tabela `DeviceTvmSecureConfigurationAssessmentKB` no esquema de busca avançada contém informações sobre as diversas configurações seguras — por exemplo, se um dispositivo possui atualizações automáticas ativadas, verificado pela [Gerenciamento de Vulnerabilidades e Ameaças](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="7fe9f-109">The `DeviceTvmSecureConfigurationAssessmentKB` table in the advanced hunting schema contains information about the various secure configurations — such as whether a device has automatic updates on — checked by [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="7fe9f-110">Também inclui informações de risco, benchmarks relacionados do setor e técnicas e táticas aplicáveis do MITRE ATT & CK.</span><span class="sxs-lookup"><span data-stu-id="7fe9f-110">It also includes risk information, related industry benchmarks, and applicable MITRE ATT&CK techniques and tactics.</span></span> <span data-ttu-id="7fe9f-111">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="7fe9f-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="7fe9f-112">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="7fe9f-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="7fe9f-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="7fe9f-113">Column name</span></span> | <span data-ttu-id="7fe9f-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="7fe9f-114">Data type</span></span> | <span data-ttu-id="7fe9f-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="7fe9f-115">Description</span></span> |
|-------------|-----------|-------------|
| `ConfigurationId` | <span data-ttu-id="7fe9f-116">string</span><span class="sxs-lookup"><span data-stu-id="7fe9f-116">string</span></span> | <span data-ttu-id="7fe9f-117">Identificador exclusivo para uma configuração específica</span><span class="sxs-lookup"><span data-stu-id="7fe9f-117">Unique identifier for a specific configuration</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="7fe9f-118">string</span><span class="sxs-lookup"><span data-stu-id="7fe9f-118">string</span></span> | <span data-ttu-id="7fe9f-119">Impacto avaliado da configuração na classificação total (1-10)</span><span class="sxs-lookup"><span data-stu-id="7fe9f-119">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `ConfigurationName` | <span data-ttu-id="7fe9f-120">string</span><span class="sxs-lookup"><span data-stu-id="7fe9f-120">string</span></span> | <span data-ttu-id="7fe9f-121">Exibir o nome da configuração</span><span class="sxs-lookup"><span data-stu-id="7fe9f-121">Display name of the configuration</span></span> |
| `ConfigurationDescription` | <span data-ttu-id="7fe9f-122">string</span><span class="sxs-lookup"><span data-stu-id="7fe9f-122">string</span></span> | <span data-ttu-id="7fe9f-123">Descrição da configuração</span><span class="sxs-lookup"><span data-stu-id="7fe9f-123">Description of the configuration</span></span> |
| `RiskDescription` | <span data-ttu-id="7fe9f-124">string</span><span class="sxs-lookup"><span data-stu-id="7fe9f-124">string</span></span> | <span data-ttu-id="7fe9f-125">Descrição do risco associado</span><span class="sxs-lookup"><span data-stu-id="7fe9f-125">Description of the associated risk</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="7fe9f-126">string</span><span class="sxs-lookup"><span data-stu-id="7fe9f-126">string</span></span> | <span data-ttu-id="7fe9f-127">Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança</span><span class="sxs-lookup"><span data-stu-id="7fe9f-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span>|
| `ConfigurationSubcategory` | <span data-ttu-id="7fe9f-128">string</span><span class="sxs-lookup"><span data-stu-id="7fe9f-128">string</span></span> |<span data-ttu-id="7fe9f-129">Subcategoria ou subgrupo ao qual a configuração pertence.</span><span class="sxs-lookup"><span data-stu-id="7fe9f-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="7fe9f-130">Em muitos casos, isso descreve capacidades ou recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="7fe9f-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationBenchmarks` | <span data-ttu-id="7fe9f-131">string</span><span class="sxs-lookup"><span data-stu-id="7fe9f-131">string</span></span> | <span data-ttu-id="7fe9f-132">Lista de benchmarks da indústria recomendando a mesma configuração ou configuração similar</span><span class="sxs-lookup"><span data-stu-id="7fe9f-132">List of industry benchmarks recommending the same or similar configuration</span></span> |
| `RelatedMitreTechniques` | <span data-ttu-id="7fe9f-133">string</span><span class="sxs-lookup"><span data-stu-id="7fe9f-133">string</span></span> | <span data-ttu-id="7fe9f-134">Lista de técnicas de estrutura Mitre ATT e CK relacionadas à configuração</span><span class="sxs-lookup"><span data-stu-id="7fe9f-134">List of Mitre ATT&CK framework techniques related to the configuration</span></span> |
| `RelatedMitreTactics ` | <span data-ttu-id="7fe9f-135">string</span><span class="sxs-lookup"><span data-stu-id="7fe9f-135">string</span></span> | <span data-ttu-id="7fe9f-136">Lista de táticas de estrutura Mitre ATT e CK relacionadas à configuração</span><span class="sxs-lookup"><span data-stu-id="7fe9f-136">List of Mitre ATT&CK framework tactics related to the configuration</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7fe9f-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7fe9f-137">Related topics</span></span>

- [<span data-ttu-id="7fe9f-138">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="7fe9f-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7fe9f-139">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="7fe9f-139">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7fe9f-140">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="7fe9f-140">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="7fe9f-141">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="7fe9f-141">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
