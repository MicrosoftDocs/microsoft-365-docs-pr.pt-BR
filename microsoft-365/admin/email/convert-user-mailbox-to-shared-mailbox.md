---
title: Converter uma caixa de correio do usuário em uma caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Saiba como converter uma caixa de correio privada em uma caixa de correio compartilhada que pode ser acessada por vários usuários. '
ms.openlocfilehash: a4b2e9ce53051feb07ea035adc0c959bbb1a0948
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521024"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="e5bb3-103">Converter uma caixa de correio do usuário em uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="e5bb3-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="e5bb3-104">Quando você converte a caixa de correio de um usuário em uma caixa de correio compartilhada, todos os emails e calendários existentes são mantidos.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="e5bb3-105">Agora, ela está em uma caixa de correio compartilhada onde várias pessoas poderão acessá-la, em vez de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="e5bb3-106">Em uma data posterior, você pode converter uma caixa de correio compartilhada de volta para uma caixa de correio de usuário (privada).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="e5bb3-107">**Veja algumas coisas realmente importantes que você precisa saber:**</span><span class="sxs-lookup"><span data-stu-id="e5bb3-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="e5bb3-108">A caixa de correio do usuário que você está convertendo precisa de uma licença atribuída a ele antes de convertê-lo em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="e5bb3-109">Caso contrário, você não verá a opção de converter a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="e5bb3-110">Se você tiver removido a licença, adicione-a de volta para que possa converter a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="e5bb3-111">Após converter a caixa de correio para uma compartilhada, você pode remover a licença da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="e5bb3-112">Caixas de correio compartilhadas podem ter até 50 GB de dados sem uma licença atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="e5bb3-113">Para armazenar mais dados do que isso, você precisa de uma licença atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="e5bb3-114">Você pode precisar excluir um monte de emails grandes (digamos, aqueles com anexos) da caixa de correio compartilhada para diminuí-lo para que você possa remover a licença.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="e5bb3-115">Não exclua a conta do usuário antigo.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-115">Don't delete the old user's account.</span></span> <span data-ttu-id="e5bb3-116">Isso é necessário para ancorar a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="e5bb3-117">Se você já tiver excluído a conta de usuário, consulte [converter a caixa de correio de um usuário excluído](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="e5bb3-118">As regras ficam intactas após a conversão da caixa de correio em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="e5bb3-119">Usar o centro de administração do Exchange para converter uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="e5bb3-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="e5bb3-120">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="e5bb3-121">Selecionar **Recipients** \> **caixas de correio**de destinatários.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="e5bb3-122">Selecione a caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-122">Select the user mailbox.</span></span> <span data-ttu-id="e5bb3-123">Em **converter em caixa de correio compartilhada**, selecione **converter**.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="e5bb3-124">Se a caixa de correio for menor do que 50 GB, você poderá remover a [licença do usuário](../manage/remove-licenses-from-users.md)e deixar de pagar por ela.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="e5bb3-125">Não exclua a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-125">Don't delete the user's account.</span></span> <span data-ttu-id="e5bb3-126">A caixa de correio compartilhada precisa dela como uma âncora.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="e5bb3-127">Se estiver convertendo a caixa de correio de um funcionário que está saindo da sua organização, você deve executar etapas adicionais para garantir que eles não consigam mais fazer logon.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="e5bb3-128">Confira [remover um antigo funcionário da Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="e5bb3-129">Para tudo o que você precisa saber sobre caixas de correio compartilhadas, consulte [sobre caixas de correio](about-shared-mailboxes.md) compartilhadas e [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="e5bb3-130">Usar o centro de administração do Microsoft 365 para converter uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="e5bb3-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e5bb3-131">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="e5bb3-132">Selecione o nome do usuário cuja caixa de correio você deseja converter.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="e5bb3-133">Redefinir a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-133">Reset the user's password.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e5bb3-134">Não é necessário redefinir a senha do usuário durante a conversão da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="e5bb3-135">No entanto, se a senha não for redefinida, **o nome de usuário e a senha originais continuarão funcionando** após a conclusão da conversão da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="e5bb3-136">Na guia **email** , em **mais ações**, selecione **converter para caixa de correio compartilhada**.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e5bb3-137">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="e5bb3-138">Selecione o usuário cuja caixa de correio você deseja converter.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="e5bb3-139">No painel direito, expanda **configurações de email**.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="e5bb3-140">Ao lado de **mais configurações**, selecione **converter para caixa de correio compartilhada**.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e5bb3-141">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="e5bb3-142">Selecione o usuário cuja caixa de correio você deseja converter.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="e5bb3-143">No painel direito, expanda **configurações de email**.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="e5bb3-144">Ao lado de **mais configurações**, selecione **converter para caixa de correio compartilhada**.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="e5bb3-145">Se a caixa de correio for menor do que 50 GB, você poderá [remover a licença do usuário](../manage/remove-licenses-from-users.md)e deixar de pagar por ela.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-145">If the mailbox is smaller than 50 GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="e5bb3-146">Não exclua a caixa de correio antiga do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="e5bb3-147">A caixa de correio compartilhada precisa dela como uma âncora.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="e5bb3-148">Se estiver convertendo a caixa de correio de um funcionário que está saindo da sua organização, você deve executar etapas adicionais para garantir que eles não consigam mais fazer logon.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="e5bb3-149">Confira [remover um antigo funcionário da Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="e5bb3-150">Para tudo o que você precisa saber sobre caixas de correio compartilhadas, consulte [sobre caixas de correio](about-shared-mailboxes.md) compartilhadas e [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e5bb3-151">Caixas de correio compartilhadas não exigem uma licença separada.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-151">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="e5bb3-152">No entanto, se você deseja habilitar o arquivo morto in-loco ou colocar um bloqueio in-loco ou uma retenção de litígio em uma caixa de correio compartilhada, você deve atribuir uma licença do Exchange Online Plan 1 com o arquivamento do Exchange Online ou do Exchange Online Plan 2 à caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-152">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="e5bb3-153">Converter a caixa de correio de um usuário excluído</span><span class="sxs-lookup"><span data-stu-id="e5bb3-153">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="e5bb3-154">Digamos que você tenha excluído uma conta de usuário e agora deseja converter sua caixa de correio antiga para uma caixa de correio de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-154">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="e5bb3-155">Veja o que você precisa fazer:</span><span class="sxs-lookup"><span data-stu-id="e5bb3-155">Here's what you need to do:</span></span>

1. <span data-ttu-id="e5bb3-156">[Restaure a conta do usuário](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-156">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="e5bb3-157">Verifique se uma licença da Microsoft 365 está atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-157">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="e5bb3-158">Redefinir a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-158">Reset the user's password.</span></span>
    
4. <span data-ttu-id="e5bb3-159">Aguarde 20-30 minutos para que a caixa de correio seja recriada.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-159">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="e5bb3-160">Agora siga as instruções nesta página para converter a caixa de correio em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-160">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="e5bb3-161">Depois disso, você pode remover a licença da caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-161">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="e5bb3-162">Não exclua a caixa de correio antiga do usuário.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-162">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="e5bb3-163">A caixa de correio compartilhada precisa dela como uma âncora.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-163">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="e5bb3-164">Adicionar membros à caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-164">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="e5bb3-165">Converter uma caixa de correio compartilhada de volta para a caixa de correio de um usuário (privado)</span><span class="sxs-lookup"><span data-stu-id="e5bb3-165">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="e5bb3-166">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-166">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="e5bb3-167">Selecione **destinatários** \> **compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-167">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="e5bb3-168">Selecione a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-168">Select the shared mailbox.</span></span> <span data-ttu-id="e5bb3-169">Em **converter em caixa de correio normal**, selecione **converter**.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-169">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="e5bb3-170">Volte para o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-170">Go back to the admin center.</span></span> <span data-ttu-id="e5bb3-171">Em **usuários**, escolha a conta de usuário associada à caixa de correio compartilhada antiga.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-171">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="e5bb3-172">Atribua uma licença à conta e redefina a senha.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-172">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="e5bb3-173">Levará alguns minutos para que a caixa de correio seja configurada, mas depois dela, a pessoa que usará a conta está pronta para começar.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-173">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="e5bb3-174">Quando eles entrarem, eles verão os itens de email e calendário que usaram a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-174">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="e5bb3-175">Converter a caixa de correio de um usuário em um ambiente híbrido</span><span class="sxs-lookup"><span data-stu-id="e5bb3-175">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="e5bb3-176">Se essa caixa de correio compartilhada estiver em um ambiente híbrido, **recomendamos enfaticamente** (quase exigir!) que você mova a caixa de correio do usuário de volta para o local, converta a caixa de correio do usuário em uma caixa de correio compartilhada e, em seguida, mova a caixa de correio compartilhada de volta para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-176">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="e5bb3-177">Veja por quê: se você converter a caixa de correio na nuvem, ela poderá ser convertida, mas o local ainda acha que a caixa de correio é a caixa de correio do usuário, porque a nova realidade não é sincronizada para o local.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-177">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="e5bb3-178">Normalmente, isso não é um problema, mas há alguns cenários em que os atributos locais (que acreditam que a caixa de correio é a caixa de correio do usuário) podem substituir as novas versões de nuvem desses atributos e, como resultado, a caixa de correio pode ser convertida novamente.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-178">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="e5bb3-179">Isso é um problema porque as caixas de correio do usuário exigem licenças **ou são excluídas de forma reversível após 30 dias**!</span><span class="sxs-lookup"><span data-stu-id="e5bb3-179">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="e5bb3-180">Abordamos a maioria dos motivos pelos quais isso acontece, mas ele ainda pode acontecer, embora com frequência.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-180">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="e5bb3-181">É melhor ser seguro e mover a caixa de correio de volta para o local, convertê-la e, em seguida, mover a caixa de correio compartilhada de volta para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-181">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="e5bb3-182">Essa solução recomendada não está violando o contrato de licenciamento para ambientes híbridos porque a existência da caixa de correio de usuário local é apenas temporária.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-182">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="e5bb3-183">Você estaria violando sua licença se manteve a caixa de correio do usuário ou a caixa de correio compartilhada em sua organização local e não a moveu de volta para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-183">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="e5bb3-184">Se você é membro do grupo de funções Gerenciamento da organização ou gerenciamento de destinatários, você pode usar o Shell de gerenciamento do Exchange para alterar uma caixa de correio de usuário para uma caixa de correio compartilhada no local.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-184">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="e5bb3-185">Por exemplo, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="e5bb3-185">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="e5bb3-186">Consulte a solução alternativa nesta solução de suporte para instâncias quando [caixas de correio compartilhadas são convertidas inesperadamente em caixas de correio de usuários](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span><span class="sxs-lookup"><span data-stu-id="e5bb3-186">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="e5bb3-187">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="e5bb3-187">Related articles</span></span>

[<span data-ttu-id="e5bb3-188">Sobre as caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="e5bb3-188">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="e5bb3-189">Criar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="e5bb3-189">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="e5bb3-190">Configurar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="e5bb3-190">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="e5bb3-191">Remover uma licença de uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="e5bb3-191">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="e5bb3-192">Solucionar problemas com caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="e5bb3-192">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
