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
# <a name="software-resource-type"></a><span data-ttu-id="bf10d-104">Tipo de recurso de software</span><span class="sxs-lookup"><span data-stu-id="bf10d-104">Software resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf10d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="bf10d-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf10d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="bf10d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bf10d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf10d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="bf10d-108">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="bf10d-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="bf10d-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="bf10d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bf10d-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="bf10d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="bf10d-111">Métodos</span><span class="sxs-lookup"><span data-stu-id="bf10d-111">Methods</span></span>

<span data-ttu-id="bf10d-112">Método</span><span class="sxs-lookup"><span data-stu-id="bf10d-112">Method</span></span> |<span data-ttu-id="bf10d-113">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="bf10d-113">Return Type</span></span> |<span data-ttu-id="bf10d-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="bf10d-114">Description</span></span>
:---|:---|:---
[<span data-ttu-id="bf10d-115">Listar software</span><span class="sxs-lookup"><span data-stu-id="bf10d-115">List software</span></span>](get-software.md) | <span data-ttu-id="bf10d-116">Coleção Software</span><span class="sxs-lookup"><span data-stu-id="bf10d-116">Software collection</span></span> | <span data-ttu-id="bf10d-117">Listar o inventário de software organizacional.</span><span class="sxs-lookup"><span data-stu-id="bf10d-117">List the organizational software inventory.</span></span>
[<span data-ttu-id="bf10d-118">Obter software por ID</span><span class="sxs-lookup"><span data-stu-id="bf10d-118">Get software by Id</span></span>](get-software-by-id.md) | <span data-ttu-id="bf10d-119">Software</span><span class="sxs-lookup"><span data-stu-id="bf10d-119">Software</span></span> | <span data-ttu-id="bf10d-120">Obter um software específico por sua ID de software.</span><span class="sxs-lookup"><span data-stu-id="bf10d-120">Get a specific software by its software ID.</span></span>
[<span data-ttu-id="bf10d-121">Listar distribuição das versões do software</span><span class="sxs-lookup"><span data-stu-id="bf10d-121">List software version distribution</span></span>](get-software-ver-distribution.md)| <span data-ttu-id="bf10d-122">Coleção Distribution</span><span class="sxs-lookup"><span data-stu-id="bf10d-122">Distribution collection</span></span> | <span data-ttu-id="bf10d-123">Listar distribuição de versão de software por ID de software.</span><span class="sxs-lookup"><span data-stu-id="bf10d-123">List software version distribution by software ID.</span></span>
[<span data-ttu-id="bf10d-124">Listar computadores por software</span><span class="sxs-lookup"><span data-stu-id="bf10d-124">List machines by software</span></span>](get-machines-by-software.md)| <span data-ttu-id="bf10d-125">Coleção MachineRef</span><span class="sxs-lookup"><span data-stu-id="bf10d-125">MachineRef collection</span></span> | <span data-ttu-id="bf10d-126">Recupere uma lista de dispositivos associados à ID de software.</span><span class="sxs-lookup"><span data-stu-id="bf10d-126">Retrieve a list of devices that are associated with the software ID.</span></span>
[<span data-ttu-id="bf10d-127">Listar vulnerabilidades por software</span><span class="sxs-lookup"><span data-stu-id="bf10d-127">List vulnerabilities by software</span></span>](get-vuln-by-software.md) | <span data-ttu-id="bf10d-128">[Coleção Vulnerability](vulnerability.md)</span><span class="sxs-lookup"><span data-stu-id="bf10d-128">[Vulnerability](vulnerability.md) collection</span></span> | <span data-ttu-id="bf10d-129">Recupere uma lista de vulnerabilidades associadas à ID do software.</span><span class="sxs-lookup"><span data-stu-id="bf10d-129">Retrieve a list of vulnerabilities associated with the software ID.</span></span>
[<span data-ttu-id="bf10d-130">Obter KBs ausentes</span><span class="sxs-lookup"><span data-stu-id="bf10d-130">Get missing KBs</span></span>](get-missing-kbs-software.md) | <span data-ttu-id="bf10d-131">Coleção KB</span><span class="sxs-lookup"><span data-stu-id="bf10d-131">KB collection</span></span> | <span data-ttu-id="bf10d-132">Obter uma lista de KBs ausentes associados à ID de software</span><span class="sxs-lookup"><span data-stu-id="bf10d-132">Get a list of missing KBs associated with the software ID</span></span>

## <a name="properties"></a><span data-ttu-id="bf10d-133">Propriedades</span><span class="sxs-lookup"><span data-stu-id="bf10d-133">Properties</span></span>

<span data-ttu-id="bf10d-134">Propriedade</span><span class="sxs-lookup"><span data-stu-id="bf10d-134">Property</span></span> |   <span data-ttu-id="bf10d-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="bf10d-135">Type</span></span>   |   <span data-ttu-id="bf10d-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="bf10d-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="bf10d-137">id</span><span class="sxs-lookup"><span data-stu-id="bf10d-137">id</span></span> | <span data-ttu-id="bf10d-138">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="bf10d-138">String</span></span> | <span data-ttu-id="bf10d-139">Software ID</span><span class="sxs-lookup"><span data-stu-id="bf10d-139">Software ID</span></span>
<span data-ttu-id="bf10d-140">Nome</span><span class="sxs-lookup"><span data-stu-id="bf10d-140">Name</span></span> | <span data-ttu-id="bf10d-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="bf10d-141">String</span></span> | <span data-ttu-id="bf10d-142">Nome do software</span><span class="sxs-lookup"><span data-stu-id="bf10d-142">Software name</span></span>
<span data-ttu-id="bf10d-143">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="bf10d-143">Vendor</span></span> | <span data-ttu-id="bf10d-144">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="bf10d-144">String</span></span> | <span data-ttu-id="bf10d-145">Nome do fornecedor de software</span><span class="sxs-lookup"><span data-stu-id="bf10d-145">Software vendor name</span></span>
<span data-ttu-id="bf10d-146">Pontos fracos</span><span class="sxs-lookup"><span data-stu-id="bf10d-146">Weaknesses</span></span> | <span data-ttu-id="bf10d-147">Longo</span><span class="sxs-lookup"><span data-stu-id="bf10d-147">Long</span></span> | <span data-ttu-id="bf10d-148">Número de vulnerabilidades descobertas</span><span class="sxs-lookup"><span data-stu-id="bf10d-148">Number of discovered vulnerabilities</span></span>
<span data-ttu-id="bf10d-149">publicExploit</span><span class="sxs-lookup"><span data-stu-id="bf10d-149">publicExploit</span></span> | <span data-ttu-id="bf10d-150">Boolean</span><span class="sxs-lookup"><span data-stu-id="bf10d-150">Boolean</span></span> | <span data-ttu-id="bf10d-151">A exploração pública existe para algumas das vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="bf10d-151">Public exploit exists for some of the vulnerabilities</span></span>
<span data-ttu-id="bf10d-152">activeAlert</span><span class="sxs-lookup"><span data-stu-id="bf10d-152">activeAlert</span></span> | <span data-ttu-id="bf10d-153">Boolean</span><span class="sxs-lookup"><span data-stu-id="bf10d-153">Boolean</span></span> | <span data-ttu-id="bf10d-154">Alerta ativo está associado a este software</span><span class="sxs-lookup"><span data-stu-id="bf10d-154">Active alert is associated with this software</span></span>
<span data-ttu-id="bf10d-155">exposedMachines</span><span class="sxs-lookup"><span data-stu-id="bf10d-155">exposedMachines</span></span> | <span data-ttu-id="bf10d-156">Longo</span><span class="sxs-lookup"><span data-stu-id="bf10d-156">Long</span></span> | <span data-ttu-id="bf10d-157">Número de dispositivos expostos</span><span class="sxs-lookup"><span data-stu-id="bf10d-157">Number of exposed devices</span></span>
<span data-ttu-id="bf10d-158">impactScore</span><span class="sxs-lookup"><span data-stu-id="bf10d-158">impactScore</span></span> | <span data-ttu-id="bf10d-159">Duplo</span><span class="sxs-lookup"><span data-stu-id="bf10d-159">Double</span></span> | <span data-ttu-id="bf10d-160">Impacto da pontuação de exposição deste software</span><span class="sxs-lookup"><span data-stu-id="bf10d-160">Exposure score impact of this software</span></span>
