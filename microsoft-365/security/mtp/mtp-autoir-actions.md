---
title: Aprovar ou rejeitar ações pendentes após uma investigação automatizada
description: Use a Central de Ações para gerenciar ações relacionadas a investigações e respostas automáticas
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930373"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="350a1-104">Aprovar ou rejeitar ações pendentes após uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="350a1-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="350a1-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="350a1-105">**Applies to:**</span></span>
- <span data-ttu-id="350a1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="350a1-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="350a1-107">Quando uma investigação automatizada é executada, pode resultar em uma ou mais [ações de correção ](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) que exigem aprovação para prosseguir.</span><span class="sxs-lookup"><span data-stu-id="350a1-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="350a1-108">Por exemplo, um cluster de mensagens de email pode precisar ser excluído, ou talvez seja necessário remover um arquivo em quarentena.</span><span class="sxs-lookup"><span data-stu-id="350a1-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="350a1-109">É importante aprovar (ou rejeitar) ações pendentes o mais rápido possível, para que suas investigações automatizadas possam prosseguir e ser concluídas a tempo.</span><span class="sxs-lookup"><span data-stu-id="350a1-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="350a1-110">Se você acha que algo foi perdido ou detectado incorretamente pelos recursos de investigação e resposta automatizados no Microsoft 365 Defender, nos avise!</span><span class="sxs-lookup"><span data-stu-id="350a1-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="350a1-111">Veja como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta [(AIR) no Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="350a1-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="350a1-112">Ações pendentes podem ser revisadas e aprovadas usando a Central [de ações](#review-a-pending-action-in-the-action-center) ou a [exibição de detalhes da investigação.](#review-a-pending-action-in-the-investigation-details-view)</span><span class="sxs-lookup"><span data-stu-id="350a1-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="350a1-113">Você deve ter [permissões apropriadas](mtp-action-center.md#required-permissions-for-action-center-tasks) para aprovar ou rejeitar ações de correção.</span><span class="sxs-lookup"><span data-stu-id="350a1-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="350a1-114">Para saber mais, confira Pré-requisitos para investigação e resposta [automatizadas no Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="350a1-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="350a1-115">Revisar uma ação pendente na Central de Ações</span><span class="sxs-lookup"><span data-stu-id="350a1-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="350a1-116">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="350a1-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="350a1-117">No painel de navegação, escolha **Central de Ações**.</span><span class="sxs-lookup"><span data-stu-id="350a1-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="350a1-118">Em Central de Ações, na guia **Pendente**, selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="350a1-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="350a1-119">Se você selecionar um item na coluna **número da investigação**, a página detalhes da investigação será aberta.</span><span class="sxs-lookup"><span data-stu-id="350a1-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="350a1-120">Nessa página, você pode checar os resultados da investigação e aprovar ou rejeitar a ação recomendada.</span><span class="sxs-lookup"><span data-stu-id="350a1-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="350a1-121">Se você selecionar uma linha na lista, um submenu será aberto, onde serão mostradas informações sobre esse item.</span><span class="sxs-lookup"><span data-stu-id="350a1-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Aprovar ou rejeitar uma ação](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="350a1-123">Use os links para exibir um alerta ou uma investigação associada e aprovar ou rejeitar a ação.</span><span class="sxs-lookup"><span data-stu-id="350a1-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="350a1-124">Revisar uma ação pendente na exibição dos detalhes da investigação</span><span class="sxs-lookup"><span data-stu-id="350a1-124">Review a pending action in the investigation details view</span></span>

![Detalhes da investigação](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="350a1-126">Na página [detalhes da investigação](mtp-autoir-results.md), selecione a guia **Ações pendentes** (ou **Ações**). Os itens pendentes estarão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="350a1-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="350a1-127">Selecione um item na lista e, em seguida, escolha **Aprovar** ou **Rejeitar**.</span><span class="sxs-lookup"><span data-stu-id="350a1-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="350a1-128">Desfazer ações concluídas</span><span class="sxs-lookup"><span data-stu-id="350a1-128">Undo completed actions</span></span>

<span data-ttu-id="350a1-129">Se você tiver determinado que um dispositivo ou um arquivo não é uma ameaça, poderá desfazer ações de correção que foram tomadas, se essas ações foram realizadas automaticamente ou manualmente.</span><span class="sxs-lookup"><span data-stu-id="350a1-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="350a1-130">Na Central de ações, na guia **Histórico,** você pode desfazer qualquer uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="350a1-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="350a1-131">Origem da ação</span><span class="sxs-lookup"><span data-stu-id="350a1-131">Action source</span></span> | <span data-ttu-id="350a1-132">Ações com suporte</span><span class="sxs-lookup"><span data-stu-id="350a1-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="350a1-133">- Investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="350a1-133">- Automated investigation</span></span> <br/><span data-ttu-id="350a1-134">- Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="350a1-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="350a1-135">- Ações de resposta manual</span><span class="sxs-lookup"><span data-stu-id="350a1-135">- Manual response actions</span></span> | <span data-ttu-id="350a1-136">- Isolar dispositivo</span><span class="sxs-lookup"><span data-stu-id="350a1-136">- Isolate device</span></span> <br/><span data-ttu-id="350a1-137">- Restringir a execução de código</span><span class="sxs-lookup"><span data-stu-id="350a1-137">- Restrict code execution</span></span> <br/><span data-ttu-id="350a1-138">- Colocar um arquivo em quarentena</span><span class="sxs-lookup"><span data-stu-id="350a1-138">- Quarantine a file</span></span> <br/><span data-ttu-id="350a1-139">- Remover uma chave do Registro</span><span class="sxs-lookup"><span data-stu-id="350a1-139">- Remove a registry key</span></span> <br/><span data-ttu-id="350a1-140">- Parar um serviço</span><span class="sxs-lookup"><span data-stu-id="350a1-140">- Stop a service</span></span> <br/><span data-ttu-id="350a1-141">- Desabilitar um driver</span><span class="sxs-lookup"><span data-stu-id="350a1-141">- Disable a driver</span></span> <br/><span data-ttu-id="350a1-142">- Remover uma tarefa agendada</span><span class="sxs-lookup"><span data-stu-id="350a1-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="350a1-143">Para desfazer uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="350a1-143">To undo a remediation action</span></span>

1. <span data-ttu-id="350a1-144">Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="350a1-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="350a1-145">Na guia **Histórico,** selecione uma ação que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="350a1-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="350a1-146">No painel no lado direito da tela, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="350a1-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="350a1-147">Para remover um arquivo da quarentena em vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="350a1-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="350a1-148">Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="350a1-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="350a1-149">Na guia **Histórico,** selecione um arquivo que tenha o arquivo de quarentena do tipo **Ação.**</span><span class="sxs-lookup"><span data-stu-id="350a1-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="350a1-150">No painel no lado direito da tela, selecione Aplicar a **X mais instâncias** deste arquivo e selecione **Desfazer.**</span><span class="sxs-lookup"><span data-stu-id="350a1-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="350a1-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="350a1-151">Next steps</span></span>

- [<span data-ttu-id="350a1-152">Exibir os detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="350a1-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="350a1-153">Lidar com falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="350a1-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
