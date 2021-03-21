---
title: Gerenciar compras de autoatendir (Administradores)
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Os administradores podem aprender a gerenciar compras de autoatendados feitas pelos usuários em sua organização.
ms.openlocfilehash: 2ce12b7dba4e765745a94fa10f4ba15e7013e3c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920175"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="53cff-103">Gerenciar compras de autoatendimento (Administrador)</span><span class="sxs-lookup"><span data-stu-id="53cff-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="53cff-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="53cff-104">The admin center is changing.</span></span> <span data-ttu-id="53cff-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="53cff-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="53cff-106">Como administrador, você pode ver compras autoatendadas feitas por pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="53cff-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="53cff-107">Você vê o nome do produto, o nome do comprador, as assinaturas compradas, a data de expiração, o preço de compra e os usuários atribuídos para cada compra de autoatendido.</span><span class="sxs-lookup"><span data-stu-id="53cff-107">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="53cff-108">Se necessário pela sua organização, você pode desativar a compra de autoatendados por produto por meio do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53cff-108">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="53cff-109">Você tem as mesmas políticas de gerenciamento e acesso de dados sobre produtos comprados por meio da compra de autoatendados ou centralmente.</span><span class="sxs-lookup"><span data-stu-id="53cff-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="53cff-110">Você também pode controlar se os usuários em sua organização podem fazer compras de autoatendado.</span><span class="sxs-lookup"><span data-stu-id="53cff-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="53cff-111">Para obter mais informações, [consulte Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="53cff-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="53cff-112">Exibir assinaturas de autoatend</span><span class="sxs-lookup"><span data-stu-id="53cff-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="53cff-113">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="53cff-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="53cff-114">Na guia **Produtos,** selecione o ícone de filtro e, em seguida, **selecione Autoatendados**.</span><span class="sxs-lookup"><span data-stu-id="53cff-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="53cff-115">Para exibir mais detalhes sobre uma assinatura, escolha um na lista.</span><span class="sxs-lookup"><span data-stu-id="53cff-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="53cff-116">Exibir quem tem licenças para uma assinatura de compra de autoatend</span><span class="sxs-lookup"><span data-stu-id="53cff-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="53cff-117">No centro de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança.</span><span class="sxs-lookup"><span data-stu-id="53cff-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="53cff-118">Selecione o ícone de filtro e escolha **Autoatendado**.</span><span class="sxs-lookup"><span data-stu-id="53cff-118">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="53cff-119">Selecione um produto para ver licenças atribuídas às pessoas.</span><span class="sxs-lookup"><span data-stu-id="53cff-119">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="53cff-120">Se houver várias compras para um produto, esse produto será listado apenas uma vez, e **a** coluna Quantidade Disponível mostrará o total de todas as assinaturas compradas para esse produto.</span><span class="sxs-lookup"><span data-stu-id="53cff-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="53cff-121">A **lista** Usuários é agrupada pelos nomes de pessoas que fizeram compras de autoatendido.</span><span class="sxs-lookup"><span data-stu-id="53cff-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="53cff-122">Para exportar uma lista de usuários com licenças para essas assinaturas, escolha as assinaturas que você deseja exportar e escolha **Exportar usuários**.</span><span class="sxs-lookup"><span data-stu-id="53cff-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="53cff-123">Desabilitar ou habilitar compras autoatendenciadas</span><span class="sxs-lookup"><span data-stu-id="53cff-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="53cff-124">Você pode desabilitar ou habilitar compras de autoatendencia para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="53cff-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="53cff-125">O **módulo MSCommerce** PowerShell inclui um valor de parâmetro **PolicyID** para **AllowSelfServicePurchase** que permite controlar se os usuários em sua organização podem fazer compras de autoatendiço e para quais produtos.</span><span class="sxs-lookup"><span data-stu-id="53cff-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="53cff-126">Você pode usar o **módulo MSCommerce** PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="53cff-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="53cff-127">Exibir o estado padrão do **valor do parâmetro AllowSelfServicePurchase,** seja ele habilitado ou desabilitado pelo produto</span><span class="sxs-lookup"><span data-stu-id="53cff-127">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="53cff-128">Exibir uma lista de produtos aplicáveis e se a compra de autoatendados está habilitada ou desabilitada</span><span class="sxs-lookup"><span data-stu-id="53cff-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="53cff-129">Exibir ou modificar a configuração atual de um produto específico para habilita-lo ou desabilitá-lo</span><span class="sxs-lookup"><span data-stu-id="53cff-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="53cff-130">Para obter mais informações, [consulte Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="53cff-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="53cff-131">Centralizar licenças em uma única assinatura</span><span class="sxs-lookup"><span data-stu-id="53cff-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="53cff-132">Você pode atribuir licenças existentes ou comprar assinaturas adicionais por meio de contratos existentes para usuários atribuídos a compras de autoatendência.</span><span class="sxs-lookup"><span data-stu-id="53cff-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="53cff-133">Depois de atribuir essas licenças compradas centralmente, você pode solicitar que os compradores cancelem suas assinaturas existentes.</span><span class="sxs-lookup"><span data-stu-id="53cff-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="53cff-134">No centro de administração, vá para a página **Serviços de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Compra de</a> Cobrança.</span><span class="sxs-lookup"><span data-stu-id="53cff-134">In the admin center go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="53cff-135">Encontre e escolha o produto que você deseja comprar e escolha **Comprar**.</span><span class="sxs-lookup"><span data-stu-id="53cff-135">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="53cff-136">Conclua as etapas restantes para concluir sua compra.</span><span class="sxs-lookup"><span data-stu-id="53cff-136">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="53cff-137">Siga as etapas em [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span><span class="sxs-lookup"><span data-stu-id="53cff-137">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="53cff-138">Atribua licenças a todos os que têm uma licença na outra assinatura.</span><span class="sxs-lookup"><span data-stu-id="53cff-138">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="53cff-139">Para etapas completas, [consulte Atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="53cff-139">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="53cff-140">Entre em contato com a pessoa que comprou a assinatura de compra de autoatend.0 e peça que [ela cancele.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="53cff-140">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="53cff-141">Assumir uma assinatura de compra de autoatend</span><span class="sxs-lookup"><span data-stu-id="53cff-141">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="53cff-142">Você pode assumir uma assinatura de compra autoatendida feita por um usuário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="53cff-142">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="53cff-143">Ao assumir uma assinatura de compra de autoatendados, você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="53cff-143">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="53cff-144">Mova os usuários para uma assinatura diferente e cancele a assinatura original.</span><span class="sxs-lookup"><span data-stu-id="53cff-144">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="53cff-145">Cancele a assinatura de compra de autoatendido e remova licenças de usuários atribuídos.</span><span class="sxs-lookup"><span data-stu-id="53cff-145">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="53cff-146">Migrar usuários para uma assinatura diferente</span><span class="sxs-lookup"><span data-stu-id="53cff-146">Move users to a different subscription</span></span>

<span data-ttu-id="53cff-147">Quando você move usuários para uma assinatura diferente, a assinatura antiga é automaticamente cancelada.</span><span class="sxs-lookup"><span data-stu-id="53cff-147">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="53cff-148">O usuário que comprou originalmente a assinatura de compra de autoatendido recebe um email informando que a assinatura foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="53cff-148">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="53cff-149">Você deve ter uma licença disponível para cada usuário que está movendo na assinatura para a que você está movendo os usuários.</span><span class="sxs-lookup"><span data-stu-id="53cff-149">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

1. <span data-ttu-id="53cff-150">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="53cff-150">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="53cff-151">Na guia **Produtos,** selecione o ícone de filtro e, em seguida, **selecione Autoatendados**.</span><span class="sxs-lookup"><span data-stu-id="53cff-151">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="53cff-152">Selecione a assinatura que você deseja assumir.</span><span class="sxs-lookup"><span data-stu-id="53cff-152">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="53cff-153">Na página detalhes da assinatura, na seção **Assinaturas e** configurações, selecione **Assumir o controle dessa assinatura**.</span><span class="sxs-lookup"><span data-stu-id="53cff-153">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="53cff-154">No painel direito, selecione **Mover usuários**.</span><span class="sxs-lookup"><span data-stu-id="53cff-154">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="53cff-155">Selecione o produto para o que você deseja mover os usuários e, em seguida, **selecione Mover usuários**.</span><span class="sxs-lookup"><span data-stu-id="53cff-155">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="53cff-156">Na caixa **Mover usuários para,** selecione **Mover usuários**.</span><span class="sxs-lookup"><span data-stu-id="53cff-156">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="53cff-157">O processo de movimentação pode levar vários minutos.</span><span class="sxs-lookup"><span data-stu-id="53cff-157">The move process might take several minutes.</span></span> <span data-ttu-id="53cff-158">Não feche o navegador enquanto o processo é executado.</span><span class="sxs-lookup"><span data-stu-id="53cff-158">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="53cff-159">Quando o processo de movimentação for concluído, feche o **painel Mover concluído.**</span><span class="sxs-lookup"><span data-stu-id="53cff-159">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="53cff-160">Na página detalhes da assinatura, o **status de assinatura** da assinatura adquirida por autoatendados mostra como **Excluído**.</span><span class="sxs-lookup"><span data-stu-id="53cff-160">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="53cff-161">Cancelar uma assinatura de compra de autoatend</span><span class="sxs-lookup"><span data-stu-id="53cff-161">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="53cff-162">Quando você opta por cancelar uma assinatura de compra de autoatendado, os usuários com licenças perdem acesso ao produto.</span><span class="sxs-lookup"><span data-stu-id="53cff-162">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="53cff-163">O usuário que comprou originalmente a assinatura de compra de autoatendido recebe um email informando que a assinatura foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="53cff-163">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

1. <span data-ttu-id="53cff-164">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="53cff-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="53cff-165">Na guia **Produtos,** selecione o ícone de filtro e, em seguida, **selecione Autoatendados**.</span><span class="sxs-lookup"><span data-stu-id="53cff-165">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="53cff-166">Selecione a assinatura que você deseja cancelar.</span><span class="sxs-lookup"><span data-stu-id="53cff-166">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="53cff-167">Na página detalhes da assinatura, na seção **Assinaturas e** configurações, selecione **Assumir o controle dessa assinatura**.</span><span class="sxs-lookup"><span data-stu-id="53cff-167">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="53cff-168">No painel direito, selecione **Cancelar assinatura**.</span><span class="sxs-lookup"><span data-stu-id="53cff-168">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="53cff-169">Selecione um motivo para o cancelamento na listada e selecione **Cancelar assinatura**.</span><span class="sxs-lookup"><span data-stu-id="53cff-169">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="53cff-170">Na caixa **Tem certeza de que deseja cancelar?** Selecione Cancelar **assinatura**.</span><span class="sxs-lookup"><span data-stu-id="53cff-170">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="53cff-171">Feche o painel direito.</span><span class="sxs-lookup"><span data-stu-id="53cff-171">Close the right pane.</span></span>
9. <span data-ttu-id="53cff-172">Na página detalhes da assinatura, o **status da assinatura** é como **Excluído**.</span><span class="sxs-lookup"><span data-stu-id="53cff-172">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="53cff-173">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="53cff-173">Need help?</span></span> <span data-ttu-id="53cff-174">Entre em contato conosco.</span><span class="sxs-lookup"><span data-stu-id="53cff-174">Contact us.</span></span>

<span data-ttu-id="53cff-175">Para perguntas comuns sobre compras de autoatend pois, consulte Perguntas frequentes sobre compras de [autoatend nome.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="53cff-175">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="53cff-176">Se você tiver dúvidas ou precisar de ajuda com compras de [autoatendém, entre em contato com o suporte](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="53cff-176">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>