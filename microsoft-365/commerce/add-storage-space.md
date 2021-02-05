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
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114902"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="bee1a-104">Adicionar espaço de armazenamento para sua assinatura</span><span class="sxs-lookup"><span data-stu-id="bee1a-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="bee1a-105">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="bee1a-105">The admin center is changing.</span></span> <span data-ttu-id="bee1a-106">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="bee1a-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="bee1a-107">Se você começar a ficar sem armazenamento para seus conjuntos de sites do SharePoint Online, será possível adicionar armazenamento à sua assinatura, se seu plano estiver qualificado.</span><span class="sxs-lookup"><span data-stu-id="bee1a-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="bee1a-108">Se você não vir o Armazenamento de Arquivos Extra do **Office 365** na lista de complementos disponíveis, isso significa que seu plano não está qualificado.</span><span class="sxs-lookup"><span data-stu-id="bee1a-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="bee1a-109">Para obter mais informações, consulte [Meu plano é qualificado?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="bee1a-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="bee1a-110">Se você comprou sua assinatura por meio de Licenciamento por Volume ou CSP, não poderá comprar o Armazenamento de Arquivos Extra do **Office 365** para sua organização diretamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bee1a-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="bee1a-111">Entre em contato com seu representante ou parceiro para ajuda.</span><span class="sxs-lookup"><span data-stu-id="bee1a-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bee1a-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="bee1a-112">Before you begin</span></span>

<span data-ttu-id="bee1a-113">Você deve ser um administrador global ou do SharePoint para realizar as tarefas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="bee1a-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="bee1a-114">Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bee1a-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="bee1a-115">Exibir armazenamento disponível</span><span class="sxs-lookup"><span data-stu-id="bee1a-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bee1a-116">No Centro de administração do SharePoint, vá para a página <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Sites</a> ativos e entre com uma conta que tenha [permissões](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) de administrador para sua organização.</span><span class="sxs-lookup"><span data-stu-id="bee1a-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="bee1a-117">No canto superior direito da página, veja a quantidade de armazenamento usada em todos os sites e o armazenamento total para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="bee1a-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="bee1a-118">Se sua organização configurou o Multi-Geo no Office 365, a barra também mostra a quantidade de armazenamento usado em todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="bee1a-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra de armazenamento na página de sites ativos](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="bee1a-120">O armazenamento usado não inclui alterações feitas nas últimas 24 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="bee1a-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bee1a-121">Entre como administrador global ou do SharePoint e selecione o painel https://portal.office.de Administrador para abrir o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="bee1a-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="bee1a-122">Se você vir uma mensagem de que não tem permissão para acessar a página, isso significa que você não tem permissões de administrador do Microsoft 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bee1a-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="bee1a-123">No painel esquerdo, em Centros de **administração,** selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bee1a-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="bee1a-124">Se aparecer o centro de administração do SharePoint clássico, selecione **Abrir agora**, na parte superior da página, para abrir o novo centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bee1a-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="bee1a-125">No painel esquerdo do novo centro de administração do SharePoint, selecione **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="bee1a-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="bee1a-126">No canto superior direito da página, veja a quantidade de armazenamento usada em todos os sites e o armazenamento total para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="bee1a-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Barra de armazenamento na página de sites ativos](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="bee1a-128">O armazenamento usado não inclui alterações feitas nas últimas 24 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="bee1a-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bee1a-129">Entre como administrador global ou do SharePoint e selecione o painel https://login.partner.microsoftonline.cn/ Administrador para abrir o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="bee1a-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="bee1a-130">(Se você vir uma mensagem de que não tem permissão para acessar a página, isso significa que você não tem permissões de administrador do Microsoft 365 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bee1a-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="bee1a-131">No painel esquerdo, em Centros de **administração,** selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bee1a-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="bee1a-132">Se aparecer o centro de administração do SharePoint clássico, selecione **Abrir agora**, na parte superior da página, para abrir o novo centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bee1a-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="bee1a-133">No painel esquerdo do novo centro de administração do SharePoint, selecione **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="bee1a-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="bee1a-134">No canto superior direito da página, veja a quantidade de armazenamento usada em todos os sites e o armazenamento total para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="bee1a-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Barra de armazenamento na página de sites ativos](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="bee1a-136">O armazenamento usado não inclui alterações feitas nas últimas 24 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="bee1a-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="bee1a-137">Após determinar a quantidade de armazenamento que está usando, você pode adicionar ou remover espaço de armazenamento da assinatura.</span><span class="sxs-lookup"><span data-stu-id="bee1a-137">After you've determined how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="bee1a-138">Para descobrir quanto custa para adicionar espaço de armazenamento, siga as etapas neste artigo e revise as informações de preços antes de comprar.</span><span class="sxs-lookup"><span data-stu-id="bee1a-138">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="bee1a-139">Para obter informações sobre como definir limites de armazenamento do conjunto de sites, consulte Gerenciar limites de armazenamento [do conjunto de sites.](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits)</span><span class="sxs-lookup"><span data-stu-id="bee1a-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="bee1a-140">Adicionar armazenamento à sua assinatura</span><span class="sxs-lookup"><span data-stu-id="bee1a-140">Add storage to your subscription</span></span>

<span data-ttu-id="bee1a-141">Se você ainda não comprou armazenamento extra para sua assinatura, faça isso.</span><span class="sxs-lookup"><span data-stu-id="bee1a-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bee1a-142">No centro de administração, vá para a página **De** compra \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">de</a> cobrança.</span><span class="sxs-lookup"><span data-stu-id="bee1a-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="bee1a-143">Na parte inferior da página **Comprar serviços,** selecione **Complementos.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="bee1a-144">Selecione **Office 365 Armazenamento adicional de arquivos.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="bee1a-145">Na página Armazenamento de Arquivos Extra do **Office 365,** se mostrado, escolha a assinatura base e insira o número de gigabytes de armazenamento que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="bee1a-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="bee1a-146">Selecione **Check-out agora.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="bee1a-147">Na página **Como isso fica?** Verifique o número de gigabytes de armazenamento selecionado, revise as informações de preços e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="bee1a-148">Na página **Concluir pedido,** verifique o total.</span><span class="sxs-lookup"><span data-stu-id="bee1a-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="bee1a-149">Se você precisar fazer alterações, selecione **Editar ordem.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="bee1a-150">Se o pedido exigir uma verificação de crédito, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="bee1a-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="bee1a-151">Quando terminar, selecione Fazer **pedido** Ir para a Página De \> **administração.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bee1a-152">No centro de administração,  vá para a página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Assinaturas de</a> Cobrança.  </span><span class="sxs-lookup"><span data-stu-id="bee1a-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="bee1a-153">Na página **Assinaturas,** escolha a assinatura à qual você deseja adicionar espaço de armazenamento e, em seguida, selecione **Complementos.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="bee1a-155">Se você não vir **complementos** e sua assinatura tiver sido adquirida por meio de um parceiro, selecione Centro de Serviços de Licenciamento **por Volume (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="bee1a-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="bee1a-156">Selecione **Comprar complementos.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-156">Select **Buy add-ons**.</span></span>

    ![Buy add-ons link on the Subscriptions page of the admin center.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="bee1a-158">Na página **Comprar serviços,** passe o mouse ou toque em Armazenamento de Arquivos Extra do **Office 365** e selecione **Comprar agora.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="bee1a-159">Insira o número de licenças de usuário de que você precisa e, se mostrado, escolha uma assinatura base.</span><span class="sxs-lookup"><span data-stu-id="bee1a-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="bee1a-160">Selecione **Check-out agora.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="bee1a-161">Na página **Como isso fica?** Verifique o número de gigabytes de armazenamento selecionado, revise as informações de preços e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="bee1a-162">Na página **Concluir pedido,** selecione **Fazer pedido.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bee1a-163">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Assinaturas</a>.</span><span class="sxs-lookup"><span data-stu-id="bee1a-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="bee1a-164">Na página **Assinaturas,** escolha a assinatura à qual você deseja adicionar espaço de armazenamento e, em seguida, selecione **Complementos.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="bee1a-166">Se você não vir **complementos** e sua assinatura tiver sido adquirida por meio de um parceiro, selecione Centro de Serviços de Licenciamento **por Volume (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="bee1a-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="bee1a-167">Selecione **Comprar complementos.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-167">Select **Buy add-ons**.</span></span>

    ![Buy add-ons link on the Subscriptions page of the admin center.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="bee1a-169">Na página **Comprar serviços,** passe o mouse ou toque em Armazenamento de Arquivos Extra do **Office 365** e selecione **Comprar agora.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="bee1a-170">Insira o número de licenças de usuário de que você precisa e, se mostrado, escolha uma assinatura base.</span><span class="sxs-lookup"><span data-stu-id="bee1a-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="bee1a-171">Selecione **Check-out agora.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="bee1a-172">Na página **Como isso fica?** Verifique o número de gigabytes de armazenamento selecionado, revise as informações de preços e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="bee1a-173">Na página **Concluir pedido,** selecione **Fazer pedido.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="bee1a-174">Aumentar ou diminuir armazenamento</span><span class="sxs-lookup"><span data-stu-id="bee1a-174">Increase or decrease storage</span></span>

<span data-ttu-id="bee1a-175">Se você já adquiriu armazenamento extra de arquivos por meio do complemento De armazenamento de arquivos extra do **Office 365,** você pode usar essas etapas para aumentar ou diminuir o espaço de armazenamento extra para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="bee1a-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="bee1a-176">Você pode reduzir o armazenamento para até 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="bee1a-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="bee1a-177">Para remover todo o espaço de armazenamento extra, contate [o suporte.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="bee1a-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="bee1a-178">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="bee1a-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="bee1a-179">Na guia **Produtos,** selecione a assinatura que contém o complemento Armazenamento de Arquivos Extra do **Office 365.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="bee1a-180">Na página de detalhes do produto, na **seção Complementos,** selecione **Gerenciar complementos.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="bee1a-181">No painel **Gerenciar complementos,** na  lista de complementos, escolha Office **365 Armazenamento de Arquivos Extra.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="bee1a-182">Na caixa **de texto Quantidade,** insira o número de GBs de espaço de armazenamento que você deseja para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="bee1a-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="bee1a-183">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bee1a-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="bee1a-184">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Assinaturas</a>.</span><span class="sxs-lookup"><span data-stu-id="bee1a-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="bee1a-185">Na página **Assinaturas,** selecione **Complementos.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="bee1a-187">Se você não vir **complementos** e sua assinatura tiver sido adquirida por meio de um parceiro, selecione Centro de Serviços de Licenciamento **por Volume (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="bee1a-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="bee1a-188">Under **Office 365 Extra File Storage**, select Change **quantity**.</span><span class="sxs-lookup"><span data-stu-id="bee1a-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Link Alterar quantidade.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="bee1a-190">No painel direito, insira o número total de gigabytes necessários e selecione **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="bee1a-191">Por exemplo, se você tem atualmente 200 GB de armazenamento adicional, mas precisa apenas de 100 GB, digite **100** na caixa.</span><span class="sxs-lookup"><span data-stu-id="bee1a-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="bee1a-192">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="bee1a-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bee1a-193">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Assinaturas</a>.</span><span class="sxs-lookup"><span data-stu-id="bee1a-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="bee1a-194">Na página **Assinaturas,** selecione **Complementos.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="bee1a-196">Se você não vir **complementos** e sua assinatura tiver sido adquirida por meio de um parceiro, selecione Centro de Serviços de Licenciamento **por Volume (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="bee1a-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="bee1a-197">Under **Office 365 Extra File Storage**, select Change **quantity**.</span><span class="sxs-lookup"><span data-stu-id="bee1a-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Link Alterar quantidade.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="bee1a-199">No painel direito, insira o número total de gigabytes necessários e selecione **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="bee1a-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="bee1a-200">Por exemplo, se você tem atualmente 200 GB de armazenamento adicional, mas precisa apenas de 100 GB, digite **100** na caixa.</span><span class="sxs-lookup"><span data-stu-id="bee1a-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="bee1a-201">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="bee1a-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="bee1a-202">Meu plano é qualificado para o Office 365 com Espaço de Armazenamento Adicional?</span><span class="sxs-lookup"><span data-stu-id="bee1a-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="bee1a-203">O Office 365 com Espaço de Armazenamento Adicional está disponível para as seguintes assinaturas:</span><span class="sxs-lookup"><span data-stu-id="bee1a-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="bee1a-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="bee1a-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="bee1a-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="bee1a-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="bee1a-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="bee1a-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="bee1a-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="bee1a-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="bee1a-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="bee1a-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="bee1a-209">Office para a Web com o SharePoint Plano 1</span><span class="sxs-lookup"><span data-stu-id="bee1a-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="bee1a-210">Office para a Web com o SharePoint Plano 2</span><span class="sxs-lookup"><span data-stu-id="bee1a-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="bee1a-211">SharePoint Online Plano 1</span><span class="sxs-lookup"><span data-stu-id="bee1a-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="bee1a-212">SharePoint Online Plano 2</span><span class="sxs-lookup"><span data-stu-id="bee1a-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="bee1a-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="bee1a-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="bee1a-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="bee1a-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="bee1a-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="bee1a-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="bee1a-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="bee1a-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="bee1a-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bee1a-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="bee1a-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="bee1a-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="bee1a-219">O Office 365 Extra File Storage também está disponível para planos GCC, GCC High e DOD.</span><span class="sxs-lookup"><span data-stu-id="bee1a-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="bee1a-220">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="bee1a-220">Related content</span></span>

<span data-ttu-id="bee1a-221">[Gerenciar limites de armazenamento de site](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (artigo)</span><span class="sxs-lookup"><span data-stu-id="bee1a-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="bee1a-222">[Definir o espaço de armazenamento padrão para usuários do OneDrive](https://docs.microsoft.com/onedrive/set-default-storage-space)(artigo)</span><span class="sxs-lookup"><span data-stu-id="bee1a-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
