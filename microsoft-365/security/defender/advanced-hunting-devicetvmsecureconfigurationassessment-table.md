---
title: Tabela DeviceTvmSecureConfigurationAssessment no esquema de busca avançada
description: Saiba mais sobre eventos de avaliação de segurança na tabela DeviceTvmSecureConfigurationAssessment do esquema de busca avançado. Esses eventos de gerenciamento & de vulnerabilidade fornecem informações de dispositivo, bem como detalhes de configuração de segurança, impacto e informações de conformidade.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, configuração de segurança, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cf37fe2aeac193c6b45f55fd5f5c850470ba6da4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053199"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="e52e7-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="e52e7-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e52e7-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e52e7-106">**Applies to:**</span></span>
- <span data-ttu-id="e52e7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e52e7-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="e52e7-108">Cada linha na tabela `DeviceTvmSecureConfigurationAssessment` contém um evento de avaliação para uma configuração de segurança específica de [Gerenciamento de Vulnerabilidades e Ameaças](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="e52e7-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="e52e7-109">Use esta referência para verificar os últimos resultados da avaliação e determinar se os dispositivos são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="e52e7-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="e52e7-110">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="e52e7-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="e52e7-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="e52e7-111">Column name</span></span> | <span data-ttu-id="e52e7-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="e52e7-112">Data type</span></span> | <span data-ttu-id="e52e7-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="e52e7-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="e52e7-114">string</span><span class="sxs-lookup"><span data-stu-id="e52e7-114">string</span></span> | <span data-ttu-id="e52e7-115">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="e52e7-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="e52e7-116">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e52e7-116">string</span></span> | <span data-ttu-id="e52e7-117">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="e52e7-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="e52e7-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e52e7-118">string</span></span> | <span data-ttu-id="e52e7-119">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e52e7-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="e52e7-120">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="e52e7-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="e52e7-121">datetime</span><span class="sxs-lookup"><span data-stu-id="e52e7-121">datetime</span></span> | <span data-ttu-id="e52e7-122">Data e hora em que o registro foi gerado</span><span class="sxs-lookup"><span data-stu-id="e52e7-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="e52e7-123">string</span><span class="sxs-lookup"><span data-stu-id="e52e7-123">string</span></span> | <span data-ttu-id="e52e7-124">Identificador exclusivo para uma configuração específica</span><span class="sxs-lookup"><span data-stu-id="e52e7-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="e52e7-125">string</span><span class="sxs-lookup"><span data-stu-id="e52e7-125">string</span></span> | <span data-ttu-id="e52e7-126">Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança</span><span class="sxs-lookup"><span data-stu-id="e52e7-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="e52e7-127">string</span><span class="sxs-lookup"><span data-stu-id="e52e7-127">string</span></span> | <span data-ttu-id="e52e7-128">Subcategoria ou subgrupo ao qual a configuração pertence.</span><span class="sxs-lookup"><span data-stu-id="e52e7-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="e52e7-129">Em muitos casos, isso descreve capacidades ou recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="e52e7-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="e52e7-130">string</span><span class="sxs-lookup"><span data-stu-id="e52e7-130">string</span></span> | <span data-ttu-id="e52e7-131">Impacto avaliado da configuração na classificação total (1-10)</span><span class="sxs-lookup"><span data-stu-id="e52e7-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="e52e7-132">booliano</span><span class="sxs-lookup"><span data-stu-id="e52e7-132">boolean</span></span> | <span data-ttu-id="e52e7-133">Indica se a configuração ou política está configurada corretamente</span><span class="sxs-lookup"><span data-stu-id="e52e7-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="e52e7-134">booliano</span><span class="sxs-lookup"><span data-stu-id="e52e7-134">boolean</span></span> | <span data-ttu-id="e52e7-135">Indica se a configuração ou a política se aplica ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="e52e7-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="e52e7-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e52e7-136">string</span></span> | <span data-ttu-id="e52e7-137">Informações contextuais adicionais sobre a configuração ou a política</span><span class="sxs-lookup"><span data-stu-id="e52e7-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="e52e7-138">booliano</span><span class="sxs-lookup"><span data-stu-id="e52e7-138">boolean</span></span> | <span data-ttu-id="e52e7-139">Indica se haverá impacto do usuário se a configuração ou a política for aplicada</span><span class="sxs-lookup"><span data-stu-id="e52e7-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e52e7-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e52e7-140">Related topics</span></span>

- [<span data-ttu-id="e52e7-141">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="e52e7-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e52e7-142">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="e52e7-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e52e7-143">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="e52e7-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="e52e7-144">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="e52e7-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="e52e7-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="e52e7-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e52e7-146">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="e52e7-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="e52e7-147">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="e52e7-147">Overview of Threat & Vulnerability Management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)