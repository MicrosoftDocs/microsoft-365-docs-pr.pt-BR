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
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 95c82f815c794662f7eb0ffaabcfb5f81df3e828
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782988"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="d0e2b-104">Exibir e gerenciar ações no Centro de Ações</span><span class="sxs-lookup"><span data-stu-id="d0e2b-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d0e2b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d0e2b-105">**Applies to:**</span></span>
- <span data-ttu-id="d0e2b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0e2b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d0e2b-107">Os recursos de proteção contra ameaças no Microsoft 365 Defender podem resultar em determinadas ações de correção.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="d0e2b-108">Aqui estão alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="d0e2b-108">Here are some examples:</span></span>

- <span data-ttu-id="d0e2b-109">[Investigações automatizadas](m365d-autoir.md) podem resultar em ações de correção que são realizadas automaticamente ou aguardam sua aprovação.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await your approval.</span></span>
- <span data-ttu-id="d0e2b-110">Antivírus, antimalware e outros recursos de proteção contra ameaças podem resultar em ações de correção, como bloquear um arquivo, URL ou processo ou enviar um artefato para a quarentena.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="d0e2b-111">Sua equipe de operações de segurança pode realizar [](advanced-hunting-overview.md) ações de correção manualmente, como durante a busca avançada ou durante a investigação de [alertas](investigate-alerts.md) [ou incidentes.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="d0e2b-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d0e2b-112">Você deve ter [permissões apropriadas](m365d-action-center.md#required-permissions-for-action-center-tasks) para aprovar ou rejeitar ações de correção.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="d0e2b-113">Para obter mais informações, consulte [os pré-requisitos](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="d0e2b-113">For more information, see the [prerequisites](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="d0e2b-114">Revisar ações pendentes no Centro de Ações</span><span class="sxs-lookup"><span data-stu-id="d0e2b-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="d0e2b-115">É importante aprovar (ou rejeitar) ações pendentes o mais rápido possível, para que suas investigações automatizadas possam prosseguir e ser concluídas a tempo.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

1. <span data-ttu-id="d0e2b-116">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="d0e2b-117">No painel de navegação, escolha **Central de ações**.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="d0e2b-118">No Centro de ações, na guia **Pendente,** selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-118">In the Action center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="d0e2b-119">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-119">Its flyout pane opens.</span></span> <span data-ttu-id="d0e2b-120">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-120">Here's an example.</span></span>

   ![Aprovar ou rejeitar uma ação](../../media/air-actioncenter-itemselected.png)

4. <span data-ttu-id="d0e2b-122">Revise as informações no painel de sobrevoos e, em seguida, dê uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d0e2b-122">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="d0e2b-123">Selecione **Abrir página de investigação** para exibir mais detalhes sobre a investigação.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-123">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="d0e2b-124">Selecione **Aprovar** para iniciar uma ação pendente.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-124">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="d0e2b-125">Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-125">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="d0e2b-126">Selecione **Ir procurar** para entrar em Busca [Avançada](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d0e2b-126">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="d0e2b-127">Desfazer ações concluídas</span><span class="sxs-lookup"><span data-stu-id="d0e2b-127">Undo completed actions</span></span>

<span data-ttu-id="d0e2b-128">Se você tiver determinado que um dispositivo ou um arquivo não é uma ameaça, poderá desfazer as ações de correção que foram tomadas, se essas ações foram tomadas automaticamente ou manualmente.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-128">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="d0e2b-129">Na central de ações, na guia **Histórico,** você pode desfazer qualquer uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="d0e2b-129">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="d0e2b-130">Origem da ação</span><span class="sxs-lookup"><span data-stu-id="d0e2b-130">Action source</span></span> | <span data-ttu-id="d0e2b-131">Ações com suporte</span><span class="sxs-lookup"><span data-stu-id="d0e2b-131">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="d0e2b-132">- Investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="d0e2b-132">- Automated investigation</span></span> <br/><span data-ttu-id="d0e2b-133">- Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="d0e2b-133">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="d0e2b-134">- Ações de resposta manual</span><span class="sxs-lookup"><span data-stu-id="d0e2b-134">- Manual response actions</span></span> | <span data-ttu-id="d0e2b-135">- Isolar dispositivo</span><span class="sxs-lookup"><span data-stu-id="d0e2b-135">- Isolate device</span></span> <br/><span data-ttu-id="d0e2b-136">- Restringir a execução de código</span><span class="sxs-lookup"><span data-stu-id="d0e2b-136">- Restrict code execution</span></span> <br/><span data-ttu-id="d0e2b-137">- Colocar em quarentena um arquivo</span><span class="sxs-lookup"><span data-stu-id="d0e2b-137">- Quarantine a file</span></span> <br/><span data-ttu-id="d0e2b-138">- Remover uma chave do Registro</span><span class="sxs-lookup"><span data-stu-id="d0e2b-138">- Remove a registry key</span></span> <br/><span data-ttu-id="d0e2b-139">- Interromper um serviço</span><span class="sxs-lookup"><span data-stu-id="d0e2b-139">- Stop a service</span></span> <br/><span data-ttu-id="d0e2b-140">- Desabilitar um driver</span><span class="sxs-lookup"><span data-stu-id="d0e2b-140">- Disable a driver</span></span> <br/><span data-ttu-id="d0e2b-141">- Remover uma tarefa agendada</span><span class="sxs-lookup"><span data-stu-id="d0e2b-141">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="d0e2b-142">Desfazer uma ação de correção</span><span class="sxs-lookup"><span data-stu-id="d0e2b-142">Undo one remediation action</span></span>

1. <span data-ttu-id="d0e2b-143">Vá para a Central de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-143">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="d0e2b-144">Na guia **Histórico,** selecione uma ação que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-144">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="d0e2b-145">No painel no lado direito da tela, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-145">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="d0e2b-146">Desfazer várias ações de correção</span><span class="sxs-lookup"><span data-stu-id="d0e2b-146">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="d0e2b-147">Vá para a Central de Ações ( https://security.microsoft.com/action-center) e entre.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-147">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="d0e2b-148">Na guia **Histórico,** selecione as ações que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-148">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="d0e2b-149">Certifique-se de selecionar itens que tenham o mesmo tipo de Ação.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-149">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="d0e2b-150">Um painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-150">A flyout pane opens.</span></span>

3. <span data-ttu-id="d0e2b-151">No painel de sobrevoos, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-151">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="d0e2b-152">Para remover um arquivo da quarentena em vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="d0e2b-152">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="d0e2b-153">Vá para a Central de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-153">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="d0e2b-154">Na guia **Histórico,** selecione um arquivo que tenha um tipo **ação de arquivo de** quarentena.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-154">On the **History** tab, select a file that has a **Quarantine file** Action type.</span></span>

3. <span data-ttu-id="d0e2b-155">No painel no lado direito da tela, selecione Aplicar a X mais **instâncias** deste arquivo e selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="d0e2b-155">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d0e2b-156">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d0e2b-156">Next steps</span></span>

- [<span data-ttu-id="d0e2b-157">Exibir os detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="d0e2b-157">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="d0e2b-158">Resolver falsos positivos ou falsos negativos</span><span class="sxs-lookup"><span data-stu-id="d0e2b-158">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
