---
title: Exibir e gerenciar ações no Centro de Ações
description: Usar o Centro de Ações para exibir e gerenciar ações de correção
keywords: ação, central, investigação e resposta automáticas, automação, investigação, resposta, correção
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7106f5d2e740d2b4cacbcaeb0b9391095bbeb356
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592019"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="bc33e-104">Exibir e gerenciar ações no Centro de Ações</span><span class="sxs-lookup"><span data-stu-id="bc33e-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bc33e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="bc33e-105">**Applies to:**</span></span>
- <span data-ttu-id="bc33e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc33e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bc33e-107">Os recursos de proteção contra ameaças no Microsoft 365 Defender podem resultar em determinadas ações de correção.</span><span class="sxs-lookup"><span data-stu-id="bc33e-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="bc33e-108">Aqui estão alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="bc33e-108">Here are some examples:</span></span>
- <span data-ttu-id="bc33e-109">[Investigações automatizadas](m365d-autoir.md) podem resultar em ações de correção que são realizadas automaticamente ou aguardam aprovação.</span><span class="sxs-lookup"><span data-stu-id="bc33e-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await approval.</span></span>
- <span data-ttu-id="bc33e-110">Antivírus, antimalware e outros recursos de proteção contra ameaças podem resultar em ações de correção, como bloquear um arquivo, URL ou processo ou enviar um artefato para a quarentena.</span><span class="sxs-lookup"><span data-stu-id="bc33e-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="bc33e-111">Sua equipe de operações de segurança pode realizar [](advanced-hunting-overview.md) ações de correção manualmente, como durante a busca avançada ou durante a investigação de [alertas](investigate-alerts.md) [ou incidentes.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="bc33e-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bc33e-112">Você deve ter [permissões apropriadas](m365d-action-center.md#required-permissions-for-action-center-tasks) para aprovar ou rejeitar ações de correção.</span><span class="sxs-lookup"><span data-stu-id="bc33e-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="bc33e-113">Para obter mais informações, consulte [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="bc33e-113">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="bc33e-114">Revisar ações pendentes no Centro de Ações</span><span class="sxs-lookup"><span data-stu-id="bc33e-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="bc33e-115">É importante aprovar (ou rejeitar) ações pendentes o mais rápido possível, para que suas investigações automatizadas possam prosseguir e ser concluídas a tempo.</span><span class="sxs-lookup"><span data-stu-id="bc33e-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

![Aprovar ou rejeitar uma ação](../../media/air-actioncenter-itemselected.png)

1. <span data-ttu-id="bc33e-117">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="bc33e-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="bc33e-118">No painel de navegação, escolha **Central de Ações**.</span><span class="sxs-lookup"><span data-stu-id="bc33e-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="bc33e-119">Em Central de Ações, na guia **Pendente**, selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="bc33e-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="bc33e-120">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="bc33e-120">Its flyout pane opens.</span></span>

4. <span data-ttu-id="bc33e-121">Revise as informações no painel de sobrevoos e, em seguida, dê uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="bc33e-121">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="bc33e-122">Selecione **Abrir página de investigação** para exibir mais detalhes sobre a investigação.</span><span class="sxs-lookup"><span data-stu-id="bc33e-122">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="bc33e-123">Selecione **Aprovar** para iniciar uma ação pendente.</span><span class="sxs-lookup"><span data-stu-id="bc33e-123">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="bc33e-124">Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.</span><span class="sxs-lookup"><span data-stu-id="bc33e-124">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="bc33e-125">Selecione **Ir procurar** para entrar em Busca [Avançada](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bc33e-125">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="bc33e-126">Desfazer ações concluídas</span><span class="sxs-lookup"><span data-stu-id="bc33e-126">Undo completed actions</span></span>

<span data-ttu-id="bc33e-127">Se você tiver determinado que um dispositivo ou um arquivo não é uma ameaça, poderá desfazer as ações de correção que foram tomadas, se essas ações foram tomadas automaticamente ou manualmente.</span><span class="sxs-lookup"><span data-stu-id="bc33e-127">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="bc33e-128">Na central de ações, na guia **Histórico,** você pode desfazer qualquer uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="bc33e-128">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="bc33e-129">Origem da ação</span><span class="sxs-lookup"><span data-stu-id="bc33e-129">Action source</span></span> | <span data-ttu-id="bc33e-130">Ações com suporte</span><span class="sxs-lookup"><span data-stu-id="bc33e-130">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="bc33e-131">- Investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="bc33e-131">- Automated investigation</span></span> <br/><span data-ttu-id="bc33e-132">- Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="bc33e-132">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="bc33e-133">- Ações de resposta manual</span><span class="sxs-lookup"><span data-stu-id="bc33e-133">- Manual response actions</span></span> | <span data-ttu-id="bc33e-134">- Isolar dispositivo</span><span class="sxs-lookup"><span data-stu-id="bc33e-134">- Isolate device</span></span> <br/><span data-ttu-id="bc33e-135">- Restringir a execução de código</span><span class="sxs-lookup"><span data-stu-id="bc33e-135">- Restrict code execution</span></span> <br/><span data-ttu-id="bc33e-136">- Colocar em quarentena um arquivo</span><span class="sxs-lookup"><span data-stu-id="bc33e-136">- Quarantine a file</span></span> <br/><span data-ttu-id="bc33e-137">- Remover uma chave do Registro</span><span class="sxs-lookup"><span data-stu-id="bc33e-137">- Remove a registry key</span></span> <br/><span data-ttu-id="bc33e-138">- Interromper um serviço</span><span class="sxs-lookup"><span data-stu-id="bc33e-138">- Stop a service</span></span> <br/><span data-ttu-id="bc33e-139">- Desabilitar um driver</span><span class="sxs-lookup"><span data-stu-id="bc33e-139">- Disable a driver</span></span> <br/><span data-ttu-id="bc33e-140">- Remover uma tarefa agendada</span><span class="sxs-lookup"><span data-stu-id="bc33e-140">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="bc33e-141">Desfazer uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="bc33e-141">Undo one remediation action</span></span>

1. <span data-ttu-id="bc33e-142">Vá para a Central de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="bc33e-142">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="bc33e-143">Na guia **Histórico,** selecione uma ação que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="bc33e-143">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="bc33e-144">No painel no lado direito da tela, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="bc33e-144">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="bc33e-145">Desfazer várias ações de correção</span><span class="sxs-lookup"><span data-stu-id="bc33e-145">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="bc33e-146">Vá para a Central de Ações ( https://security.microsoft.com/action-center) e entre.</span><span class="sxs-lookup"><span data-stu-id="bc33e-146">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="bc33e-147">Na guia **Histórico,** selecione as ações que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="bc33e-147">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="bc33e-148">Certifique-se de selecionar itens que tenham o mesmo tipo de Ação.</span><span class="sxs-lookup"><span data-stu-id="bc33e-148">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="bc33e-149">Um painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="bc33e-149">A flyout pane opens.</span></span>

3. <span data-ttu-id="bc33e-150">No painel de sobrevoos, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="bc33e-150">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="bc33e-151">Para remover um arquivo da quarentena em vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="bc33e-151">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="bc33e-152">Vá para a Central de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="bc33e-152">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="bc33e-153">Na guia **Histórico,** selecione um arquivo que tenha o arquivo De quarentena tipo **ação.**</span><span class="sxs-lookup"><span data-stu-id="bc33e-153">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="bc33e-154">No painel no lado direito da tela, selecione Aplicar a X mais **instâncias** deste arquivo e selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="bc33e-154">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc33e-155">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bc33e-155">Next steps</span></span>

- [<span data-ttu-id="bc33e-156">Exibir os detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="bc33e-156">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="bc33e-157">Saiba como lidar com falsos positivos/negativos (se você receber um)</span><span class="sxs-lookup"><span data-stu-id="bc33e-157">Learn how to handle false positives/negatives (if you get one)</span></span>](m365d-autoir-report-false-positives-negatives.md)
