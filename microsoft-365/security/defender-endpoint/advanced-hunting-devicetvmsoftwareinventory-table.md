---
title: Tabela DeviceTvmSoftwareInventory no esquema de busca avançado
description: Saiba mais sobre o inventário de software em seus dispositivos na tabela DeviceTvmSoftwareInventory do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID de CVE, DEVICETvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408618"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="25f84-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="25f84-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="25f84-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="25f84-105">**Applies to:**</span></span>
- [<span data-ttu-id="25f84-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="25f84-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="25f84-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="25f84-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="25f84-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="25f84-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="25f84-109">A tabela no esquema de busca avançada contém o inventário de gerenciamento de ameaças e vulnerabilidades do software atualmente instalado em dispositivos em sua rede, incluindo informações de `DeviceTvmSoftwareInventory` fim de suporte. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="25f84-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="25f84-110">Você pode, por exemplo, procurar eventos envolvendo dispositivos instalados com uma versão de software vulnerável no momento.</span><span class="sxs-lookup"><span data-stu-id="25f84-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="25f84-111">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="25f84-111">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="25f84-112">DeviceTVMSoftwareInventory contém todo o software que o gerenciamento de ameaças e vulnerabilidades conseguiu corresponder a uma Enumeração de Plataforma Comum (CPE) – se está vulnerável ou não.</span><span class="sxs-lookup"><span data-stu-id="25f84-112">DeviceTVMSoftwareInventory contains all the software which threat and vulnerability management was able to match to a Common Platform Enumeration (CPE) – whether it is vulnerable or not.</span></span>

>[!NOTE]
><span data-ttu-id="25f84-113">As `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` tabelas e substituíram a `DeviceTvmSoftwareInventoryVulnerabilities` tabela.</span><span class="sxs-lookup"><span data-stu-id="25f84-113">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="25f84-114">Juntas, as duas primeiras tabelas incluem mais colunas que você pode usar para ajudar a informar suas atividades de gerenciamento de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="25f84-114">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="25f84-115">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="25f84-115">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="25f84-116">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="25f84-116">Column name</span></span> | <span data-ttu-id="25f84-117">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="25f84-117">Data type</span></span> | <span data-ttu-id="25f84-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="25f84-118">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="25f84-119">string</span><span class="sxs-lookup"><span data-stu-id="25f84-119">string</span></span> | <span data-ttu-id="25f84-120">Identificador exclusivo do dispositivo no serviço.</span><span class="sxs-lookup"><span data-stu-id="25f84-120">Unique identifier for the device in the service.</span></span> |
| `DeviceName` | <span data-ttu-id="25f84-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="25f84-121">string</span></span> | <span data-ttu-id="25f84-122">Nome de domínio totalmente qualificado (FQDN) do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25f84-122">Fully qualified domain name (FQDN) of the device.</span></span> |
| `OSPlatform` | <span data-ttu-id="25f84-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="25f84-123">string</span></span> | <span data-ttu-id="25f84-124">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25f84-124">Platform of the operating system running on the device.</span></span> <span data-ttu-id="25f84-125">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="25f84-125">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="25f84-126">string</span><span class="sxs-lookup"><span data-stu-id="25f84-126">string</span></span> | <span data-ttu-id="25f84-127">Versão do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25f84-127">Version of the operating system running on the device.</span></span> |
| `OSArchitecture` | <span data-ttu-id="25f84-128">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="25f84-128">string</span></span> | <span data-ttu-id="25f84-129">Arquitetura do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25f84-129">Architecture of the operating system running on the device.</span></span> |
| `SoftwareVendor` | <span data-ttu-id="25f84-130">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="25f84-130">string</span></span> | <span data-ttu-id="25f84-131">Nome do fornecedor de software.</span><span class="sxs-lookup"><span data-stu-id="25f84-131">Name of the software vendor.</span></span> |
| `SoftwareName` | <span data-ttu-id="25f84-132">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="25f84-132">string</span></span> | <span data-ttu-id="25f84-133">Nome do produto de software.</span><span class="sxs-lookup"><span data-stu-id="25f84-133">Name of the software product.</span></span> |
| `SoftwareVersion` | <span data-ttu-id="25f84-134">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="25f84-134">string</span></span> | <span data-ttu-id="25f84-135">Número da versão do produto de software.</span><span class="sxs-lookup"><span data-stu-id="25f84-135">Version number of the software product.</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="25f84-136">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="25f84-136">string</span></span> | <span data-ttu-id="25f84-137">Indica o estágio de ciclo de vida do produto de software em relação à data especificada de fim de suporte (EOS) ou fim de vida útil (EOL).</span><span class="sxs-lookup"><span data-stu-id="25f84-137">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date.</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="25f84-138">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="25f84-138">string</span></span> | <span data-ttu-id="25f84-139">Data de fim de suporte (EOS) ou fim da vida útil (EOL) do produto de software.</span><span class="sxs-lookup"><span data-stu-id="25f84-139">End-of-support (EOS) or end-of-life (EOL) date of the software product.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="25f84-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="25f84-140">Related topics</span></span>

- [<span data-ttu-id="25f84-141">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="25f84-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="25f84-142">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="25f84-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="25f84-143">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="25f84-143">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="25f84-144">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="25f84-144">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)
