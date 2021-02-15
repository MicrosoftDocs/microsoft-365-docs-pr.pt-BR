---
title: Remover licença de caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Remova a licença de uma caixa de correio compartilhada para atribuí-la a outro usuário. '
ms.openlocfilehash: 11d5185cc3f79899a737ddccc0a93160acb380bc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698298"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="ab1a5-103">Remover uma licença de uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="ab1a5-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ab1a5-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-104">The admin center is changing.</span></span> <span data-ttu-id="ab1a5-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="ab1a5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="ab1a5-106">As caixas de correio compartilhadas geralmente não exigem uma licença.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="ab1a5-107">Siga estas instruções para remover uma licença de uma caixa de correio compartilhada para que você possa atribuí-la a um usuário ou retornar a licença para que você não está pagando por uma licença de que não precisa.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="ab1a5-108">Uma licença é necessária nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="ab1a5-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="ab1a5-109">A caixa de correio compartilhada tem mais de 50 GB de armazenamento em uso.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="ab1a5-110">A caixa de correio compartilhada usa o arquivamento no local.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="ab1a5-111">A caixa de correio compartilhada é colocada em espera de litígio.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-111">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="ab1a5-112">A caixa de correio compartilhada tem uma licença do Microsoft Defender atribuída.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-112">The shared mailbox has a Microsoft Defender license assigned.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="ab1a5-113">Remover a licença</span><span class="sxs-lookup"><span data-stu-id="ab1a5-113">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ab1a5-114">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ab1a5-115">Você precisa remover a licença da página Usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="ab1a5-116">Não é possível remover a licença da página De caixa de correio compartilhada porque as licenças são configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="ab1a5-117">Selecione a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="ab1a5-118">Uma das **guias Licenças e** **Aplicativos, expanda Licenças** e desmarque a caixa da licença que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="ab1a5-119">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="ab1a5-120">Quando você voltar para a **página Usuários ativos,** o status da caixa de correio compartilhada não **será licençada.**</span><span class="sxs-lookup"><span data-stu-id="ab1a5-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="ab1a5-121">Você ainda está pagando pela licença.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-121">You're still paying for the license.</span></span> <span data-ttu-id="ab1a5-122">Para parar de pagar por ela, [remova a licença da sua assinatura.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="ab1a5-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="ab1a5-123">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1a5-124">Você precisa remover a licença da página Usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="ab1a5-125">Não é possível remover a licença da página De caixa de correio compartilhada porque as licenças são configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="ab1a5-126">Selecione a caixa de correio compartilhada e, em seguida, **selecione Editar** ao lado **de licenças de produto.**</span><span class="sxs-lookup"><span data-stu-id="ab1a5-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="ab1a5-127">Uma página **de licenças de** produto, de definir a alternância para **Desligado** para a licença que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="ab1a5-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-128">Select **Save**.</span></span>

5. <span data-ttu-id="ab1a5-129">Quando você voltar para a **página Usuários ativos,** o status da caixa de correio compartilhada não **será licençada.**</span><span class="sxs-lookup"><span data-stu-id="ab1a5-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="ab1a5-130">Você ainda está pagando pela licença.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-130">You're still paying for the license.</span></span> <span data-ttu-id="ab1a5-131">Para parar de pagar por ela, [remova a licença da sua assinatura.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="ab1a5-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="ab1a5-132">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ab1a5-133">Você precisa remover a licença da página Usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="ab1a5-134">Não é possível remover a licença da página De caixa de correio compartilhada porque as licenças são configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="ab1a5-135">Selecione a caixa de correio compartilhada e, em seguida, **selecione Editar** ao lado **de licenças de produto.**</span><span class="sxs-lookup"><span data-stu-id="ab1a5-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="ab1a5-136">Uma página **de licenças de** produto, de definir a alternância para **Desligado** para a licença que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="ab1a5-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-137">Select **Save**.</span></span>

5. <span data-ttu-id="ab1a5-138">Quando você voltar para a **página Usuários ativos,** o status da caixa de correio compartilhada não **será licençada.**</span><span class="sxs-lookup"><span data-stu-id="ab1a5-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="ab1a5-139">Você ainda está pagando pela licença.</span><span class="sxs-lookup"><span data-stu-id="ab1a5-139">You're still paying for the license.</span></span> <span data-ttu-id="ab1a5-140">Para parar de pagar por ela, [remova a licença da sua assinatura.](../../commerce/licenses/remove-licenses-from-subscription.md)</span><span class="sxs-lookup"><span data-stu-id="ab1a5-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

 

## <a name="related-articles"></a><span data-ttu-id="ab1a5-141">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="ab1a5-141">Related articles</span></span>

[<span data-ttu-id="ab1a5-142">Sobre as caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="ab1a5-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="ab1a5-143">Criar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="ab1a5-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="ab1a5-144">Configurar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="ab1a5-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

<span data-ttu-id="ab1a5-145">[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ab1a5-145">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md)</span></span>

[<span data-ttu-id="ab1a5-146">Solucionar problemas com caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="ab1a5-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
