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
ms.openlocfilehash: fc9e5fb29518207c5360d5fbe29b8b4848d350e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054221"
---
# <a name="devicetvmsoftwareinventory"></a><span data-ttu-id="b522d-104">DeviceTvmSoftwareInventory</span><span class="sxs-lookup"><span data-stu-id="b522d-104">DeviceTvmSoftwareInventory</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b522d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b522d-105">**Applies to:**</span></span>
- [<span data-ttu-id="b522d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b522d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="b522d-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b522d-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b522d-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b522d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b522d-109">A tabela no esquema de busca avançada contém o inventário de Gerenciamento de Vulnerabilidades & Ameaças do software atualmente instalado em dispositivos em sua rede, incluindo informações de fim `DeviceTvmSoftwareInventory` do suporte. [](next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="b522d-109">The `DeviceTvmSoftwareInventory` table in the advanced hunting schema contains the [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md) inventory of software currently installed on devices in your network, including end of support information.</span></span> <span data-ttu-id="b522d-110">Você pode, por exemplo, procurar eventos envolvendo dispositivos instalados com uma versão de software vulnerável no momento.</span><span class="sxs-lookup"><span data-stu-id="b522d-110">You can, for instance, hunt for events involving devices that are installed with a currently vulnerable software version.</span></span> <span data-ttu-id="b522d-111">Use esta referência para criar consultas quer retiram informações desta tabela.</span><span class="sxs-lookup"><span data-stu-id="b522d-111">Use this reference to construct queries that return information from the table.</span></span>

>[!NOTE]
><span data-ttu-id="b522d-112">As `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` tabelas e substituíram a `DeviceTvmSoftwareInventoryVulnerabilities` tabela.</span><span class="sxs-lookup"><span data-stu-id="b522d-112">The `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables have replaced the `DeviceTvmSoftwareInventoryVulnerabilities` table.</span></span> <span data-ttu-id="b522d-113">Juntas, as duas primeiras tabelas incluem mais colunas que você pode usar para ajudar a informar suas atividades de gerenciamento de vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="b522d-113">Together, the first two tables include more columns you can use to help inform your vulnerability management activities.</span></span>

<span data-ttu-id="b522d-114">Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="b522d-114">For information on other tables in the advanced hunting schema, see [the advanced hunting reference](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).</span></span>

| <span data-ttu-id="b522d-115">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="b522d-115">Column name</span></span> | <span data-ttu-id="b522d-116">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="b522d-116">Data type</span></span> | <span data-ttu-id="b522d-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="b522d-117">Description</span></span> |
|-------------|-----------|-------------|
| `DeviceId` | <span data-ttu-id="b522d-118">string</span><span class="sxs-lookup"><span data-stu-id="b522d-118">string</span></span> | <span data-ttu-id="b522d-119">Identificador exclusivo do dispositivo no serviço</span><span class="sxs-lookup"><span data-stu-id="b522d-119">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="b522d-120">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b522d-120">string</span></span> | <span data-ttu-id="b522d-121">FQDN (nome de domínio totalmente qualificado) do dispositivo</span><span class="sxs-lookup"><span data-stu-id="b522d-121">Fully qualified domain name (FQDN) of the device</span></span> |
| `OSPlatform` | <span data-ttu-id="b522d-122">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b522d-122">string</span></span> | <span data-ttu-id="b522d-123">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b522d-123">Platform of the operating system running on the device.</span></span> <span data-ttu-id="b522d-124">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b522d-124">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `OSVersion` | <span data-ttu-id="b522d-125">string</span><span class="sxs-lookup"><span data-stu-id="b522d-125">string</span></span> | <span data-ttu-id="b522d-126">Versão do sistema operacional em execução no dispositivo</span><span class="sxs-lookup"><span data-stu-id="b522d-126">Version of the operating system running on the device</span></span> |
| `OSArchitecture` | <span data-ttu-id="b522d-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b522d-127">string</span></span> | <span data-ttu-id="b522d-128">Arquitetura do sistema operacional em execução no dispositivo</span><span class="sxs-lookup"><span data-stu-id="b522d-128">Architecture of the operating system running on the device</span></span> |
| `SoftwareVendor` | <span data-ttu-id="b522d-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b522d-129">string</span></span> | <span data-ttu-id="b522d-130">Nome do fornecedor de software</span><span class="sxs-lookup"><span data-stu-id="b522d-130">Name of the software vendor</span></span> |
| `SoftwareName` | <span data-ttu-id="b522d-131">string</span><span class="sxs-lookup"><span data-stu-id="b522d-131">string</span></span> | <span data-ttu-id="b522d-132">Nome do produto de software</span><span class="sxs-lookup"><span data-stu-id="b522d-132">Name of the software product</span></span> |
| `SoftwareVersion` | <span data-ttu-id="b522d-133">string</span><span class="sxs-lookup"><span data-stu-id="b522d-133">string</span></span> | <span data-ttu-id="b522d-134">Número da versão do produto software</span><span class="sxs-lookup"><span data-stu-id="b522d-134">Version number of the software product</span></span> |
| `EndOfSupportStatus` | <span data-ttu-id="b522d-135">string</span><span class="sxs-lookup"><span data-stu-id="b522d-135">string</span></span> | <span data-ttu-id="b522d-136">Indica o estágio de ciclo de vida do produto de software em relação à data especificada de fim de suporte (EOS) ou fim da vida útil (EOL)</span><span class="sxs-lookup"><span data-stu-id="b522d-136">Indicates the lifecycle stage of the software product relative to its specified end-of-support (EOS) or end-of-life (EOL) date</span></span> |
| `EndOfSupportDate` | <span data-ttu-id="b522d-137">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b522d-137">string</span></span> | <span data-ttu-id="b522d-138">Data de fim de suporte (EOS) ou fim da vida útil (EOL) do produto de software</span><span class="sxs-lookup"><span data-stu-id="b522d-138">End-of-support (EOS) or end-of-life (EOL) date of the software product</span></span> |



## <a name="related-topics"></a><span data-ttu-id="b522d-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b522d-139">Related topics</span></span>

- [<span data-ttu-id="b522d-140">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="b522d-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b522d-141">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="b522d-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b522d-142">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="b522d-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="b522d-143">Visão geral do Gerenciamento de Vulnerabilidades e Ameaças</span><span class="sxs-lookup"><span data-stu-id="b522d-143">Overview of Threat & Vulnerability Management</span></span>](next-gen-threat-and-vuln-mgt.md)

