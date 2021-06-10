---
title: Integração ao serviço microsoft defender para ponto de extremidade
description: Saiba como integrar pontos de extremidade ao serviço do Microsoft Defender para Ponto de Extremidade
keywords: microsoft defender para ponto de extremidade, onboard, deploy
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
ms.openlocfilehash: f63b4f81f454fec60a26c7cb063d66bed4a2bead
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933536"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="542f7-104">Integração ao serviço microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="542f7-104">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="542f7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="542f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="542f7-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="542f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="542f7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="542f7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="542f7-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="542f7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="542f7-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="542f7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="542f7-110">Saiba mais sobre as várias fases de implantação do Microsoft Defender para Ponto de Extremidade e como configurar os recursos dentro da solução.</span><span class="sxs-lookup"><span data-stu-id="542f7-110">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="542f7-111">Implantar o Defender para Ponto de Extremidade é um processo de três fases:</span><span class="sxs-lookup"><span data-stu-id="542f7-111">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="542f7-112">[![fase de implantação - preparar](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="542f7-112">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="542f7-113">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="542f7-113">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="542f7-114">[![fase de implantação - instalação](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="542f7-114">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="542f7-115">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="542f7-115">Phase 2: Setup</span></span>](production-deployment.md) | ![fase de implantação - onboard](images/phase-diagrams/onboard.png)<br><span data-ttu-id="542f7-117">Fase 3: Integrar</span><span class="sxs-lookup"><span data-stu-id="542f7-117">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="542f7-118">*Você está aqui!*</span><span class="sxs-lookup"><span data-stu-id="542f7-118">*You are here!*</span></span>|

<span data-ttu-id="542f7-119">No momento, você está na fase de integração.</span><span class="sxs-lookup"><span data-stu-id="542f7-119">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="542f7-120">Estas são as etapas que você precisa seguir para implantar o Defender para o Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="542f7-120">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="542f7-121">Etapa 1: Pontos de extremidade de integração para o serviço</span><span class="sxs-lookup"><span data-stu-id="542f7-121">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="542f7-122">Etapa 2: Configurar recursos</span><span class="sxs-lookup"><span data-stu-id="542f7-122">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="542f7-123">Etapa 1: Pontos de extremidade de integração usando qualquer uma das ferramentas de gerenciamento com suporte</span><span class="sxs-lookup"><span data-stu-id="542f7-123">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="542f7-124">O [tópico Planejar implantação](deployment-strategy.md) descreve as etapas gerais que você precisa seguir para implantar o Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="542f7-124">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="542f7-125">Assista a este vídeo para uma visão geral rápida do processo de integração e saiba mais sobre as ferramentas e métodos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="542f7-125">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="542f7-126">Depois de identificar sua arquitetura, você precisará decidir qual método de implantação usar.</span><span class="sxs-lookup"><span data-stu-id="542f7-126">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="542f7-127">A ferramenta de implantação escolhida influencia como você integra pontos de extremidade ao serviço.</span><span class="sxs-lookup"><span data-stu-id="542f7-127">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="542f7-128">Opções da ferramenta de integração</span><span class="sxs-lookup"><span data-stu-id="542f7-128">Onboarding tool options</span></span>

<span data-ttu-id="542f7-129">A tabela a seguir lista as ferramentas disponíveis com base no ponto de extremidade que você precisa integrar.</span><span class="sxs-lookup"><span data-stu-id="542f7-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="542f7-130">Ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="542f7-130">Endpoint</span></span>     | <span data-ttu-id="542f7-131">Opções de ferramenta</span><span class="sxs-lookup"><span data-stu-id="542f7-131">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="542f7-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="542f7-132">**Windows**</span></span>  |  [<span data-ttu-id="542f7-133">Script local (até 10 dispositivos)</span><span class="sxs-lookup"><span data-stu-id="542f7-133">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="542f7-134">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="542f7-134">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="542f7-135">Microsoft Endpoint Manager/ Gerenciador de Dispositivos Móveis</span><span class="sxs-lookup"><span data-stu-id="542f7-135">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="542f7-136">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="542f7-136">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="542f7-137">Scripts VDI</span><span class="sxs-lookup"><span data-stu-id="542f7-137">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="542f7-138">Integração com o Azure Defender</span><span class="sxs-lookup"><span data-stu-id="542f7-138">Integration with Azure Defender</span></span>](configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="542f7-139">**macOS**</span><span class="sxs-lookup"><span data-stu-id="542f7-139">**macOS**</span></span>    | [<span data-ttu-id="542f7-140">Scripts locais</span><span class="sxs-lookup"><span data-stu-id="542f7-140">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="542f7-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="542f7-141">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="542f7-142">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="542f7-142">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="542f7-143">Gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="542f7-143">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="542f7-144">**Servidor Linux**</span><span class="sxs-lookup"><span data-stu-id="542f7-144">**Linux Server**</span></span> | [<span data-ttu-id="542f7-145">Script local</span><span class="sxs-lookup"><span data-stu-id="542f7-145">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="542f7-146">Puppet</span><span class="sxs-lookup"><span data-stu-id="542f7-146">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="542f7-147">Ansible</span><span class="sxs-lookup"><span data-stu-id="542f7-147">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="542f7-148">**iOS**</span><span class="sxs-lookup"><span data-stu-id="542f7-148">**iOS**</span></span>      | [<span data-ttu-id="542f7-149">Baseado em aplicativos</span><span class="sxs-lookup"><span data-stu-id="542f7-149">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="542f7-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="542f7-150">**Android**</span></span>  | [<span data-ttu-id="542f7-151">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="542f7-151">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="542f7-152">Etapa 2: Configurar recursos</span><span class="sxs-lookup"><span data-stu-id="542f7-152">Step 2: Configure capabilities</span></span>
<span data-ttu-id="542f7-153">Após a integração dos pontos de extremidade, você configurará os vários recursos, como detecção e resposta de ponto de extremidade, proteção de próxima geração e redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="542f7-153">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="542f7-154">Exemplo de implantações</span><span class="sxs-lookup"><span data-stu-id="542f7-154">Example deployments</span></span>
<span data-ttu-id="542f7-155">Neste guia de implantação, vamos orientá-lo usando duas ferramentas de implantação para pontos de extremidade de integração e como configurar recursos.</span><span class="sxs-lookup"><span data-stu-id="542f7-155">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="542f7-156">As ferramentas nas implantações de exemplo são:</span><span class="sxs-lookup"><span data-stu-id="542f7-156">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="542f7-157">Integração usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="542f7-157">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="542f7-158">Integração usando o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="542f7-158">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="542f7-159">Usando as ferramentas de implantação mencionadas acima, você será orientado a configurar os seguintes recursos do Defender para o Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="542f7-159">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="542f7-160">Configuração de resposta e detecção de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="542f7-160">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="542f7-161">Configuração de proteção de última geração</span><span class="sxs-lookup"><span data-stu-id="542f7-161">Next-generation protection configuration</span></span>
- <span data-ttu-id="542f7-162">Configuração de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="542f7-162">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="542f7-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="542f7-163">Related topics</span></span>
- [<span data-ttu-id="542f7-164">Integração usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="542f7-164">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="542f7-165">Integração usando o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="542f7-165">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="542f7-166">Documentos Seguros no Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="542f7-166">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
