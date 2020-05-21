---
title: Remover licença de caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Remover a licença de uma caixa de correio compartilhada para atribuí-la a outro usuário. '
ms.openlocfilehash: 9ba411c614fee93e37ac45e58fd40bf246a9c2ab
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327237"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="87abd-103">Remover uma licença de uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="87abd-103">Remove a license from a shared mailbox</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="87abd-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="87abd-104">The admin center is changing.</span></span> <span data-ttu-id="87abd-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="87abd-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="87abd-106">Caixas de correio compartilhadas normalmente não exigem uma licença.</span><span class="sxs-lookup"><span data-stu-id="87abd-106">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="87abd-107">Siga estas instruções para remover uma licença de uma caixa de correio compartilhada para que você possa atribuí-la a um usuário ou retorná-la para que não esteja pagando por uma licença desnecessária.</span><span class="sxs-lookup"><span data-stu-id="87abd-107">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
> <span data-ttu-id="87abd-108">É necessário ter uma licença nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="87abd-108">A license is required in the following scenarios:</span></span>
> 1. <span data-ttu-id="87abd-109">A caixa de correio compartilhada tem mais de 50 GB de armazenamento em uso.</span><span class="sxs-lookup"><span data-stu-id="87abd-109">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="87abd-110">A caixa de correio compartilhada usa arquivamento in-loco.</span><span class="sxs-lookup"><span data-stu-id="87abd-110">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="87abd-111">A caixa de correio compartilhada é colocada em retenção de litígio.</span><span class="sxs-lookup"><span data-stu-id="87abd-111">The shared mailbox is placed in litigation hold.</span></span>

  
## <a name="remove-the-license"></a><span data-ttu-id="87abd-112">Remover a licença</span><span class="sxs-lookup"><span data-stu-id="87abd-112">Remove the license</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="87abd-113">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="87abd-113">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="87abd-114">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="87abd-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="87abd-115">Você precisa remover a licença da página usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="87abd-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="87abd-116">Você não pode remover a licença da página de caixa de correio compartilhada, pois as licenças são configurações de usuário.</span><span class="sxs-lookup"><span data-stu-id="87abd-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span> 
  
2. <span data-ttu-id="87abd-117">Selecione a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="87abd-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="87abd-118">Uma guia **licenças e aplicativos** , expanda **licenças** e desmarque a caixa da licença que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="87abd-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="87abd-119">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="87abd-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="87abd-120">Quando você retornar à página **usuários ativos** , o status da caixa de correio compartilhada será sem **licença**.</span><span class="sxs-lookup"><span data-stu-id="87abd-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="87abd-121">Você ainda está pagando pela licença.</span><span class="sxs-lookup"><span data-stu-id="87abd-121">You're still paying for the license.</span></span> <span data-ttu-id="87abd-122">Para parar de pagar, [remova a licença da sua assinatura](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="87abd-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="87abd-123">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="87abd-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="87abd-124">Você precisa remover a licença da página usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="87abd-124">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="87abd-125">Você não pode remover a licença da página de caixa de correio compartilhada, pois as licenças são configurações de usuário.</span><span class="sxs-lookup"><span data-stu-id="87abd-125">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="87abd-126">Selecione a caixa de correio compartilhada e, em seguida, selecione **Editar** ao lado de **licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="87abd-126">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="87abd-127">Uma página de **licenças de produto** , defina a **opção** de alternância para a licença que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="87abd-127">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="87abd-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="87abd-128">Select **Save**.</span></span>

5. <span data-ttu-id="87abd-129">Quando você retornar à página **usuários ativos** , o status da caixa de correio compartilhada será sem **licença**.</span><span class="sxs-lookup"><span data-stu-id="87abd-129">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="87abd-130">Você ainda está pagando pela licença.</span><span class="sxs-lookup"><span data-stu-id="87abd-130">You're still paying for the license.</span></span> <span data-ttu-id="87abd-131">Para parar de pagar, [remova a licença da sua assinatura](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="87abd-131">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="87abd-132">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="87abd-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

   > [!NOTE]
   > <span data-ttu-id="87abd-133">Você precisa remover a licença da página usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="87abd-133">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="87abd-134">Você não pode remover a licença da página de caixa de correio compartilhada, pois as licenças são configurações de usuário.</span><span class="sxs-lookup"><span data-stu-id="87abd-134">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>

2. <span data-ttu-id="87abd-135">Selecione a caixa de correio compartilhada e, em seguida, selecione **Editar** ao lado de **licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="87abd-135">Select the shared mailbox, and then select **Edit** next to **Product licenses**.</span></span>

3. <span data-ttu-id="87abd-136">Uma página de **licenças de produto** , defina a **opção** de alternância para a licença que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="87abd-136">One the **Product licenses** page, set the toggle to **Off** for the license you want to remove.</span></span>

4. <span data-ttu-id="87abd-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="87abd-137">Select **Save**.</span></span>

5. <span data-ttu-id="87abd-138">Quando você retornar à página **usuários ativos** , o status da caixa de correio compartilhada será sem **licença**.</span><span class="sxs-lookup"><span data-stu-id="87abd-138">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="87abd-139">Você ainda está pagando pela licença.</span><span class="sxs-lookup"><span data-stu-id="87abd-139">You're still paying for the license.</span></span> <span data-ttu-id="87abd-140">Para parar de pagar, [remova a licença da sua assinatura](../../commerce/licenses/remove-licenses-from-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="87abd-140">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>

::: moniker-end 

## <a name="related-articles"></a><span data-ttu-id="87abd-141">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="87abd-141">Related articles</span></span>

[<span data-ttu-id="87abd-142">Sobre as caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="87abd-142">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="87abd-143">Criar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="87abd-143">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="87abd-144">Configurar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="87abd-144">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

<span data-ttu-id="87abd-145">[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="87abd-145">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md)</span></span>

[<span data-ttu-id="87abd-146">Solucionar problemas com caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="87abd-146">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
