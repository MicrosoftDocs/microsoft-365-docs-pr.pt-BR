---
title: Tabela DeviceTvmSecureConfigurationAssessment no esquema de busca avançada
description: Saiba mais sobre & eventos de avaliação de segurança do Gerenciamento de Vulnerabilidades na tabela DeviceTvmSecureConfigurationAssessment do esquema de busca avançado. Esses eventos fornecem informações do dispositivo, bem como detalhes de configuração de segurança, impacto e informações de conformidade.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, configuração de segurança, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 1be5d911d1a2d21abdadce5745151a2778361672
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054097"
---
# <a name="devicetvmsecureconfigurationassessment"></a><span data-ttu-id="61576-105">DeviceTvmSecureConfigurationAssessment</span><span class="sxs-lookup"><span data-stu-id="61576-105">DeviceTvmSecureConfigurationAssessment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61576-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="61576-106">**Applies to:**</span></span>
- [<span data-ttu-id="61576-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="61576-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)



><span data-ttu-id="61576-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="61576-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="61576-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="61576-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="61576-110">Cada linha na tabela `DeviceTvmSecureConfigurationAssessment` contém um evento de avaliação para uma configuração de segurança específica de [Gerenciamento de Vulnerabilidades e Ameaças](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="61576-110">Each row in the `DeviceTvmSecureConfigurationAssessment` table contains an assessment event for a specific security configuration from [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span> <span data-ttu-id="61576-111">Use esta referência para verificar os últimos resultados da avaliação e determinar se os dispositivos são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="61576-111">Use this reference to check the latest assessment results and determine whether devices are compliant.</span></span>

<span data-ttu-id="61576-112">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="61576-112">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="61576-113">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="61576-113">Column name</span></span> | <span data-ttu-id="61576-114">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="61576-114">Data type</span></span> | <span data-ttu-id="61576-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="61576-115">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="61576-116">string</span><span class="sxs-lookup"><span data-stu-id="61576-116">string</span></span> | <span data-ttu-id="61576-117">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="61576-117">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="61576-118">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="61576-118">string</span></span> | <span data-ttu-id="61576-119">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="61576-119">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="61576-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="61576-120">string</span></span> | <span data-ttu-id="61576-121">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="61576-121">Platform of the operating system running on the device.</span></span> <span data-ttu-id="61576-122">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="61576-122">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span>|
| `Timestamp` | <span data-ttu-id="61576-123">datetime</span><span class="sxs-lookup"><span data-stu-id="61576-123">datetime</span></span> |<span data-ttu-id="61576-124">Data e hora em que o registro foi gerado</span><span class="sxs-lookup"><span data-stu-id="61576-124">Date and time when the record was generated</span></span> |
| `ConfigurationId` | <span data-ttu-id="61576-125">string</span><span class="sxs-lookup"><span data-stu-id="61576-125">string</span></span> | <span data-ttu-id="61576-126">Identificador exclusivo para uma configuração específica</span><span class="sxs-lookup"><span data-stu-id="61576-126">Unique identifier for a specific configuration</span></span> |
| `ConfigurationCategory` | <span data-ttu-id="61576-127">string</span><span class="sxs-lookup"><span data-stu-id="61576-127">string</span></span> | <span data-ttu-id="61576-128">Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança</span><span class="sxs-lookup"><span data-stu-id="61576-128">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> |
| `ConfigurationSubcategory` | <span data-ttu-id="61576-129">string</span><span class="sxs-lookup"><span data-stu-id="61576-129">string</span></span> |<span data-ttu-id="61576-130">Subcategoria ou subgrupo ao qual a configuração pertence.</span><span class="sxs-lookup"><span data-stu-id="61576-130">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="61576-131">Em muitos casos, isso descreve capacidades ou recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="61576-131">In many cases, this describes specific capabilities or features.</span></span> |
| `ConfigurationImpact` | <span data-ttu-id="61576-132">string</span><span class="sxs-lookup"><span data-stu-id="61576-132">string</span></span> | <span data-ttu-id="61576-133">Impacto avaliado da configuração na classificação total (1-10)</span><span class="sxs-lookup"><span data-stu-id="61576-133">Rated impact of the configuration to the overall configuration score (1-10)</span></span> |
| `IsCompliant` | <span data-ttu-id="61576-134">booliano</span><span class="sxs-lookup"><span data-stu-id="61576-134">boolean</span></span> | <span data-ttu-id="61576-135">Indica se a configuração ou política está configurada corretamente</span><span class="sxs-lookup"><span data-stu-id="61576-135">Indicates whether the configuration or policy is properly configured</span></span> |
| `IsApplicable` | <span data-ttu-id="61576-136">booliano</span><span class="sxs-lookup"><span data-stu-id="61576-136">boolean</span></span> | <span data-ttu-id="61576-137">Indica se a configuração ou a política se aplica ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="61576-137">Indicates whether the configuration or policy applies to the device</span></span> |
| `Context` | <span data-ttu-id="61576-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="61576-138">string</span></span> | <span data-ttu-id="61576-139">Informações contextuais adicionais sobre a configuração ou a política</span><span class="sxs-lookup"><span data-stu-id="61576-139">Additional contextual information about the configuration or policy</span></span> |
| `IsExpectedUserImpactCompliant` | <span data-ttu-id="61576-140">booliano</span><span class="sxs-lookup"><span data-stu-id="61576-140">boolean</span></span> | <span data-ttu-id="61576-141">Indica se haverá impacto do usuário se a configuração ou a política for aplicada</span><span class="sxs-lookup"><span data-stu-id="61576-141">Indicates whether there will be user impact if the configuration or policy is applied</span></span> |

## <a name="related-topics"></a><span data-ttu-id="61576-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="61576-142">Related topics</span></span>

- [<span data-ttu-id="61576-143">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="61576-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="61576-144">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="61576-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="61576-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="61576-145">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="61576-146">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="61576-146">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)