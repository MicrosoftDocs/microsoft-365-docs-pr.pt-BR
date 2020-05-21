---
title: Tabela DeviceTvmSecureConfigurationAssessment no esquema de busca avançada
description: Saiba mais sobre os eventos de avaliação de segurança de Gerenciamento de Vulnerabilidades e Ameaças na tabela DeviceTvmSecureConfigurationAssessment do esquema de busca avançada. Esses eventos fornecem informações do computador, bem como informações de conformidade, impacto e detalhes da configuração de segurança.
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, ameaça & gerenciamento de vulnerabilidades, TVM, gerenciamento de dispositivos, configuração de segurança, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ade218a440f8e7db223460e95363eae2cb659622
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327934"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="b152e-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="b152e-105">DeviceTvmSecureConfigurationAssessment</span></span>

<span data-ttu-id="b152e-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b152e-106">**Applies to:**</span></span>
- <span data-ttu-id="b152e-107">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b152e-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="b152e-108">Cada linha na tabela `DeviceTvmSecureConfigurationAssessment` contém um evento de avaliação para uma configuração de segurança específica de [Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="b152e-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="b152e-109">Use esta referência para verificar os últimos resultados da avaliação e determinar se os dispositivos são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="b152e-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="b152e-110">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="b152e-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="b152e-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="b152e-111">Column name</span></span> | <span data-ttu-id="b152e-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b152e-112">Data type</span></span> | <span data-ttu-id="b152e-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="b152e-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="b152e-114">string</span><span class="sxs-lookup"><span data-stu-id="b152e-114">string</span></span> | <span data-ttu-id="b152e-115">Identificador exclusivo da máquina no serviço</span><span class="sxs-lookup"><span data-stu-id="b152e-115">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b152e-116">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b152e-116">string</span></span> | <span data-ttu-id="b152e-117">Nome de domínio totalmente qualificado (FQDN) da máquina</span><span class="sxs-lookup"><span data-stu-id="b152e-117">Fully qualified domain name (FQDN) of the machine</span></span> |
| `OSPlatform` | <span data-ttu-id="b152e-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b152e-118">string</span></span> | <span data-ttu-id="b152e-119">Plataforma do sistema operacional em execução no computador.</span><span class="sxs-lookup"><span data-stu-id="b152e-119">Platform of the operating system running on the machine.</span></span> <span data-ttu-id="b152e-120">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b152e-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="b152e-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b152e-121">datetime</span></span> | <span data-ttu-id="b152e-122">Data e hora em que o registro foi gerado</span><span class="sxs-lookup"><span data-stu-id="b152e-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="b152e-123">string</span><span class="sxs-lookup"><span data-stu-id="b152e-123">string</span></span> | <span data-ttu-id="b152e-124">Identificador exclusivo para uma configuração específica</span><span class="sxs-lookup"><span data-stu-id="b152e-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="b152e-125">string</span><span class="sxs-lookup"><span data-stu-id="b152e-125">string</span></span> | <span data-ttu-id="b152e-126">Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança</span><span class="sxs-lookup"><span data-stu-id="b152e-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="b152e-127">string</span><span class="sxs-lookup"><span data-stu-id="b152e-127">string</span></span> | <span data-ttu-id="b152e-128">Subcategoria ou subgrupo ao qual a configuração pertence.</span><span class="sxs-lookup"><span data-stu-id="b152e-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="b152e-129">Em muitos casos, isso descreve capacidades ou recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="b152e-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="b152e-130">string</span><span class="sxs-lookup"><span data-stu-id="b152e-130">string</span></span> | <span data-ttu-id="b152e-131">Impacto avaliado da configuração na classificação total (1-10)</span><span class="sxs-lookup"><span data-stu-id="b152e-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="b152e-132">booliano</span><span class="sxs-lookup"><span data-stu-id="b152e-132">boolean</span></span> | <span data-ttu-id="b152e-133">Indica se a configuração ou política está configurada corretamente</span><span class="sxs-lookup"><span data-stu-id="b152e-133">Indicates whether the configuration or policy is properly configured</span></span> |

## <a name="related-topics"></a><span data-ttu-id="b152e-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b152e-134">Related topics</span></span>

- [<span data-ttu-id="b152e-135">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="b152e-135">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b152e-136">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b152e-136">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b152e-137">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="b152e-137">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b152e-138">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="b152e-138">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b152e-139">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="b152e-139">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b152e-140">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="b152e-140">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b152e-141">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="b152e-141">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
