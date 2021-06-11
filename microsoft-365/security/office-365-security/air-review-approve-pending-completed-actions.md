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
ms.openlocfilehash: 7894a9aa38239bf661c809cce96ea2a2a96c3725
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904123"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="842b5-104">Analisar e gerenciar ações de correção em Office 365</span><span class="sxs-lookup"><span data-stu-id="842b5-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="842b5-105">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="842b5-105">**Applies to**</span></span>
- [<span data-ttu-id="842b5-106">Plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="842b5-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="842b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="842b5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="842b5-108">À medida que investigações automatizadas no email & conteúdo  de colaboração resultam em vereditos, como Mal-intencionados ou *suspeitos,* determinadas ações de correção são criadas.</span><span class="sxs-lookup"><span data-stu-id="842b5-108">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="842b5-109">No Microsoft Defender para Office 365, as ações de correção podem incluir:</span><span class="sxs-lookup"><span data-stu-id="842b5-109">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="842b5-110">Bloqueando uma URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="842b5-110">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="842b5-111">Exclusão suave de mensagens de email ou clusters</span><span class="sxs-lookup"><span data-stu-id="842b5-111">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="842b5-112">Quarantining email or email attachments</span><span class="sxs-lookup"><span data-stu-id="842b5-112">Quarantining email or email attachments</span></span>
- <span data-ttu-id="842b5-113">Desligar o encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="842b5-113">Turning off external mail forwarding</span></span>

<span data-ttu-id="842b5-114">Essas ações de correção não serão tomadas, a menos que e até que sua equipe de operações de segurança as aprove.</span><span class="sxs-lookup"><span data-stu-id="842b5-114">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="842b5-115">Recomendamos revisar e aprovar todas as ações pendentes assim que possível para que suas investigações automatizadas concluam em tempo hábil.</span><span class="sxs-lookup"><span data-stu-id="842b5-115">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="842b5-116">Em alguns casos, você pode desfazer uma ação de correção.</span><span class="sxs-lookup"><span data-stu-id="842b5-116">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="842b5-117">Aprovar (ou rejeitar) ações pendentes</span><span class="sxs-lookup"><span data-stu-id="842b5-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="842b5-118">Vá para o portal Microsoft 365 Defender ( <https://security.microsoft.com> ) e entre.</span><span class="sxs-lookup"><span data-stu-id="842b5-118">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="842b5-119">No painel de navegação, selecione **Centro de ações**.</span><span class="sxs-lookup"><span data-stu-id="842b5-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="842b5-120">Na guia **Pendente,** revise a lista de ações que estão aguardando aprovação.</span><span class="sxs-lookup"><span data-stu-id="842b5-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="842b5-121">Selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="842b5-121">Select an item in the list.</span></span> <span data-ttu-id="842b5-122">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="842b5-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="842b5-123">Revise as informações no painel de sobrevoos e, em seguida, dê uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="842b5-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="842b5-124">Selecione **Abrir página de investigação** para exibir mais detalhes sobre a investigação.</span><span class="sxs-lookup"><span data-stu-id="842b5-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="842b5-125">Selecione **Aprovar** para iniciar uma ação pendente.</span><span class="sxs-lookup"><span data-stu-id="842b5-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="842b5-126">Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.</span><span class="sxs-lookup"><span data-stu-id="842b5-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="842b5-127">Alterar ou desfazer uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="842b5-127">Change or undo one remediation action</span></span>

1. <span data-ttu-id="842b5-128">Vá para a Central de Ações ( <https://security.microsoft.com/action-center> ) e entre.</span><span class="sxs-lookup"><span data-stu-id="842b5-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="842b5-129">Na guia **Histórico,** selecione uma ação que você deseja alterar ou desfazer.</span><span class="sxs-lookup"><span data-stu-id="842b5-129">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="842b5-130">No painel no lado direito da tela, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="842b5-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="change-or-undo-multiple-remediation-actions"></a><span data-ttu-id="842b5-131">Alterar ou desfazer várias ações de correção</span><span class="sxs-lookup"><span data-stu-id="842b5-131">Change or undo multiple remediation actions</span></span>

1. <span data-ttu-id="842b5-132">Vá para a Central de Ações ( <https://security.microsoft.com/action-center> ) e entre.</span><span class="sxs-lookup"><span data-stu-id="842b5-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="842b5-133">Na guia **Histórico,** selecione as ações que você deseja alterar ou desfazer.</span><span class="sxs-lookup"><span data-stu-id="842b5-133">On the **History** tab, select the actions that you want to change or undo.</span></span> <span data-ttu-id="842b5-134">Certifique-se de selecionar itens que tenham o mesmo tipo de Ação.</span><span class="sxs-lookup"><span data-stu-id="842b5-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="842b5-135">Um painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="842b5-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="842b5-136">No painel de sobrevoos, selecione Desfazer.</span><span class="sxs-lookup"><span data-stu-id="842b5-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="842b5-137">Para remover um arquivo da quarentena em vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="842b5-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="842b5-138">Vá para a Central de Ações ( <https://security.microsoft.com/action-center> ) e entre.</span><span class="sxs-lookup"><span data-stu-id="842b5-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="842b5-139">Na guia **Histórico,** selecione um arquivo que tenha o arquivo De quarentena tipo **ação.**</span><span class="sxs-lookup"><span data-stu-id="842b5-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="842b5-140">No painel no lado direito da tela, selecione Aplicar a X mais **instâncias** deste arquivo e selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="842b5-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="842b5-141">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="842b5-141">Next steps</span></span>

- [<span data-ttu-id="842b5-142">Usar o Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="842b5-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="842b5-143">Como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="842b5-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="842b5-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="842b5-144">See also</span></span>

- [<span data-ttu-id="842b5-145">Exibir detalhes e resultados de uma investigação automatizada no Office 365</span><span class="sxs-lookup"><span data-stu-id="842b5-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
