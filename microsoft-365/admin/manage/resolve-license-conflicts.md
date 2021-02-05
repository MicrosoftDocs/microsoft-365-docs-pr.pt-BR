---
title: Resolver conflitos de licença
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Saiba como resolver conflitos de licença com sua assinatura do Microsoft 365 para empresas.
ms.openlocfilehash: 284a6b169c02314dd2bbd0e13c10c081cb50f58d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114448"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="0a3ae-103">Resolver conflitos de licença</span><span class="sxs-lookup"><span data-stu-id="0a3ae-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0a3ae-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-104">The admin center is changing.</span></span> <span data-ttu-id="0a3ae-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="0a3ae-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="0a3ae-106">Recomendamos que você compre as licenças de que precisa para sua assinatura antes de criar novos usuários.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="0a3ae-107">Dessa forma, uma licença pode ser atribuída a novos usuários conforme as contas de usuário vão sendo criadas.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="0a3ae-108">Se você já tiver atribuído todas as suas licenças aos usuários, mas algumas das licenças tiverem expirado, ou se tentar remover uma licença que já foi atribuída a um usuário, haverá conflitos de licença.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="0a3ae-109">Para obter mais informações, [consulte Remover licenças da sua assinatura.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="0a3ae-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="0a3ae-110">Como faço para exibir conflitos de licença?</span><span class="sxs-lookup"><span data-stu-id="0a3ae-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0a3ae-111">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0a3ae-112">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0a3ae-113">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="0a3ae-114">Verifique a coluna de **Status** para obter informações sobre o conflito.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="0a3ae-115">Se houver um conflito, você verá uma mensagem de aviso informando que um ou mais usuários precisam de uma licença válida.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0a3ae-116">Você não verá a coluna **Status** se não houver conflitos.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="0a3ae-117">Como faço para resolver conflitos de licença?</span><span class="sxs-lookup"><span data-stu-id="0a3ae-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="0a3ae-118">Você pode resolver conflitos de licença comprando mais [licenças](../../commerce/licenses/buy-licenses.md) ou [removendo licenças](remove-licenses-from-users.md)de usuários que não precisam mais delas.</span><span class="sxs-lookup"><span data-stu-id="0a3ae-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="0a3ae-119">Opcionalmente, você pode [excluir uma conta de usuário para liberar uma licença](../add-users/delete-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="0a3ae-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="0a3ae-120">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="0a3ae-120">Related articles</span></span>

[<span data-ttu-id="0a3ae-121">Atribuir licenças a usuários</span><span class="sxs-lookup"><span data-stu-id="0a3ae-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="0a3ae-122">Remover licenças de usuários</span><span class="sxs-lookup"><span data-stu-id="0a3ae-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
