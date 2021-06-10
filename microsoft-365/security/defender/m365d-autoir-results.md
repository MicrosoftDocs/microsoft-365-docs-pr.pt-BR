---
title: Detalhes e resultados de uma investigação automatizada
description: Exibir os resultados e os principais resultados da investigação automatizada no Microsoft 365 Defender
keywords: automatização, investigação, resultados, análise, detalhes, correção, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
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
ms.openlocfilehash: ad774fc36f4f167cb7a4e695b9f572ceb55b968b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274671"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="3de78-104">Detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="3de78-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3de78-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3de78-105">**Applies to:**</span></span>
- <span data-ttu-id="3de78-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3de78-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3de78-107">Com Microsoft 365 Defender, quando [](m365d-autoir.md) uma investigação automatizada é executado, detalhes sobre essa investigação ficam disponíveis durante e após o processo de investigação automatizado.</span><span class="sxs-lookup"><span data-stu-id="3de78-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="3de78-108">Se você tiver as [permissões necessárias](m365d-action-center.md#required-permissions-for-action-center-tasks), poderá exibir esses detalhes na exibição de detalhes da investigação.</span><span class="sxs-lookup"><span data-stu-id="3de78-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="3de78-109">Essa exibição fornece o status atualizado e a capacidade de aprovar ações pendentes.</span><span class="sxs-lookup"><span data-stu-id="3de78-109">This view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Detalhes da investigação](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a><span data-ttu-id="3de78-111">(NEW!) Página de investigação unificada</span><span class="sxs-lookup"><span data-stu-id="3de78-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="3de78-112">A página de investigação foi atualizada recentemente para incluir informações em seus dispositivos, email e conteúdo de colaboração.</span><span class="sxs-lookup"><span data-stu-id="3de78-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="3de78-113">A nova página de investigação unificada define um idioma comum e fornece uma experiência unificada para investigações automáticas no [Microsoft Defender para Ponto](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) de Extremidade e no Microsoft [Defender](../office-365-security/defender-for-office-365.md)para Office 365 .</span><span class="sxs-lookup"><span data-stu-id="3de78-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="3de78-114">Para acessar a página de investigação unificada, selecione o link na faixa amarela que você verá em:</span><span class="sxs-lookup"><span data-stu-id="3de78-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>

- <span data-ttu-id="3de78-115">Qualquer página de investigação no Office 365 Segurança & Centro de Conformidade ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="3de78-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="3de78-116">Qualquer página de investigação no Central de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="3de78-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="3de78-117">Qualquer incidente ou experiência do Centro de Ações no Microsoft 365 de segurança ( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="3de78-117">Any incident or Action center experience in the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="3de78-118">Abrir a exibição de detalhes da investigação</span><span class="sxs-lookup"><span data-stu-id="3de78-118">Open the investigation details view</span></span>

<span data-ttu-id="3de78-119">Você pode abrir a exibição de detalhes da investigação usando um destes métodos:</span><span class="sxs-lookup"><span data-stu-id="3de78-119">You can open the investigation details view by using one of the following methods:</span></span>

- [<span data-ttu-id="3de78-120">Selecionar um item na central de Ações</span><span class="sxs-lookup"><span data-stu-id="3de78-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="3de78-121">Selecionar uma investigação em uma página de detalhes do incidente</span><span class="sxs-lookup"><span data-stu-id="3de78-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="3de78-122">Selecionar um item na central de Ações</span><span class="sxs-lookup"><span data-stu-id="3de78-122">Select an item in the Action center</span></span>

<span data-ttu-id="3de78-123">O Centro de [Ações](m365d-action-center.md) aprimorado ( ) reúne ações de correção em seus dispositivos, email & conteúdo de colaboração [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) e identidades. [](m365d-remediation-actions.md)</span><span class="sxs-lookup"><span data-stu-id="3de78-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="3de78-124">As ações listadas incluem ações de correção que foram realizadas automaticamente ou manualmente.</span><span class="sxs-lookup"><span data-stu-id="3de78-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="3de78-125">No Centro de ações, você pode exibir ações que estão aguardando aprovação e ações que já foram aprovadas ou concluídas.</span><span class="sxs-lookup"><span data-stu-id="3de78-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="3de78-126">Você também pode navegar até mais detalhes, como uma página de investigação.</span><span class="sxs-lookup"><span data-stu-id="3de78-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="3de78-127">Você deve ter [certas permissões para](m365d-action-center.md#required-permissions-for-action-center-tasks) aprovar, rejeitar ou desfazer ações.</span><span class="sxs-lookup"><span data-stu-id="3de78-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="3de78-128">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="3de78-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="3de78-129">No painel de navegação, escolha **Central de ações**.</span><span class="sxs-lookup"><span data-stu-id="3de78-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="3de78-130">Na guia **Pendente** ou **Histórico**, selecione um item.</span><span class="sxs-lookup"><span data-stu-id="3de78-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="3de78-131">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="3de78-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="3de78-132">Revise as informações no painel de sobrevoos e, em seguida, dê uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3de78-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="3de78-133">Selecione **Abrir página de investigação** para exibir mais detalhes sobre a investigação.</span><span class="sxs-lookup"><span data-stu-id="3de78-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="3de78-134">Selecione **Aprovar** para iniciar uma ação pendente.</span><span class="sxs-lookup"><span data-stu-id="3de78-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="3de78-135">Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.</span><span class="sxs-lookup"><span data-stu-id="3de78-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="3de78-136">Selecione **Ir procurar** para entrar em Busca [Avançada](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3de78-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="3de78-137">Abrir uma investigação em uma página de detalhes do incidente</span><span class="sxs-lookup"><span data-stu-id="3de78-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="3de78-138">Use uma página de detalhes do incidente para exibir informações detalhadas sobre um incidente, incluindo os alertas que foram disparados com informações sobre os dispositivos afetados, contas de usuários ou caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="3de78-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="3de78-139">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="3de78-139">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="3de78-140">No painel de navegação, escolha **Incidentes &**  >  **alertas Incidentes**.</span><span class="sxs-lookup"><span data-stu-id="3de78-140">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="3de78-141">Selecione um item na lista e escolha **Abrir página de incidentes**.</span><span class="sxs-lookup"><span data-stu-id="3de78-141">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="3de78-142">Selecione a **guia Investigações** e selecione uma investigação na lista.</span><span class="sxs-lookup"><span data-stu-id="3de78-142">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="3de78-143">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="3de78-143">Its flyout pane opens.</span></span>

5. <span data-ttu-id="3de78-144">Selecione **Abrir página de investigação**.</span><span class="sxs-lookup"><span data-stu-id="3de78-144">Select **Open investigation page**.</span></span> 

<span data-ttu-id="3de78-145">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="3de78-145">Here's an example.</span></span>

![Detalhes do incidente](../../media/mtp-incidentdetails-tabs.png)

## <a name="investigation-details"></a><span data-ttu-id="3de78-147">Detalhes da investigação</span><span class="sxs-lookup"><span data-stu-id="3de78-147">Investigation details</span></span>

<span data-ttu-id="3de78-148">Use o modo de exibição de detalhes da investigação para ver as atividades antigas, atuais e pendentes referentes a uma investigação.</span><span class="sxs-lookup"><span data-stu-id="3de78-148">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="3de78-149">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="3de78-149">Here's an example.</span></span>

![Detalhes da investigação](../../media/mtp-air-investdetails.png)

<span data-ttu-id="3de78-151">Na exibição de detalhes da investigação, você pode ver as informações nas guias **Gráfico de Investigação**, **Alertas**, **Dispositivos**, **Identidades**, **Principais descobertas**, **Entidades**,**Log** e **Ações pendentes**, descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="3de78-151">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="3de78-152">As guias específicas que você vê em uma página de detalhes da investigação dependem do que sua assinatura inclui.</span><span class="sxs-lookup"><span data-stu-id="3de78-152">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="3de78-153">Por exemplo, se sua assinatura não incluir o Microsoft Defender para Office 365 Plano 2, você não verá uma guia **Caixas de** Correio.</span><span class="sxs-lookup"><span data-stu-id="3de78-153">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="3de78-154">Guia</span><span class="sxs-lookup"><span data-stu-id="3de78-154">Tab</span></span> | <span data-ttu-id="3de78-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="3de78-155">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="3de78-156">**Gráficos de investigação**</span><span class="sxs-lookup"><span data-stu-id="3de78-156">**Investigation graph**</span></span>   | <span data-ttu-id="3de78-157">Oferece uma representação visual da investigação.</span><span class="sxs-lookup"><span data-stu-id="3de78-157">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="3de78-158">Descreve entidades e lista as ameaças encontradas, juntamente com os alertas, e se as ações estão aguardando aprovação.</span><span class="sxs-lookup"><span data-stu-id="3de78-158">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="3de78-159">Você pode selecionar um item no gráfico para exibir mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="3de78-159">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="3de78-160">Por exemplo, selecionar **o ícone**  Evidência o leva à guia Evidências, onde você pode ver entidades detectadas e seus vereditos.</span><span class="sxs-lookup"><span data-stu-id="3de78-160">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="3de78-161">**Alertas**</span><span class="sxs-lookup"><span data-stu-id="3de78-161">**Alerts**</span></span>    | <span data-ttu-id="3de78-162">Lista os alertas associados à investigação.</span><span class="sxs-lookup"><span data-stu-id="3de78-162">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="3de78-163">Os alertas podem vir de recursos de proteção contra ameaças no dispositivo de um usuário, em Office aplicativos, Microsoft Cloud App Security e outros recursos Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3de78-163">Alerts can come from threat protection features on a user's device, in Office apps, Microsoft Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="3de78-164">**Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="3de78-164">**Devices**</span></span> | <span data-ttu-id="3de78-165">Lista os dispositivos incluídos na investigação juntamente com seu nível de correção.</span><span class="sxs-lookup"><span data-stu-id="3de78-165">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="3de78-166">(Os níveis de correção correspondem [ao nível de automação para grupos de dispositivos](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span><span class="sxs-lookup"><span data-stu-id="3de78-166">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="3de78-167">**Caixas de correio**</span><span class="sxs-lookup"><span data-stu-id="3de78-167">**Mailboxes**</span></span> |<span data-ttu-id="3de78-168">Lista caixas de correio que são impactadas por ameaças detectadas.</span><span class="sxs-lookup"><span data-stu-id="3de78-168">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="3de78-169">**Usuários**</span><span class="sxs-lookup"><span data-stu-id="3de78-169">**Users**</span></span>  | <span data-ttu-id="3de78-170">Lista contas de usuário que são impactadas por ameaças detectadas.</span><span class="sxs-lookup"><span data-stu-id="3de78-170">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="3de78-171">**Evidências**</span><span class="sxs-lookup"><span data-stu-id="3de78-171">**Evidence**</span></span> | <span data-ttu-id="3de78-172">Lista partes de evidências levantadas por alertas ou investigações.</span><span class="sxs-lookup"><span data-stu-id="3de78-172">Lists pieces of evidence raised by alerts or investigations.</span></span> <span data-ttu-id="3de78-173">Inclui vereditos (*Mal-intencionados,*  *suspeitos,* desconhecidos ou *nenhuma* ameaça encontrada ) e status de correção.</span><span class="sxs-lookup"><span data-stu-id="3de78-173">Includes verdicts (*Malicious*, *Suspicious*, *Unknown*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="3de78-174">**Entities**</span><span class="sxs-lookup"><span data-stu-id="3de78-174">**Entities**</span></span>  | <span data-ttu-id="3de78-175">Fornece detalhes sobre cada entidade analisada, incluindo um veredito para cada tipo de entidade (*Mal-intencionado,* *suspeito* ou *nenhuma ameaça encontrada*).</span><span class="sxs-lookup"><span data-stu-id="3de78-175">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="3de78-176">**Log**</span><span class="sxs-lookup"><span data-stu-id="3de78-176">**Log**</span></span>    | <span data-ttu-id="3de78-177">Fornece uma exibição cronológica e detalhada de todas as ações de investigação realizadas após a acionamento de um alerta.</span><span class="sxs-lookup"><span data-stu-id="3de78-177">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="3de78-178">**Histórico de ações pendentes**</span><span class="sxs-lookup"><span data-stu-id="3de78-178">**Pending actions history**</span></span> | <span data-ttu-id="3de78-179">Lista os itens que exigem aprovação para prosseguir.</span><span class="sxs-lookup"><span data-stu-id="3de78-179">Lists items that require approval to proceed.</span></span> <span data-ttu-id="3de78-180">Vá para a Central de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) para aprovar ações pendentes.</span><span class="sxs-lookup"><span data-stu-id="3de78-180">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="3de78-181">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3de78-181">Next steps</span></span>

- [<span data-ttu-id="3de78-182">Exibir e gerenciar ações de correção</span><span class="sxs-lookup"><span data-stu-id="3de78-182">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="3de78-183">Saiba mais sobre ações de correção</span><span class="sxs-lookup"><span data-stu-id="3de78-183">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)
