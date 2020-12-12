---
title: Execute seu projeto piloto do Microsoft 365 defender
description: Execute seu projeto piloto do Microsoft 365 defender em produção para determinar efetivamente os benefícios e a adoção do Microsoft 365 defender.
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
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: f01e918d35ce77d9239c200355c7b4c48c9e2b84
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659311"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="c44ff-104">Execute seu projeto piloto do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="c44ff-104">Run your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c44ff-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c44ff-105">**Applies to:**</span></span>
- <span data-ttu-id="c44ff-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c44ff-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="c44ff-107">Este guia ajuda você a executar um projeto piloto, fornecendo ponteiros para garantir que você tenha um plano bem estruturado, orienta você usando o recurso de simulação de ataque e, finalmente, concluindo o piloto com a chave para que você reflita e documente os resultados.</span><span class="sxs-lookup"><span data-stu-id="c44ff-107">This guide helps you run a pilot project by providing pointers to ensure you have a well-structured plan, guiding you through using the attack simulation feature, and finally concluding the pilot with key take-aways for you to reflect on and document results.</span></span>

![Fases na execução de um piloto do Microsoft 365 defender](../../media/pilotphases.png)


<span data-ttu-id="c44ff-109">A execução de um piloto ajuda a determinar efetivamente o benefício do adoptiing Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="c44ff-109">Running a pilot helps you effectively determine the benefit of adoptiing Microsoft 365 Defender.</span></span> <span data-ttu-id="c44ff-110">Antes de habilitar o Microsoft 365 defender em seu ambiente de produção e iniciar seus casos de uso, é melhor planejar determinar as tarefas a serem realizadas para o projeto piloto e definir os critérios de sucesso.</span><span class="sxs-lookup"><span data-stu-id="c44ff-110">Before enabling Microsoft 365 Defender in your production environment and starting your use cases, it's best to plan to determine the tasks to accomplish for your pilot project and set the success criteria.</span></span> 


## <a name="how-to-use-this-pilot-playbook"></a><span data-ttu-id="c44ff-111">Como usar este guia estratégico piloto</span><span class="sxs-lookup"><span data-stu-id="c44ff-111">How to use this pilot playbook</span></span>

<span data-ttu-id="c44ff-112">Este guia fornece uma visão geral do Microsoft 365 defender e instruções passo a passo sobre como configurar seu projeto piloto.</span><span class="sxs-lookup"><span data-stu-id="c44ff-112">This guide provides an overview of Microsoft 365 Defender and step-by-step instructions on how to set up your pilot project.</span></span> 

<span data-ttu-id="c44ff-113">O Microsoft 365 defender é um pacote de defesa unificado do Enterprise Defense, que coordena nativamente a proteção, detecção, prevenção, investigação e resposta entre os pontos de extremidade, as identidades, os emails e os aplicativos para fornecer proteção integrada contra ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="c44ff-113">Microsoft 365 Defender is a unified pre- and post-breach enterprise defense suite that natively coordinates protection, detection, prevention, investigation, and response across endpoints, identities, email, and applications to provide integrated protection against sophisticated attacks.</span></span> <span data-ttu-id="c44ff-114">Isso é feito combinando e organizando os seguintes recursos em uma única solução de segurança:</span><span class="sxs-lookup"><span data-stu-id="c44ff-114">It does so by combining and orchestrating the following capabilities into a single security solution:</span></span>
  - <span data-ttu-id="c44ff-115">Microsoft defender para ponto de extremidade, o novo nome da proteção avançada contra ameaças do Microsoft defender (pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="c44ff-115">Microsoft Defender for Endpoint, the new name for Microsoft Defender Advanced Threat Protection (endpoints)</span></span>
  - <span data-ttu-id="c44ff-116">Microsoft defender para Office 365, o novo nome do Office 365 ATP (email)</span><span class="sxs-lookup"><span data-stu-id="c44ff-116">Microsoft Defender for Office 365, the new name for Office 365 ATP (email)</span></span> 
  - <span data-ttu-id="c44ff-117">Microsoft defender para identidade, o novo nome para o Azure ATP (identidade)</span><span class="sxs-lookup"><span data-stu-id="c44ff-117">Microsoft Defender for Identity, the new name for Azure ATP (identity)</span></span> 
  - <span data-ttu-id="c44ff-118">Microsoft Cloud app Security (aplicativos)</span><span class="sxs-lookup"><span data-stu-id="c44ff-118">Microsoft Cloud App Security (apps)</span></span>

![Image of_Microsoft 365 defender Solution for users, Microsoft defender para identidade, para pontos de extremidade Microsoft defender for Endpoint, para aplicativos de nuvem, segurança do aplicativo do Microsoft Cloud e para dados, Microsoft defender para Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="c44ff-120">Com a solução integrada do Microsoft 365 defender, os profissionais de segurança podem unir os sinais de ameaça que o Microsoft defender para ponto de extremidade, o Microsoft defender para Office 365, o Microsoft defender para identidade e o Microsoft Cloud app Security recebem, e determinar o escopo completo e o impacto da ameaça, como ele entrou no ambiente, o que é afetado e como ele está afetando a organização.</span><span class="sxs-lookup"><span data-stu-id="c44ff-120">With the integrated Microsoft 365 Defender solution, security professionals can stitch together the threat signals that Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Defender for Identity, and Microsoft Cloud App Security receive, and determine the full scope and impact of the threat, how it entered the environment, what it's affected, and how it's currently impacting the organization.</span></span> <span data-ttu-id="c44ff-121">O Microsoft 365 defender realiza ações automáticas para impedir ou interromper o ataque e a AutoCorreção de caixas de correio, pontos de extremidade e identidades de usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="c44ff-121">Microsoft 365 Defender takes automatic action to prevent or stop the attack and self-heal affected mailboxes, endpoints, and user identities.</span></span> <span data-ttu-id="c44ff-122">Consulte a [visão geral do Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="c44ff-122">See the [Microsoft 365 Defender overview](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) for details.</span></span>



<span data-ttu-id="c44ff-123">A linha do tempo de exemplo a seguir varia de acordo com os recursos corretos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c44ff-123">The following sample timeline varies depending on having the right resources in your environment.</span></span> <span data-ttu-id="c44ff-124">Algumas detecções e fluxos de trabalho podem precisar de mais tempo de aprendizagem do que os outros.</span><span class="sxs-lookup"><span data-stu-id="c44ff-124">Some detections and workflows might need more learning time than the others.</span></span>

![Linha do tempo de amostra na execução de um piloto do Microsoft 365 defender](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
><span data-ttu-id="c44ff-126">Para obter resultados ideais, siga as instruções do piloto o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="c44ff-126">For optimum results, follow the pilot instructions as closely as possible.</span></span>


### <a name="pilot-playbook-phases"></a><span data-ttu-id="c44ff-127">Fases do manual do piloto</span><span class="sxs-lookup"><span data-stu-id="c44ff-127">Pilot playbook phases</span></span> 

<span data-ttu-id="c44ff-128">Há quatro fases na execução de um piloto do Microsoft 365 defender:</span><span class="sxs-lookup"><span data-stu-id="c44ff-128">There are four phases in running a Microsoft 365 Defender pilot:</span></span>

|<span data-ttu-id="c44ff-129">Fase</span><span class="sxs-lookup"><span data-stu-id="c44ff-129">Phase</span></span> | <span data-ttu-id="c44ff-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="c44ff-130">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="c44ff-131">Planejamento</span><span class="sxs-lookup"><span data-stu-id="c44ff-131">Planning</span></span>](mtp-pilot-plan.md)<br> <span data-ttu-id="c44ff-132">aproximadamente 1 dia</span><span class="sxs-lookup"><span data-stu-id="c44ff-132">~ 1 day</span></span>| <span data-ttu-id="c44ff-133">Saiba o que você precisa considerar antes de executar o projeto piloto do Microsoft 365 defender:</span><span class="sxs-lookup"><span data-stu-id="c44ff-133">Learn what you need to consider before running your Microsoft 365 Defender pilot project:</span></span> <br><br><span data-ttu-id="c44ff-134">-Escopo</span><span class="sxs-lookup"><span data-stu-id="c44ff-134">- Scope</span></span> <br> <span data-ttu-id="c44ff-135">– Casos de uso</span><span class="sxs-lookup"><span data-stu-id="c44ff-135">- Use cases</span></span> <br><span data-ttu-id="c44ff-136">- Requisitos</span><span class="sxs-lookup"><span data-stu-id="c44ff-136">- Requirements</span></span> <br><span data-ttu-id="c44ff-137">– Plano de teste</span><span class="sxs-lookup"><span data-stu-id="c44ff-137">- Test plan</span></span> <br> <span data-ttu-id="c44ff-138">-Critérios de êxito</span><span class="sxs-lookup"><span data-stu-id="c44ff-138">- Success criteria</span></span> <br> <span data-ttu-id="c44ff-139">-Scorecard</span><span class="sxs-lookup"><span data-stu-id="c44ff-139">- Scorecard</span></span> 
| [<span data-ttu-id="c44ff-140">Preparação</span><span class="sxs-lookup"><span data-stu-id="c44ff-140">Preparation</span></span>](mtp-evaluation.md) <br><span data-ttu-id="c44ff-141">~ 2 dias</span><span class="sxs-lookup"><span data-stu-id="c44ff-141">~2 days</span></span>|  <span data-ttu-id="c44ff-142">Acesse o centro de segurança do Microsoft 365 para configurar seu ambiente piloto do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="c44ff-142">Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot  environment.</span></span> <span data-ttu-id="c44ff-143">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="c44ff-143">You'll be guided to:</span></span><br><br><span data-ttu-id="c44ff-144">– Identificar os participantes e a aprovação de busca para o seu piloto</span><span class="sxs-lookup"><span data-stu-id="c44ff-144">- Identify stakeholders and seek sign-off for your pilot</span></span> <br> <span data-ttu-id="c44ff-145">-Considerações de ambiente</span><span class="sxs-lookup"><span data-stu-id="c44ff-145">- Environment considerations</span></span> <br><span data-ttu-id="c44ff-146">– Acesso</span><span class="sxs-lookup"><span data-stu-id="c44ff-146">- Access</span></span> <br><span data-ttu-id="c44ff-147">-Configuração do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c44ff-147">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="c44ff-148">-Ordem de configuração</span><span class="sxs-lookup"><span data-stu-id="c44ff-148">- Configuration order</span></span> <br> <span data-ttu-id="c44ff-149">-Inscrever-se no Microsoft 365 E5 Trial</span><span class="sxs-lookup"><span data-stu-id="c44ff-149">- Sign up for Microsoft 365 E5 Trial</span></span> <br> <span data-ttu-id="c44ff-150">-Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="c44ff-150">- Configure domain</span></span> <br><span data-ttu-id="c44ff-151">-Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="c44ff-151">- Assign Microsoft 365 E5 licenses</span></span> <br> <span data-ttu-id="c44ff-152">– Concluir o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="c44ff-152">- Complete the setup wizard in the portal</span></span>|
| [<span data-ttu-id="c44ff-153">Simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="c44ff-153">Attack simulation</span></span>](mtp-pilot-simulate.md) <br><span data-ttu-id="c44ff-154">~ 2 dias</span><span class="sxs-lookup"><span data-stu-id="c44ff-154">~2 days</span></span>| <span data-ttu-id="c44ff-155">Para simular um ataque, você será orientado a:</span><span class="sxs-lookup"><span data-stu-id="c44ff-155">To simulate an attack, you'll be guided to:</span></span><br><br><span data-ttu-id="c44ff-156">– Verificar os requisitos do ambiente de teste</span><span class="sxs-lookup"><span data-stu-id="c44ff-156">- Verify the test environment requirements</span></span> <br><span data-ttu-id="c44ff-157">– Executar a simulação</span><span class="sxs-lookup"><span data-stu-id="c44ff-157">-  Run the simulation</span></span> <br><span data-ttu-id="c44ff-158">– Investigue um incidente</span><span class="sxs-lookup"><span data-stu-id="c44ff-158">- Investigate an incident</span></span> <br><span data-ttu-id="c44ff-159">-resolver o incidente</span><span class="sxs-lookup"><span data-stu-id="c44ff-159">- resolve the incident</span></span> 
| [<span data-ttu-id="c44ff-160">Fechamento e Resumo</span><span class="sxs-lookup"><span data-stu-id="c44ff-160">Closing and summary</span></span>](mtp-pilot-close.md) <br><span data-ttu-id="c44ff-161">aproximadamente 1 dia</span><span class="sxs-lookup"><span data-stu-id="c44ff-161">~ 1 day</span></span>| <span data-ttu-id="c44ff-162">Quando você chegar ao final do processo, será orientado para:</span><span class="sxs-lookup"><span data-stu-id="c44ff-162">When you've reached the end of the process, you'll be guided to:</span></span><br><br><span data-ttu-id="c44ff-163">-Passar pela saída final</span><span class="sxs-lookup"><span data-stu-id="c44ff-163">- Go through your final output</span></span><br><span data-ttu-id="c44ff-164">-Apresentar sua saída para seus participantes</span><span class="sxs-lookup"><span data-stu-id="c44ff-164">- Present your output to your stakeholders</span></span> <br><span data-ttu-id="c44ff-165">– Fornecer comentários</span><span class="sxs-lookup"><span data-stu-id="c44ff-165">- Provide feedback</span></span> <br><span data-ttu-id="c44ff-166">-Siga as próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c44ff-166">- Take next steps</span></span> 

## <a name="next-step"></a><span data-ttu-id="c44ff-167">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c44ff-167">Next step</span></span>
|[<span data-ttu-id="c44ff-168">Fase de planejamento</span><span class="sxs-lookup"><span data-stu-id="c44ff-168">Planning phase</span></span>](mtp-pilot-plan.md) | <span data-ttu-id="c44ff-169">Planejar seu projeto piloto do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="c44ff-169">Plan your Microsoft 365 Defender pilot project</span></span> 
|:-------|:-----|
