---
title: Planejar sua implantação do Microsoft Defender para Ponto de Extremidade
description: Selecione a melhor estratégia de implantação do Microsoft Defender para Ponto de Extremidade para seu ambiente
keywords: deploy, plan, deployment strategy, cloud native, management, on prem, evaluation, onboarding, local, group policy, gp, endpoint manager, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163570"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="464bf-104">Planejar sua implantação do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="464bf-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="464bf-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="464bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="464bf-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="464bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="464bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="464bf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="464bf-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="464bf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="464bf-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="464bf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="464bf-110">Planeje a implantação do Microsoft Defender para o Ponto de Extremidade para que você possa maximizar os recursos de segurança dentro do pacote e proteger melhor sua empresa contra ameaças cibernéticas.</span><span class="sxs-lookup"><span data-stu-id="464bf-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="464bf-111">Essa solução fornece orientações sobre como identificar sua arquitetura de ambiente, selecionar o tipo de ferramenta de implantação que melhor atende às suas necessidades e orientações sobre como configurar recursos.</span><span class="sxs-lookup"><span data-stu-id="464bf-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![Imagem do fluxo de implantação](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="464bf-113">Etapa 1: Identificar arquitetura</span><span class="sxs-lookup"><span data-stu-id="464bf-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="464bf-114">Entendemos que todos os ambientes corporativos são exclusivos, portanto, fornecemos várias opções para dar a você a flexibilidade de escolher como implantar o serviço.</span><span class="sxs-lookup"><span data-stu-id="464bf-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="464bf-115">Dependendo do ambiente, algumas ferramentas são mais adequadas para determinadas arquiteturas.</span><span class="sxs-lookup"><span data-stu-id="464bf-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="464bf-116">Use o material a seguir para selecionar o Defender para a arquitetura do Ponto de Extremidade apropriado que melhor acompanha sua organização.</span><span class="sxs-lookup"><span data-stu-id="464bf-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="464bf-117">Item</span><span class="sxs-lookup"><span data-stu-id="464bf-117">Item</span></span> | <span data-ttu-id="464bf-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="464bf-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="464bf-119">[![Imagem em miniatura da estratégia de implantação do Defender para Ponto de Extremidade](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="464bf-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="464bf-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="464bf-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="464bf-121">O material arquitetônico ajuda a planejar a implantação para as seguintes arquiteturas:</span><span class="sxs-lookup"><span data-stu-id="464bf-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="464bf-122">Nuvem nativa</span><span class="sxs-lookup"><span data-stu-id="464bf-122">Cloud-native</span></span> </li><li> <span data-ttu-id="464bf-123">Cogerenciamento</span><span class="sxs-lookup"><span data-stu-id="464bf-123">Co-management</span></span> </li><li> <span data-ttu-id="464bf-124">No local</span><span class="sxs-lookup"><span data-stu-id="464bf-124">On-premise</span></span></li><li><span data-ttu-id="464bf-125">Avaliação e integração local</span><span class="sxs-lookup"><span data-stu-id="464bf-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="464bf-126">Etapa 2: selecionar o método de implantação</span><span class="sxs-lookup"><span data-stu-id="464bf-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="464bf-127">O Defender para Ponto de Extremidade oferece suporte a uma variedade de pontos de extremidade que você pode integrar ao serviço.</span><span class="sxs-lookup"><span data-stu-id="464bf-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="464bf-128">A tabela a seguir lista os pontos de extremidade com suporte e a ferramenta de implantação correspondente que você pode usar para que você possa planejar a implantação adequadamente.</span><span class="sxs-lookup"><span data-stu-id="464bf-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="464bf-129">Ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="464bf-129">Endpoint</span></span>     | <span data-ttu-id="464bf-130">Ferramenta de implantação</span><span class="sxs-lookup"><span data-stu-id="464bf-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="464bf-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="464bf-131">**Windows**</span></span>  |  [<span data-ttu-id="464bf-132">Script local (até 10 dispositivos)</span><span class="sxs-lookup"><span data-stu-id="464bf-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="464bf-133">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="464bf-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="464bf-134">Microsoft Endpoint Manager/ Gerenciador de Dispositivos Móveis</span><span class="sxs-lookup"><span data-stu-id="464bf-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="464bf-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="464bf-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="464bf-136">Scripts VDI</span><span class="sxs-lookup"><span data-stu-id="464bf-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="464bf-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="464bf-137">**macOS**</span></span>    | [<span data-ttu-id="464bf-138">Script local</span><span class="sxs-lookup"><span data-stu-id="464bf-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="464bf-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="464bf-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="464bf-140">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="464bf-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="464bf-141">Gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="464bf-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="464bf-142">**Servidor Linux**</span><span class="sxs-lookup"><span data-stu-id="464bf-142">**Linux Server**</span></span> | [<span data-ttu-id="464bf-143">Script local</span><span class="sxs-lookup"><span data-stu-id="464bf-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="464bf-144">Puppet</span><span class="sxs-lookup"><span data-stu-id="464bf-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="464bf-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="464bf-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="464bf-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="464bf-146">**iOS**</span></span>      | [<span data-ttu-id="464bf-147">Baseado em aplicativos</span><span class="sxs-lookup"><span data-stu-id="464bf-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="464bf-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="464bf-148">**Android**</span></span>  | [<span data-ttu-id="464bf-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="464bf-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="464bf-150">Etapa 3: Configurar recursos</span><span class="sxs-lookup"><span data-stu-id="464bf-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="464bf-151">Após a integração dos pontos de extremidade, configure os recursos de segurança no Defender para Ponto de Extremidade para que você possa maximizar a proteção de segurança robusta disponível no pacote.</span><span class="sxs-lookup"><span data-stu-id="464bf-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="464bf-152">Os recursos incluem:</span><span class="sxs-lookup"><span data-stu-id="464bf-152">Capabilities include:</span></span>

- <span data-ttu-id="464bf-153">Detecção de ponto de extremidade e resposta</span><span class="sxs-lookup"><span data-stu-id="464bf-153">Endpoint detection and response</span></span>
- <span data-ttu-id="464bf-154">Proteção de próxima geração</span><span class="sxs-lookup"><span data-stu-id="464bf-154">Next-generation protection</span></span>
- <span data-ttu-id="464bf-155">Redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="464bf-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="464bf-156">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="464bf-156">Related topics</span></span>
- [<span data-ttu-id="464bf-157">Fases da implementação</span><span class="sxs-lookup"><span data-stu-id="464bf-157">Deployment phases</span></span>](deployment-phases.md)
