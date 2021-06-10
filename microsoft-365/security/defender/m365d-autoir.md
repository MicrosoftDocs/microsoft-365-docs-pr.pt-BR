---
title: Investigação e resposta automatizadas no Microsoft 365 Defender
description: Obter uma visão geral dos recursos automatizados de investigação e resposta, também chamados de auto-recuperação, Microsoft 365 Defender
keywords: automated, investigation, alert, trigger, action, remediation, self-healing
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 976a79be98efcbb5d7fd3749ddb0cdb282b1e3e3
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274563"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="3b6f6-104">Investigação e resposta automatizadas no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b6f6-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3b6f6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3b6f6-105">**Applies to:**</span></span>
- <span data-ttu-id="3b6f6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b6f6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3b6f6-107">Se sua organização estiver usando [o Microsoft 365 Defender](microsoft-365-defender.md), sua equipe de operações de segurança receberá um alerta dentro do centro de segurança Microsoft 365 sempre que uma atividade ou artefato mal-intencionado ou suspeito for detectado.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-107">If your organization is using [Microsoft 365 Defender](microsoft-365-defender.md), your security operations team receives an alert within the Microsoft 365 security center whenever a malicious or suspicious activity or artifact is detected.</span></span> <span data-ttu-id="3b6f6-108">Devido ao fluxo aparentemente interminável de ameaças que podem entrar, as equipes de segurança geralmente enfrentam o desafio de lidar com o alto volume de alertas.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-108">Given the seemingly never-ending flow of threats that can come in, security teams often face the challenge of addressing the high volume of alerts.</span></span> <span data-ttu-id="3b6f6-109">Felizmente, o Microsoft 365 Defender inclui recursos automatizados de investigação e resposta (AIR) que podem ajudar sua equipe de operações de segurança a lidar com ameaças de forma mais eficiente e eficaz.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-109">Fortunately, Microsoft 365 Defender includes automated investigation and response (AIR) capabilities that can help your security operations team address threats more efficiently and effectively.</span></span>

<span data-ttu-id="3b6f6-110">Este artigo fornece uma visão geral do AIR e inclui links para as próximas etapas e recursos adicionais.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-110">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="3b6f6-111">Quer experimentar o Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="3b6f6-111">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="3b6f6-112">Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="3b6f6-112">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="3b6f6-113">Como funciona a investigação automatizada e a auto-recuperação</span><span class="sxs-lookup"><span data-stu-id="3b6f6-113">How automated investigation and self-healing works</span></span>

<span data-ttu-id="3b6f6-114">À medida que os alertas de segurança são disparados, a equipe de operações de segurança deve procurar esses alertas e tomar medidas para proteger sua organização.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-114">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="3b6f6-115">Priorizar e investigar alertas pode consumir muito tempo, especialmente quando novos alertas continuam chegando enquanto uma investigação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-115">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="3b6f6-116">As equipes de operações de segurança podem se sentir sobrecarregadas pelo simples volume de ameaças que devem ser monitoradas e protegidas.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-116">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="3b6f6-117">Recursos automatizados de investigação e resposta, com auto-recuperação, Microsoft 365 o Defender pode ajudar.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-117">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="3b6f6-118">Assista ao vídeo a seguir para ver como funciona a auto-recuperação:</span><span class="sxs-lookup"><span data-stu-id="3b6f6-118">Watch the following video to see how self-healing works:</span></span> <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="3b6f6-119">No Microsoft 365 Defender, a investigação e a resposta automatizadas com recursos de auto-recuperação funcionam em seus dispositivos, emails & conteúdo e identidades.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-119">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="3b6f6-120">Este artigo descreve como funciona a investigação e a resposta automatizadas.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-120">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="3b6f6-121">Para configurar esses recursos, consulte [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="3b6f6-121">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="3b6f6-122">Seu próprio analista virtual</span><span class="sxs-lookup"><span data-stu-id="3b6f6-122">Your own virtual analyst</span></span>

<span data-ttu-id="3b6f6-123">Imagine ter um analista virtual em sua equipe de operações de segurança de Camada 1 ou Camada 2.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-123">Imagine having a virtual analyst in your Tier 1 or Tier 2 security operations team.</span></span> <span data-ttu-id="3b6f6-124">O analista virtual imita as etapas ideais que as operações de segurança poderiam executar para investigar e corrigir ameaças.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-124">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="3b6f6-125">O analista virtual poderia trabalhar 24x7, com capacidade ilimitada, e assumir uma carga significativa de investigações e correção de ameaças.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-125">The virtual analyst could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="3b6f6-126">Esse analista virtual poderia reduzir significativamente o tempo de resposta, liberando sua equipe de operações de segurança para outras ameaças importantes ou projetos estratégicos.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-126">Such a virtual analyst could significantly reduce the time to respond, freeing up your security operations team for other important threats or strategic projects.</span></span> <span data-ttu-id="3b6f6-127">Se esse cenário parece com a ficção científica, não é!</span><span class="sxs-lookup"><span data-stu-id="3b6f6-127">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="3b6f6-128">Esse analista virtual faz parte do seu pacote Microsoft 365 Defender, e seu nome é investigação e resposta *automatizadas.*</span><span class="sxs-lookup"><span data-stu-id="3b6f6-128">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="3b6f6-129">Os recursos automatizados de investigação e resposta permitem que sua equipe de operações de segurança aumente drasticamente a capacidade da sua organização de lidar com alertas e incidentes de segurança.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-129">Automated investigation and response capabilities enable your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="3b6f6-130">Com a investigação e a resposta automatizadas, você pode reduzir o custo de lidar com atividades de investigação e resposta e obter o máximo de seu pacote de proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-130">With automated investigation and response, you can reduce the cost of dealing with investigation and response activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="3b6f6-131">Os recursos automatizados de investigação e resposta ajudam sua equipe de operações de segurança:</span><span class="sxs-lookup"><span data-stu-id="3b6f6-131">Automated investigation and response capabilities help your security operations team by:</span></span>

1. <span data-ttu-id="3b6f6-132">Determinando se uma ameaça requer ação.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-132">Determining whether a threat requires action.</span></span>
2. <span data-ttu-id="3b6f6-133">Tomar (ou recomendar) quaisquer ações de correção necessárias.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-133">Taking (or recommending) any necessary remediation actions.</span></span>
3. <span data-ttu-id="3b6f6-134">Determinando se e quais outras investigações devem ocorrer.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-134">Determining whether and what other investigations should occur.</span></span>
4. <span data-ttu-id="3b6f6-135">Repetir o processo conforme necessário para outros alertas.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-135">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="3b6f6-136">O processo de investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="3b6f6-136">The automated investigation process</span></span>

<span data-ttu-id="3b6f6-137">Um alerta cria um incidente, que pode iniciar uma investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-137">An alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="3b6f6-138">A investigação automatizada resulta em um veredito para cada prova.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-138">The automated investigation results in a verdict for each piece of evidence.</span></span> <span data-ttu-id="3b6f6-139">Os vereditos podem ser:</span><span class="sxs-lookup"><span data-stu-id="3b6f6-139">Verdicts can be:</span></span>
- <span data-ttu-id="3b6f6-140">*Mal-intencionado*</span><span class="sxs-lookup"><span data-stu-id="3b6f6-140">*Malicious*</span></span>
- <span data-ttu-id="3b6f6-141">*Suspeito*</span><span class="sxs-lookup"><span data-stu-id="3b6f6-141">*Suspicious*</span></span> 
- <span data-ttu-id="3b6f6-142">*Nenhuma ameaça encontrada*</span><span class="sxs-lookup"><span data-stu-id="3b6f6-142">*No threats found*</span></span> 

<span data-ttu-id="3b6f6-143">Ações de correção para entidades mal-intencionadas ou suspeitas são identificadas.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-143">Remediation actions for malicious or suspicious entities are identified.</span></span> <span data-ttu-id="3b6f6-144">Exemplos de ações de correção incluem:</span><span class="sxs-lookup"><span data-stu-id="3b6f6-144">Examples of remediation actions include:</span></span>

- <span data-ttu-id="3b6f6-145">Enviando um arquivo para quarentena</span><span class="sxs-lookup"><span data-stu-id="3b6f6-145">Sending a file to quarantine</span></span>
- <span data-ttu-id="3b6f6-146">Interromper um processo</span><span class="sxs-lookup"><span data-stu-id="3b6f6-146">Stopping a process</span></span>
- <span data-ttu-id="3b6f6-147">Isolando um dispositivo</span><span class="sxs-lookup"><span data-stu-id="3b6f6-147">Isolating a device</span></span>
- <span data-ttu-id="3b6f6-148">Bloqueando uma URL</span><span class="sxs-lookup"><span data-stu-id="3b6f6-148">Blocking a URL</span></span> 
- <span data-ttu-id="3b6f6-149">Outras ações</span><span class="sxs-lookup"><span data-stu-id="3b6f6-149">Other actions</span></span>

<span data-ttu-id="3b6f6-150">Para obter mais informações, consulte [Ações de correção no Microsoft 365 Defender](m365d-remediation-actions.md).</span><span class="sxs-lookup"><span data-stu-id="3b6f6-150">For more information, see See [Remediation actions in Microsoft 365 Defender](m365d-remediation-actions.md).</span></span>

<span data-ttu-id="3b6f6-151">Dependendo de como [os](m365d-configure-auto-investigation-response.md) recursos automatizados de investigação e resposta são configurados para sua organização, as ações de correção são tomadas automaticamente ou somente após a aprovação pela sua equipe de operações de segurança.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-151">Depending on [how automated investigation and response capabilities are configured](m365d-configure-auto-investigation-response.md) for your organization, remediation actions are taken automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="3b6f6-152">Todas as ações, pendentes ou concluídas, estão listadas no [Centro de Ações](m365d-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="3b6f6-152">All actions, whether pending or completed, are listed in the [Action center](m365d-action-center.md).</span></span>

<span data-ttu-id="3b6f6-153">Enquanto uma investigação está em execução, quaisquer outros alertas relacionados que surgirem são adicionados à investigação até que ela seja concluída.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-153">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="3b6f6-154">Se uma entidade afetada for vista em outro lugar, a investigação automatizada expandirá seu escopo para incluir essa entidade e o processo de investigação se repetirá.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-154">If an affected entity is seen elsewhere, the automated investigation expands its scope to include that entity, and the investigation process repeats.</span></span> 

<span data-ttu-id="3b6f6-155">No Microsoft 365 Defender, cada investigação automatizada correlaciona sinais no Microsoft Defender for Identity, no Microsoft Defender para Ponto de Extremidade e no Microsoft Defender para Office 365, conforme resumido na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="3b6f6-155">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="3b6f6-156">Entidades</span><span class="sxs-lookup"><span data-stu-id="3b6f6-156">Entities</span></span> |<span data-ttu-id="3b6f6-157">Serviços de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="3b6f6-157">Threat protection services</span></span>  |
|:---------|:---------|
|<span data-ttu-id="3b6f6-158">Dispositivos (também chamados de pontos de extremidade ou máquinas)</span><span class="sxs-lookup"><span data-stu-id="3b6f6-158">Devices (also referred to as endpoints or machines)</span></span> |[<span data-ttu-id="3b6f6-159">Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3b6f6-159">Defender for Endpoint</span></span>](../defender-endpoint/automated-investigations.md) |      
|<span data-ttu-id="3b6f6-160">Usuários locais do Active Directory, comportamento da entidade e atividades</span><span class="sxs-lookup"><span data-stu-id="3b6f6-160">On-premises Active Directory users, entity behavior, and activities</span></span>     |[<span data-ttu-id="3b6f6-161">Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="3b6f6-161">Defender for Identity</span></span>](/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="3b6f6-162">Conteúdo de email (mensagens de email que podem conter arquivos e URLs)</span><span class="sxs-lookup"><span data-stu-id="3b6f6-162">Email content (email messages that can contain files and URLs)</span></span>     |[<span data-ttu-id="3b6f6-163">Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3b6f6-163">Defender for Office 365</span></span>](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> <span data-ttu-id="3b6f6-164">Nem todos os alertas disparam uma investigação automatizada, e nem todas as investigações resulta em ações de correção automatizadas.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-164">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions.</span></span> <span data-ttu-id="3b6f6-165">Depende de como a investigação e a resposta automatizadas são configuradas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3b6f6-165">It depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="3b6f6-166">Consulte [Configurar recursos automatizados de investigação e resposta.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="3b6f6-166">See [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).</span></span>

## <a name="viewing-a-list-of-investigations"></a><span data-ttu-id="3b6f6-167">Exibindo uma lista de investigações</span><span class="sxs-lookup"><span data-stu-id="3b6f6-167">Viewing a list of investigations</span></span>

<span data-ttu-id="3b6f6-168">Para exibir investigações, vá para a **página Incidentes.**</span><span class="sxs-lookup"><span data-stu-id="3b6f6-168">To view investigations, go to the **Incidents** page.</span></span> <span data-ttu-id="3b6f6-169">Selecione um incidente e selecione a guia **Investigações.** Para saber mais, confira [Detalhes e resultados de uma investigação automatizada.](m365d-autoir-results.md)</span><span class="sxs-lookup"><span data-stu-id="3b6f6-169">Select an incident, and then select the **Investigations** tab. To learn more, see [Details and results of an automated investigation](m365d-autoir-results.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="3b6f6-170">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3b6f6-170">Next steps</span></span>

- [<span data-ttu-id="3b6f6-171">Consulte os pré-requisitos para investigação e resposta automatizadas</span><span class="sxs-lookup"><span data-stu-id="3b6f6-171">See the prerequisites for automated investigation and response</span></span>](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="3b6f6-172">Configurar investigação e resposta automatizadas para sua organização</span><span class="sxs-lookup"><span data-stu-id="3b6f6-172">Configure automated investigation and response for your organization</span></span>](m365d-configure-auto-investigation-response.md)
- [<span data-ttu-id="3b6f6-173">Saiba mais sobre a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="3b6f6-173">Learn more about the Action center</span></span>](m365d-action-center.md)
