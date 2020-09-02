---
title: Adicionar espaço de armazenamento para sua assinatura
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
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Saiba como adicionar e reduzir o armazenamento de arquivos em sua assinatura do Microsoft 365. Com o armazenamento de arquivos extra, você pode armazenar mais conteúdo no SharePoint Online e no OneDrive.
ms.date: ''
ms.openlocfilehash: 7f9973054bfe97beae36e28b73a3eb2025a13e73
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324463"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="e6a62-104">Adicionar espaço de armazenamento para sua assinatura</span><span class="sxs-lookup"><span data-stu-id="e6a62-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e6a62-105">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="e6a62-105">The admin center is changing.</span></span> <span data-ttu-id="e6a62-106">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e6a62-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e6a62-107">Se você começar a ficar sem armazenamento para seus conjuntos de sites do SharePoint Online, será possível adicionar armazenamento à sua assinatura, se seu plano estiver qualificado.</span><span class="sxs-lookup"><span data-stu-id="e6a62-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="e6a62-108">Se você não vir o **armazenamento de arquivos extra do Office 365** na lista de Complementos disponíveis, isso significa que seu plano não está qualificado.</span><span class="sxs-lookup"><span data-stu-id="e6a62-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="e6a62-109">Para obter mais informações, veja [o meu plano está qualificado?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="e6a62-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="e6a62-110">Se você comprou a assinatura por meio de licenciamento por volume ou um CSP, não poderá comprar o **armazenamento de arquivos extra do Office 365** para sua organização diretamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e6a62-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="e6a62-111">Entre em contato com seu representante ou parceiro para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="e6a62-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e6a62-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e6a62-112">Before you begin</span></span>

<span data-ttu-id="e6a62-113">Você deve ser um administrador global ou do SharePoint para realizar as tarefas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e6a62-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="e6a62-114">Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e6a62-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="e6a62-115">Exibir armazenamento disponível</span><span class="sxs-lookup"><span data-stu-id="e6a62-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e6a62-116">No centro de administração do SharePoint, vá para a página <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">sites ativos</a> e entre com uma conta que tenha [permissões de administrador](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e6a62-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="e6a62-117">No canto superior direito da página, confira a quantidade de armazenamento usada em todos os sites e o armazenamento total da sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="e6a62-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="e6a62-118">Se sua organização tiver configurado várias geografias no Office 365, a barra também mostrará a quantidade de armazenamento usada em todos os locais geográficos.</span><span class="sxs-lookup"><span data-stu-id="e6a62-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra de armazenamento na página sites ativos](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="e6a62-120">O armazenamento usado não inclui as alterações feitas nas últimas 24-48 horas.</span><span class="sxs-lookup"><span data-stu-id="e6a62-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e6a62-121">Entre https://portal.office.de como um administrador global ou do SharePoint e selecione o bloco administrador para abrir o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="e6a62-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="e6a62-122">Se você vir uma mensagem informando que você não tem permissão para acessar a página, isso significa que você não tem permissões de administrador do Microsoft 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e6a62-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="e6a62-123">No painel esquerdo, em **centros de administração**, selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="e6a62-124">Se aparecer o centro de administração do SharePoint clássico, selecione **Abrir agora**, na parte superior da página, para abrir o novo centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e6a62-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="e6a62-125">No painel esquerdo do novo centro de administração do SharePoint, selecione **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="e6a62-126">No canto superior direito da página, confira a quantidade de armazenamento usada em todos os sites e o armazenamento total da sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="e6a62-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Barra de armazenamento na página sites ativos](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="e6a62-128">O armazenamento usado não inclui as alterações feitas nas últimas 24-48 horas.</span><span class="sxs-lookup"><span data-stu-id="e6a62-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e6a62-129">Entre https://login.partner.microsoftonline.cn/ como um administrador global ou do SharePoint e selecione o bloco administrador para abrir o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="e6a62-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="e6a62-130">(Se você vir uma mensagem informando que você não tem permissão para acessar a página, significa que você não tem permissões de administrador do Microsoft 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e6a62-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="e6a62-131">No painel esquerdo, em **centros de administração**, selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="e6a62-132">Se aparecer o centro de administração do SharePoint clássico, selecione **Abrir agora**, na parte superior da página, para abrir o novo centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e6a62-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="e6a62-133">No painel esquerdo do novo centro de administração do SharePoint, selecione **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="e6a62-134">No canto superior direito da página, confira a quantidade de armazenamento usada em todos os sites e o armazenamento total da sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="e6a62-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Barra de armazenamento na página sites ativos](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="e6a62-136">O armazenamento usado não inclui as alterações feitas nas últimas 24-48 horas.</span><span class="sxs-lookup"><span data-stu-id="e6a62-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="e6a62-137">Após determinar a quantidade de armazenamento que está usando, você pode adicionar ou remover espaço de armazenamento da assinatura.</span><span class="sxs-lookup"><span data-stu-id="e6a62-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="e6a62-138">Para descobrir quanto custará para adicionar espaço de armazenamento, siga as etapas deste artigo e revise as informações sobre preços antes de comprar.</span><span class="sxs-lookup"><span data-stu-id="e6a62-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="e6a62-139">Para obter informações sobre como configurar os limites de armazenamento do conjunto de sites, consulte [manage site Collection Storage Limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="e6a62-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="e6a62-140">Adicionar armazenamento à sua assinatura</span><span class="sxs-lookup"><span data-stu-id="e6a62-140">Add storage to your subscription</span></span>

<span data-ttu-id="e6a62-141">Se você ainda não comprou o armazenamento adicional para sua assinatura, é possível fazer isso.</span><span class="sxs-lookup"><span data-stu-id="e6a62-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e6a62-142">No centro de administração, vá para a **Billing** \> página <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">serviços de compra</a> de cobrança.</span><span class="sxs-lookup"><span data-stu-id="e6a62-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="e6a62-143">Na parte inferior da página de **serviços de compra** , selecione **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="e6a62-144">Selecione o **armazenamento de arquivos extra do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="e6a62-145">Na página **armazenamento de arquivos extra do Office 365** , se mostrado, escolha a assinatura base e, em seguida, insira o número de gigabytes de armazenamento que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="e6a62-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="e6a62-146">Selecione **fazer check-out agora**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="e6a62-147">Na página **como esta?** , verifique o número de gigabytes de armazenamento que você selecionou, revise as informações de preços e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="e6a62-148">Na página **ordem completa** , verifique o total.</span><span class="sxs-lookup"><span data-stu-id="e6a62-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="e6a62-149">Se você precisar fazer alterações, selecione **Editar ordem**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="e6a62-150">Se a ordem exigir uma verificação de crédito, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="e6a62-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="e6a62-151">Quando tiver terminado, selecione **fazer pedido** \> **ir para a home page do administrador**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e6a62-152">No centro de administração, vá para a **Billing** \> página <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">assinaturas</a> de cobrança.  </span><span class="sxs-lookup"><span data-stu-id="e6a62-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="e6a62-153">Na página **assinaturas** , escolha a assinatura à qual você deseja adicionar o espaço de armazenamento e, em seguida, **selecione Complementos**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="e6a62-155">Se você **não vir Complementos e se**sua assinatura foi adquirida por meio de um parceiro, selecione o centro de **serviços de licenciamento por volume (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="e6a62-156">Selecione **comprar Complementos**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-156">Select **Buy add-ons**.</span></span>

    ![Comprar Complementos link na página assinaturas do centro de administração.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="e6a62-158">Na página **comprar serviços** , passe o mouse ou toque no **armazenamento de arquivos Extra do Office 365**e selecione **comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="e6a62-159">Insira o número de licenças de usuário necessárias e, se mostrado, escolha uma assinatura base.</span><span class="sxs-lookup"><span data-stu-id="e6a62-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="e6a62-160">Selecione **fazer check-out agora**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="e6a62-161">Na página **como esta?** , verifique o número de gigabytes de armazenamento que você selecionou, revise as informações de preços e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="e6a62-162">Na página **ordem completa** , selecione **fazer pedido**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e6a62-163">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Assinaturas</a>.</span><span class="sxs-lookup"><span data-stu-id="e6a62-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="e6a62-164">Na página **assinaturas** , escolha a assinatura à qual você deseja adicionar o espaço de armazenamento e, em seguida, **selecione Complementos**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="e6a62-166">Se você **não vir Complementos e se**sua assinatura foi adquirida por meio de um parceiro, selecione o centro de **serviços de licenciamento por volume (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="e6a62-167">Selecione **comprar Complementos**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-167">Select **Buy add-ons**.</span></span>

    ![Comprar Complementos link na página assinaturas do centro de administração.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="e6a62-169">Na página **comprar serviços** , passe o mouse ou toque no **armazenamento de arquivos Extra do Office 365**e selecione **comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="e6a62-170">Insira o número de licenças de usuário necessárias e, se mostrado, escolha uma assinatura base.</span><span class="sxs-lookup"><span data-stu-id="e6a62-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="e6a62-171">Selecione **fazer check-out agora**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="e6a62-172">Na página **como esta?** , verifique o número de gigabytes de armazenamento que você selecionou, revise as informações de preços e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="e6a62-173">Na página **ordem completa** , selecione **fazer pedido**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="e6a62-174">Aumentar ou diminuir armazenamento</span><span class="sxs-lookup"><span data-stu-id="e6a62-174">Increase or decrease storage</span></span>

<span data-ttu-id="e6a62-175">Se você já comprou o armazenamento de arquivos extra por meio do complemento de **armazenamento de arquivos extra do Office 365** , poderá usar estas etapas para aumentar ou diminuir o espaço de armazenamento adicional da sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="e6a62-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="e6a62-176">Você pode reduzir o armazenamento para, no máximo, 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="e6a62-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="e6a62-177">Para remover todo o espaço de armazenamento adicional, [entre em contato com o suporte](../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="e6a62-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e6a62-178">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="e6a62-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="e6a62-179">Na guia **produtos** , selecione a assinatura que contém o complemento **armazenamento adicional de arquivos do Office 365** .</span><span class="sxs-lookup"><span data-stu-id="e6a62-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="e6a62-180">Na página detalhes do produto, na seção **Complementos** , selecione **gerenciar**Complementos.</span><span class="sxs-lookup"><span data-stu-id="e6a62-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="e6a62-181">No painel **gerenciar** Complementos, na lista **complemento** , escolha o **armazenamento de arquivos extra do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="e6a62-182">Na caixa de texto **quantidade** , insira o número de GBS de espaço de armazenamento desejado para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="e6a62-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="e6a62-183">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e6a62-184">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Assinaturas</a>.</span><span class="sxs-lookup"><span data-stu-id="e6a62-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="e6a62-185">Na página **assinaturas** , selecione **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="e6a62-187">Se você **não vir Complementos e se**sua assinatura foi adquirida por meio de um parceiro, selecione o centro de **serviços de licenciamento por volume (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="e6a62-188">Em **armazenamento de arquivos extra do Office 365**, selecione **Alterar quantidade**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Link Alterar quantidade.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="e6a62-190">No painel direito, insira o número total de gigabytes necessários e, em seguida, selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="e6a62-191">Por exemplo, se você tem atualmente 200 GB de armazenamento adicional, mas precisa apenas de 100 GB, digite **100** na caixa.</span><span class="sxs-lookup"><span data-stu-id="e6a62-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="e6a62-192">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e6a62-193">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Assinaturas</a>.</span><span class="sxs-lookup"><span data-stu-id="e6a62-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="e6a62-194">Na página **assinaturas** , selecione **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="e6a62-196">Se você **não vir Complementos e se**sua assinatura foi adquirida por meio de um parceiro, selecione o centro de **serviços de licenciamento por volume (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="e6a62-197">Em **armazenamento de arquivos extra do Office 365**, selecione **Alterar quantidade**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Link Alterar quantidade.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="e6a62-199">No painel direito, insira o número total de gigabytes necessários e, em seguida, selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="e6a62-200">Por exemplo, se você tem atualmente 200 GB de armazenamento adicional, mas precisa apenas de 100 GB, digite **100** na caixa.</span><span class="sxs-lookup"><span data-stu-id="e6a62-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="e6a62-201">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e6a62-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="e6a62-202">Meu plano é qualificado para o Office 365 com Espaço de Armazenamento Adicional?</span><span class="sxs-lookup"><span data-stu-id="e6a62-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="e6a62-203">O Office 365 com Espaço de Armazenamento Adicional está disponível para as seguintes assinaturas:</span><span class="sxs-lookup"><span data-stu-id="e6a62-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="e6a62-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="e6a62-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="e6a62-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="e6a62-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="e6a62-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="e6a62-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="e6a62-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="e6a62-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="e6a62-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="e6a62-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="e6a62-209">Office para a Web com o SharePoint plano 1</span><span class="sxs-lookup"><span data-stu-id="e6a62-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="e6a62-210">Office para a Web com o SharePoint Plan 2</span><span class="sxs-lookup"><span data-stu-id="e6a62-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="e6a62-211">SharePoint Online Plano 1</span><span class="sxs-lookup"><span data-stu-id="e6a62-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="e6a62-212">SharePoint Online Plano 2</span><span class="sxs-lookup"><span data-stu-id="e6a62-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="e6a62-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="e6a62-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="e6a62-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="e6a62-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="e6a62-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="e6a62-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="e6a62-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="e6a62-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="e6a62-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e6a62-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="e6a62-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="e6a62-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="e6a62-219">O armazenamento de arquivos extra do Office 365 também está disponível para os planos GCC, GCC alto e DOD.</span><span class="sxs-lookup"><span data-stu-id="e6a62-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="e6a62-220">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="e6a62-220">Related content</span></span>

<span data-ttu-id="e6a62-221">[Gerenciar limites de armazenamento do site](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (artigo) </span><span class="sxs-lookup"><span data-stu-id="e6a62-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="e6a62-222">[Definir o espaço de armazenamento padrão para os usuários do onedrive](https://docs.microsoft.com/onedrive/set-default-storage-space)(artigo)</span><span class="sxs-lookup"><span data-stu-id="e6a62-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
