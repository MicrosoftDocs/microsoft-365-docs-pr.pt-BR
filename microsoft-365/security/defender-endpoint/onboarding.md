---
title: Integração ao serviço microsoft defender para ponto de extremidade
description: Saiba como integrar pontos de extremidade ao serviço do Microsoft Defender para Ponto de Extremidade
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cc538c887397d5bbea78f63c8a8acd318ec7fe9f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689528"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="251e1-103">Integração ao serviço microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="251e1-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="251e1-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="251e1-104">**Applies to:**</span></span>
- [<span data-ttu-id="251e1-105">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="251e1-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="251e1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="251e1-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="251e1-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="251e1-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="251e1-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="251e1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="251e1-109">Saiba mais sobre as várias fases de implantação do Microsoft Defender para Ponto de Extremidade e como configurar os recursos dentro da solução.</span><span class="sxs-lookup"><span data-stu-id="251e1-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="251e1-110">Implantar o Defender para Ponto de Extremidade é um processo de três fases:</span><span class="sxs-lookup"><span data-stu-id="251e1-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="251e1-111">[![fase de implantação - preparar](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="251e1-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="251e1-112">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="251e1-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="251e1-113">[![fase de implantação - instalação](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="251e1-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="251e1-114">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="251e1-114">Phase 2: Setup</span></span>](production-deployment.md) | ![fase de implantação - onboard](images/phase-diagrams/onboard.png)<br><span data-ttu-id="251e1-116">Fase 3: Integrar</span><span class="sxs-lookup"><span data-stu-id="251e1-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="251e1-117">*Você está aqui!*</span><span class="sxs-lookup"><span data-stu-id="251e1-117">*You are here!*</span></span>|

<span data-ttu-id="251e1-118">No momento, você está na fase de integração.</span><span class="sxs-lookup"><span data-stu-id="251e1-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="251e1-119">Estas são as etapas que você precisa seguir para implantar o Defender para o Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="251e1-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="251e1-120">Etapa 1: Pontos de extremidade de integração para o serviço</span><span class="sxs-lookup"><span data-stu-id="251e1-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="251e1-121">Etapa 2: Configurar recursos</span><span class="sxs-lookup"><span data-stu-id="251e1-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="251e1-122">Etapa 1: Pontos de extremidade de integração usando qualquer uma das ferramentas de gerenciamento com suporte</span><span class="sxs-lookup"><span data-stu-id="251e1-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="251e1-123">O [tópico Planejar implantação](deployment-strategy.md) descreve as etapas gerais que você precisa seguir para implantar o Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="251e1-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="251e1-124">Assista a este vídeo para uma visão geral rápida do processo de integração e saiba mais sobre as ferramentas e métodos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="251e1-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="251e1-125">Depois de identificar sua arquitetura, você precisará decidir qual método de implantação usar.</span><span class="sxs-lookup"><span data-stu-id="251e1-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="251e1-126">A ferramenta de implantação escolhida influencia como você integra pontos de extremidade ao serviço.</span><span class="sxs-lookup"><span data-stu-id="251e1-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="251e1-127">Opções da ferramenta de integração</span><span class="sxs-lookup"><span data-stu-id="251e1-127">Onboarding tool options</span></span>

<span data-ttu-id="251e1-128">A tabela a seguir lista as ferramentas disponíveis com base no ponto de extremidade que você precisa integrar.</span><span class="sxs-lookup"><span data-stu-id="251e1-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="251e1-129">Ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="251e1-129">Endpoint</span></span>     | <span data-ttu-id="251e1-130">Opções de ferramenta</span><span class="sxs-lookup"><span data-stu-id="251e1-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="251e1-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="251e1-131">**Windows**</span></span>  |  [<span data-ttu-id="251e1-132">Script local (até 10 dispositivos)</span><span class="sxs-lookup"><span data-stu-id="251e1-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="251e1-133">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="251e1-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="251e1-134">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="251e1-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="251e1-135">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="251e1-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="251e1-136">Scripts VDI</span><span class="sxs-lookup"><span data-stu-id="251e1-136">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="251e1-137">Central de Segurança do Azure</span><span class="sxs-lookup"><span data-stu-id="251e1-137">Azure Security Center</span></span>](configure-server-endpoints.md#integration-with-azure-security-center) |
| <span data-ttu-id="251e1-138">**macOS**</span><span class="sxs-lookup"><span data-stu-id="251e1-138">**macOS**</span></span>    | [<span data-ttu-id="251e1-139">Scripts locais</span><span class="sxs-lookup"><span data-stu-id="251e1-139">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="251e1-140">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="251e1-140">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="251e1-141">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="251e1-141">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="251e1-142">Gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="251e1-142">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="251e1-143">**Servidor Linux**</span><span class="sxs-lookup"><span data-stu-id="251e1-143">**Linux Server**</span></span> | [<span data-ttu-id="251e1-144">Script local</span><span class="sxs-lookup"><span data-stu-id="251e1-144">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="251e1-145">Puppet</span><span class="sxs-lookup"><span data-stu-id="251e1-145">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="251e1-146">Ansible</span><span class="sxs-lookup"><span data-stu-id="251e1-146">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="251e1-147">**iOS**</span><span class="sxs-lookup"><span data-stu-id="251e1-147">**iOS**</span></span>      | [<span data-ttu-id="251e1-148">Baseado em aplicativos</span><span class="sxs-lookup"><span data-stu-id="251e1-148">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="251e1-149">**Android**</span><span class="sxs-lookup"><span data-stu-id="251e1-149">**Android**</span></span>  | [<span data-ttu-id="251e1-150">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="251e1-150">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="251e1-151">Etapa 2: Configurar recursos</span><span class="sxs-lookup"><span data-stu-id="251e1-151">Step 2: Configure capabilities</span></span>
<span data-ttu-id="251e1-152">Após a integração dos pontos de extremidade, você configurará os vários recursos, como detecção e resposta do ponto de extremidade, proteção de próxima geração e redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="251e1-152">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="251e1-153">Exemplo de implantações</span><span class="sxs-lookup"><span data-stu-id="251e1-153">Example deployments</span></span>
<span data-ttu-id="251e1-154">Neste guia de implantação, vamos orientá-lo usando duas ferramentas de implantação para pontos de extremidade de integração e como configurar recursos.</span><span class="sxs-lookup"><span data-stu-id="251e1-154">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="251e1-155">As ferramentas nas implantações de exemplo são:</span><span class="sxs-lookup"><span data-stu-id="251e1-155">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="251e1-156">Integração usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="251e1-156">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="251e1-157">Integração usando o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="251e1-157">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="251e1-158">Usando as ferramentas de implantação mencionadas acima, você será orientado a configurar os seguintes recursos do Defender para o Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="251e1-158">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="251e1-159">Configuração de resposta e detecção de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="251e1-159">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="251e1-160">Configuração de proteção de última geração</span><span class="sxs-lookup"><span data-stu-id="251e1-160">Next-generation protection configuration</span></span>
- <span data-ttu-id="251e1-161">Configuração de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="251e1-161">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="251e1-162">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="251e1-162">Related topics</span></span>
- [<span data-ttu-id="251e1-163">Integração usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="251e1-163">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="251e1-164">Integração usando o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="251e1-164">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="251e1-165">Documentos Seguros no Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="251e1-165">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
