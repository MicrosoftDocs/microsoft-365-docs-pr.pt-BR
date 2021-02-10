---
title: Revisar e gerenciar ações de correção no Microsoft Defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.date: 01/29/2021
ms.openlocfilehash: 3fb77fa41ff3e9af995cf80b9f4024aa92a51212
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176010"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="73d0c-104">Revisar e gerenciar ações de correção no Office 365</span><span class="sxs-lookup"><span data-stu-id="73d0c-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="73d0c-105">Como investigações automatizadas em emails & conteúdo de colaboração  resultam em vereditos, como Mal-intencionados ou *suspeitos,* determinadas ações de correção são criadas.</span><span class="sxs-lookup"><span data-stu-id="73d0c-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="73d0c-106">No Microsoft Defender para Office 365, as ações de correção podem incluir:</span><span class="sxs-lookup"><span data-stu-id="73d0c-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="73d0c-107">Bloqueando uma URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="73d0c-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="73d0c-108">Exclusão suave de mensagens de email ou clusters</span><span class="sxs-lookup"><span data-stu-id="73d0c-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="73d0c-109">Quarentena de emails ou anexos de email</span><span class="sxs-lookup"><span data-stu-id="73d0c-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="73d0c-110">Como desligar o encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="73d0c-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="73d0c-111">Essas ações de correção não serão tomadas, a menos e até que sua equipe de operações de segurança as aprove.</span><span class="sxs-lookup"><span data-stu-id="73d0c-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="73d0c-112">Recomendamos analisar e aprovar todas as ações pendentes assim que possível para que suas investigações automatizadas seja concluídas em tempo hábil.</span><span class="sxs-lookup"><span data-stu-id="73d0c-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="73d0c-113">Em alguns casos, você pode desfazer uma ação de correção.</span><span class="sxs-lookup"><span data-stu-id="73d0c-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="73d0c-114">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="73d0c-114">**Applies to**</span></span>
- [<span data-ttu-id="73d0c-115">Microsoft Defender para Office 365 plano 2</span><span class="sxs-lookup"><span data-stu-id="73d0c-115">Microsoft Defender for Office 365 plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="73d0c-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73d0c-116">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="73d0c-117">Aprovar (ou rejeitar) ações pendentes</span><span class="sxs-lookup"><span data-stu-id="73d0c-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="73d0c-118">Vá para a central de segurança do Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="73d0c-118">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="73d0c-119">No painel de navegação, selecione Central **de ações.**</span><span class="sxs-lookup"><span data-stu-id="73d0c-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="73d0c-120">Na guia **Pendente,** revise a lista de ações que estão aguardando aprovação.</span><span class="sxs-lookup"><span data-stu-id="73d0c-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="73d0c-121">Selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="73d0c-121">Select an item in the list.</span></span> <span data-ttu-id="73d0c-122">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="73d0c-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="73d0c-123">Revise as informações no painel do flyout e, em seguida, tome uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="73d0c-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="73d0c-124">Selecione **a página Abrir investigação** para exibir mais detalhes sobre a investigação.</span><span class="sxs-lookup"><span data-stu-id="73d0c-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="73d0c-125">Selecione **Aprovar** para iniciar uma ação pendente.</span><span class="sxs-lookup"><span data-stu-id="73d0c-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="73d0c-126">Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.</span><span class="sxs-lookup"><span data-stu-id="73d0c-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="73d0c-127">Desfazer uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="73d0c-127">Undo one remediation action</span></span>

1. <span data-ttu-id="73d0c-128">Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="73d0c-128">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="73d0c-129">Na guia **Histórico,** selecione uma ação que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="73d0c-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="73d0c-130">No painel no lado direito da tela, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="73d0c-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="73d0c-131">Desfazer várias ações de correção</span><span class="sxs-lookup"><span data-stu-id="73d0c-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="73d0c-132">Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="73d0c-132">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="73d0c-133">Na guia **Histórico,** selecione as ações que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="73d0c-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="73d0c-134">Certifique-se de selecionar itens que tenham o mesmo tipo de ação.</span><span class="sxs-lookup"><span data-stu-id="73d0c-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="73d0c-135">Um painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="73d0c-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="73d0c-136">No painel do flyout, selecione Desfazer.</span><span class="sxs-lookup"><span data-stu-id="73d0c-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="73d0c-137">Para remover um arquivo da quarentena em vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="73d0c-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="73d0c-138">Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="73d0c-138">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="73d0c-139">Na guia **Histórico,** selecione um arquivo que tenha o arquivo de quarentena do tipo **Ação.**</span><span class="sxs-lookup"><span data-stu-id="73d0c-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="73d0c-140">No painel no lado direito da tela, selecione Aplicar a **X mais instâncias** deste arquivo e selecione **Desfazer.**</span><span class="sxs-lookup"><span data-stu-id="73d0c-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="73d0c-141">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="73d0c-141">Next steps</span></span>

- [<span data-ttu-id="73d0c-142">Usar o Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="73d0c-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="73d0c-143">Como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="73d0c-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="73d0c-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="73d0c-144">See also</span></span>

- [<span data-ttu-id="73d0c-145">Exibir detalhes e resultados de uma investigação automatizada no Office 365</span><span class="sxs-lookup"><span data-stu-id="73d0c-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
