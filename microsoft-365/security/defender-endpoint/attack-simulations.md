---
title: Experimente o Microsoft Defender para Ponto de Extremidade por meio de ataques simulados
description: Execute as simulações de cenário de ataque fornecidas para experimentar como o Microsoft Defender for Endpoint pode detectar, investigar e responder a violações.
keywords: test, scenario, attack, simulation, simulated, diy, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 6ecbf98c81b1f68e42f39269809592fb446e6036
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934376"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="bb4e5-104">Experimente o Microsoft Defender para Ponto de Extremidade por meio de ataques simulados</span><span class="sxs-lookup"><span data-stu-id="bb4e5-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bb4e5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="bb4e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="bb4e5-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="bb4e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bb4e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb4e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="bb4e5-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="bb4e5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bb4e5-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="bb4e5-110">Saiba mais sobre os aprimoramentos mais recentes no Microsoft Defender para Ponto de Extremidade: [Novidades no Defender para Ponto de Extremidade?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="bb4e5-110">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="bb4e5-111">O Defender for Endpoint demonstrou recursos de detecção e ótica líderes do setor na avaliação recente do MITRE.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="bb4e5-112">Leitura: [Insights do MITRE ATT&avaliação baseada em CK.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="bb4e5-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="bb4e5-113">Talvez você queira experimentar o Defender para Ponto de Extremidade antes de entrar em mais de alguns dispositivos no serviço.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="bb4e5-114">Para fazer isso, você pode executar simulações de ataque controladas em alguns dispositivos de teste.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="bb4e5-115">Depois de executar os ataques simulados, você pode revisar como o Defender for Endpoint superfície atividade mal-intencionada e explorar como ele habilita uma resposta eficiente.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bb4e5-116">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="bb4e5-116">Before you begin</span></span>

<span data-ttu-id="bb4e5-117">Para executar qualquer uma das simulações fornecidas, você precisa de pelo menos [um dispositivo integrado.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="bb4e5-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="bb4e5-118">Leia o documento passo a passo fornecido com cada cenário de ataque.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="bb4e5-119">Cada documento inclui requisitos de sistema operacional e aplicativo, bem como instruções detalhadas específicas para um cenário de ataque.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="bb4e5-120">Executar uma simulação</span><span class="sxs-lookup"><span data-stu-id="bb4e5-120">Run a simulation</span></span>

1. <span data-ttu-id="bb4e5-121">Em   >  **Simulações de Ajuda & tutoriais**, selecione qual dos cenários de ataque disponíveis você gostaria de simular:</span><span class="sxs-lookup"><span data-stu-id="bb4e5-121">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="bb4e5-122">**Cenário 1: o documento solta o backdoor** - simula a entrega de um documento de adução de engenharia social.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="bb4e5-123">O documento inicia um backdoor especialmente criado que dá controle aos invasores.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="bb4e5-124">**Cenário 2: script** do PowerShell em ataque sem arquivo - simula um ataque sem arquivo que depende do PowerShell, mostrando a redução de superfície de ataque e a detecção de aprendizado de dispositivo de atividade de memória mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="bb4e5-125">**Cenário 3:** Resposta automatizada a incidentes - dispara investigação automatizada, que busca e correção automática de artefatos de violação para dimensionar sua capacidade de resposta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="bb4e5-126">Baixe e leia o documento passo a passo correspondente fornecido com o cenário selecionado.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="bb4e5-127">Baixe o arquivo de simulação ou copie o script de simulação navegando para **Simulações** de Ajuda  >  **& tutoriais.**</span><span class="sxs-lookup"><span data-stu-id="bb4e5-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="bb4e5-128">Você pode optar por baixar o arquivo ou o script no dispositivo de teste, mas ele não é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="bb4e5-129">Execute o arquivo de simulação ou o script no dispositivo de teste conforme instruído no documento passo a passo.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="bb4e5-130">Arquivos de simulação ou scripts imitam a atividade de ataque, mas são realmente benignos e não prejudicarão ou comprometerão o dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="bb4e5-131">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="bb4e5-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bb4e5-132">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="bb4e5-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="bb4e5-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bb4e5-133">Related topics</span></span>

- [<span data-ttu-id="bb4e5-134">Dispositivos de integração</span><span class="sxs-lookup"><span data-stu-id="bb4e5-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="bb4e5-135">Dispositivos integrados do Windows 10</span><span class="sxs-lookup"><span data-stu-id="bb4e5-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
