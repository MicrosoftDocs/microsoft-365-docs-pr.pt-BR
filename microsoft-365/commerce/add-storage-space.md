---
title: Adicionar espaço de armazenamento para sua assinatura
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: drjones, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: Adicione armazenamento de arquivos em sua assinatura Microsoft 365 de arquivo. Com o armazenamento de arquivos extra, você pode armazenar mais conteúdo no SharePoint Online e OneDrive.
ms.date: 04/02/2021
ms.openlocfilehash: 14b688e850f62a06c39e4a315d871202e57d70d6
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635853"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="f8503-104">Adicionar espaço de armazenamento para sua assinatura</span><span class="sxs-lookup"><span data-stu-id="f8503-104">Add storage space for your subscription</span></span>

<span data-ttu-id="f8503-105">Se você começar a ficar sem armazenamento para seus conjuntos de sites do SharePoint Online, será possível adicionar armazenamento à sua assinatura, se seu plano estiver qualificado.</span><span class="sxs-lookup"><span data-stu-id="f8503-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="f8503-106">Se você não vir o **Office 365 com Espaço de Armazenamento Adicional** na lista de complementos disponíveis, isso significa que seu plano não está qualificado.</span><span class="sxs-lookup"><span data-stu-id="f8503-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="f8503-107">Para obter mais informações, consulte [Meu plano é qualificado?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="f8503-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="f8503-108">Se você comprou sua assinatura por meio de Licenciamento por Volume ou CSP, não poderá comprar Office 365 com Espaço de Armazenamento Adicional **sua** organização diretamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8503-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="f8503-109">Entre em contato com seu representante ou parceiro para pedir ajuda.</span><span class="sxs-lookup"><span data-stu-id="f8503-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f8503-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f8503-110">Before you begin</span></span>

<span data-ttu-id="f8503-111">Você deve ser um administrador global ou SharePoint para realizar as tarefas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="f8503-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="f8503-112">Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f8503-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="f8503-113">Exibir armazenamento disponível</span><span class="sxs-lookup"><span data-stu-id="f8503-113">View available storage</span></span>

1. <span data-ttu-id="f8503-114">No centro SharePoint de administração, vá para a página <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Sites</a> ativos e entre com uma conta que tenha permissões de administrador [para](/sharepoint/sharepoint-admin-role) sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8503-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="f8503-115">No canto superior direito da página, veja a quantidade de armazenamento usada em todos os sites e o armazenamento total para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="f8503-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="f8503-116">Se sua organização configurou o Multi-Geo em Office 365, a barra também mostra a quantidade de armazenamento usada em todos os locais geo.</span><span class="sxs-lookup"><span data-stu-id="f8503-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra de armazenamento na página de sites ativos](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="f8503-118">O armazenamento usado não inclui alterações feitas nas últimas 24 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="f8503-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="f8503-119">Depois de determinar quanto armazenamento você está usando, você pode adicionar ou remover o espaço de armazenamento para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="f8503-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="f8503-120">Para descobrir quanto custará para adicionar espaço de armazenamento, siga as etapas deste artigo e revise as informações de preços antes de comprar mais.</span><span class="sxs-lookup"><span data-stu-id="f8503-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="f8503-121">Para obter informações sobre como definir limites de armazenamento do conjunto de sites, consulte [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="f8503-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="f8503-122">Adicionar armazenamento à sua assinatura</span><span class="sxs-lookup"><span data-stu-id="f8503-122">Add storage to your subscription</span></span>

<span data-ttu-id="f8503-123">Se você ainda não comprou armazenamento extra para sua assinatura, você pode fazer isso.</span><span class="sxs-lookup"><span data-stu-id="f8503-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="f8503-124">No centro de administração, vá para a página **Serviços de** Compra \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">de</a> Cobrança.</span><span class="sxs-lookup"><span data-stu-id="f8503-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="f8503-125">Na parte inferior da página **Serviços de** Compra, na seção **Complementos,** encontre Office 365 com Espaço de Armazenamento Adicional **e** selecione **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="f8503-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="f8503-126">Na página detalhes do produto, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f8503-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="f8503-127">Se necessário, escolha a assinatura base e insira o número de gigabytes de armazenamento que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="f8503-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="f8503-128">Selecione **Check-out agora**.</span><span class="sxs-lookup"><span data-stu-id="f8503-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="f8503-129">Na página **Como isso fica?** Verifique o número de gigabytes de armazenamento selecionado, revise as informações de preços e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f8503-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="f8503-130">Na página **Concluir o pedido,** verifique o total.</span><span class="sxs-lookup"><span data-stu-id="f8503-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="f8503-131">Se precisar fazer alterações, selecione **Editar ordem**.</span><span class="sxs-lookup"><span data-stu-id="f8503-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="f8503-132">Se o pedido exigir uma verificação de crédito, marque a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="f8503-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="f8503-133">Quando terminar, selecione Local **order** \> **Go to Admin Home**.</span><span class="sxs-lookup"><span data-stu-id="f8503-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="f8503-134">Aumentar ou diminuir armazenamento</span><span class="sxs-lookup"><span data-stu-id="f8503-134">Increase or decrease storage</span></span>

<span data-ttu-id="f8503-135">Se você já comprou armazenamento de arquivo extra por meio do complemento **Office 365 com Espaço de Armazenamento Adicional,** você pode usar essas etapas para aumentar ou diminuir o espaço de armazenamento extra para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="f8503-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="f8503-136">Você pode reduzir o armazenamento para até 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="f8503-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="f8503-137">Para remover todo o espaço de armazenamento extra, contate [o suporte](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="f8503-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="f8503-138">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="f8503-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="f8503-139">Na guia **Produtos,** selecione a assinatura que contém o **Office 365 com Espaço de Armazenamento Adicional** complemento.</span><span class="sxs-lookup"><span data-stu-id="f8503-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="f8503-140">Na página detalhes do produto, na seção **Complementos,** selecione **Gerenciar complementos**.</span><span class="sxs-lookup"><span data-stu-id="f8503-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="f8503-141">No painel **Gerenciar complementos,** na lista **Complementos,** escolha **Office 365 com Espaço de Armazenamento Adicional**.</span><span class="sxs-lookup"><span data-stu-id="f8503-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="f8503-142">Na caixa **de texto Quantidade,** digite o número de GBs de espaço de armazenamento que você deseja para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="f8503-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="f8503-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f8503-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="f8503-144">Meu plano é qualificado para o Office 365 com Espaço de Armazenamento Adicional?</span><span class="sxs-lookup"><span data-stu-id="f8503-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="f8503-145">O Office 365 com Espaço de Armazenamento Adicional está disponível para as seguintes assinaturas:</span><span class="sxs-lookup"><span data-stu-id="f8503-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="f8503-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="f8503-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="f8503-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="f8503-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="f8503-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="f8503-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="f8503-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="f8503-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="f8503-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="f8503-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="f8503-151">Office para a Web com SharePoint Plano 1</span><span class="sxs-lookup"><span data-stu-id="f8503-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="f8503-152">Office para a Web com SharePoint Plano 2</span><span class="sxs-lookup"><span data-stu-id="f8503-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="f8503-153">SharePoint Online Plano 1</span><span class="sxs-lookup"><span data-stu-id="f8503-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="f8503-154">SharePoint Online Plano 2</span><span class="sxs-lookup"><span data-stu-id="f8503-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="f8503-155">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="f8503-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="f8503-156">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="f8503-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="f8503-157">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="f8503-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="f8503-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="f8503-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="f8503-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f8503-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="f8503-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="f8503-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="f8503-161">Office 365 com Espaço de Armazenamento Adicional também está disponível para planos GCC, GCC High e DOD.</span><span class="sxs-lookup"><span data-stu-id="f8503-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="f8503-162">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="f8503-162">Related content</span></span>

<span data-ttu-id="f8503-163">[Gerenciar limites de armazenamento de site](/sharepoint/manage-site-collection-storage-limits) (artigo)</span><span class="sxs-lookup"><span data-stu-id="f8503-163">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="f8503-164">[Definir o espaço de armazenamento padrão para OneDrive usuários](/onedrive/set-default-storage-space) (artigo)</span><span class="sxs-lookup"><span data-stu-id="f8503-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space) (article)</span></span>
