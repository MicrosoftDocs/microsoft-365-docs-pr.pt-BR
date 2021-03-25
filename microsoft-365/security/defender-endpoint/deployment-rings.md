---
title: Implantar o Microsoft Defender para Ponto de Extremidade em anéis
description: Saiba como implantar o Microsoft Defender para Ponto de Extremidade em anéis
keywords: implantar, anéis, avaliar, piloto, insider rápido, insider lento, configuração, integração, fase, implantação, implantação, adoção, configuração
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2d34b984436b3ed0537af2eebcd8475ec270cd8e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165784"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="d0f12-104">Implantar o Microsoft Defender para Ponto de Extremidade em anéis</span><span class="sxs-lookup"><span data-stu-id="d0f12-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d0f12-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d0f12-105">**Applies to:**</span></span>
- [<span data-ttu-id="d0f12-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d0f12-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d0f12-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0f12-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d0f12-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d0f12-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d0f12-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d0f12-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="d0f12-110">A implantação do Microsoft Defender para Ponto de Extremidade pode ser feita usando uma abordagem de implantação baseada em anel.</span><span class="sxs-lookup"><span data-stu-id="d0f12-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="d0f12-111">Os anéis de implantação podem ser aplicados nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="d0f12-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="d0f12-112">Novas implantações</span><span class="sxs-lookup"><span data-stu-id="d0f12-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="d0f12-113">Implantações existentes</span><span class="sxs-lookup"><span data-stu-id="d0f12-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="d0f12-114">Novas implantações</span><span class="sxs-lookup"><span data-stu-id="d0f12-114">New deployments</span></span>

![Imagem dos anéis de implantação](images/deployment-rings.png)


<span data-ttu-id="d0f12-116">Uma abordagem baseada em anel é um método de identificar um conjunto de pontos de extremidade para a integração e verificar se determinados critérios são atendidos antes de continuar a implantar o serviço em um conjunto maior de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d0f12-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="d0f12-117">Você pode definir os critérios de saída para cada anel e garantir que eles sejam satisfeitos antes de passar para o próximo anel.</span><span class="sxs-lookup"><span data-stu-id="d0f12-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="d0f12-118">A adoção de uma implantação baseada em anel ajuda a reduzir possíveis problemas que podem surgir durante a implantação do serviço.</span><span class="sxs-lookup"><span data-stu-id="d0f12-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="d0f12-119">Pilotando um determinado número de dispositivos primeiro, você pode identificar possíveis problemas e reduzir possíveis riscos que possam surgir.</span><span class="sxs-lookup"><span data-stu-id="d0f12-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="d0f12-120">A Tabela 1 fornece um exemplo dos anéis de implantação que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="d0f12-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="d0f12-121">**Tabela 1**</span><span class="sxs-lookup"><span data-stu-id="d0f12-121">**Table 1**</span></span>

|<span data-ttu-id="d0f12-122">**Anel de implantação**</span><span class="sxs-lookup"><span data-stu-id="d0f12-122">**Deployment ring**</span></span>|<span data-ttu-id="d0f12-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d0f12-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="d0f12-124">Avaliar</span><span class="sxs-lookup"><span data-stu-id="d0f12-124">Evaluate</span></span> | <span data-ttu-id="d0f12-125">Anel 1: identificar 50 sistemas para testes piloto</span><span class="sxs-lookup"><span data-stu-id="d0f12-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="d0f12-126">Piloto</span><span class="sxs-lookup"><span data-stu-id="d0f12-126">Pilot</span></span> | <span data-ttu-id="d0f12-127">Anel 2: identificar os próximos 50 a 100 pontos de extremidade no ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="d0f12-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="d0f12-128">Implantação completa</span><span class="sxs-lookup"><span data-stu-id="d0f12-128">Full deployment</span></span> | <span data-ttu-id="d0f12-129">Anel 3: lançar serviço para o restante do ambiente em incrementos maiores</span><span class="sxs-lookup"><span data-stu-id="d0f12-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="d0f12-130">Critérios de saída</span><span class="sxs-lookup"><span data-stu-id="d0f12-130">Exit criteria</span></span>
<span data-ttu-id="d0f12-131">Um conjunto de exemplos de critérios de saída para esses anéis pode incluir:</span><span class="sxs-lookup"><span data-stu-id="d0f12-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="d0f12-132">Dispositivos aparecem na lista de inventário de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d0f12-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="d0f12-133">Alertas aparecem no painel</span><span class="sxs-lookup"><span data-stu-id="d0f12-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="d0f12-134">Executar um teste de detecção</span><span class="sxs-lookup"><span data-stu-id="d0f12-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="d0f12-135">Executar um ataque simulado em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="d0f12-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="d0f12-136">Avaliar</span><span class="sxs-lookup"><span data-stu-id="d0f12-136">Evaluate</span></span>
<span data-ttu-id="d0f12-137">Identifique um pequeno número de máquinas de teste em seu ambiente para integração ao serviço.</span><span class="sxs-lookup"><span data-stu-id="d0f12-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="d0f12-138">O ideal é que esses máquinas sejam menos de 50 pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="d0f12-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="d0f12-139">Piloto</span><span class="sxs-lookup"><span data-stu-id="d0f12-139">Pilot</span></span>
<span data-ttu-id="d0f12-140">O Microsoft Defender ATP oferece suporte a uma variedade de pontos de extremidade que você pode integrar ao serviço.</span><span class="sxs-lookup"><span data-stu-id="d0f12-140">Microsoft Defender ATP supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="d0f12-141">Nesse anel, identifique vários dispositivos para integração e com base nos critérios de saída que você definir, decida prosseguir para o próximo anel de implantação.</span><span class="sxs-lookup"><span data-stu-id="d0f12-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="d0f12-142">A tabela a seguir mostra os pontos de extremidade com suporte e a ferramenta correspondente que você pode usar para a integração de dispositivos ao serviço.</span><span class="sxs-lookup"><span data-stu-id="d0f12-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="d0f12-143">Ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="d0f12-143">Endpoint</span></span>     | <span data-ttu-id="d0f12-144">Ferramenta de implantação</span><span class="sxs-lookup"><span data-stu-id="d0f12-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="d0f12-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d0f12-145">**Windows**</span></span>  |  [<span data-ttu-id="d0f12-146">Script local (até 10 dispositivos)</span><span class="sxs-lookup"><span data-stu-id="d0f12-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="d0f12-147">OBSERVAÇÃO: se você quiser implantar mais de 10 dispositivos em um ambiente de produção, use o método de Política de Grupo ou as outras ferramentas com suporte listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="d0f12-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="d0f12-148">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="d0f12-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="d0f12-149">Microsoft Endpoint Manager/ Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="d0f12-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="d0f12-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d0f12-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="d0f12-151">Scripts VDI</span><span class="sxs-lookup"><span data-stu-id="d0f12-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="d0f12-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="d0f12-152">**macOS**</span></span>    | [<span data-ttu-id="d0f12-153">Script local</span><span class="sxs-lookup"><span data-stu-id="d0f12-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="d0f12-154">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d0f12-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="d0f12-155">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="d0f12-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="d0f12-156">Gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="d0f12-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="d0f12-157">**Servidor Linux**</span><span class="sxs-lookup"><span data-stu-id="d0f12-157">**Linux Server**</span></span> | [<span data-ttu-id="d0f12-158">Script local</span><span class="sxs-lookup"><span data-stu-id="d0f12-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="d0f12-159">Puppet</span><span class="sxs-lookup"><span data-stu-id="d0f12-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="d0f12-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="d0f12-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="d0f12-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="d0f12-161">**iOS**</span></span>      | [<span data-ttu-id="d0f12-162">Baseado em aplicativos</span><span class="sxs-lookup"><span data-stu-id="d0f12-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="d0f12-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="d0f12-163">**Android**</span></span>  | [<span data-ttu-id="d0f12-164">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d0f12-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="d0f12-165">Implantação completa</span><span class="sxs-lookup"><span data-stu-id="d0f12-165">Full deployment</span></span>
<span data-ttu-id="d0f12-166">Neste estágio, você pode usar o material [planejar a](deployment-strategy.md) implantação para ajudá-lo a planejar sua implantação.</span><span class="sxs-lookup"><span data-stu-id="d0f12-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="d0f12-167">Use o material a seguir para selecionar a arquitetura apropriada do Microsoft Defender ATP que melhor acompanha sua organização.</span><span class="sxs-lookup"><span data-stu-id="d0f12-167">Use the following material to select the appropriate Microsoft Defender ATP architecture that best suites your organization.</span></span>

|<span data-ttu-id="d0f12-168">**Item**</span><span class="sxs-lookup"><span data-stu-id="d0f12-168">**Item**</span></span>|<span data-ttu-id="d0f12-169">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d0f12-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d0f12-170">[![Imagem em miniatura da estratégia de implantação do Microsoft Defender ATP](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="d0f12-170">[![Thumb image for Microsoft Defender ATP deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="d0f12-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="d0f12-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="d0f12-172">O material arquitetônico ajuda a planejar a implantação para as seguintes arquiteturas:</span><span class="sxs-lookup"><span data-stu-id="d0f12-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="d0f12-173">Nuvem nativa</span><span class="sxs-lookup"><span data-stu-id="d0f12-173">Cloud-native</span></span> </li><li> <span data-ttu-id="d0f12-174">Cogerenciamento</span><span class="sxs-lookup"><span data-stu-id="d0f12-174">Co-management</span></span> </li><li> <span data-ttu-id="d0f12-175">No local</span><span class="sxs-lookup"><span data-stu-id="d0f12-175">On-premise</span></span></li><li><span data-ttu-id="d0f12-176">Avaliação e integração local</span><span class="sxs-lookup"><span data-stu-id="d0f12-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="d0f12-177">Implantações existentes</span><span class="sxs-lookup"><span data-stu-id="d0f12-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="d0f12-178">Pontos de extremidade do Windows</span><span class="sxs-lookup"><span data-stu-id="d0f12-178">Windows endpoints</span></span>
<span data-ttu-id="d0f12-179">Para Servidores Windows e/ou Windows, você seleciona vários computadores para testar com antecedência (antes do patch terça-feira) usando o programa **DEP (Validação** de Atualização de Segurança).</span><span class="sxs-lookup"><span data-stu-id="d0f12-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="d0f12-180">Para mais informações, confira:</span><span class="sxs-lookup"><span data-stu-id="d0f12-180">For more information, see:</span></span>
- [<span data-ttu-id="d0f12-181">O que é o Programa de Validação de Atualizações de Segurança</span><span class="sxs-lookup"><span data-stu-id="d0f12-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="d0f12-182">Programa de Validação de Atualização de Software e Centro de Proteção contra Malware da Microsoft Estabelecimento - TwC Interactive Timeline Part 4</span><span class="sxs-lookup"><span data-stu-id="d0f12-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="d0f12-183">Pontos de extremidade que não são do Windows</span><span class="sxs-lookup"><span data-stu-id="d0f12-183">Non-Windows endpoints</span></span>
<span data-ttu-id="d0f12-184">Com macOS e Linux, você pode usar alguns sistemas e executar no canal "InsidersFast".</span><span class="sxs-lookup"><span data-stu-id="d0f12-184">With macOS and Linux, you could take a couple of systems and run in the "InsidersFast" channel.</span></span>

>[!NOTE]
><span data-ttu-id="d0f12-185">Idealmente, pelo menos um administrador de segurança e um desenvolvedor para que você possa encontrar problemas de compatibilidade, desempenho e confiabilidade antes que a com build o faça no canal "Produção".</span><span class="sxs-lookup"><span data-stu-id="d0f12-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the "Production" channel.</span></span>

<span data-ttu-id="d0f12-186">A escolha do canal determina o tipo e a frequência de atualizações oferecidas ao seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d0f12-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="d0f12-187">Os dispositivos em insiders-fast são os primeiros a receber atualizações e novos recursos, seguidos posteriormente por insiders-slow e por último por prod.</span><span class="sxs-lookup"><span data-stu-id="d0f12-187">Devices in insiders-fast are the first ones to receive updates and new features, followed later by insiders-slow and lastly by prod.</span></span>

![Imagem de anéis insider](images/insider-rings.png)

<span data-ttu-id="d0f12-189">Para visualizar novos recursos e fornecer comentários antecipados, é recomendável configurar alguns dispositivos em sua empresa para usar insiders-fast ou insiders-slow.</span><span class="sxs-lookup"><span data-stu-id="d0f12-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either insiders-fast or insiders-slow.</span></span>

>[!WARNING]
><span data-ttu-id="d0f12-190">Alternar o canal após a instalação inicial exige que o produto seja reinstalado.</span><span class="sxs-lookup"><span data-stu-id="d0f12-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="d0f12-191">Para alternar o canal do produto: desinstale o pacote existente, configure novamente seu dispositivo para usar o novo canal e siga as etapas deste documento para instalar o pacote no novo local.</span><span class="sxs-lookup"><span data-stu-id="d0f12-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
