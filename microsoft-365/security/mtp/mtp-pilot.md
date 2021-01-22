---
title: Executar seu projeto piloto do Microsoft 365 Defender
description: Execute seu projeto piloto do Microsoft 365 Defender em produção para determinar efetivamente os benefícios e a adoção do Microsoft 365 Defender.
keywords: Piloto da Proteção contra Ameaças da Microsoft, execute o projeto piloto da Proteção contra Ameaças da Microsoft, avalie a Proteção contra Ameaças da Microsoft em produção, projeto piloto da Proteção contra Ameaças da Microsoft, segurança cibernética, ameaça persistente avançada, segurança corporativa, dispositivo, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933025"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="682d9-104">Executar seu projeto piloto do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="682d9-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="682d9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="682d9-105">**Applies to:**</span></span>
- <span data-ttu-id="682d9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="682d9-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="682d9-107">Este guia ajuda você a executar um projeto piloto fornecendo ponteiros para garantir que você tenha um plano bem estruturado, orientando você pelo uso do recurso de simulação de ataque e, por fim, concluindo o piloto com as principais dicas para refletir e documentar os resultados.</span><span class="sxs-lookup"><span data-stu-id="682d9-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fases da execução de um piloto do Microsoft 365 Defender](../../media/pilotphases.png)


<span data-ttu-id="682d9-109">Executar um piloto ajuda você a determinar efetivamente o benefício de adotar o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="682d9-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="682d9-110">Antes de ativar o Microsoft 365 Defender em seu ambiente de produção e iniciar seus casos de uso, é melhor planejar a determinação das tarefas a realizar para seu projeto piloto e definir os critérios de sucesso.</span><span class="sxs-lookup"><span data-stu-id="682d9-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="682d9-111">Como usar este manual piloto</span><span class="sxs-lookup"><span data-stu-id="682d9-111">How to use this pilot playbook</span></span>

<span data-ttu-id="682d9-112">Este guia fornece uma visão geral do Microsoft 365 Defender e instruções passo a passo sobre como configurar seu projeto piloto.</span><span class="sxs-lookup"><span data-stu-id="682d9-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="682d9-113">O Microsoft 365 Defender é um pacote unificado de defesa empresarial pré e pós-violação que coordena na verdade a proteção, a detecção, a prevenção, a investigação e a resposta entre pontos de extremidade, identidades, email e aplicativos para fornecer proteção integrada contra ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="682d9-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="682d9-114">Ele faz isso combinando e orquestrando os seguintes recursos em uma única solução de segurança:</span><span class="sxs-lookup"><span data-stu-id="682d9-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="682d9-115">Microsoft Defender para Ponto de Extremidade, o novo nome da Proteção Avançada contra Ameaças do Microsoft Defender (pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="682d9-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="682d9-116">Microsoft Defender para Office 365, o novo nome do Office 365 ATP (email)</span><span class="sxs-lookup"><span data-stu-id="682d9-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="682d9-117">Microsoft Defender for Identity, o novo nome da ATP do Azure (identidade)</span><span class="sxs-lookup"><span data-stu-id="682d9-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="682d9-118">Microsoft Cloud App Security (aplicativos)</span><span class="sxs-lookup"><span data-stu-id="682d9-118">Microsoft Cloud App Security (apps)</span></span>

![Imagem of_Microsoft solução do 365 Defender para usuários, Microsoft Defender for Identity, para pontos de extremidade do Microsoft Defender para Ponto de Extremidade, para aplicativos em nuvem, Microsoft Cloud App Security e para dados, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="682d9-120">Com a solução integrada do Microsoft 365 Defender, os profissionais de segurança podem unir os sinais de ameaça que o Microsoft Defender para Ponto de Extremidade, o Microsoft Defender para Office 365, o Microsoft Defender para Identidade e o Microsoft Cloud App Security recebem e determinar o escopo completo e o impacto da ameaça, como ele entrou no ambiente, o que é afetado e como ele está afetando a organização no momento.</span><span class="sxs-lookup"><span data-stu-id="682d9-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="682d9-121">O Microsoft 365 Defender faz uma ação automática para impedir ou parar o ataque e auto-recuperar caixas de correio afetadas, pontos de extremidade e identidades de usuário.</span><span class="sxs-lookup"><span data-stu-id="682d9-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="682d9-122">Consulte a [visão geral do Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="682d9-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="682d9-123">A linha do tempo de exemplo a seguir varia dependendo de ter os recursos certos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="682d9-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="682d9-124">Algumas detecções e fluxos de trabalho podem precisar de mais tempo de aprendizagem do que os outros.</span><span class="sxs-lookup"><span data-stu-id="682d9-124">Some detections and workflows might need more learning time than the others.</span></span>

![Linha do tempo de exemplo na execução de um piloto do Microsoft 365 Defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="682d9-126">Para obter os melhores resultados, siga as instruções do piloto o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="682d9-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="682d9-127">Fases do manual piloto</span><span class="sxs-lookup"><span data-stu-id="682d9-127">Pilot playbook phases</span></span> 

<span data-ttu-id="682d9-128">Há quatro fases na execução de um piloto do Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="682d9-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="682d9-129">Fase</span><span class="sxs-lookup"><span data-stu-id="682d9-129">Phase</span></span> | <span data-ttu-id="682d9-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="682d9-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="682d9-131">Planejamento</span><span class="sxs-lookup"><span data-stu-id="682d9-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="682d9-132">~ 1 dia</span><span class="sxs-lookup"><span data-stu-id="682d9-132">~ 1 day</span></span>| <span data-ttu-id="682d9-133">Saiba o que você precisa considerar antes de executar seu projeto piloto do Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="682d9-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="682d9-134">- Escopo</span><span class="sxs-lookup"><span data-stu-id="682d9-134">- Scope</span></span> <br> <span data-ttu-id="682d9-135">- Casos de uso</span><span class="sxs-lookup"><span data-stu-id="682d9-135">- Use cases</span></span> <br><span data-ttu-id="682d9-136">- Requisitos</span><span class="sxs-lookup"><span data-stu-id="682d9-136">- Requirements</span></span> <br><span data-ttu-id="682d9-137">- Plano de teste</span><span class="sxs-lookup"><span data-stu-id="682d9-137">- Test plan</span></span> <br> <span data-ttu-id="682d9-138">- Critérios de sucesso</span><span class="sxs-lookup"><span data-stu-id="682d9-138">- Success criteria</span></span> <br> <span data-ttu-id="682d9-139">- Scorecard</span><span class="sxs-lookup"><span data-stu-id="682d9-139">- Scorecard</span></span> 
| [<span data-ttu-id="682d9-140">Preparação</span><span class="sxs-lookup"><span data-stu-id="682d9-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="682d9-141">~2 dias</span><span class="sxs-lookup"><span data-stu-id="682d9-141">~2 days</span></span>|  <span data-ttu-id="682d9-142">Acesse a Central de Segurança do Microsoft 365 para configurar seu ambiente piloto do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="682d9-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="682d9-143">Você será orientado a:</span><span class="sxs-lookup"><span data-stu-id="682d9-143">You'll be guided to:</span></span><br><br><span data-ttu-id="682d9-144">- Identificar os participantes e buscar a aprovação para o seu piloto</span><span class="sxs-lookup"><span data-stu-id="682d9-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="682d9-145">- Considerações sobre o ambiente</span><span class="sxs-lookup"><span data-stu-id="682d9-145">- Environment considerations</span></span> <br><span data-ttu-id="682d9-146">- Acesso</span><span class="sxs-lookup"><span data-stu-id="682d9-146">- Access</span></span> <br><span data-ttu-id="682d9-147">- Configuração do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="682d9-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="682d9-148">- Ordem de configuração</span><span class="sxs-lookup"><span data-stu-id="682d9-148">- Configuration order</span></span> <br> <span data-ttu-id="682d9-149">- Inscreva-se na avaliação do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="682d9-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="682d9-150">- Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="682d9-150">- Configure domain</span></span> <br><span data-ttu-id="682d9-151">- Atribuir licenças do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="682d9-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="682d9-152">– Conclua o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="682d9-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="682d9-153">Simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="682d9-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="682d9-154">~2 dias</span><span class="sxs-lookup"><span data-stu-id="682d9-154">~2 days</span></span>| <span data-ttu-id="682d9-155">Para simular um ataque, você será orientado a:</span><span class="sxs-lookup"><span data-stu-id="682d9-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="682d9-156">- Verificar os requisitos do ambiente de teste</span><span class="sxs-lookup"><span data-stu-id="682d9-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="682d9-157">- Executar a simulação</span><span class="sxs-lookup"><span data-stu-id="682d9-157">-  Run the simulation</span></span> <br><span data-ttu-id="682d9-158">- Investigar um incidente</span><span class="sxs-lookup"><span data-stu-id="682d9-158">- Investigate an incident</span></span> <br><span data-ttu-id="682d9-159">- resolver o incidente</span><span class="sxs-lookup"><span data-stu-id="682d9-159">- resolve the incident</span></span> 
| [<span data-ttu-id="682d9-160">Fechamento e resumo</span><span class="sxs-lookup"><span data-stu-id="682d9-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="682d9-161">~ 1 dia</span><span class="sxs-lookup"><span data-stu-id="682d9-161">~ 1 day</span></span>| <span data-ttu-id="682d9-162">Quando chegar ao final do processo, você será orientado a:</span><span class="sxs-lookup"><span data-stu-id="682d9-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="682d9-163">- Passar pela saída final</span><span class="sxs-lookup"><span data-stu-id="682d9-163">- Go through your final output</span></span><br><span data-ttu-id="682d9-164">- Apresente sua saída aos stakeholders</span><span class="sxs-lookup"><span data-stu-id="682d9-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="682d9-165">- Fornecer comentários</span><span class="sxs-lookup"><span data-stu-id="682d9-165">- Provide feedback</span></span> <br><span data-ttu-id="682d9-166">- Tomar as próximas etapas</span><span class="sxs-lookup"><span data-stu-id="682d9-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="682d9-167">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="682d9-167">Next step</span></span>
|[<span data-ttu-id="682d9-168">Fase de planejamento</span><span class="sxs-lookup"><span data-stu-id="682d9-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="682d9-169">Planejar seu projeto piloto do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="682d9-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
