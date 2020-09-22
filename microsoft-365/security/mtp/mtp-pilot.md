---
title: Executar seu projeto piloto de proteção contra ameaças da Microsoft
description: Execute seu projeto piloto de proteção contra ameaças da Microsoft em produção para determinar efetivamente os benefícios e a adoção da MTP (proteção contra ameaças da Microsoft).
keywords: Piloto de proteção contra ameaças da Microsoft, executar o piloto de proteção contra ameaças da Microsoft, avaliar a proteção contra ameaças da Microsoft em produção, projeto piloto de proteção contra ameaças da Microsoft, segurança na CyberSource, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, caça avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 88d92558d86e0aa2e90ef04d88a3cd4676386f15
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195622"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a><span data-ttu-id="c47f9-104">Executar seu projeto piloto de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c47f9-104">Run your pilot Microsoft Threat Protection project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c47f9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c47f9-105">**Applies to:**</span></span>
- <span data-ttu-id="c47f9-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c47f9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c47f9-107">Para determinar efetivamente o benefício e a adoção da MTP (proteção contra ameaças) da Microsoft, você pode executar um projeto piloto.</span><span class="sxs-lookup"><span data-stu-id="c47f9-107">To effectively determine the benefit and adoption of Microsoft Threat Protection (MTP), you can run a pilot project.</span></span> <span data-ttu-id="c47f9-108">Antes de habilitar a proteção contra ameaças da Microsoft em seu ambiente de produção e começar com os casos de uso definidos, é melhor passar por um processo de planejamento para determinar as tarefas que devem ser realizadas neste projeto piloto e os critérios de sucesso.</span><span class="sxs-lookup"><span data-stu-id="c47f9-108">Before enabling Microsoft Threat Protection in your production environment and starting with defined use cases, it is best to go through a planning process to determine the tasks that must be accomplished in this pilot project, and the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="c47f9-109">Como usar este guia estratégico piloto</span><span class="sxs-lookup"><span data-stu-id="c47f9-109">How to use this pilot playbook</span></span>

<span data-ttu-id="c47f9-110">Este guia fornece uma visão geral da proteção contra ameaças da Microsoft e orientações passo a passo sobre como configurar seu projeto piloto.</span><span class="sxs-lookup"><span data-stu-id="c47f9-110">This guide provides an overview of Microsoft Threat Protection and step-by-step guidance on how to set up your pilot project.</span></span> 

![Fases na execução de um piloto de proteção contra ameaças da Microsoft](../../media/pilotphases.png)

<span data-ttu-id="c47f9-112">A linha do tempo de exemplo a seguir varia de acordo com os recursos corretos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c47f9-112">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="c47f9-113">Algumas detecções e fluxos de trabalho podem precisar de mais tempo de aprendizagem do que os outros.</span><span class="sxs-lookup"><span data-stu-id="c47f9-113">Some detections and workflows might need more learning time than the others.</span></span>

![Linha do tempo de exemplo na execução de um piloto de proteção contra ameaças da Microsoft](../../media/pilotimeline.png)

>[!IMPORTANT]
><span data-ttu-id="c47f9-115">Para obter resultados ideais, siga as instruções do piloto o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="c47f9-115">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="c47f9-116">Fases do manual do piloto</span><span class="sxs-lookup"><span data-stu-id="c47f9-116">Pilot playbook phases</span></span> 

<span data-ttu-id="c47f9-117">Há quatro fases na execução de um piloto de proteção contra ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c47f9-117">There are four phases in running a Microsoft Threat Protection pilot:</span></span>

|<span data-ttu-id="c47f9-118">Fase</span><span class="sxs-lookup"><span data-stu-id="c47f9-118">Phase</span></span> | <span data-ttu-id="c47f9-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="c47f9-119">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="c47f9-120">![Planejamento](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="c47f9-120">![Planning](../../media/mtp/plan.png)</span></span><br>[<span data-ttu-id="c47f9-121">Planejamento</span><span class="sxs-lookup"><span data-stu-id="c47f9-121">Planning</span></span>](mtp-pilot-plan.md)| <span data-ttu-id="c47f9-122">Saiba o que você precisa considerar antes de executar o projeto piloto de proteção contra ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c47f9-122">Learn what you need to consider before running your Microsoft Threat Protection pilot project:</span></span> <br><br><span data-ttu-id="c47f9-123">-Escopo</span><span class="sxs-lookup"><span data-stu-id="c47f9-123">- Scope</span></span> <br> <span data-ttu-id="c47f9-124">– Casos de uso</span><span class="sxs-lookup"><span data-stu-id="c47f9-124">- Use cases</span></span> <br><span data-ttu-id="c47f9-125">- Requisitos</span><span class="sxs-lookup"><span data-stu-id="c47f9-125">- Requirements</span></span> <br><span data-ttu-id="c47f9-126">– Plano de teste</span><span class="sxs-lookup"><span data-stu-id="c47f9-126">- Test plan</span></span> <br> <span data-ttu-id="c47f9-127">-Critérios de êxito</span><span class="sxs-lookup"><span data-stu-id="c47f9-127">- Success criteria</span></span> <br> <span data-ttu-id="c47f9-128">-Scorecard</span><span class="sxs-lookup"><span data-stu-id="c47f9-128">- Scorecard</span></span> 
| <span data-ttu-id="c47f9-129">![Preparação](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="c47f9-129">![Preparation](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="c47f9-130">Preparação</span><span class="sxs-lookup"><span data-stu-id="c47f9-130">Preparation</span></span>](mtp-evaluation.md)|  <span data-ttu-id="c47f9-131">Acesse a central de segurança do Microsoft 365 para configurar seu ambiente piloto de proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c47f9-131">Access Microsoft 365 Security Center to setup your Microsoft Threat Protection pilot  environment.</span></span> <span data-ttu-id="c47f9-132">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="c47f9-132">You will be guided to:</span></span><br><br><span data-ttu-id="c47f9-133">– Identificar os participantes e a aprovação de busca para o seu piloto</span><span class="sxs-lookup"><span data-stu-id="c47f9-133">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="c47f9-134">-Considerações de ambiente</span><span class="sxs-lookup"><span data-stu-id="c47f9-134">- Environment considerations</span></span> <br><span data-ttu-id="c47f9-135">– Acesso</span><span class="sxs-lookup"><span data-stu-id="c47f9-135">- Access</span></span> <br><span data-ttu-id="c47f9-136">-Configuração do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c47f9-136">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="c47f9-137">-Ordem de configuração</span><span class="sxs-lookup"><span data-stu-id="c47f9-137">- Configuration order</span></span> <br> <span data-ttu-id="c47f9-138">-Inscrever-se no Microsoft 365 E5 Trial</span><span class="sxs-lookup"><span data-stu-id="c47f9-138">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="c47f9-139">-Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="c47f9-139">- Configure domain</span></span> <br><span data-ttu-id="c47f9-140">-Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="c47f9-140">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="c47f9-141">– Concluir o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="c47f9-141">- Complete the setup wizard in the portal</span></span>|
| <span data-ttu-id="c47f9-142">![Simulação de ataque](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="c47f9-142">![Attack simulation](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="c47f9-143">Simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="c47f9-143">Attack simulation</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="c47f9-144">Para simular um ataque, você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="c47f9-144">To simulate an attack, you will be guided to:</span></span><br><br><span data-ttu-id="c47f9-145">– Verificar os requisitos do ambiente de teste</span><span class="sxs-lookup"><span data-stu-id="c47f9-145">- Verify the test environment requirements</span></span> <br><span data-ttu-id="c47f9-146">– Executar a simulação</span><span class="sxs-lookup"><span data-stu-id="c47f9-146">-  Run the simulation</span></span> <br><span data-ttu-id="c47f9-147">– Investigue um incidente</span><span class="sxs-lookup"><span data-stu-id="c47f9-147">- Investigate an incident</span></span> <br><span data-ttu-id="c47f9-148">-resolver o incidente</span><span class="sxs-lookup"><span data-stu-id="c47f9-148">- resolve the incident</span></span> 
| <span data-ttu-id="c47f9-149">![Fechamento e Resumo](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="c47f9-149">![Closing and summary](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="c47f9-150">Fechamento e Resumo</span><span class="sxs-lookup"><span data-stu-id="c47f9-150">Closing and summary</span></span>](mtp-pilot-close.md) | <span data-ttu-id="c47f9-151">Quando atingir o final do processo, você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="c47f9-151">When you've reached the end of the process, you will be guided to:</span></span><br><br><span data-ttu-id="c47f9-152">-Passar pela saída final</span><span class="sxs-lookup"><span data-stu-id="c47f9-152">- Go through your final output</span></span><br><span data-ttu-id="c47f9-153">-Apresentar sua saída para seus participantes</span><span class="sxs-lookup"><span data-stu-id="c47f9-153">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="c47f9-154">– Fornecer comentários</span><span class="sxs-lookup"><span data-stu-id="c47f9-154">- Provide feedback</span></span> <br><span data-ttu-id="c47f9-155">-Siga as próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c47f9-155">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="c47f9-156">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c47f9-156">Next step</span></span>
|<span data-ttu-id="c47f9-157">![Fase de planejamento](../../media/mtp/plan.png)</span><span class="sxs-lookup"><span data-stu-id="c47f9-157">![Planning phase](../../media/mtp/plan.png)</span></span> <br>[<span data-ttu-id="c47f9-158">Fase de planejamento</span><span class="sxs-lookup"><span data-stu-id="c47f9-158">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="c47f9-159">Planejar seu projeto piloto de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c47f9-159">Plan your Microsoft Threat Protection pilot project</span></span> 
|:-------|:-----|
