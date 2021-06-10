---
title: Tabela DeviceTvmSecureConfigurationAssessment no esquema de busca avançada
description: Saiba mais sobre eventos de avaliação de segurança na tabela DeviceTvmSecureConfigurationAssessment do esquema de busca avançado. Esses eventos & Gerenciamento de Vulnerabilidades ameaças fornecem informações do dispositivo, bem como detalhes de configuração de segurança, impacto e informações de conformidade.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, ameaça & Gerenciamento de Vulnerabilidades, TVM, gerenciamento de dispositivos, configuração de segurança, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2e3e649911cb2ce63c2a49be0ebc93e35e8055d6
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024212"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="f314b-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="f314b-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f314b-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f314b-106">**Applies to:**</span></span>
- <span data-ttu-id="f314b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f314b-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="f314b-108">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f314b-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="f314b-109">Cada linha na tabela `DeviceTvmSecureConfigurationAssessment` contém um evento de avaliação para uma configuração de segurança específica de [Gerenciamento de Vulnerabilidades e Ameaças](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="f314b-109">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="f314b-110">Use esta referência para verificar os últimos resultados da avaliação e determinar se os dispositivos são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="f314b-110">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="f314b-111">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f314b-111">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f314b-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="f314b-112">Column name</span></span> | <span data-ttu-id="f314b-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f314b-113">Data type</span></span> | <span data-ttu-id="f314b-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="f314b-114">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="f314b-115">string</span><span class="sxs-lookup"><span data-stu-id="f314b-115">string</span></span> | <span data-ttu-id="f314b-116">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="f314b-116">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="f314b-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f314b-117">string</span></span> | <span data-ttu-id="f314b-118">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f314b-118">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="f314b-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f314b-119">string</span></span> | <span data-ttu-id="f314b-120">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f314b-120">Platform of the operating system running on the device.</span></span> <span data-ttu-id="f314b-121">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="f314b-121">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="f314b-122">datetime</span><span class="sxs-lookup"><span data-stu-id="f314b-122">datetime</span></span> | <span data-ttu-id="f314b-123">Data e hora em que o registro foi gerado</span><span class="sxs-lookup"><span data-stu-id="f314b-123">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="f314b-124">string</span><span class="sxs-lookup"><span data-stu-id="f314b-124">string</span></span> | <span data-ttu-id="f314b-125">Identificador exclusivo para uma configuração específica</span><span class="sxs-lookup"><span data-stu-id="f314b-125">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="f314b-126">string</span><span class="sxs-lookup"><span data-stu-id="f314b-126">string</span></span> | <span data-ttu-id="f314b-127">Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança</span><span class="sxs-lookup"><span data-stu-id="f314b-127">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="f314b-128">string</span><span class="sxs-lookup"><span data-stu-id="f314b-128">string</span></span> | <span data-ttu-id="f314b-129">Subcategoria ou subgrupo ao qual a configuração pertence.</span><span class="sxs-lookup"><span data-stu-id="f314b-129">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="f314b-130">Em muitos casos, isso descreve capacidades ou recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="f314b-130">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="f314b-131">string</span><span class="sxs-lookup"><span data-stu-id="f314b-131">string</span></span> | <span data-ttu-id="f314b-132">Impacto avaliado da configuração na classificação total (1-10)</span><span class="sxs-lookup"><span data-stu-id="f314b-132">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="f314b-133">booliano</span><span class="sxs-lookup"><span data-stu-id="f314b-133">boolean</span></span> | <span data-ttu-id="f314b-134">Indica se a configuração ou política está configurada corretamente</span><span class="sxs-lookup"><span data-stu-id="f314b-134">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="f314b-135">booliano</span><span class="sxs-lookup"><span data-stu-id="f314b-135">boolean</span></span> | <span data-ttu-id="f314b-136">Indica se a configuração ou a política se aplica ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="f314b-136">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="f314b-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f314b-137">string</span></span> | <span data-ttu-id="f314b-138">Informações contextuais adicionais sobre a configuração ou a política</span><span class="sxs-lookup"><span data-stu-id="f314b-138">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpact` | <span data-ttu-id="f314b-139">booliano</span><span class="sxs-lookup"><span data-stu-id="f314b-139">boolean</span></span> | <span data-ttu-id="f314b-140">Indica se haverá impacto do usuário se a configuração ou a política for aplicada</span><span class="sxs-lookup"><span data-stu-id="f314b-140">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="f314b-141">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f314b-141">Related topics</span></span>

- [<span data-ttu-id="f314b-142">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="f314b-142">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f314b-143">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="f314b-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f314b-144">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="f314b-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f314b-145">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="f314b-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f314b-146">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="f314b-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f314b-147">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="f314b-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="f314b-148">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="f314b-148">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)