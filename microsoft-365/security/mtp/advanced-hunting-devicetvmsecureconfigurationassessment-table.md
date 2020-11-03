---
title: Tabela DeviceTvmSecureConfigurationAssessment no esquema de busca avançada
description: Saiba mais sobre eventos de avaliação de segurança na tabela DeviceTvmSecureConfigurationAssessment do esquema de busca avançada. Essas ameaças & eventos de gerenciamento de vulnerabilidade fornecem informações sobre o dispositivo, bem como detalhes da configuração de segurança, impacto e informações de conformidade.
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bfe63397d194567a7d71de703363083d2fd4fe75
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847603"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="2ec98-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="2ec98-105">DeviceTvmSecureConfigurationAssessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2ec98-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2ec98-106">**Applies to:**</span></span>
- <span data-ttu-id="2ec98-107">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="2ec98-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="2ec98-108">Cada linha na tabela `DeviceTvmSecureConfigurationAssessment` contém um evento de avaliação para uma configuração de segurança específica de [Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span><span class="sxs-lookup"><span data-stu-id="2ec98-108">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).</span></span> <span data-ttu-id="2ec98-109">Use esta referência para verificar os últimos resultados da avaliação e determinar se os dispositivos são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="2ec98-109">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="2ec98-110">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2ec98-110">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2ec98-111">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="2ec98-111">Column name</span></span> | <span data-ttu-id="2ec98-112">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2ec98-112">Data type</span></span> | <span data-ttu-id="2ec98-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="2ec98-113">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="2ec98-114">string</span><span class="sxs-lookup"><span data-stu-id="2ec98-114">string</span></span> | <span data-ttu-id="2ec98-115">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="2ec98-115">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="2ec98-116">string</span><span class="sxs-lookup"><span data-stu-id="2ec98-116">string</span></span> | <span data-ttu-id="2ec98-117">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2ec98-117">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="2ec98-118">string</span><span class="sxs-lookup"><span data-stu-id="2ec98-118">string</span></span> | <span data-ttu-id="2ec98-119">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2ec98-119">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2ec98-120">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2ec98-120">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="2ec98-121">datetime</span><span class="sxs-lookup"><span data-stu-id="2ec98-121">datetime</span></span> | <span data-ttu-id="2ec98-122">Data e hora em que o registro foi gerado</span><span class="sxs-lookup"><span data-stu-id="2ec98-122">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="2ec98-123">string</span><span class="sxs-lookup"><span data-stu-id="2ec98-123">string</span></span> | <span data-ttu-id="2ec98-124">Identificador exclusivo para uma configuração específica</span><span class="sxs-lookup"><span data-stu-id="2ec98-124">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="2ec98-125">string</span><span class="sxs-lookup"><span data-stu-id="2ec98-125">string</span></span> | <span data-ttu-id="2ec98-126">Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança</span><span class="sxs-lookup"><span data-stu-id="2ec98-126">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="2ec98-127">string</span><span class="sxs-lookup"><span data-stu-id="2ec98-127">string</span></span> | <span data-ttu-id="2ec98-128">Subcategoria ou subgrupo ao qual a configuração pertence.</span><span class="sxs-lookup"><span data-stu-id="2ec98-128">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="2ec98-129">Em muitos casos, isso descreve capacidades ou recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="2ec98-129">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="2ec98-130">string</span><span class="sxs-lookup"><span data-stu-id="2ec98-130">string</span></span> | <span data-ttu-id="2ec98-131">Impacto avaliado da configuração na classificação total (1-10)</span><span class="sxs-lookup"><span data-stu-id="2ec98-131">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="2ec98-132">booliano</span><span class="sxs-lookup"><span data-stu-id="2ec98-132">boolean</span></span> | <span data-ttu-id="2ec98-133">Indica se a configuração ou política está configurada corretamente</span><span class="sxs-lookup"><span data-stu-id="2ec98-133">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="2ec98-134">booliano</span><span class="sxs-lookup"><span data-stu-id="2ec98-134">boolean</span></span> | <span data-ttu-id="2ec98-135">Indica se a configuração ou política se aplica ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="2ec98-135">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="2ec98-136">string</span><span class="sxs-lookup"><span data-stu-id="2ec98-136">string</span></span> | <span data-ttu-id="2ec98-137">Informações contextuais adicionais sobre a configuração ou política</span><span class="sxs-lookup"><span data-stu-id="2ec98-137">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="2ec98-138">booliano</span><span class="sxs-lookup"><span data-stu-id="2ec98-138">boolean</span></span> | <span data-ttu-id="2ec98-139">Indica se haverá impacto no usuário se a configuração ou política for aplicada</span><span class="sxs-lookup"><span data-stu-id="2ec98-139">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2ec98-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2ec98-140">Related topics</span></span>

- [<span data-ttu-id="2ec98-141">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="2ec98-141">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2ec98-142">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="2ec98-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2ec98-143">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="2ec98-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2ec98-144">Procure em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="2ec98-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2ec98-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="2ec98-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2ec98-146">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="2ec98-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="2ec98-147">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="2ec98-147">Overview of Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
