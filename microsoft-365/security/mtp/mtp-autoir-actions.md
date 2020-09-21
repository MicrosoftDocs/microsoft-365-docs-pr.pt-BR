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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: d7739ac6184509abe4df3aaf140db66f6039717c
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962648"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="8c850-104">Aprovar ou rejeitar ações pendentes após uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="8c850-104">Approve or reject pending actions following an automated investigation</span></span>

<span data-ttu-id="8c850-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8c850-105">**Applies to:**</span></span>
- <span data-ttu-id="8c850-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8c850-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8c850-107">Quando uma investigação automatizada é executada, pode resultar em uma ou mais [ações de correção ](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) que exigem aprovação para prosseguir.</span><span class="sxs-lookup"><span data-stu-id="8c850-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="8c850-108">Por exemplo, um cluster de mensagens de email pode precisar ser excluído, ou talvez seja necessário remover um arquivo em quarentena.</span><span class="sxs-lookup"><span data-stu-id="8c850-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="8c850-109">É importante aprovar (ou rejeitar) ações pendentes o mais rápido possível, para que suas investigações automatizadas possam prosseguir e ser concluídas a tempo.</span><span class="sxs-lookup"><span data-stu-id="8c850-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="8c850-110">Se você acha que algo foi perdido ou detectado incorretamente por recursos de investigação e resposta automatizados na proteção contra ameaças da Microsoft, vamos nos lembrar!</span><span class="sxs-lookup"><span data-stu-id="8c850-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="8c850-111">Veja [como relatar falsos positivos/negativos em recursos de investigação e resposta automatizados (Air) no Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="8c850-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="8c850-112">Ações pendentes podem ser revisadas e aprovadas usando a [central de ações](#review-a-pending-action-in-the-action-center) ou o [modo de exibição detalhes da investigação](#review-a-pending-action-in-the-investigation-details-view).</span><span class="sxs-lookup"><span data-stu-id="8c850-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="8c850-113">Você deve ter [permissões apropriadas](mtp-action-center.md#required-permissions-for-action-center-tasks) para aprovar ou rejeitar ações de correção.</span><span class="sxs-lookup"><span data-stu-id="8c850-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="8c850-114">Revisar uma ação pendente na Central de Ações</span><span class="sxs-lookup"><span data-stu-id="8c850-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="8c850-115">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="8c850-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="8c850-116">No painel de navegação, escolha **Central de Ações**.</span><span class="sxs-lookup"><span data-stu-id="8c850-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="8c850-117">Em Central de Ações, na guia **Pendente**, selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="8c850-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="8c850-118">Se você selecionar um item na coluna\*\*número da investigação \*\*, a página detalhes da investigação será aberta.</span><span class="sxs-lookup"><span data-stu-id="8c850-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="8c850-119">Nessa página, você pode checar os resultados da investigação e aprovar ou rejeitar a ação recomendada.</span><span class="sxs-lookup"><span data-stu-id="8c850-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="8c850-120">Se você selecionar uma linha na lista, um submenu será aberto, onde serão mostradas informações sobre esse item.</span><span class="sxs-lookup"><span data-stu-id="8c850-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Aprovar ou rejeitar uma ação](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="8c850-122">Use os links para exibir um alerta ou uma investigação associada e aprovar ou rejeitar a ação.</span><span class="sxs-lookup"><span data-stu-id="8c850-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="8c850-123">Revisar uma ação pendente na exibição dos detalhes da investigação</span><span class="sxs-lookup"><span data-stu-id="8c850-123">Review a pending action in the investigation details view</span></span>

![Detalhes da investigação](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="8c850-125">Na página [detalhes da investigação](mtp-autoir-results.md), selecione a guia **Ações pendentes** (ou **Ações**). Os itens pendentes estarão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="8c850-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="8c850-126">Selecione um item na lista e, em seguida, escolha **Aprovar** ou **Rejeitar**.</span><span class="sxs-lookup"><span data-stu-id="8c850-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8c850-127">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8c850-127">Next steps</span></span>

- [<span data-ttu-id="8c850-128">Exibir os detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="8c850-128">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="8c850-129">Lidar com falsos positivos/negativos em recursos de investigação e resposta automatizados</span><span class="sxs-lookup"><span data-stu-id="8c850-129">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
