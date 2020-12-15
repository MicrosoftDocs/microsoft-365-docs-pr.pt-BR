---
title: Aprovar ou rejeitar ações pendentes após uma investigação automatizada
description: Use a Central de Ações para gerenciar ações relacionadas a investigações e respostas automáticas
keywords: ação, central, investigação e resposta automáticas, automação, investigação, resposta, correção
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
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: b34f4a532571d6215500ab2bec022489fd462d0f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683353"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="e9f71-104">Aprovar ou rejeitar ações pendentes após uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="e9f71-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e9f71-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e9f71-105">**Applies to:**</span></span>
- <span data-ttu-id="e9f71-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9f71-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e9f71-107">Quando uma investigação automatizada é executada, pode resultar em uma ou mais [ações de correção ](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) que exigem aprovação para prosseguir.</span><span class="sxs-lookup"><span data-stu-id="e9f71-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="e9f71-108">Por exemplo, um cluster de mensagens de email pode precisar ser excluído, ou talvez seja necessário remover um arquivo em quarentena.</span><span class="sxs-lookup"><span data-stu-id="e9f71-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="e9f71-109">É importante aprovar (ou rejeitar) ações pendentes o mais rápido possível, para que suas investigações automatizadas possam prosseguir e ser concluídas a tempo.</span><span class="sxs-lookup"><span data-stu-id="e9f71-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="e9f71-110">Se você acha que algo foi perdido ou detectado incorretamente por recursos de investigação e resposta automatizados no Microsoft 365 defender, vamos nos lembrar!</span><span class="sxs-lookup"><span data-stu-id="e9f71-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="e9f71-111">Confira [como relatar falsos positivos/negativos em recursos de investigação e resposta automatizados (Air) no Microsoft 365 defender](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="e9f71-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="e9f71-112">Ações pendentes podem ser revisadas e aprovadas usando a [central de ações](#review-a-pending-action-in-the-action-center) ou o [modo de exibição detalhes da investigação](#review-a-pending-action-in-the-investigation-details-view).</span><span class="sxs-lookup"><span data-stu-id="e9f71-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="e9f71-113">Você deve ter [permissões apropriadas](mtp-action-center.md#required-permissions-for-action-center-tasks) para aprovar ou rejeitar ações de correção.</span><span class="sxs-lookup"><span data-stu-id="e9f71-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="e9f71-114">Para obter mais informações, consulte [pré-requisitos para investigação e resposta automatizadas no Microsoft 365 defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="e9f71-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="e9f71-115">Revisar uma ação pendente na Central de Ações</span><span class="sxs-lookup"><span data-stu-id="e9f71-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="e9f71-116">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="e9f71-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="e9f71-117">No painel de navegação, escolha **Central de Ações**.</span><span class="sxs-lookup"><span data-stu-id="e9f71-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="e9f71-118">Em Central de Ações, na guia **Pendente**, selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="e9f71-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="e9f71-119">Se você selecionar um item na coluna **número da investigação**, a página detalhes da investigação será aberta.</span><span class="sxs-lookup"><span data-stu-id="e9f71-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="e9f71-120">Nessa página, você pode checar os resultados da investigação e aprovar ou rejeitar a ação recomendada.</span><span class="sxs-lookup"><span data-stu-id="e9f71-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="e9f71-121">Se você selecionar uma linha na lista, um submenu será aberto, onde serão mostradas informações sobre esse item.</span><span class="sxs-lookup"><span data-stu-id="e9f71-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Aprovar ou rejeitar uma ação](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="e9f71-123">Use os links para exibir um alerta ou uma investigação associada e aprovar ou rejeitar a ação.</span><span class="sxs-lookup"><span data-stu-id="e9f71-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="e9f71-124">Revisar uma ação pendente na exibição dos detalhes da investigação</span><span class="sxs-lookup"><span data-stu-id="e9f71-124">Review a pending action in the investigation details view</span></span>

![Detalhes da investigação](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="e9f71-126">Na página [detalhes da investigação](mtp-autoir-results.md), selecione a guia **Ações pendentes** (ou **Ações**). Os itens pendentes estarão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="e9f71-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="e9f71-127">Selecione um item na lista e, em seguida, escolha **Aprovar** ou **Rejeitar**.</span><span class="sxs-lookup"><span data-stu-id="e9f71-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e9f71-128">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e9f71-128">Next steps</span></span>

- [<span data-ttu-id="e9f71-129">Exibir os detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="e9f71-129">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="e9f71-130">Lidar com falsos positivos/negativos em recursos de investigação e resposta automatizados</span><span class="sxs-lookup"><span data-stu-id="e9f71-130">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
