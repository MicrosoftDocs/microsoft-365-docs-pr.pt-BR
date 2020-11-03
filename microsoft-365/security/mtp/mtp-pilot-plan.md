---
title: Planejando seu projeto piloto do Microsoft 365 defender
description: Planeje seu projeto piloto do Microsoft 365 defender com os participantes para gerenciar as expectativas e garantir o resultado bem-sucedido.
keywords: Piloto de proteção contra ameaças da Microsoft, plano piloto de proteção contra ameaças da Microsoft, avaliar a proteção contra ameaças da Microsoft em produção, projeto piloto de proteção contra ameaças da Microsoft, segurança na CyberSource, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, caça avançada
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
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: ec2bfe52308231577e4f2749e1f4cdf24a36f604
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846015"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a><span data-ttu-id="7f4ac-104">Planejando seu projeto piloto do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7f4ac-104">Planning your pilot Microsoft 365 Defender project</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="7f4ac-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7f4ac-105">**Applies to:**</span></span>
- <span data-ttu-id="7f4ac-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7f4ac-106">Microsoft 365 Defender</span></span>
<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-plan"> 
        <img src="../../media/mtp/plan.png" alt="Plan your pilot Microsoft 365 Defender project" title="Planejar seu projeto piloto do Microsoft 365 defender" />
      <br/><span data-ttu-id="7f4ac-108">Plano</a></span><span class="sxs-lookup"><span data-stu-id="7f4ac-108">Plan</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval">
        <img src="../../media/mtp/prep.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Prepare seu laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto" />
      <br/><span data-ttu-id="7f4ac-110">Preparar</a></span><span class="sxs-lookup"><span data-stu-id="7f4ac-110">Prepare</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate">
        <img src="../../media/mtp/run-sim.png" alt="Run your Microsoft 365 Defender attack simulations" title="Executar as simulações de ataque do Microsoft 365 defender" />
     <br/><span data-ttu-id="7f4ac-112">Simular ameaças</a></span><span class="sxs-lookup"><span data-stu-id="7f4ac-112">Simulate attack</a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-close">
        <img src="../../media/mtp/close.png" alt="Close and summarize your Microsoft 365 Defender pilot" title="Feche e resuma seu piloto do Microsoft 365 defender" />
     <br/><span data-ttu-id="7f4ac-114">Fechar e resumir</a></span><span class="sxs-lookup"><span data-stu-id="7f4ac-114">Close and summarize</a></span></span><br>
    </td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
    <td valign="top" style="width:25%; border:0;">

</td>
  </tr>
</table>

<span data-ttu-id="7f4ac-115">Você está atualmente na fase de planejamento.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-115">You're currently in the planning phase.</span></span>

<span data-ttu-id="7f4ac-116">Para garantir que seu projeto piloto seja um sucesso, é essencial planejar com detalhes e obter aprovações de seus participantes no início.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-116">To ensure that your pilot project is a success, it is essential to plan thoroughly with and get approvals from your stakeholders in the beginning.</span></span> <span data-ttu-id="7f4ac-117">Os elementos de planejamento incluem o escopo de identificação, casos de uso, requisitos e critérios de sucesso.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-117">Elements of planning include identifying scope, use cases, requirements, and success criteria.</span></span>

<span data-ttu-id="7f4ac-118">Este guia descreve como planejar o projeto piloto.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-118">This guide walks you through how to plan your pilot project.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="7f4ac-119">Para obter resultados ideais, siga as instruções do piloto o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-119">For optimum results, follow the pilot instructions as closely as possible.</span></span>


## <a name="scope"></a><span data-ttu-id="7f4ac-120">Escopo</span><span class="sxs-lookup"><span data-stu-id="7f4ac-120">Scope</span></span>

<span data-ttu-id="7f4ac-121">O escopo do piloto determinará como o teste será amplo, com base no seu ambiente e nos métodos de teste aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-121">The scope of the pilot will determine how broad the test will be, based on your environment and acceptable testing methods.</span></span> <span data-ttu-id="7f4ac-122">Estes são alguns exemplos de escopos a serem considerados:</span><span class="sxs-lookup"><span data-stu-id="7f4ac-122">Here are some example scopes to consider:</span></span>
- <span data-ttu-id="7f4ac-123">Ambiente de desenvolvimento ou teste, que inclui pontos de extremidade, servidores, controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-123">Development or test environment which includes endpoints, servers, domain controllers.</span></span>
- <span data-ttu-id="7f4ac-124">Ambiente de produção com o Microsoft 365, Azure, serviços do Active Directory, pontos de extremidade e servidores</span><span class="sxs-lookup"><span data-stu-id="7f4ac-124">Production environment with Microsoft 365, Azure, Active Directory services, endpoints, and servers</span></span>

>[!NOTE]
><span data-ttu-id="7f4ac-125">Se você ainda não tem as licenças completas, pode obter licenças de avaliação para [avaliar o Microsoft 365 defender](https://aka.ms/mtp-trial-lab) – planejar, preparar, configurar, configurar e executar o projeto piloto.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-125">If you don’t have the full licenses yet, you can get trial licenses to [evaluate Microsoft 365 Defender](https://aka.ms/mtp-trial-lab) – plan, prepare, setup, configure, and run your pilot project.</span></span> <span data-ttu-id="7f4ac-126">Suas partes interessadas desempenharão uma grande função para ajudar a facilitar o processo de início ao fim.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-126">Your stakeholders will play a big role in helping facilitate the process from start to finish.</span></span>

<span data-ttu-id="7f4ac-127">Os tipos de sistemas operacionais a serem avaliados também devem ser definidos com base na composição organizacional.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-127">The types of operating systems to be evaluated should also be defined based on the organizational makeup.</span></span> <span data-ttu-id="7f4ac-128">Isso pode incluir o seguinte: [pontos de extremidade Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [servidores Linux](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [pontos de extremidade do windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span><span class="sxs-lookup"><span data-stu-id="7f4ac-128">This may include the following: [Mac endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements), [Linux Servers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements), [Windows 10 endpoints](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions), [Windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions).</span></span>

## <a name="use-cases"></a><span data-ttu-id="7f4ac-129">Casos de uso</span><span class="sxs-lookup"><span data-stu-id="7f4ac-129">Use cases</span></span>

<span data-ttu-id="7f4ac-130">Os casos de uso representam instruções sobre como a ferramenta que está sendo testada deve ser consumida por seus usuários pretendidos.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-130">Use cases represent statements of how the tool being tested is meant to be consumed by its intended users.</span></span> <span data-ttu-id="7f4ac-131">Eles podem ser formulados como histórias de usuários do ponto de vista de uma pessoa específica, como um analista do SOC.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-131">These can be formulated as user stories from the point of view of a particular persona, such as a SOC analyst.</span></span> <span data-ttu-id="7f4ac-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7f4ac-132">For example:</span></span>
- <span data-ttu-id="7f4ac-133">Como analista da SOC, preciso exibir, correlacionar, avaliar e gerenciar alertas e eventos em dispositivos, usuários e caixas de correio em minha rede.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-133">As a SOC analyst, I need to view, correlate, assess and manage alerts and events across devices, users, and mailboxes in my network.</span></span> <span data-ttu-id="7f4ac-134">[Gerenciamento de incidentes]</span><span class="sxs-lookup"><span data-stu-id="7f4ac-134">[Incident management]</span></span>
- <span data-ttu-id="7f4ac-135">Como analista do SOC, eu preciso ter a ferramenta e o processo para investigar e responder automaticamente a eventos mal-intencionados em minha rede.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-135">As a SOC analyst, I must have the tool and process to automatically investigate and respond to malicious events in my network.</span></span> <span data-ttu-id="7f4ac-136">[Infravermelho automático]</span><span class="sxs-lookup"><span data-stu-id="7f4ac-136">[Auto IR]</span></span>
- <span data-ttu-id="7f4ac-137">Como analista do SOC, eu preciso pesquisar dados do meu ambiente para encontrar ameaças conhecidas e potenciais e atividades suspeitas.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-137">As a SOC analyst, I must search data from my environment to find known and potential threats, and suspicious activities.</span></span> <span data-ttu-id="7f4ac-138">[Caça avançada]</span><span class="sxs-lookup"><span data-stu-id="7f4ac-138">[Advanced Hunting]</span></span>

<span data-ttu-id="7f4ac-139">Tenha em mente que esses casos de uso devem ser criados dentro dos parâmetros do escopo definido.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-139">Keep in mind that these use cases should be created within the parameters of the defined scope.</span></span> <span data-ttu-id="7f4ac-140">Se, por exemplo, o escopo de teste não incluir uma avaliação de ferramentas como o Microsoft Cloud app Security, os casos que dependem dele como uma fonte de dados não devem ser criados.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-140">If, for example, the scope of testing does not include an evaluation of tools such as Microsoft Cloud App Security, then use cases that rely on this as a data source should not be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="7f4ac-141">Requirements</span><span class="sxs-lookup"><span data-stu-id="7f4ac-141">Requirements</span></span>

<span data-ttu-id="7f4ac-142">Na lista de casos de uso, você pode começar a criar requisitos.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-142">From the list of use cases, you can start to create requirements.</span></span> <span data-ttu-id="7f4ac-143">Os requisitos incluem recursos que uma ferramenta deve ter para satisfazer os casos de uso.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-143">Requirements include features a tool must have to satisfy the use cases.</span></span> <span data-ttu-id="7f4ac-144">Esses requisitos podem ser divididos em categorias como configuração e manutenção, suporte para integrações e requisitos específicos de recursos, como a capacidade de busca e a capacidade de criar alertas personalizados.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-144">These requirements can be broken down into categories such as configuration and maintenance, support for integrations, and feature-specific requirements like hunting ability and the ability to build custom alerts.</span></span>

## <a name="test-plan"></a><span data-ttu-id="7f4ac-145">Plano de teste</span><span class="sxs-lookup"><span data-stu-id="7f4ac-145">Test plan</span></span>

<span data-ttu-id="7f4ac-146">Dependendo dos requisitos, diferentes métodos de teste podem ser apropriados.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-146">Depending on the requirements, different methods of testing may be appropriate.</span></span> <span data-ttu-id="7f4ac-147">Por exemplo, se o requisito é avaliar a eficácia da correção automatizada, o plano de teste precisa incluir etapas para gerar o (s) comportamento (es) que acionaria uma ação de correção automatizada no Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-147">For instance, if the requirement is to evaluate the efficacy of Automated Remediation, the test plan needs to include steps to generate the behavior(s) that would trigger an automated remediation action within Microsoft 365 Defender.</span></span> <span data-ttu-id="7f4ac-148">Se o requisito for detectar um determinado comportamento ou ataque, o teste poderá envolver mais etapas.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-148">If the requirement is to detect a particular behavior or attack, then the test may involve more steps.</span></span> <span data-ttu-id="7f4ac-149">O ponto é ter um plano para fazer um teste com precisão em relação aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-149">The point is to have a plan in place to accurately test against your requirements.</span></span>

## <a name="success-criteria"></a><span data-ttu-id="7f4ac-150">Critérios de sucesso</span><span class="sxs-lookup"><span data-stu-id="7f4ac-150">Success criteria</span></span>

<span data-ttu-id="7f4ac-151">O critério de sucesso é, basicamente, a barra definida para medir o que você está testando.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-151">Success criteria is ultimately the bar set to measure against what you are testing.</span></span> <span data-ttu-id="7f4ac-152">Se você estiver testando o Microsoft 365 defender (ou qualquer outra tecnologia para esse assunto) em relação a outras ferramentas ou por si só, deve haver alguns critérios quantificáveis para determinar o valor que a ferramenta fornece.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-152">Whether you are testing Microsoft 365 Defender (or any other technology for that matter) against other tools or by itself, there must be some quantifiable criteria to determine the value the tool provides.</span></span> <span data-ttu-id="7f4ac-153">Com base no escopo, nos requisitos e no plano de testes, o critério de sucesso determinará como o teste será pontuado.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-153">Based on the scope, requirements, and testing plan, the success criteria will determine how to score the test.</span></span> <span data-ttu-id="7f4ac-154">Isso deve ser inferior a uma passagem ou falhar e mais de uma pontuação ponderada com base nas suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-154">This should be less of a pass or fail and more of a weighted scoring based on your needs.</span></span> <span data-ttu-id="7f4ac-155">Por exemplo, para ter êxito, uma ferramenta pode precisar de uma pontuação acima de 80% em determinadas áreas críticas que você identificar.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-155">For example, to be successful, a tool may need to score above 80% in certain critical areas you identify.</span></span>

## <a name="scorecard"></a><span data-ttu-id="7f4ac-156">Scorecard</span><span class="sxs-lookup"><span data-stu-id="7f4ac-156">Scorecard</span></span>

<span data-ttu-id="7f4ac-157">Uma maneira de reunir todos os elementos de seu plano pode ser criar um scorecard.</span><span class="sxs-lookup"><span data-stu-id="7f4ac-157">One way to bring all elements of your plan together can be to create a scorecard.</span></span> <span data-ttu-id="7f4ac-158">Veja um exemplo de Scorecard abaixo:</span><span class="sxs-lookup"><span data-stu-id="7f4ac-158">See a sample scorecard below:</span></span>

| <span data-ttu-id="7f4ac-159">Caso de uso</span><span class="sxs-lookup"><span data-stu-id="7f4ac-159">Use case</span></span> | <span data-ttu-id="7f4ac-160">Requirements</span><span class="sxs-lookup"><span data-stu-id="7f4ac-160">Requirements</span></span> | <span data-ttu-id="7f4ac-161">Requisitos de configuração</span><span class="sxs-lookup"><span data-stu-id="7f4ac-161">Configuration requirements</span></span> | <span data-ttu-id="7f4ac-162">Plano de teste</span><span class="sxs-lookup"><span data-stu-id="7f4ac-162">Test plan</span></span> | <span data-ttu-id="7f4ac-163">Resultado esperado</span><span class="sxs-lookup"><span data-stu-id="7f4ac-163">Expected outcome</span></span> | <span data-ttu-id="7f4ac-164">Status do teste</span><span class="sxs-lookup"><span data-stu-id="7f4ac-164">Test status</span></span> | <span data-ttu-id="7f4ac-165">Pontuação</span><span class="sxs-lookup"><span data-stu-id="7f4ac-165">Score</span></span> | <span data-ttu-id="7f4ac-166">Observações</span><span class="sxs-lookup"><span data-stu-id="7f4ac-166">Notes</span></span> |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|<span data-ttu-id="7f4ac-167">Gerenciamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="7f4ac-167">Incident management</span></span>|<span data-ttu-id="7f4ac-168">-Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7f4ac-168">-  Microsoft 365 Defender</span></span>  </br></br><span data-ttu-id="7f4ac-169">– Microsoft defender para identidade</span><span class="sxs-lookup"><span data-stu-id="7f4ac-169">- Microsoft Defender for Identity</span></span> </br></br><span data-ttu-id="7f4ac-170">– Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="7f4ac-170">- Microsoft Defender for Endpoint</span></span> </br></br><span data-ttu-id="7f4ac-171">– Segurança do aplicativo do Microsoft Cloud (opcional)</span><span class="sxs-lookup"><span data-stu-id="7f4ac-171">- Microsoft Cloud App Security (optional)</span></span>|<span data-ttu-id="7f4ac-172">Consulte os [pré-requisitos](https://aka.ms/mtp-trial-lab) para preparação, configuração e configuração para obter detalhes</span><span class="sxs-lookup"><span data-stu-id="7f4ac-172">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> |[<span data-ttu-id="7f4ac-173">Simular ameaças</span><span class="sxs-lookup"><span data-stu-id="7f4ac-173">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="7f4ac-174">Investigue o incidente</span><span class="sxs-lookup"><span data-stu-id="7f4ac-174">Investigate the incident</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |<span data-ttu-id="7f4ac-175">Os investigadores podem entender o escopo e o impacto do incidente e gerenciar o incidente</span><span class="sxs-lookup"><span data-stu-id="7f4ac-175">Investigators can understand the scope and impact of the incident and manage the incident</span></span>||||
|<span data-ttu-id="7f4ac-176">AutoIR</span><span class="sxs-lookup"><span data-stu-id="7f4ac-176">AutoIR</span></span>|<span data-ttu-id="7f4ac-177">-Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7f4ac-177">-   Microsoft 365 Defender</span></span> </br></br><span data-ttu-id="7f4ac-178">– Microsoft defender para identidade</span><span class="sxs-lookup"><span data-stu-id="7f4ac-178">- Microsoft Defender for Identity</span></span> </br></br><span data-ttu-id="7f4ac-179">– Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="7f4ac-179">- Microsoft Defender for Endpoint</span></span> |<span data-ttu-id="7f4ac-180">Consulte os [pré-requisitos](https://aka.ms/mtp-trial-lab) para preparação, configuração e configuração para obter detalhes</span><span class="sxs-lookup"><span data-stu-id="7f4ac-180">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span> <br><span data-ttu-id="7f4ac-181">Habilitar AutoIR</span><span class="sxs-lookup"><span data-stu-id="7f4ac-181">Enable AutoIR</span></span>  |[<span data-ttu-id="7f4ac-182">Simular ameaças</span><span class="sxs-lookup"><span data-stu-id="7f4ac-182">Simulate attack</span></span>](mtp-pilot-simulate.md) <br></br>[<span data-ttu-id="7f4ac-183">Investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="7f4ac-183">Automated investigation</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#automated-investigation-and-remediation) |<span data-ttu-id="7f4ac-184">Alertas e incidentes são corrigidos automaticamente pelo Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7f4ac-184">Alerts and incidents are automatically remediated by Microsoft 365 Defender</span></span>||||
|<span data-ttu-id="7f4ac-185">Busca avançada</span><span class="sxs-lookup"><span data-stu-id="7f4ac-185">Advanced hunting</span></span>|<span data-ttu-id="7f4ac-186">-Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7f4ac-186">- Microsoft 365 Defender</span></span> </br></br><span data-ttu-id="7f4ac-187">– Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="7f4ac-187">- Microsoft Defender for Endpoint</span></span> </br></br><span data-ttu-id="7f4ac-188">– Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7f4ac-188">-Microsoft Defender for Office 365</span></span> |<span data-ttu-id="7f4ac-189">Consulte os [pré-requisitos](https://aka.ms/mtp-trial-lab) para preparação, configuração e configuração para obter detalhes</span><span class="sxs-lookup"><span data-stu-id="7f4ac-189">See the [prerequisites](https://aka.ms/mtp-trial-lab) for preparation, set-up, and configuration for details</span></span>|[<span data-ttu-id="7f4ac-190">Cenário de busca avançada</span><span class="sxs-lookup"><span data-stu-id="7f4ac-190">Advanced hunting scenario</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate.md#advanced-hunting-scenario) |<span data-ttu-id="7f4ac-191">Os investigadores podem localizar dados por meio de busca avançada, dinamização para entidades impactadas e criação de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="7f4ac-191">Investigators can find data through advanced hunting, pivoting to impacted entities, and by creating custom detections</span></span>||||



## <a name="next-step"></a><span data-ttu-id="7f4ac-192">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7f4ac-192">Next step</span></span>
|<span data-ttu-id="7f4ac-193">![Fase de preparação](../../media/mtp/prep.png)</span><span class="sxs-lookup"><span data-stu-id="7f4ac-193">![Preparation phase](../../media/mtp/prep.png)</span></span> <br>[<span data-ttu-id="7f4ac-194">Fase de preparação</span><span class="sxs-lookup"><span data-stu-id="7f4ac-194">Preparation phase</span></span>](prepare-mtpeval.md) | <span data-ttu-id="7f4ac-195">Prepare seu ambiente piloto do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="7f4ac-195">Prepare your Microsoft 365 Defender pilot environment</span></span>
|:-------|:-----|
