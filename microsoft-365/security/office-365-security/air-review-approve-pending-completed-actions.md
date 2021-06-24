---
title: Analisar e gerenciar ações de correção no Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba mais sobre ações de correção em recursos automatizados de investigação e resposta no Microsoft Defender para Office 365 Plano 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 987771616acfd2f2faf425e525505b320155388e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108530"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="3b684-104">Analisar e gerenciar ações de correção em Office 365</span><span class="sxs-lookup"><span data-stu-id="3b684-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="3b684-105">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="3b684-105">**Applies to**</span></span>
- [<span data-ttu-id="3b684-106">Plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3b684-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="3b684-107">À medida que investigações automatizadas no email & conteúdo  de colaboração resultam em vereditos, como Mal-intencionados ou *suspeitos,* determinadas ações de correção são criadas.</span><span class="sxs-lookup"><span data-stu-id="3b684-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="3b684-108">No Microsoft Defender para Office 365, as ações de correção podem incluir:</span><span class="sxs-lookup"><span data-stu-id="3b684-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="3b684-109">Exclusão suave de mensagens de email ou clusters</span><span class="sxs-lookup"><span data-stu-id="3b684-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="3b684-110">Desligar o encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="3b684-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="3b684-111">Essas ações de correção não serão tomadas, a menos que e até que sua equipe de operações de segurança as aprove.</span><span class="sxs-lookup"><span data-stu-id="3b684-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="3b684-112">Recomendamos revisar e aprovar todas as ações pendentes assim que possível para que suas investigações automatizadas concluam em tempo hábil.</span><span class="sxs-lookup"><span data-stu-id="3b684-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="3b684-113">Em alguns casos, você pode reconsiderar as ações enviadas.</span><span class="sxs-lookup"><span data-stu-id="3b684-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="3b684-114">Você precisa fazer parte do Search & função de limpeza antes de realizar qualquer ação.</span><span class="sxs-lookup"><span data-stu-id="3b684-114">You need to be part of Search & purge role before taking any actions.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="3b684-115">Aprovar (ou rejeitar) ações pendentes</span><span class="sxs-lookup"><span data-stu-id="3b684-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="3b684-116">Há quatro maneiras diferentes de encontrar e tomar ações de investigação automática:</span><span class="sxs-lookup"><span data-stu-id="3b684-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="3b684-117">Fila de incidentes</span><span class="sxs-lookup"><span data-stu-id="3b684-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="3b684-118">Centro de ações</span><span class="sxs-lookup"><span data-stu-id="3b684-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="3b684-119">Investigação em si (acessada por meio de Incidente ou de um alerta)</span><span class="sxs-lookup"><span data-stu-id="3b684-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="3b684-120">Fila de investigações de investigação e correção</span><span class="sxs-lookup"><span data-stu-id="3b684-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="3b684-121">Fila de incidentes</span><span class="sxs-lookup"><span data-stu-id="3b684-121">Incident queue</span></span>

1. <span data-ttu-id="3b684-122">Abra o Microsoft 365 Defender portal ( <https://security.microsoft.com> ) e entre.</span><span class="sxs-lookup"><span data-stu-id="3b684-122">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="3b684-123">No painel de navegação, selecione **Incidentes & alertas > Incidentes**.</span><span class="sxs-lookup"><span data-stu-id="3b684-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="3b684-124">Selecione um nome de incidente para abrir sua página de resumo.</span><span class="sxs-lookup"><span data-stu-id="3b684-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="3b684-125">Selecione a **guia Evidência e Resposta.**</span><span class="sxs-lookup"><span data-stu-id="3b684-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="3b684-126">Selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="3b684-126">Select an item in the list.</span></span> <span data-ttu-id="3b684-127">Seu painel lateral é aberto.</span><span class="sxs-lookup"><span data-stu-id="3b684-127">Its side pane opens.</span></span>
6. <span data-ttu-id="3b684-128">No painel lateral, tome ações de aprovação ou rejeição.</span><span class="sxs-lookup"><span data-stu-id="3b684-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="3b684-129">Fila de investigação</span><span class="sxs-lookup"><span data-stu-id="3b684-129">Investigation queue</span></span>

1. <span data-ttu-id="3b684-130">Abra o Microsoft 365 Defender portal ( <https://security.microsoft.com> ) e entre.</span><span class="sxs-lookup"><span data-stu-id="3b684-130">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="3b684-131">Navegue na página alertas/incidentes.</span><span class="sxs-lookup"><span data-stu-id="3b684-131">Navigate from the alerts/incident page.</span></span>
3. <span data-ttu-id="3b684-132">Na página Investigação, vá para a guia **Ações pendentes.**</span><span class="sxs-lookup"><span data-stu-id="3b684-132">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="3b684-133">Selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="3b684-133">Select an item in the list.</span></span> <span data-ttu-id="3b684-134">Seu painel lateral é aberto.</span><span class="sxs-lookup"><span data-stu-id="3b684-134">Its side pane opens.</span></span>
5. <span data-ttu-id="3b684-135">No painel lateral, tome ações de aprovação ou rejeição.</span><span class="sxs-lookup"><span data-stu-id="3b684-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="3b684-136">Central de ações</span><span class="sxs-lookup"><span data-stu-id="3b684-136">Action center</span></span>

1. <span data-ttu-id="3b684-137">Abra o Microsoft 365 Defender portal ( <https://security.microsoft.com> ) e entre.</span><span class="sxs-lookup"><span data-stu-id="3b684-137">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="3b684-138">No painel de navegação, selecione **Centro de ações**.</span><span class="sxs-lookup"><span data-stu-id="3b684-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="3b684-139">Na guia **Pendente,** revise a lista de ações que estão aguardando aprovação.</span><span class="sxs-lookup"><span data-stu-id="3b684-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="3b684-140">Selecione **Abrir página de investigação** para exibir mais detalhes sobre a investigação.</span><span class="sxs-lookup"><span data-stu-id="3b684-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="3b684-141">Selecione **Aprovar** para iniciar uma ação pendente.</span><span class="sxs-lookup"><span data-stu-id="3b684-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="3b684-142">Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.</span><span class="sxs-lookup"><span data-stu-id="3b684-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="3b684-143">Fila de investigações de investigação e correção</span><span class="sxs-lookup"><span data-stu-id="3b684-143">Investigation and remediation investigations queue</span></span>

1. <span data-ttu-id="3b684-144">Abra o Microsoft 365 Defender portal ( <https://security.microsoft.com> ) e entre.</span><span class="sxs-lookup"><span data-stu-id="3b684-144">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="3b684-145">Abra investigações pendentes.</span><span class="sxs-lookup"><span data-stu-id="3b684-145">Open pending investigations.</span></span>
3. <span data-ttu-id="3b684-146">Na página Investigação, vá para a guia **Ações pendentes.**</span><span class="sxs-lookup"><span data-stu-id="3b684-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="3b684-147">Selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="3b684-147">Select an item in the list.</span></span> <span data-ttu-id="3b684-148">Seu painel lateral é aberto.</span><span class="sxs-lookup"><span data-stu-id="3b684-148">Its side pane opens.</span></span>
5. <span data-ttu-id="3b684-149">No painel lateral, tome ações de aprovação ou rejeição.</span><span class="sxs-lookup"><span data-stu-id="3b684-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="3b684-150">Alterar ou desfazer uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="3b684-150">Change or undo one remediation action</span></span>

<span data-ttu-id="3b684-151">Há duas maneiras diferentes de reconsiderar as ações enviadas:</span><span class="sxs-lookup"><span data-stu-id="3b684-151">There are two different ways to reconsider submitted actions:</span></span>

- <span data-ttu-id="3b684-152">Por meio do [centro de ações unificado](https://security.microsoft.com/action-center).</span><span class="sxs-lookup"><span data-stu-id="3b684-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
- <span data-ttu-id="3b684-153">Embora o [centro de Office de ação](https://security.microsoft.com/threatincidents).</span><span class="sxs-lookup"><span data-stu-id="3b684-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>

## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="3b684-154">Alterar ou desfazer por meio do centro de ações unificado</span><span class="sxs-lookup"><span data-stu-id="3b684-154">Change or undo through the unified action center</span></span>

1. <span data-ttu-id="3b684-155">Vá para o [centro de ações unificado](https://security.microsoft.com/action-center) e entre.</span><span class="sxs-lookup"><span data-stu-id="3b684-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="3b684-156">Na guia **Histórico,** selecione uma ação que você deseja alterar ou desfazer.</span><span class="sxs-lookup"><span data-stu-id="3b684-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="3b684-157">No painel no lado direito da tela, selecione a ação apropriada **(** mover para a caixa de **entrada,** mover para lixo **eletrônico,** mover para itens excluídos, exclusão suave ou **exclusão difícil**).</span><span class="sxs-lookup"><span data-stu-id="3b684-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, **soft delete**, or **hard delete**).</span></span>

## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="3b684-158">Alterar ou desfazer através do centro de Office de ação</span><span class="sxs-lookup"><span data-stu-id="3b684-158">Change or undo through the Office action center</span></span>

1. <span data-ttu-id="3b684-159">Vá para o centro [de Office e](https://security.microsoft.com/threatincidents) entre.</span><span class="sxs-lookup"><span data-stu-id="3b684-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="3b684-160">Selecione a correção apropriada.</span><span class="sxs-lookup"><span data-stu-id="3b684-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="3b684-161">No painel lateral, clique na entrada envios de email e aguarde o carregamento da lista.</span><span class="sxs-lookup"><span data-stu-id="3b684-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span>
4. <span data-ttu-id="3b684-162">Aguarde o botão Ação na parte superior para habilitar e selecione o botão Ação para alterar o tipo de ação.</span><span class="sxs-lookup"><span data-stu-id="3b684-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span>
5. <span data-ttu-id="3b684-163">Isso criará as ações apropriadas.</span><span class="sxs-lookup"><span data-stu-id="3b684-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b684-164">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3b684-164">Next steps</span></span>

- [<span data-ttu-id="3b684-165">Usar o Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="3b684-165">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="3b684-166">Ações de administrador /manual</span><span class="sxs-lookup"><span data-stu-id="3b684-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="3b684-167">Como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="3b684-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="3b684-168">Confira também</span><span class="sxs-lookup"><span data-stu-id="3b684-168">See also</span></span>

- [<span data-ttu-id="3b684-169">Exibir detalhes e resultados de uma investigação automatizada no Office 365</span><span class="sxs-lookup"><span data-stu-id="3b684-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
