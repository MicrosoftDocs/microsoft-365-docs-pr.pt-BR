---
title: Remover um domínio do Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Saiba como remover um domínio antigo do Office 365 e mover usuários e grupos para outro domínio.
ms.openlocfilehash: 621b50384b39a21bc0bf5256841c703b3ee0f74a
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210363"
---
# <a name="remove-a-domain-from-office-365"></a><span data-ttu-id="9583b-103">Remover um domínio do Office 365</span><span class="sxs-lookup"><span data-stu-id="9583b-103">Remove a domain from Office 365</span></span>

<span data-ttu-id="9583b-104">Colaboradores: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span><span class="sxs-lookup"><span data-stu-id="9583b-104">Contributors: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span></span>
  
 <span data-ttu-id="9583b-105">**[Caso não encontre o conteúdo que está procurando, verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="9583b-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9583b-p101">Você está removendo seu domínio porque deseja adicioná-lo a um plano de assinatura diferente do Office 365 ou deseja apenas cancelar a assinatura? É possível [alterar o plano ou a assinatura](../../commerce/subscriptions/switch-to-a-different-plan.md) ou [cancelar a assinatura](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="9583b-p101">Are you removing your domain because you want to add it to a different Office 365 subscription plan? Or do you just want to cancel your subscription? You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="9583b-109">Etapa 1: mover usuários para outro domínio</span><span class="sxs-lookup"><span data-stu-id="9583b-109">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="9583b-110">Mover usuários</span><span class="sxs-lookup"><span data-stu-id="9583b-110">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="9583b-111">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="9583b-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="9583b-112">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração</a>.</span><span class="sxs-lookup"><span data-stu-id="9583b-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="9583b-113">Selecione usuários **ativos**do **usuário** > .</span><span class="sxs-lookup"><span data-stu-id="9583b-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="9583b-114">Selecione as caixas ao lado dos nomes de todos os usuários que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="9583b-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="9583b-115">Selecione **mais opções** (**...**), na parte superior da página, e, em seguida, escolha **alterar domínios**.</span><span class="sxs-lookup"><span data-stu-id="9583b-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="9583b-116">No painel **alterar domínios** , selecione um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="9583b-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="9583b-p102">Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.</span><span class="sxs-lookup"><span data-stu-id="9583b-p102">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9583b-119">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>.</span><span class="sxs-lookup"><span data-stu-id="9583b-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="9583b-120">Selecione usuários **ativos**do **usuário** > .</span><span class="sxs-lookup"><span data-stu-id="9583b-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="9583b-121">Selecione as caixas ao lado dos nomes de todos os usuários que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="9583b-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="9583b-122">Na parte superior da página, escolha **mais** > **domínios de edição**.</span><span class="sxs-lookup"><span data-stu-id="9583b-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="9583b-123">No painel **Editar domínios** , selecione um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="9583b-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="9583b-p103">Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.</span><span class="sxs-lookup"><span data-stu-id="9583b-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9583b-126">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>.</span><span class="sxs-lookup"><span data-stu-id="9583b-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="9583b-127">Selecione usuários **ativos**do **usuário** > .</span><span class="sxs-lookup"><span data-stu-id="9583b-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="9583b-128">Selecione as caixas ao lado dos nomes de todos os usuários que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="9583b-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="9583b-129">Na parte superior da página, escolha **mais** > **domínios de edição**.</span><span class="sxs-lookup"><span data-stu-id="9583b-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="9583b-130">No painel **Editar domínios** , selecione um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="9583b-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="9583b-p104">Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.</span><span class="sxs-lookup"><span data-stu-id="9583b-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="9583b-133">Mover-se</span><span class="sxs-lookup"><span data-stu-id="9583b-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="9583b-134">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="9583b-134">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="9583b-135">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>.</span><span class="sxs-lookup"><span data-stu-id="9583b-135">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="9583b-136">Vá para usuários **ativos**do **usuário** \> e selecione sua conta na lista.</span><span class="sxs-lookup"><span data-stu-id="9583b-136">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="9583b-137">Na guia **conta** , selecione **gerenciar nome de usuário**e, em seguida, escolha um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="9583b-137">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="9583b-138">Na parte superior **, selecione o**nome da conta e, em seguida, selecione sair.</span><span class="sxs-lookup"><span data-stu-id="9583b-138">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="9583b-139">Entre com o novo domínio e a mesma senha.</span><span class="sxs-lookup"><span data-stu-id="9583b-139">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="9583b-140">Você também pode usar o PowerShell para mover os usuários para outro domínio.</span><span class="sxs-lookup"><span data-stu-id="9583b-140">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="9583b-141">Confira [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9583b-141">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="9583b-142">Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="9583b-142">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9583b-143">Vá para **Users** \> **usuários ativos**do usuário e selecione seu nome na lista.</span><span class="sxs-lookup"><span data-stu-id="9583b-143">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="9583b-144">Na seção **nome de usuário/email** , selecione **Editar**e, em seguida, escolha um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="9583b-144">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="9583b-145">Selecione **definir como fechamento de** > **salvamento** > **Close**principal.</span><span class="sxs-lookup"><span data-stu-id="9583b-145">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="9583b-146">Na parte superior **, selecione o**nome da conta e, em seguida, selecione sair.</span><span class="sxs-lookup"><span data-stu-id="9583b-146">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="9583b-147">Entre com o novo domínio e a mesma senha.</span><span class="sxs-lookup"><span data-stu-id="9583b-147">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="9583b-148">Você também pode usar o PowerShell para mover os usuários para outro domínio.</span><span class="sxs-lookup"><span data-stu-id="9583b-148">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="9583b-149">Confira [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9583b-149">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="9583b-150">Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="9583b-150">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9583b-151">Vá para **Users** \> **usuários ativos**do usuário e selecione seu nome na lista.</span><span class="sxs-lookup"><span data-stu-id="9583b-151">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="9583b-152">Na seção **nome de usuário/email** , selecione **Editar**e, em seguida, escolha um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="9583b-152">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="9583b-153">Selecione **definir como fechamento de** > **salvamento** > **Close**principal.</span><span class="sxs-lookup"><span data-stu-id="9583b-153">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="9583b-154">Na parte superior **, selecione o**nome da conta e, em seguida, selecione sair.</span><span class="sxs-lookup"><span data-stu-id="9583b-154">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="9583b-155">Entre com o novo domínio e a mesma senha.</span><span class="sxs-lookup"><span data-stu-id="9583b-155">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="9583b-156">Você também pode usar o PowerShell para mover os usuários para outro domínio.</span><span class="sxs-lookup"><span data-stu-id="9583b-156">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="9583b-157">Confira [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9583b-157">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="9583b-158">Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="9583b-158">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="9583b-159">Etapa 2: mover grupos para outro domínio</span><span class="sxs-lookup"><span data-stu-id="9583b-159">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9583b-160">No centro de administração, vá para <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">a página grupos</a> de **grupos** \> .</span><span class="sxs-lookup"><span data-stu-id="9583b-160">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="9583b-161">Selecione o nome do grupo e, na guia **geral** , em **endereço de email, principal**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9583b-161">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="9583b-162">Use a lista suspensa para escolher outro domínio.</span><span class="sxs-lookup"><span data-stu-id="9583b-162">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="9583b-163">Selecione **Salvar**, **Feche**.</span><span class="sxs-lookup"><span data-stu-id="9583b-163">Select **Save**, then **Close**.</span></span> <span data-ttu-id="9583b-164">Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="9583b-164">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9583b-165">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, vá para **a página grupos** de **grupos** > .</span><span class="sxs-lookup"><span data-stu-id="9583b-165">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="9583b-166">Selecione o nome do grupo e, em seguida, selecione **Editar** ao lado de **nome**.</span><span class="sxs-lookup"><span data-stu-id="9583b-166">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="9583b-167">Use a lista suspensa para escolher outro domínio.</span><span class="sxs-lookup"><span data-stu-id="9583b-167">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="9583b-168">Selecione **Salvar**, **Feche**.</span><span class="sxs-lookup"><span data-stu-id="9583b-168">Select **Save**, then **Close**.</span></span> <span data-ttu-id="9583b-169">Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="9583b-169">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9583b-170">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, vá para **a página grupos** de **grupos** > .</span><span class="sxs-lookup"><span data-stu-id="9583b-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="9583b-171">Selecione o nome do grupo e, em seguida, selecione **Editar** ao lado de **nome**.</span><span class="sxs-lookup"><span data-stu-id="9583b-171">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="9583b-172">Use a lista suspensa para escolher outro domínio.</span><span class="sxs-lookup"><span data-stu-id="9583b-172">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="9583b-173">Selecione **Salvar**, **Feche**.</span><span class="sxs-lookup"><span data-stu-id="9583b-173">Select **Save**, then **Close**.</span></span> <span data-ttu-id="9583b-174">Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="9583b-174">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="9583b-175">Etapa 3: remover o domínio antigo</span><span class="sxs-lookup"><span data-stu-id="9583b-175">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="9583b-176">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="9583b-176">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="9583b-177">No centro de administração, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="9583b-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="9583b-178">No centro de administração, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="9583b-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="9583b-179">Na página **domínios** , selecione o domínio que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="9583b-179">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="9583b-180">No painel direito, selecione **remover**.</span><span class="sxs-lookup"><span data-stu-id="9583b-180">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="9583b-181">Siga os avisos adicionais e selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="9583b-181">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="9583b-182">Quanto tempo leva para um domínio ser removido?</span><span class="sxs-lookup"><span data-stu-id="9583b-182">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="9583b-183">Pode levar apenas 5 minutos para que o Office 365 remova um domínio se ele não for referenciado em muitos lugares, como grupos de segurança, listas de distribuição, usuários e grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9583b-183">It can take as little as 5 minutes for Office 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Office 365 groups.</span></span> <span data-ttu-id="9583b-184">Se há muitas referências que usam o domínio, pode levar várias horas (um dia) para que ele seja removido.</span><span class="sxs-lookup"><span data-stu-id="9583b-184">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="9583b-p112">Se você tem centenas ou milhares de usuários, use o PowerShell para fazer uma consulta de todos os usuários e mova-os para outro domínio. Caso contrário, é possível que alguns usuários fiquem de fora da interface e, quando você tentar remover o domínio, não conseguirá e não saberá por quê. Saiba mais em [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="9583b-p112">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="9583b-189">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="9583b-189">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="9583b-190">Você não pode remover o domínio [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) da sua conta.</span><span class="sxs-lookup"><span data-stu-id="9583b-190">You can't remove the [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) domain from your account.</span></span>
  
<span data-ttu-id="9583b-p113">Ainda não funciona? É possível que seja necessário remover seu domínio manualmente. [Ligue para nós](../contact-support-for-business-products.md). Ajudaremos você com essa questão!</span><span class="sxs-lookup"><span data-stu-id="9583b-p113">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="9583b-194">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="9583b-194">Related articles</span></span>

[<span data-ttu-id="9583b-195">Perguntas frequentes sobre domínios</span><span class="sxs-lookup"><span data-stu-id="9583b-195">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="9583b-196">Obter ajuda com os domínios do Office 365</span><span class="sxs-lookup"><span data-stu-id="9583b-196">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="9583b-197">Migrar para outro plano do Office 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="9583b-197">Switch to a different Office 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="9583b-198">Cancelar sua assinatura</span><span class="sxs-lookup"><span data-stu-id="9583b-198">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
