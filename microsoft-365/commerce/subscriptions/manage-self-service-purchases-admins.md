---
title: Gerenciar compras de autoatendir (Administradores)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce_ssp
search.appverid:
- MET150
description: Os administradores podem aprender a gerenciar compras de autoatendados feitas pelos usuários em sua organização.
ms.date: 03/26/2021
ms.openlocfilehash: a4ac4b79a9a73f80fc22e6f14696e25925df9faf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536089"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="d9eb3-103">Gerenciar compras de autoatendimento (Administrador)</span><span class="sxs-lookup"><span data-stu-id="d9eb3-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="d9eb3-104">Como administrador, você pode ver compras autoatendadas feitas por pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="d9eb3-105">Você vê o nome do produto, o nome do comprador, as assinaturas compradas, a data de expiração, o preço de compra e os usuários atribuídos para cada compra de autoatendido.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-105">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="d9eb3-106">Se necessário pela sua organização, você pode desativar a compra de autoatendados por produto por meio do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-106">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="d9eb3-107">Você tem as mesmas políticas de gerenciamento e acesso de dados sobre produtos comprados por meio da compra de autoatendados ou centralmente.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="d9eb3-108">Você também pode controlar se os usuários em sua organização podem fazer compras de autoatendado.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="d9eb3-109">Para obter mais informações, [consulte Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d9eb3-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="d9eb3-110">Exibir assinaturas de autoatend</span><span class="sxs-lookup"><span data-stu-id="d9eb3-110">View self-service subscriptions</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d9eb3-111">No centro de administração, vá para a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d9eb3-112">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-112">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d9eb3-113">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-113">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="d9eb3-114">Na guia **Produtos,** selecione o ícone de filtro e, em seguida, **selecione Autoatendados**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="d9eb3-115">Para exibir mais detalhes sobre uma assinatura, escolha um na lista.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="d9eb3-116">Exibir quem tem licenças para uma assinatura de compra de autoatend</span><span class="sxs-lookup"><span data-stu-id="d9eb3-116">View who has licenses for a self-service purchase subscription</span></span>

> [!NOTE]
> <span data-ttu-id="d9eb3-117">Como administrador, você não pode atribuir ou cancelar a atribuição de licenças para uma assinatura de compra de autoatendimento comprada por um usuário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-117">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="d9eb3-118">Você pode [assumir uma assinatura de compra de autoatendimento](#take-over-a-self-service-purchase-subscription), e, em seguida, atribuir ou cancelar a atribuição de licenças.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-118">You can [take over a self-service purchase subscription](#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d9eb3-119">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="d9eb3-120">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="d9eb3-121">No centro de administração, acesse a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenças</a>.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="d9eb3-122">Selecione o ícone de filtro e escolha **Autoatendado**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-122">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="d9eb3-123">Selecione um produto para ver licenças atribuídas às pessoas.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-123">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="d9eb3-124">Se houver várias compras para um produto, esse produto será listado apenas uma vez, e **a** coluna Quantidade Disponível mostrará o total de todas as assinaturas compradas para esse produto.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-124">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="d9eb3-125">A **lista** Usuários é agrupada pelos nomes de pessoas que fizeram compras de autoatendido.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-125">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="d9eb3-126">Para exportar uma lista de usuários com licenças para essas assinaturas, escolha as assinaturas que você deseja exportar e escolha **Exportar usuários**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-126">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="d9eb3-127">Desabilitar ou habilitar compras autoatendenciadas</span><span class="sxs-lookup"><span data-stu-id="d9eb3-127">Disable or enable self-service purchases</span></span>

<span data-ttu-id="d9eb3-128">Você pode desabilitar ou habilitar compras de autoatendencia para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-128">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="d9eb3-129">O **módulo MSCommerce** PowerShell inclui um valor de parâmetro **PolicyID** para **AllowSelfServicePurchase** que permite controlar se os usuários em sua organização podem fazer compras de autoatendiço e para quais produtos.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-129">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="d9eb3-130">Você pode usar o **módulo MSCommerce** PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="d9eb3-130">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="d9eb3-131">Exibir o estado padrão do **valor do parâmetro AllowSelfServicePurchase,** seja ele habilitado ou desabilitado pelo produto</span><span class="sxs-lookup"><span data-stu-id="d9eb3-131">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="d9eb3-132">Exibir uma lista de produtos aplicáveis e se a compra de autoatendados está habilitada ou desabilitada</span><span class="sxs-lookup"><span data-stu-id="d9eb3-132">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="d9eb3-133">Exibir ou modificar a configuração atual de um produto específico para habilita-lo ou desabilitá-lo</span><span class="sxs-lookup"><span data-stu-id="d9eb3-133">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="d9eb3-134">Para obter mais informações, [consulte Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d9eb3-134">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="d9eb3-135">Centralizar licenças em uma única assinatura</span><span class="sxs-lookup"><span data-stu-id="d9eb3-135">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="d9eb3-136">Você pode atribuir licenças existentes ou comprar assinaturas adicionais por meio de contratos existentes para usuários atribuídos a compras de autoatendência.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-136">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="d9eb3-137">Depois de atribuir essas licenças compradas centralmente, você pode solicitar que os compradores cancelem suas assinaturas existentes.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-137">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d9eb3-138">No centro de administração, vá para a página **Serviços de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Compra de</a> Cobrança.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-138">In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d9eb3-139">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Serviços de** Compra > **de** Cobrança.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-139">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d9eb3-140">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página **Serviços de** Compra > **de** Cobrança.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-140">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

2. <span data-ttu-id="d9eb3-141">Encontre e escolha o produto que você deseja comprar e escolha **Comprar**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-141">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="d9eb3-142">Conclua as etapas restantes para concluir sua compra.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-142">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="d9eb3-143">Siga as etapas em [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-143">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="d9eb3-144">Atribua licenças a todos os que têm uma licença na outra assinatura.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-144">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="d9eb3-145">Para etapas completas, [consulte Atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="d9eb3-145">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="d9eb3-146">Entre em contato com a pessoa que comprou a assinatura de compra de autoatend.0 e peça que [ela cancele.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="d9eb3-146">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="d9eb3-147">Assumir uma assinatura de compra de autoatend</span><span class="sxs-lookup"><span data-stu-id="d9eb3-147">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="d9eb3-148">Você pode assumir uma assinatura de compra autoatendida feita por um usuário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-148">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="d9eb3-149">Ao assumir uma assinatura de compra de autoatendados, você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="d9eb3-149">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="d9eb3-150">Mova os usuários para uma assinatura diferente e cancele a assinatura original.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-150">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="d9eb3-151">Cancele a assinatura de compra de autoatendido e remova licenças de usuários atribuídos.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-151">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="d9eb3-152">Migrar usuários para uma assinatura diferente</span><span class="sxs-lookup"><span data-stu-id="d9eb3-152">Move users to a different subscription</span></span>

<span data-ttu-id="d9eb3-153">Quando você move usuários para uma assinatura diferente, a assinatura antiga é automaticamente cancelada.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-153">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="d9eb3-154">O usuário que comprou originalmente a assinatura de compra de autoatendido recebe um email informando que a assinatura foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-154">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="d9eb3-155">Você deve ter uma licença disponível para cada usuário que está movendo na assinatura para a que você está movendo os usuários.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-155">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d9eb3-156">No centro de administração, vá para a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d9eb3-157">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Cobrança** > **seus** produtos.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-157">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d9eb3-158">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página **Cobrança** > **seus** produtos.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-158">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="d9eb3-159">Na guia **Produtos,** selecione o ícone de filtro e, em seguida, **selecione Autoatendados**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-159">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="d9eb3-160">Selecione a assinatura que você deseja assumir.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-160">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="d9eb3-161">Na página detalhes da assinatura, na seção **Assinaturas e** configurações, selecione **Assumir o controle dessa assinatura**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-161">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="d9eb3-162">No painel direito, selecione **Mover usuários**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-162">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="d9eb3-163">Selecione o produto para o que você deseja mover os usuários e, em seguida, **selecione Mover usuários**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-163">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="d9eb3-164">Na caixa **Mover usuários para,** selecione **Mover usuários**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-164">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="d9eb3-165">O processo de movimentação pode levar vários minutos.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-165">The move process might take several minutes.</span></span> <span data-ttu-id="d9eb3-166">Não feche o navegador enquanto o processo é executado.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-166">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="d9eb3-167">Quando o processo de movimentação for concluído, feche o **painel Mover concluído.**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-167">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="d9eb3-168">Na página detalhes da assinatura, o **status de assinatura** da assinatura adquirida por autoatendados mostra como **Excluído**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-168">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="d9eb3-169">Cancelar uma assinatura de compra de autoatend</span><span class="sxs-lookup"><span data-stu-id="d9eb3-169">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="d9eb3-170">Quando você opta por cancelar uma assinatura de compra de autoatendado, os usuários com licenças perdem acesso ao produto.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-170">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="d9eb3-171">O usuário que comprou originalmente a assinatura de compra de autoatendido recebe um email informando que a assinatura foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-171">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d9eb3-172">No centro de administração, vá para a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-172">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d9eb3-173">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Cobrança** > **seus** produtos.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-173">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d9eb3-174">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página **Cobrança** > **seus** produtos.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-174">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="d9eb3-175">Na guia **Produtos,** selecione o ícone de filtro e, em seguida, **selecione Autoatendados**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-175">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="d9eb3-176">Selecione a assinatura que você deseja alterar.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-176">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="d9eb3-177">Na página detalhes da assinatura, na seção **Assinaturas e** configurações, selecione **Assumir o controle dessa assinatura**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-177">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="d9eb3-178">No painel direito, selecione **Cancelar assinatura**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-178">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="d9eb3-179">Selecione um motivo para o cancelamento na listada e selecione **Cancelar assinatura**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-179">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="d9eb3-180">Na caixa **Tem certeza de que deseja cancelar?** Selecione Cancelar **assinatura**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-180">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="d9eb3-181">Feche o painel direito.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-181">Close the right pane.</span></span>
9. <span data-ttu-id="d9eb3-182">Na página detalhes da assinatura, o **status da assinatura** é como **Excluído**.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-182">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="d9eb3-183">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="d9eb3-183">Need help?</span></span> <span data-ttu-id="d9eb3-184">Entre em contato conosco.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-184">Contact us.</span></span>

<span data-ttu-id="d9eb3-185">Para perguntas comuns sobre compras de autoatend pois, consulte Perguntas frequentes sobre compras de [autoatend nome.](self-service-purchase-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="d9eb3-185">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.yml).</span></span>

<span data-ttu-id="d9eb3-186">Se você tiver dúvidas ou precisar de ajuda com compras de [autoatendém, entre em contato com o suporte](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="d9eb3-186">If you have questions or need help with self-service purchases, [contact support](../../business-video/get-help-support.md).</span></span>
