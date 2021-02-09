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
description: Saiba mais sobre as ações de correção em recursos automatizados de investigação e resposta no Microsoft Defender para Office 365 Plano 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: bcff8f12133ea16e3d91e293943be1593eaf9659
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142688"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="6223e-104">Revisar e gerenciar ações de correção no Office 365</span><span class="sxs-lookup"><span data-stu-id="6223e-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="6223e-105">Como investigações automatizadas em emails & conteúdo de colaboração  resultam em vereditos, como Mal-intencionados ou *suspeitos,* determinadas ações de correção são criadas.</span><span class="sxs-lookup"><span data-stu-id="6223e-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="6223e-106">No Microsoft Defender para Office 365, as ações de correção podem incluir:</span><span class="sxs-lookup"><span data-stu-id="6223e-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="6223e-107">Bloqueando uma URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="6223e-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="6223e-108">Exclusão suave de mensagens de email ou clusters</span><span class="sxs-lookup"><span data-stu-id="6223e-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="6223e-109">Quarentena de emails ou anexos de email</span><span class="sxs-lookup"><span data-stu-id="6223e-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="6223e-110">Como desligar o encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="6223e-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="6223e-111">Essas ações de correção não serão tomadas, a menos e até que sua equipe de operações de segurança as aprove.</span><span class="sxs-lookup"><span data-stu-id="6223e-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="6223e-112">Recomendamos analisar e aprovar todas as ações pendentes assim que possível para que suas investigações automatizadas seja concluídas em tempo hábil.</span><span class="sxs-lookup"><span data-stu-id="6223e-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="6223e-113">Em alguns casos, você pode desfazer uma ação de correção.</span><span class="sxs-lookup"><span data-stu-id="6223e-113">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="6223e-114">Aprovar (ou rejeitar) ações pendentes</span><span class="sxs-lookup"><span data-stu-id="6223e-114">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="6223e-115">Vá para a central de segurança do Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="6223e-115">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="6223e-116">No painel de navegação, selecione Central **de ações.**</span><span class="sxs-lookup"><span data-stu-id="6223e-116">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="6223e-117">Na guia **Pendente,** revise a lista de ações que estão aguardando aprovação.</span><span class="sxs-lookup"><span data-stu-id="6223e-117">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="6223e-118">Selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="6223e-118">Select an item in the list.</span></span> <span data-ttu-id="6223e-119">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="6223e-119">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="6223e-120">Revise as informações no painel do flyout e, em seguida, tome uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="6223e-120">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="6223e-121">Selecione **a página Abrir investigação** para exibir mais detalhes sobre a investigação.</span><span class="sxs-lookup"><span data-stu-id="6223e-121">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="6223e-122">Selecione **Aprovar** para iniciar uma ação pendente.</span><span class="sxs-lookup"><span data-stu-id="6223e-122">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="6223e-123">Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.</span><span class="sxs-lookup"><span data-stu-id="6223e-123">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="6223e-124">Desfazer uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="6223e-124">Undo one remediation action</span></span>

1. <span data-ttu-id="6223e-125">Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="6223e-125">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="6223e-126">Na guia **Histórico,** selecione uma ação que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="6223e-126">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="6223e-127">No painel no lado direito da tela, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="6223e-127">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="6223e-128">Desfazer várias ações de correção</span><span class="sxs-lookup"><span data-stu-id="6223e-128">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="6223e-129">Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="6223e-129">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="6223e-130">Na guia **Histórico,** selecione as ações que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="6223e-130">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="6223e-131">Certifique-se de selecionar itens que tenham o mesmo tipo de ação.</span><span class="sxs-lookup"><span data-stu-id="6223e-131">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="6223e-132">Um painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="6223e-132">A flyout pane opens.</span></span>
3. <span data-ttu-id="6223e-133">No painel do flyout, selecione Desfazer.</span><span class="sxs-lookup"><span data-stu-id="6223e-133">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="6223e-134">Para remover um arquivo da quarentena em vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="6223e-134">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="6223e-135">Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="6223e-135">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="6223e-136">Na guia **Histórico,** selecione um arquivo que tenha o arquivo de quarentena do tipo **Ação.**</span><span class="sxs-lookup"><span data-stu-id="6223e-136">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="6223e-137">No painel no lado direito da tela, selecione Aplicar a **X mais instâncias** deste arquivo e selecione **Desfazer.**</span><span class="sxs-lookup"><span data-stu-id="6223e-137">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6223e-138">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="6223e-138">Next steps</span></span>

- [<span data-ttu-id="6223e-139">Usar o Explorador de Ameaças</span><span class="sxs-lookup"><span data-stu-id="6223e-139">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="6223e-140">Como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="6223e-140">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="6223e-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="6223e-141">See also</span></span>

- [<span data-ttu-id="6223e-142">Exibir detalhes e resultados de uma investigação automatizada no Office 365</span><span class="sxs-lookup"><span data-stu-id="6223e-142">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
