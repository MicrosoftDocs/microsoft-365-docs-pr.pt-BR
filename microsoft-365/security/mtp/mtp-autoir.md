---
title: Investigação e resposta automatizadas no Microsoft 365 Defender
description: Obter uma visão geral dos recursos automatizados de investigação e resposta, também chamados de autorreeração, no Microsoft 365 Defender
keywords: automatizado, investigação, alerta, gatilho, ação, correção, autorreeração
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930325"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="6968a-104">Investigação e resposta automatizadas no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6968a-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6968a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6968a-105">**Applies to:**</span></span>
- <span data-ttu-id="6968a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6968a-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="6968a-107">Deseja experimentar o Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="6968a-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="6968a-108">Você pode [avaliá-lo em um ambiente de laboratório](https://aka.ms/mtp-trial-lab) ou executar seu projeto piloto em [produção.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="6968a-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

## <a name="how-automated-investigation-and-self-healing-works"></a><span data-ttu-id="6968a-109">Como funciona a investigação automatizada e a autorrecumentação</span><span class="sxs-lookup"><span data-stu-id="6968a-109">How automated investigation and self-healing works</span></span>

<span data-ttu-id="6968a-110">À medida que os alertas de segurança são disparados, fica a sua equipe de operações de segurança procurar esses alertas e tomar medidas para proteger sua organização.</span><span class="sxs-lookup"><span data-stu-id="6968a-110">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="6968a-111">Priorizar e investigar alertas pode consumir muito tempo, especialmente quando novos alertas continuam chegando enquanto uma investigação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="6968a-111">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="6968a-112">As equipes de operações de segurança podem se sentir sobrecarregadas pelo simples volume de ameaças que devem ser monitoradas e protegidas.</span><span class="sxs-lookup"><span data-stu-id="6968a-112">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="6968a-113">Os recursos automatizados de investigação e resposta, com auto-recuperação, no Microsoft 365 Defender podem ajudar.</span><span class="sxs-lookup"><span data-stu-id="6968a-113">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="6968a-114">Assista ao vídeo a seguir para ver como funciona a autorrerecução:</span><span class="sxs-lookup"><span data-stu-id="6968a-114">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="6968a-115">No Microsoft 365 Defender, a investigação e resposta automatizadas com recursos de auto-recuperação funcionam em seus dispositivos, emails & conteúdo e identidades.</span><span class="sxs-lookup"><span data-stu-id="6968a-115">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span>
 
> [!TIP]
> <span data-ttu-id="6968a-116">Este artigo descreve como funciona a investigação e resposta automatizadas.</span><span class="sxs-lookup"><span data-stu-id="6968a-116">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="6968a-117">Para configurar esses recursos, consulte Configurar recursos automatizados de investigação [e resposta no Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="6968a-117">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-own-virtual-analyst"></a><span data-ttu-id="6968a-118">Seu próprio analista virtual</span><span class="sxs-lookup"><span data-stu-id="6968a-118">Your own virtual analyst</span></span>

<span data-ttu-id="6968a-119">Imagine ter um analista virtual em sua equipe de operações de segurança do Nível 1 / Nível 2.</span><span class="sxs-lookup"><span data-stu-id="6968a-119">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="6968a-120">O analista virtual imita as etapas ideais que as operações de segurança poderiam executar para investigar e corrigir ameaças.</span><span class="sxs-lookup"><span data-stu-id="6968a-120">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="6968a-121">O assistente virtual pode funcionar 24 horas e assumir uma carga significativa de investigações e correções de ameaças.</span><span class="sxs-lookup"><span data-stu-id="6968a-121">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="6968a-122">Esse assistente virtual pode reduzir significativamente o tempo de resposta, liberando sua equipe de operações de segurança para outros projetos estratégicos importantes.</span><span class="sxs-lookup"><span data-stu-id="6968a-122">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="6968a-123">Se esse cenário parece uma história de ciência, não é!</span><span class="sxs-lookup"><span data-stu-id="6968a-123">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="6968a-124">Esse analista virtual faz parte do seu pacote do Microsoft 365 Defender e seu nome é uma investigação e resposta *automatizadas.*</span><span class="sxs-lookup"><span data-stu-id="6968a-124">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="6968a-125">A investigação e resposta automatizadas permitem que sua equipe de operações de segurança aumente drasticamente a capacidade da sua organização de lidar com alertas e incidentes de segurança.</span><span class="sxs-lookup"><span data-stu-id="6968a-125">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="6968a-126">Com a investigação e a resposta automatizadas, você pode reduzir o custo de lidar com atividades de investigação e correção e obter o máximo de seu pacote de proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="6968a-126">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="6968a-127">a investigação e resposta automatizadas ajudam sua equipe de operações de segurança ao:</span><span class="sxs-lookup"><span data-stu-id="6968a-127">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="6968a-128">Determinar se uma ameaça requer ação;</span><span class="sxs-lookup"><span data-stu-id="6968a-128">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="6968a-129">Executar (ou recomendar) todas as ações de correção necessárias;</span><span class="sxs-lookup"><span data-stu-id="6968a-129">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="6968a-130">Determinar quais investigações adicionais devem ocorrer; e</span><span class="sxs-lookup"><span data-stu-id="6968a-130">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="6968a-131">Repetir o processo conforme necessário para outros alertas.</span><span class="sxs-lookup"><span data-stu-id="6968a-131">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="6968a-132">O processo de investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="6968a-132">The automated investigation process</span></span>

<span data-ttu-id="6968a-133">**Alerta** > **incidente** > **investigação automatizada** > **veredito** > **ação de correção**</span><span class="sxs-lookup"><span data-stu-id="6968a-133">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="6968a-134">Um alerta disparado cria um incidente, que pode iniciar uma investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="6968a-134">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="6968a-135">Essa investigação pode resultar em uma ou mais ações de correção.</span><span class="sxs-lookup"><span data-stu-id="6968a-135">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="6968a-136">No Microsoft 365 Defender, cada investigação automatizada correlaciona sinais no Microsoft Defender for Identity, no Microsoft Defender for Endpoint e no Defender para Office 365, conforme resumido na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="6968a-136">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="6968a-137">Entidades</span><span class="sxs-lookup"><span data-stu-id="6968a-137">Entities</span></span> |<span data-ttu-id="6968a-138">Serviços de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="6968a-138">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="6968a-139">Dispositivos (também chamados de pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="6968a-139">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="6968a-140">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6968a-140">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="6968a-141">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="6968a-141">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="6968a-142">Conteúdo de email (arquivos e mensagens nas caixas de correio)</span><span class="sxs-lookup"><span data-stu-id="6968a-142">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="6968a-143">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6968a-143">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="6968a-144">Cada investigação gera vereditos (*mal-intencionados*, *suspeitos* ou nenhuma ameaça *encontrada*) para cada evidência investigada.</span><span class="sxs-lookup"><span data-stu-id="6968a-144">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *No threats found*) for each piece of evidence investigated.</span></span> <span data-ttu-id="6968a-145">Dependendo do tipo de ameaça e veredito resultante, as ações de correção ocorrem automaticamente ou mediante aprovação da equipe de operações de segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6968a-145">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="6968a-146">As ações pendentes e concluídas estão listadas na [Central de ações](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="6968a-146">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="6968a-147">Enquanto uma investigação está em execução, quaisquer outros alertas relacionados que surgirem são adicionados à investigação até que ela seja concluída.</span><span class="sxs-lookup"><span data-stu-id="6968a-147">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="6968a-148">Se uma entidade incriminada for vista em outro lugar, a investigação automatizada expandirá seu escopo para incluir essa entidade, e um manual geral de segurança será executado.</span><span class="sxs-lookup"><span data-stu-id="6968a-148">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="6968a-149">Nem todos os alertas acionam uma investigação automatizada, e nem todas as investigações resulta em ações de correção automatizadas; tudo isso depende de como a investigação e resposta automatizadas são configuradas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6968a-149">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="6968a-150">Consulte [Configurar recursos automatizados de investigação e resposta no Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="6968a-150">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="6968a-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="6968a-151">Next steps</span></span>

- [<span data-ttu-id="6968a-152">Confira os pré-requisitos para investigação e resposta automatizadas no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6968a-152">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="6968a-153">Configurar investigação e resposta automatizadas para sua organização</span><span class="sxs-lookup"><span data-stu-id="6968a-153">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="6968a-154">Saiba mais sobre a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="6968a-154">Learn more about the Action center</span></span>](mtp-action-center.md)
