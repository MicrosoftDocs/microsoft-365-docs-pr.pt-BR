---
title: Excluir um domínio
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Saiba como remover um domínio antigo do Microsoft 365 e mover usuários e grupos para outro domínio.
ms.openlocfilehash: c5e629f0d683c6dc3e18b1278027ac3a88cc834b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399891"
---
# <a name="remove-a-domain"></a><span data-ttu-id="7942f-103">Excluir um domínio</span><span class="sxs-lookup"><span data-stu-id="7942f-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7942f-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="7942f-104">The admin center is changing.</span></span> <span data-ttu-id="7942f-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="7942f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="7942f-106">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="7942f-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7942f-107">Você está removendo seu domínio porque deseja adicioná-lo a um plano de assinatura diferente do Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="7942f-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="7942f-108">Ou apenas deseja cancelar sua assinatura?</span><span class="sxs-lookup"><span data-stu-id="7942f-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="7942f-109">Você pode [alterar seu plano ou assinatura](../../commerce/subscriptions/switch-to-a-different-plan.md) ou [cancelar sua assinatura](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="7942f-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="7942f-110">Etapa 1: mover usuários para outro domínio</span><span class="sxs-lookup"><span data-stu-id="7942f-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="7942f-111">Mover usuários</span><span class="sxs-lookup"><span data-stu-id="7942f-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="7942f-112">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="7942f-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="7942f-113">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração</a>.</span><span class="sxs-lookup"><span data-stu-id="7942f-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="7942f-114">Selecione usuários ativos do **usuário** > **Active users**.</span><span class="sxs-lookup"><span data-stu-id="7942f-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="7942f-115">Selecione as caixas ao lado dos nomes de todos os usuários que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="7942f-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="7942f-116">Selecione **mais opções** (**...**), na parte superior da página, e, em seguida, escolha **alterar domínios**.</span><span class="sxs-lookup"><span data-stu-id="7942f-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="7942f-117">No painel **alterar domínios** , selecione um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="7942f-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="7942f-p103">Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.</span><span class="sxs-lookup"><span data-stu-id="7942f-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7942f-120">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>.</span><span class="sxs-lookup"><span data-stu-id="7942f-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="7942f-121">Selecione usuários ativos do **usuário** > **Active users**.</span><span class="sxs-lookup"><span data-stu-id="7942f-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="7942f-122">Selecione as caixas ao lado dos nomes de todos os usuários que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="7942f-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="7942f-123">Na parte superior da página, escolha **mais** > **domínios de edição**.</span><span class="sxs-lookup"><span data-stu-id="7942f-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="7942f-124">No painel **Editar domínios** , selecione um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="7942f-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="7942f-p104">Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.</span><span class="sxs-lookup"><span data-stu-id="7942f-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7942f-127">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>.</span><span class="sxs-lookup"><span data-stu-id="7942f-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="7942f-128">Selecione usuários ativos do **usuário** > **Active users**.</span><span class="sxs-lookup"><span data-stu-id="7942f-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="7942f-129">Selecione as caixas ao lado dos nomes de todos os usuários que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="7942f-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="7942f-130">Na parte superior da página, escolha **mais** > **domínios de edição**.</span><span class="sxs-lookup"><span data-stu-id="7942f-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="7942f-131">No painel **Editar domínios** , selecione um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="7942f-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="7942f-p105">Será preciso fazer o mesmo para você, caso esteja no domínio que deseja remover. Ao editar o domínio para sua conta, será preciso se desconectar e conectar novamente usando o novo domínio que você escolheu para continuar.</span><span class="sxs-lookup"><span data-stu-id="7942f-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="7942f-134">Mover-se</span><span class="sxs-lookup"><span data-stu-id="7942f-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="7942f-135">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="7942f-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="7942f-136">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>.</span><span class="sxs-lookup"><span data-stu-id="7942f-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="7942f-137">Vá para usuários ativos do **usuário** \> **Active Users**e selecione sua conta na lista.</span><span class="sxs-lookup"><span data-stu-id="7942f-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="7942f-138">Na guia **conta** , selecione **gerenciar nome de usuário**e, em seguida, escolha um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="7942f-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="7942f-139">Na parte superior **, selecione o**nome da conta e, em seguida, selecione sair.</span><span class="sxs-lookup"><span data-stu-id="7942f-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="7942f-140">Entre com o novo domínio e a mesma senha.</span><span class="sxs-lookup"><span data-stu-id="7942f-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="7942f-141">Você também pode usar o PowerShell para mover os usuários para outro domínio.</span><span class="sxs-lookup"><span data-stu-id="7942f-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="7942f-142">Confira [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="7942f-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="7942f-143">Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="7942f-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7942f-144">Vá para **Users** \> **usuários ativos**do usuário e selecione seu nome na lista.</span><span class="sxs-lookup"><span data-stu-id="7942f-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="7942f-145">Na seção **nome de usuário/email** , selecione **Editar**e, em seguida, escolha um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="7942f-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="7942f-146">Selecione **definir como fechamento de** > **salvamento** principal > **Close**.</span><span class="sxs-lookup"><span data-stu-id="7942f-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="7942f-147">Na parte superior **, selecione o**nome da conta e, em seguida, selecione sair.</span><span class="sxs-lookup"><span data-stu-id="7942f-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="7942f-148">Entre com o novo domínio e a mesma senha.</span><span class="sxs-lookup"><span data-stu-id="7942f-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="7942f-149">Você também pode usar o PowerShell para mover os usuários para outro domínio.</span><span class="sxs-lookup"><span data-stu-id="7942f-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="7942f-150">Confira [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="7942f-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="7942f-151">Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="7942f-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7942f-152">Vá para **Users** \> **usuários ativos**do usuário e selecione seu nome na lista.</span><span class="sxs-lookup"><span data-stu-id="7942f-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="7942f-153">Na seção **nome de usuário/email** , selecione **Editar**e, em seguida, escolha um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="7942f-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="7942f-154">Selecione **definir como fechamento de** > **salvamento** principal > **Close**.</span><span class="sxs-lookup"><span data-stu-id="7942f-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="7942f-155">Na parte superior **, selecione o**nome da conta e, em seguida, selecione sair.</span><span class="sxs-lookup"><span data-stu-id="7942f-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="7942f-156">Entre com o novo domínio e a mesma senha.</span><span class="sxs-lookup"><span data-stu-id="7942f-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="7942f-157">Você também pode usar o PowerShell para mover os usuários para outro domínio.</span><span class="sxs-lookup"><span data-stu-id="7942f-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="7942f-158">Confira [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="7942f-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="7942f-159">Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="7942f-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="7942f-160">Etapa 2: mover grupos para outro domínio</span><span class="sxs-lookup"><span data-stu-id="7942f-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7942f-161">No centro de administração, vá para a página grupos de **grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="7942f-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="7942f-162">Selecione o nome do grupo e, na guia **geral** , em **endereço de email, principal**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7942f-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="7942f-163">Use a lista suspensa para escolher outro domínio.</span><span class="sxs-lookup"><span data-stu-id="7942f-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="7942f-164">Selecione **Salvar**, **Feche**.</span><span class="sxs-lookup"><span data-stu-id="7942f-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="7942f-165">Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="7942f-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7942f-166">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, vá para a página grupos de **grupos** > **Groups** .</span><span class="sxs-lookup"><span data-stu-id="7942f-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="7942f-167">Selecione o nome do grupo e, em seguida, selecione **Editar** ao lado de **nome**.</span><span class="sxs-lookup"><span data-stu-id="7942f-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="7942f-168">Use a lista suspensa para escolher outro domínio.</span><span class="sxs-lookup"><span data-stu-id="7942f-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="7942f-169">Selecione **Salvar**, **Feche**.</span><span class="sxs-lookup"><span data-stu-id="7942f-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="7942f-170">Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="7942f-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7942f-171">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, vá para a página grupos de **grupos** > **Groups** .</span><span class="sxs-lookup"><span data-stu-id="7942f-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="7942f-172">Selecione o nome do grupo e, em seguida, selecione **Editar** ao lado de **nome**.</span><span class="sxs-lookup"><span data-stu-id="7942f-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="7942f-173">Use a lista suspensa para escolher outro domínio.</span><span class="sxs-lookup"><span data-stu-id="7942f-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="7942f-174">Selecione **Salvar**, **Feche**.</span><span class="sxs-lookup"><span data-stu-id="7942f-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="7942f-175">Repita esse processo para qualquer grupo ou lista de distribuição associada ao domínio que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="7942f-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="7942f-176">Etapa 3: remover o domínio antigo</span><span class="sxs-lookup"><span data-stu-id="7942f-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7942f-177">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="7942f-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7942f-178">No centro de administração, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="7942f-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7942f-179">No centro de administração, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="7942f-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="7942f-180">Na página **domínios** , selecione o domínio que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="7942f-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="7942f-181">No painel direito, selecione **remover**.</span><span class="sxs-lookup"><span data-stu-id="7942f-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="7942f-182">Siga os avisos adicionais e selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="7942f-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="7942f-183">Quanto tempo leva para um domínio ser removido?</span><span class="sxs-lookup"><span data-stu-id="7942f-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="7942f-184">Pode levar até 5 minutos para que o Microsoft 365 remova um domínio, caso não seja mencionado em muitos lugares, como grupos de segurança, listas de distribuição, usuários e grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7942f-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="7942f-185">Se há muitas referências que usam o domínio, pode levar várias horas (um dia) para que ele seja removido.</span><span class="sxs-lookup"><span data-stu-id="7942f-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="7942f-p113">Se você tem centenas ou milhares de usuários, use o PowerShell para fazer uma consulta de todos os usuários e mova-os para outro domínio. Caso contrário, é possível que alguns usuários fiquem de fora da interface e, quando você tentar remover o domínio, não conseguirá e não saberá por quê. Saiba mais em [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Para definir o domínio padrão, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="7942f-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="7942f-190">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="7942f-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="7942f-191">Você não pode remover o domínio [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) da sua conta.</span><span class="sxs-lookup"><span data-stu-id="7942f-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="7942f-p114">Ainda não funciona? É possível que seja necessário remover seu domínio manualmente. [Ligue para nós](../contact-support-for-business-products.md). Ajudaremos você com essa questão!</span><span class="sxs-lookup"><span data-stu-id="7942f-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="7942f-195">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="7942f-195">Related articles</span></span>

[<span data-ttu-id="7942f-196">Perguntas frequentes sobre domínios</span><span class="sxs-lookup"><span data-stu-id="7942f-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="7942f-197">Obter ajuda com os domínios do Office 365</span><span class="sxs-lookup"><span data-stu-id="7942f-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="7942f-198">Mudar para outro plano do Microsoft 365 for business</span><span class="sxs-lookup"><span data-stu-id="7942f-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="7942f-199">Cancelar sua assinatura</span><span class="sxs-lookup"><span data-stu-id="7942f-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
