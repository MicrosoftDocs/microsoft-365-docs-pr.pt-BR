---
title: Investigação e resposta automatizadas no Microsoft 365 defender
description: Obtenha uma visão geral dos recursos de investigação e resposta automatizados, também chamados de auto-recuperação, no Microsoft 365 defender
keywords: automatizado, investigação, alerta, gatilho, ação, correção, auto-recuperação
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: d17bd49206bcdef9f60a4873c642179165753887
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843679"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a><span data-ttu-id="76ca6-104">Investigação e resposta automatizadas no Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="76ca6-104">Automated investigation and response in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="76ca6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="76ca6-105">**Applies to:**</span></span>
- <span data-ttu-id="76ca6-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="76ca6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="76ca6-107">Como os alertas de segurança são disparados, a equipe de operações de segurança pode examinar os alertas e realizar etapas para proteger sua organização.</span><span class="sxs-lookup"><span data-stu-id="76ca6-107">As security alerts are triggered, it's up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="76ca6-108">Priorizar e investigar alertas pode consumir muito tempo, especialmente quando novos alertas continuam chegando enquanto uma investigação está em andamento.</span><span class="sxs-lookup"><span data-stu-id="76ca6-108">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="76ca6-109">As equipes de operações de segurança podem se sentir sobrecarregadas pelo simples volume de ameaças que devem ser monitoradas e protegidas.</span><span class="sxs-lookup"><span data-stu-id="76ca6-109">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> <span data-ttu-id="76ca6-110">Os recursos de investigação e resposta automatizados, com auto-recuperação, no Microsoft 365 defender podem ajudar.</span><span class="sxs-lookup"><span data-stu-id="76ca6-110">Automated investigation and response capabilities, with self-healing, in Microsoft 365 Defender can help.</span></span>

<span data-ttu-id="76ca6-111">Assista ao vídeo a seguir para ver como a auto-recuperação funciona:</span><span class="sxs-lookup"><span data-stu-id="76ca6-111">Watch the following video to see how self-healing works:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

<span data-ttu-id="76ca6-112">No Microsoft 365 defender, a investigação e a resposta automatizadas com recursos de auto-recuperação funcionam em seus dispositivos, email & conteúdo e identidades.</span><span class="sxs-lookup"><span data-stu-id="76ca6-112">In Microsoft 365 Defender, automated investigation and response with self-healing capabilities works across your devices, email & content, and identities.</span></span> <span data-ttu-id="76ca6-113">O Microsoft 365 defender reúne recursos de:</span><span class="sxs-lookup"><span data-stu-id="76ca6-113">Microsoft 365 Defender brings together capabilities from:</span></span> 
- [<span data-ttu-id="76ca6-114">Investigação e correção automatizadas no Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="76ca6-114">Automated investigation and remediation in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [<span data-ttu-id="76ca6-115">Investigação e resposta automatizadas no Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="76ca6-115">Automated investigation and response in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [<span data-ttu-id="76ca6-116">Detecção avançada de ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="76ca6-116">Azure advanced threat detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [<span data-ttu-id="76ca6-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="76ca6-117">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
<span data-ttu-id="76ca6-118">Este artigo descreve como funciona a investigação e a resposta automatizadas.</span><span class="sxs-lookup"><span data-stu-id="76ca6-118">This article describes how automated investigation and response works.</span></span> <span data-ttu-id="76ca6-119">Para configurar esses recursos, consulte [Configure Automated Investigation and Response Capabilities in Microsoft 365 defender](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="76ca6-119">To configure these capabilities, see [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>

## <a name="your-virtual-analyst"></a><span data-ttu-id="76ca6-120">Seu analista virtual</span><span class="sxs-lookup"><span data-stu-id="76ca6-120">Your virtual analyst</span></span>

<span data-ttu-id="76ca6-121">Imagine ter um analista virtual em sua equipe de operações de segurança do Nível 1 / Nível 2.</span><span class="sxs-lookup"><span data-stu-id="76ca6-121">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="76ca6-122">O analista virtual imita as etapas ideais que as operações de segurança poderiam executar para investigar e corrigir ameaças.</span><span class="sxs-lookup"><span data-stu-id="76ca6-122">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="76ca6-123">O assistente virtual pode funcionar 24 horas e assumir uma carga significativa de investigações e correções de ameaças.</span><span class="sxs-lookup"><span data-stu-id="76ca6-123">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="76ca6-124">Esse assistente virtual pode reduzir significativamente o tempo de resposta, liberando sua equipe de operações de segurança para outros projetos estratégicos importantes.</span><span class="sxs-lookup"><span data-stu-id="76ca6-124">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="76ca6-125">Se este cenário soa como ficção científica, não é!</span><span class="sxs-lookup"><span data-stu-id="76ca6-125">If this scenario sounds like science fiction, it's not!</span></span> <span data-ttu-id="76ca6-126">Esse analista virtual faz parte do seu pacote Microsoft 365 defender, e seu nome é *investigação e resposta automatizadas*.</span><span class="sxs-lookup"><span data-stu-id="76ca6-126">Such a virtual analyst is part of your Microsoft 365 Defender suite, and its name is *automated investigation and response*.</span></span>

<span data-ttu-id="76ca6-127">A investigação e a resposta automatizadas permitem que a equipe de operações de segurança aumente drasticamente a capacidade da sua organização para lidar com incidentes e alertas de segurança.</span><span class="sxs-lookup"><span data-stu-id="76ca6-127">Automated investigation and response enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="76ca6-128">Com a investigação e a resposta automatizadas, você pode reduzir o custo de lidar com as atividades de investigação e correção e obter o máximo do seu pacote de proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="76ca6-128">With automated investigation and response, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="76ca6-129">a investigação e a resposta automatizadas ajudam a equipe de operações de segurança:</span><span class="sxs-lookup"><span data-stu-id="76ca6-129">automated investigation and response helps your security operations team by:</span></span>

1. <span data-ttu-id="76ca6-130">Determinar se uma ameaça requer ação;</span><span class="sxs-lookup"><span data-stu-id="76ca6-130">Determining whether a threat requires action;</span></span>
2. <span data-ttu-id="76ca6-131">Executar (ou recomendar) todas as ações de correção necessárias;</span><span class="sxs-lookup"><span data-stu-id="76ca6-131">Performing (or recommending) any necessary remediation actions;</span></span>
3. <span data-ttu-id="76ca6-132">Determinar quais investigações adicionais devem ocorrer; e</span><span class="sxs-lookup"><span data-stu-id="76ca6-132">Determining what additional investigations should occur; and</span></span>
4. <span data-ttu-id="76ca6-133">Repetir o processo conforme necessário para outros alertas.</span><span class="sxs-lookup"><span data-stu-id="76ca6-133">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="76ca6-134">O processo de investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="76ca6-134">The automated investigation process</span></span>

<span data-ttu-id="76ca6-135">**Alerta** > **incidente** > **investigação automatizada** > **veredito** > **ação de correção**</span><span class="sxs-lookup"><span data-stu-id="76ca6-135">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="76ca6-136">Um alerta disparado cria um incidente, que pode iniciar uma investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="76ca6-136">A triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="76ca6-137">Essa investigação pode resultar em uma ou mais ações de correção.</span><span class="sxs-lookup"><span data-stu-id="76ca6-137">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="76ca6-138">No Microsoft 365 defender, cada investigação automatizada correlaciona sinais no Microsoft defender para identidade, Microsoft defender para ponto de extremidade e defender para Office 365, conforme resumido na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="76ca6-138">In Microsoft 365 Defender, each automated investigation correlates signals across Microsoft Defender for Identity, Microsoft Defender for Endpoint, and Defender for Office 365, as summarized in the following table:</span></span> 

|<span data-ttu-id="76ca6-139">Entidades</span><span class="sxs-lookup"><span data-stu-id="76ca6-139">Entities</span></span> |<span data-ttu-id="76ca6-140">Serviços de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="76ca6-140">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="76ca6-141">Dispositivos (também chamados de pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="76ca6-141">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="76ca6-142">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="76ca6-142">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="76ca6-143">Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="76ca6-143">Microsoft Defender for Identity</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="76ca6-144">Conteúdo de email (arquivos e mensagens nas caixas de correio)</span><span class="sxs-lookup"><span data-stu-id="76ca6-144">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="76ca6-145">Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="76ca6-145">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

<span data-ttu-id="76ca6-146">Cada investigação gera verdicts ( *mal-intencionado* , *suspeito* ou *nenhuma ameaça encontrada* ) para cada evidência investigada.</span><span class="sxs-lookup"><span data-stu-id="76ca6-146">Each investigation generates verdicts ( *Malicious* , *Suspicious* , or *No threats found* ) for each piece of evidence investigated.</span></span> <span data-ttu-id="76ca6-147">Dependendo do tipo de ameaça e veredicto resultante, as ações de correção ocorrerão automaticamente ou após a aprovação da equipe de operações de segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="76ca6-147">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization's security operations team.</span></span> <span data-ttu-id="76ca6-148">As ações pendentes e concluídas estão listadas na [Central de ações](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="76ca6-148">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="76ca6-149">Enquanto uma investigação está em execução, quaisquer outros alertas relacionados que surgirem são adicionados à investigação até que ela seja concluída.</span><span class="sxs-lookup"><span data-stu-id="76ca6-149">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="76ca6-150">Se uma entidade incriminada for vista em outro lugar, a investigação automatizada expandirá seu escopo para incluir essa entidade, e um manual geral de segurança será executado.</span><span class="sxs-lookup"><span data-stu-id="76ca6-150">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="76ca6-151">Nem todos os alertas disparam uma investigação automatizada, e nem todas as investigações resultam em ações de correção automatizadas; Isso depende de como a investigação e a resposta automáticas são configuradas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="76ca6-151">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how automated investigation and response is configured for your organization.</span></span> <span data-ttu-id="76ca6-152">Consulte [Configure Automated Investigation and Response Capabilities in Microsoft 365 defender](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="76ca6-152">See [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="76ca6-153">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="76ca6-153">Next steps</span></span>

- [<span data-ttu-id="76ca6-154">Consulte os pré-requisitos para investigação e resposta automatizadas no Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="76ca6-154">See the prerequisites for automated investigation and response in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [<span data-ttu-id="76ca6-155">Configurar investigação e resposta automatizadas para sua organização</span><span class="sxs-lookup"><span data-stu-id="76ca6-155">Configure automated investigation and response for your organization</span></span>](mtp-configure-auto-investigation-response.md)
- [<span data-ttu-id="76ca6-156">Saiba mais sobre a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="76ca6-156">Learn more about the Action center</span></span>](mtp-action-center.md)
