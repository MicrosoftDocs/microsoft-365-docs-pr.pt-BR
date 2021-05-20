---
title: Adicione espaço de armazenamento para sua assinatura
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
description: Adicione armazenamento de arquivos em sua assinatura de Microsoft 365. Com armazenamento extra de arquivos, você pode armazenar mais conteúdo em SharePoint Online e OneDrive.
ms.date: 04/02/2021
ms.openlocfilehash: b573205c7053aba0339d1f32deb2996ef80f8754
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572316"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="3bb1a-104">Adicione espaço de armazenamento para sua assinatura</span><span class="sxs-lookup"><span data-stu-id="3bb1a-104">Add storage space for your subscription</span></span>

<span data-ttu-id="3bb1a-105">Se você começar a ficar sem armazenamento para seus conjuntos de sites do SharePoint Online, será possível adicionar armazenamento à sua assinatura, se seu plano estiver qualificado.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="3bb1a-106">Se você não ver o **Office 365 com Espaço de Armazenamento Adicional** na lista de complementos disponíveis, isso significa que seu plano não é elegível.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="3bb1a-107">Para obter mais informações, consulte [meu plano é elegível?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="3bb1a-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="3bb1a-108">Se você comprou sua assinatura através do Licenciamento de Volume ou de um CSP, você não pode comprar **Office 365 com Espaço de Armazenamento Adicional** para sua organização diretamente da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="3bb1a-109">Entre em contato com seu representante ou parceiro para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3bb1a-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3bb1a-110">Before you begin</span></span>

<span data-ttu-id="3bb1a-111">Você deve ser um administrador global ou SharePoint para fazer as tarefas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="3bb1a-112">Para mais informações, consulte [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3bb1a-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="3bb1a-113">Exibir armazenamento disponível</span><span class="sxs-lookup"><span data-stu-id="3bb1a-113">View available storage</span></span>

1. <span data-ttu-id="3bb1a-114">No SharePoint centro administrativo, acesse a página <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">dos sites Ativos</a> e faça login com uma conta que tenha [permissões administrativas](/sharepoint/sharepoint-admin-role) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="3bb1a-115">No canto superior direito da página, veja a quantidade de armazenamento usada em todos os sites e o armazenamento total para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="3bb1a-116">Se sua organização configurou Multi-Geo em Office 365, a barra também mostra a quantidade de armazenamento usada em todos os locais geográficos.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Barra de armazenamento na página de sites ativos](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="3bb1a-118">O armazenamento usado não inclui alterações feitas nas últimas 24 a 48 horas.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="3bb1a-119">Depois de determinar quanto armazenamento está usando, você pode adicionar ou remover o espaço de armazenamento para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="3bb1a-120">Para saber quanto custará adicionar espaço de armazenamento, siga os passos deste artigo e revise as informações de preços antes de comprar mais.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="3bb1a-121">Para obter informações sobre a definição dos limites de armazenamento de coleta de locais, consulte [Gerenciar os limites de armazenamento de coleta de sites](/sharepoint/manage-site-collection-storage-limits).</span><span class="sxs-lookup"><span data-stu-id="3bb1a-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="3bb1a-122">Adicione armazenamento à sua assinatura</span><span class="sxs-lookup"><span data-stu-id="3bb1a-122">Add storage to your subscription</span></span>

<span data-ttu-id="3bb1a-123">Se você ainda não comprou armazenamento extra para sua assinatura, você pode fazer isso.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="3bb1a-124">No centro administrativo, acesse a página de serviços de Compra **de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Faturamento.</a></span><span class="sxs-lookup"><span data-stu-id="3bb1a-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="3bb1a-125">Na parte inferior da página de **serviços de compra,** na seção **Adicionar,** encontre **Office 365 com Espaço de Armazenamento Adicional** e selecione **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="3bb1a-126">Na página de detalhes do produto, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="3bb1a-127">Se necessário, escolha a assinatura base e digite o número de gigabytes de armazenamento que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="3bb1a-128">Selecione **Confira agora**.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="3bb1a-129">Na página **Como isso parece?** </span><span class="sxs-lookup"><span data-stu-id="3bb1a-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="3bb1a-130">Na página completa do **pedido,** verifique o total.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="3bb1a-131">Se você precisar fazer alguma alteração, selecione **Editar ordem**.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="3bb1a-132">Se o pedido exigir um cheque de crédito, selecione a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="3bb1a-133">Quando terminar, selecione **Fazer o pedido** \> **ir para O Administrador Home**.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="3bb1a-134">Aumentar ou diminuir armazenamento</span><span class="sxs-lookup"><span data-stu-id="3bb1a-134">Increase or decrease storage</span></span>

<span data-ttu-id="3bb1a-135">Se você já comprou armazenamento extra de arquivos através do **Office 365 com Espaço de Armazenamento Adicional** complemento, você pode usar essas etapas para aumentar ou diminuir o espaço de armazenamento extra para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="3bb1a-136">Você pode reduzir o armazenamento para até 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="3bb1a-137">Para remover todo o espaço de armazenamento extra, [suporte de contato](../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="3bb1a-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="3bb1a-138">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="3bb1a-139">Na guia **Produtos,** selecione a assinatura que contém o **complemento Office 365 com Espaço de Armazenamento Adicional.**</span><span class="sxs-lookup"><span data-stu-id="3bb1a-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="3bb1a-140">Na página de detalhes do produto, na seção **Adicionar,** selecione **Gerenciar complementos**.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="3bb1a-141">No **painel de complementos Gerenciar,** a partir da lista **Add-on,** escolha **Office 365 com Espaço de Armazenamento Adicional**.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="3bb1a-142">Na caixa de texto **Quantidade,** digite o número de GBs do espaço de armazenamento que deseja para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="3bb1a-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="3bb1a-144">Meu plano é qualificado para o Office 365 com Espaço de Armazenamento Adicional?</span><span class="sxs-lookup"><span data-stu-id="3bb1a-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="3bb1a-145">O Office 365 com Espaço de Armazenamento Adicional está disponível para as seguintes assinaturas:</span><span class="sxs-lookup"><span data-stu-id="3bb1a-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="3bb1a-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="3bb1a-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="3bb1a-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="3bb1a-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="3bb1a-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="3bb1a-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="3bb1a-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="3bb1a-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="3bb1a-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="3bb1a-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="3bb1a-151">Office para a web com SharePoint Plano 1</span><span class="sxs-lookup"><span data-stu-id="3bb1a-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="3bb1a-152">Office para a web com SharePoint Plano 2</span><span class="sxs-lookup"><span data-stu-id="3bb1a-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="3bb1a-153">SharePoint Online Plano 1</span><span class="sxs-lookup"><span data-stu-id="3bb1a-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="3bb1a-154">SharePoint Online Plano 2</span><span class="sxs-lookup"><span data-stu-id="3bb1a-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="3bb1a-155">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="3bb1a-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="3bb1a-156">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="3bb1a-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="3bb1a-157">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3bb1a-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="3bb1a-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="3bb1a-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="3bb1a-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3bb1a-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="3bb1a-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="3bb1a-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="3bb1a-161">Office 365 com Espaço de Armazenamento Adicional também está disponível para planos GCC, GCC High e DOD.</span><span class="sxs-lookup"><span data-stu-id="3bb1a-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="3bb1a-162">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="3bb1a-162">Related content</span></span>

<span data-ttu-id="3bb1a-163">[Gerenciar os limites de armazenamento do site](/sharepoint/manage-site-collection-storage-limits) (artigo)</span><span class="sxs-lookup"><span data-stu-id="3bb1a-163">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="3bb1a-164">[Defina o espaço de armazenamento padrão para usuários OneDrive](/onedrive/set-default-storage-space)(artigo)</span><span class="sxs-lookup"><span data-stu-id="3bb1a-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>
