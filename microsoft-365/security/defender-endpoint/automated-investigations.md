---
title: Usar investigações automatizadas para investigar e remediar ameaças
description: Entenda o fluxo de investigação automatizado no Microsoft Defender para Ponto de Extremidade.
keywords: automatizado, investigação, detecção, defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: d2effb44c145a4fbf1006446685dbcd703754e6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166204"
---
# <a name="overview-of-automated-investigations"></a><span data-ttu-id="8e9be-104">Visão geral das investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="8e9be-104">Overview of automated investigations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8e9be-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8e9be-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e9be-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8e9be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8e9be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e9be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="8e9be-108">Quer ver como funciona?</span><span class="sxs-lookup"><span data-stu-id="8e9be-108">Want to see how it works?</span></span> <span data-ttu-id="8e9be-109">Assista ao seguinte vídeo:</span><span class="sxs-lookup"><span data-stu-id="8e9be-109">Watch the following video:</span></span> <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

<span data-ttu-id="8e9be-110">A tecnologia na investigação automatizada usa vários algoritmos de inspeção e se baseia em processos usados por analistas de segurança.</span><span class="sxs-lookup"><span data-stu-id="8e9be-110">The technology in automated investigation uses various inspection algorithms and is based on processes that are used by security analysts.</span></span> <span data-ttu-id="8e9be-111">Os recursos AIR foram projetados para examinar alertas e tomar medidas imediatas para resolver violações.</span><span class="sxs-lookup"><span data-stu-id="8e9be-111">AIR capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="8e9be-112">Os recursos air reduzem significativamente o volume de alerta, permitindo que as operações de segurança se concentrem em ameaças mais sofisticadas e em outras iniciativas de alto valor.</span><span class="sxs-lookup"><span data-stu-id="8e9be-112">AIR capabilities significantly reduce alert volume, allowing security operations to focus on more sophisticated threats and other high-value initiatives.</span></span> <span data-ttu-id="8e9be-113">Todas as ações de correção, pendentes ou concluídas, são controladas no [Centro de Ações](auto-investigation-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="8e9be-113">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="8e9be-114">No Centro de ações, as ações pendentes são aprovadas (ou rejeitadas) e as ações concluídas podem ser desfeitas, se necessário.</span><span class="sxs-lookup"><span data-stu-id="8e9be-114">In the Action center, pending actions are approved (or rejected), and completed actions can be undone if needed.</span></span>

<span data-ttu-id="8e9be-115">Este artigo fornece uma visão geral do AIR e inclui links para as próximas etapas e recursos adicionais.</span><span class="sxs-lookup"><span data-stu-id="8e9be-115">This article provides an overview of AIR and includes links to next steps and additional resources.</span></span>

> [!TIP]
> <span data-ttu-id="8e9be-116">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8e9be-116">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="8e9be-117">[Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="8e9be-117">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).</span></span>

## <a name="how-the-automated-investigation-starts"></a><span data-ttu-id="8e9be-118">Como a investigação automatizada é iniciada</span><span class="sxs-lookup"><span data-stu-id="8e9be-118">How the automated investigation starts</span></span>

<span data-ttu-id="8e9be-119">Uma investigação automatizada pode começar quando um alerta é disparado ou quando um operador de segurança inicia a investigação.</span><span class="sxs-lookup"><span data-stu-id="8e9be-119">An automated investigation can start when an alert is triggered or when a security operator initiates the investigation.</span></span>

|<span data-ttu-id="8e9be-120">Situação</span><span class="sxs-lookup"><span data-stu-id="8e9be-120">Situation</span></span>  |<span data-ttu-id="8e9be-121">O que acontece</span><span class="sxs-lookup"><span data-stu-id="8e9be-121">What happens</span></span>  |
|---------|---------|
|<span data-ttu-id="8e9be-122">Um alerta é disparado</span><span class="sxs-lookup"><span data-stu-id="8e9be-122">An alert is triggered</span></span>     | <span data-ttu-id="8e9be-123">Em geral, uma investigação automatizada é iniciada quando um [alerta](review-alerts.md) é disparado e [um incidente](view-incidents-queue.md) é criado.</span><span class="sxs-lookup"><span data-stu-id="8e9be-123">In general, an automated investigation starts when an [alert](review-alerts.md) is triggered, and an [incident](view-incidents-queue.md) is created.</span></span> <span data-ttu-id="8e9be-124">Por exemplo, suponha que um arquivo mal-intencionado reside em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8e9be-124">For example, suppose a malicious file resides on a device.</span></span> <span data-ttu-id="8e9be-125">Quando esse arquivo é detectado, um alerta é disparado e um incidente é criado.</span><span class="sxs-lookup"><span data-stu-id="8e9be-125">When that file is detected, an alert is triggered, and incident is created.</span></span> <span data-ttu-id="8e9be-126">Um processo de investigação automatizado começa no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8e9be-126">An automated investigation process begins on the device.</span></span> <span data-ttu-id="8e9be-127">Como outros alertas são gerados devido ao mesmo arquivo em outros dispositivos, eles são adicionados ao incidente associado e à investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="8e9be-127">As other alerts are generated because of the same file on other devices, they are added to the associated incident and to the automated investigation.</span></span>         |
|<span data-ttu-id="8e9be-128">Uma investigação é iniciada manualmente</span><span class="sxs-lookup"><span data-stu-id="8e9be-128">An investigation is started manually</span></span>     | <span data-ttu-id="8e9be-129">Uma investigação automatizada pode ser iniciada manualmente pela sua equipe de operações de segurança.</span><span class="sxs-lookup"><span data-stu-id="8e9be-129">An automated investigation can be started manually by your security operations team.</span></span> <span data-ttu-id="8e9be-130">Por exemplo, suponha que um operador de segurança está revendo uma lista de dispositivos e observe que um dispositivo tem um nível de alto risco.</span><span class="sxs-lookup"><span data-stu-id="8e9be-130">For example, suppose a security operator is reviewing a list of devices and notices that a device has a high risk level.</span></span> <span data-ttu-id="8e9be-131">O operador de segurança pode selecionar o dispositivo na lista para abrir seu sobrevoo e, em seguida, **selecionar Iniciar Investigação Automatizada**.</span><span class="sxs-lookup"><span data-stu-id="8e9be-131">The security operator can select the device in the list to open its flyout, and then select **Initiate Automated Investigation**.</span></span> |

## <a name="how-an-automated-investigation-expands-its-scope"></a><span data-ttu-id="8e9be-132">Como uma investigação automatizada expande seu escopo</span><span class="sxs-lookup"><span data-stu-id="8e9be-132">How an automated investigation expands its scope</span></span>

<span data-ttu-id="8e9be-133">Enquanto uma investigação está em execução, quaisquer outros alertas gerados do dispositivo são adicionados a uma investigação automatizada em andamento até que essa investigação seja concluída.</span><span class="sxs-lookup"><span data-stu-id="8e9be-133">While an investigation is running, any other alerts generated from the device are added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="8e9be-134">Além disso, se a mesma ameaça for vista em outros dispositivos, esses dispositivos serão adicionados à investigação.</span><span class="sxs-lookup"><span data-stu-id="8e9be-134">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>

<span data-ttu-id="8e9be-135">Se uma entidade for vista em outro dispositivo, o processo de investigação automatizada expandirá seu escopo para incluir esse dispositivo e uma playbook de segurança geral será iniciada nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8e9be-135">If an incriminated entity is seen in another device, the automated investigation process expands its scope to include that device, and a general security playbook starts on that device.</span></span> <span data-ttu-id="8e9be-136">Se 10 ou mais dispositivos são encontrados durante esse processo de expansão da mesma entidade, essa ação de expansão requer uma aprovação e fica visível na guia Ações **pendentes.**</span><span class="sxs-lookup"><span data-stu-id="8e9be-136">If 10 or more devices are found during this expansion process from the same entity, then that expansion action requires an approval, and is visible on the **Pending actions** tab.</span></span>

## <a name="how-threats-are-remediated"></a><span data-ttu-id="8e9be-137">Como as ameaças são remediadas</span><span class="sxs-lookup"><span data-stu-id="8e9be-137">How threats are remediated</span></span>

<span data-ttu-id="8e9be-138">À medida que os alertas são disparados e uma investigação automatizada é executado, um veredito é gerado para cada parte das evidências investigadas.</span><span class="sxs-lookup"><span data-stu-id="8e9be-138">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="8e9be-139">Os vereditos podem ser</span><span class="sxs-lookup"><span data-stu-id="8e9be-139">Verdicts can be</span></span> 
- <span data-ttu-id="8e9be-140">*Mal-intencionado;*</span><span class="sxs-lookup"><span data-stu-id="8e9be-140">*Malicious*;</span></span>
- <span data-ttu-id="8e9be-141">*Suspeito;* ou</span><span class="sxs-lookup"><span data-stu-id="8e9be-141">*Suspicious*; or</span></span> 
- <span data-ttu-id="8e9be-142">*Nenhuma ameaça encontrada*.</span><span class="sxs-lookup"><span data-stu-id="8e9be-142">*No threats found*.</span></span> 

<span data-ttu-id="8e9be-143">À medida que os vereditos são atingidos, investigações automatizadas podem resultar em uma ou mais ações de correção.</span><span class="sxs-lookup"><span data-stu-id="8e9be-143">As verdicts are reached, automated investigations can result in one or more remediation actions.</span></span> <span data-ttu-id="8e9be-144">Exemplos de ações de correção incluem o envio de um arquivo para a quarentena, a interrupção de um serviço, a remoção de uma tarefa agendada e muito mais.</span><span class="sxs-lookup"><span data-stu-id="8e9be-144">Examples of remediation actions include sending a file to quarantine, stopping a service, removing a scheduled task, and more.</span></span> <span data-ttu-id="8e9be-145">Para saber mais, confira [Ações de correção.](manage-auto-investigation.md#remediation-actions)</span><span class="sxs-lookup"><span data-stu-id="8e9be-145">To learn more, see [Remediation actions](manage-auto-investigation.md#remediation-actions).</span></span>  

<span data-ttu-id="8e9be-146">Dependendo do [](automation-levels.md) nível de automação definido para sua organização, bem como de outras configurações de segurança, as ações de correção podem ocorrer automaticamente ou somente após a aprovação pela sua equipe de operações de segurança.</span><span class="sxs-lookup"><span data-stu-id="8e9be-146">Depending on the [level of automation](automation-levels.md) set for your organization, as well as other security settings, remediation actions can occur automatically or only upon approval by your security operations team.</span></span> <span data-ttu-id="8e9be-147">As configurações de segurança adicionais que podem afetar a correção automática incluem [proteção contra](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) aplicativos potencialmente indesejados (PUA).</span><span class="sxs-lookup"><span data-stu-id="8e9be-147">Additional security settings that can affect automatic remediation include [protection from potentially unwanted applications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA).</span></span> 

<span data-ttu-id="8e9be-148">Todas as ações de correção, pendentes ou concluídas, são controladas no [Centro de Ações](auto-investigation-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="8e9be-148">All remediation actions, whether pending or completed, are tracked in the [Action center](auto-investigation-action-center.md).</span></span> <span data-ttu-id="8e9be-149">Se necessário, sua equipe de operações de segurança pode desfazer uma ação de correção.</span><span class="sxs-lookup"><span data-stu-id="8e9be-149">If necessary, your security operations team can undo a remediation action.</span></span> <span data-ttu-id="8e9be-150">Para saber mais, confira Revisar e aprovar ações [de correção após uma investigação automatizada.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)</span><span class="sxs-lookup"><span data-stu-id="8e9be-150">To learn more, see [Review and approve remediation actions following an automated investigation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation).</span></span>

> [!TIP]
> <span data-ttu-id="8e9be-151">Confira a nova página de investigação unificada no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8e9be-151">Check out the new, unified investigation page in the Microsoft 365 security center.</span></span> <span data-ttu-id="8e9be-152">Para saber mais, consulte [(NEW!) Página de investigação unificada](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span><span class="sxs-lookup"><span data-stu-id="8e9be-152">To learn more, see [(NEW!) Unified investigation page](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).</span></span>


## <a name="requirements-for-air"></a><span data-ttu-id="8e9be-153">Requisitos para AIR</span><span class="sxs-lookup"><span data-stu-id="8e9be-153">Requirements for AIR</span></span>

<span data-ttu-id="8e9be-154">Sua organização deve ter o Defender para Ponto de Extremidade (consulte [Requisitos mínimos para o Microsoft Defender para Ponto de Extremidade](minimum-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="8e9be-154">Your organization must have Defender for Endpoint (see [Minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)).</span></span>

<span data-ttu-id="8e9be-155">Atualmente, o AIR dá suporte apenas às seguintes versões do sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="8e9be-155">Currently, AIR only supports the following OS versions:</span></span>
- <span data-ttu-id="8e9be-156">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8e9be-156">Windows Server 2019</span></span>
- <span data-ttu-id="8e9be-157">Windows 10, versão 1709 (Build 16299.1085 com [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) ou posterior</span><span class="sxs-lookup"><span data-stu-id="8e9be-157">Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) or later</span></span>
- <span data-ttu-id="8e9be-158">Windows 10, versão 1803 (Build 17134.704 com [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) ou posterior</span><span class="sxs-lookup"><span data-stu-id="8e9be-158">Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) or later</span></span>
- <span data-ttu-id="8e9be-159">Windows 10, versão [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) ou posterior</span><span class="sxs-lookup"><span data-stu-id="8e9be-159">Windows 10, version [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) or later</span></span>

## <a name="next-steps"></a><span data-ttu-id="8e9be-160">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8e9be-160">Next steps</span></span>

- [<span data-ttu-id="8e9be-161">Saiba mais sobre níveis de automação</span><span class="sxs-lookup"><span data-stu-id="8e9be-161">Learn more about automation levels</span></span>](automation-levels.md)
- [<span data-ttu-id="8e9be-162">Consulte o guia interativo: Investigar e correção de ameaças com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8e9be-162">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
- [<span data-ttu-id="8e9be-163">Configurar recursos automatizados de investigação e correção no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8e9be-163">Configure automated investigation and remediation capabilities in Microsoft Defender for Endpoint</span></span>](configure-automated-investigations-remediation.md)

## <a name="see-also"></a><span data-ttu-id="8e9be-164">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e9be-164">See also</span></span>

- [<span data-ttu-id="8e9be-165">Proteção PUA</span><span class="sxs-lookup"><span data-stu-id="8e9be-165">PUA protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="8e9be-166">Investigação e resposta automatizadas no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8e9be-166">Automated investigation and response in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-air)
- [<span data-ttu-id="8e9be-167">Investigação e resposta automatizadas no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e9be-167">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
