---
title: Métodos e propriedades de software
description: Recupera os principais alertas recentes.
keywords: apis, api gráfica, apis com suporte, obter, alertas, recentes
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 14291cbbba2272d268a8e79b6df7bd87992885db
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771388"
---
# <a name="software-resource-type"></a><span data-ttu-id="6cbb2-104">Tipo de recurso de software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6cbb2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6cbb2-105">**Applies to:**</span></span>
- [<span data-ttu-id="6cbb2-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6cbb2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6cbb2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6cbb2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="6cbb2-108">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="6cbb2-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="6cbb2-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6cbb2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6cbb2-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6cbb2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="6cbb2-111">Métodos</span><span class="sxs-lookup"><span data-stu-id="6cbb2-111">Methods</span></span>

<span data-ttu-id="6cbb2-112">Método</span><span class="sxs-lookup"><span data-stu-id="6cbb2-112">Method</span></span> |<span data-ttu-id="6cbb2-113">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="6cbb2-113">Return Type</span></span> |<span data-ttu-id="6cbb2-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="6cbb2-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="6cbb2-115">Listar software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-115">List software</span></span>](get-software.md) | <span data-ttu-id="6cbb2-116">Coleção Software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-116">Software collection</span></span> | <span data-ttu-id="6cbb2-117">Listar o inventário de software organizacional.</span><span class="sxs-lookup"><span data-stu-id="6cbb2-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="6cbb2-118">Obter software por ID</span><span class="sxs-lookup"><span data-stu-id="6cbb2-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="6cbb2-119">Software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-119">Software</span></span> | <span data-ttu-id="6cbb2-120">Obter um software específico por sua ID de software.</span><span class="sxs-lookup"><span data-stu-id="6cbb2-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="6cbb2-121">Listar distribuição das versões do software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="6cbb2-122">Coleção Distribution</span><span class="sxs-lookup"><span data-stu-id="6cbb2-122">Distribution collection</span></span> | <span data-ttu-id="6cbb2-123">Listar distribuição de versão de software por ID de software.</span><span class="sxs-lookup"><span data-stu-id="6cbb2-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="6cbb2-124">Listar computadores por software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="6cbb2-125">Coleção MachineRef</span><span class="sxs-lookup"><span data-stu-id="6cbb2-125">MachineRef collection</span></span> | <span data-ttu-id="6cbb2-126">Recupere uma lista de dispositivos associados à ID de software.</span><span class="sxs-lookup"><span data-stu-id="6cbb2-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="6cbb2-127">Listar vulnerabilidades por software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="6cbb2-128">[Coleção Vulnerability](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="6cbb2-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="6cbb2-129">Recupere uma lista de vulnerabilidades associadas à ID do software.</span><span class="sxs-lookup"><span data-stu-id="6cbb2-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="6cbb2-130">Obter KBs ausentes</span><span class="sxs-lookup"><span data-stu-id="6cbb2-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="6cbb2-131">Coleção KB</span><span class="sxs-lookup"><span data-stu-id="6cbb2-131">KB collection</span></span> | <span data-ttu-id="6cbb2-132">Obter uma lista de KBs ausentes associados à ID de software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="6cbb2-133">Propriedades</span><span class="sxs-lookup"><span data-stu-id="6cbb2-133">Properties</span></span>

<span data-ttu-id="6cbb2-134">Propriedade</span><span class="sxs-lookup"><span data-stu-id="6cbb2-134">Property</span></span> |   <span data-ttu-id="6cbb2-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="6cbb2-135">Type</span></span>   |   <span data-ttu-id="6cbb2-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="6cbb2-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="6cbb2-137">id</span><span class="sxs-lookup"><span data-stu-id="6cbb2-137">id</span></span> | <span data-ttu-id="6cbb2-138">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6cbb2-138">String</span></span> | <span data-ttu-id="6cbb2-139">Software ID</span><span class="sxs-lookup"><span data-stu-id="6cbb2-139">Software ID</span></span>
<span data-ttu-id="6cbb2-140">Nome</span><span class="sxs-lookup"><span data-stu-id="6cbb2-140">Name</span></span> | <span data-ttu-id="6cbb2-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6cbb2-141">String</span></span> | <span data-ttu-id="6cbb2-142">Nome do software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-142">Software name</span></span>
<span data-ttu-id="6cbb2-143">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="6cbb2-143">Vendor</span></span> | <span data-ttu-id="6cbb2-144">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6cbb2-144">String</span></span> | <span data-ttu-id="6cbb2-145">Nome do fornecedor de software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-145">Software vendor name</span></span>
<span data-ttu-id="6cbb2-146">Pontos fracos</span><span class="sxs-lookup"><span data-stu-id="6cbb2-146">Weaknesses</span></span> | <span data-ttu-id="6cbb2-147">Longo</span><span class="sxs-lookup"><span data-stu-id="6cbb2-147">Long</span></span> | <span data-ttu-id="6cbb2-148">Número de vulnerabilidades descobertas</span><span class="sxs-lookup"><span data-stu-id="6cbb2-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="6cbb2-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="6cbb2-149">publicExploit</span></span> | <span data-ttu-id="6cbb2-150">Booliano</span><span class="sxs-lookup"><span data-stu-id="6cbb2-150">Boolean</span></span> | <span data-ttu-id="6cbb2-151">A exploração pública existe para algumas das vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="6cbb2-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="6cbb2-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="6cbb2-152">activeAlert</span></span> | <span data-ttu-id="6cbb2-153">Booliano</span><span class="sxs-lookup"><span data-stu-id="6cbb2-153">Boolean</span></span> | <span data-ttu-id="6cbb2-154">Alerta ativo está associado a este software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-154">Active alert is associated with this software</span></span>
<span data-ttu-id="6cbb2-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="6cbb2-155">exposedMachines</span></span> | <span data-ttu-id="6cbb2-156">Longo</span><span class="sxs-lookup"><span data-stu-id="6cbb2-156">Long</span></span> | <span data-ttu-id="6cbb2-157">Número de dispositivos expostos</span><span class="sxs-lookup"><span data-stu-id="6cbb2-157">Number of exposed devices</span></span>
<span data-ttu-id="6cbb2-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="6cbb2-158">impactScore</span></span> | <span data-ttu-id="6cbb2-159">Duplo</span><span class="sxs-lookup"><span data-stu-id="6cbb2-159">Double</span></span> | <span data-ttu-id="6cbb2-160">Impacto da pontuação de exposição deste software</span><span class="sxs-lookup"><span data-stu-id="6cbb2-160">Exposure score impact of this software</span></span>
