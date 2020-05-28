---
title: Gerenciar métodos de pagamento
f1.keywords:
- CSH
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
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Saiba como gerenciar seus métodos de pagamento no centro de administração do Microsoft 365.
ms.openlocfilehash: 0320f71180a5c2c127217ebf01854943409e6386
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403673"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="25fed-103">Gerenciar métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="25fed-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="25fed-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="25fed-104">The admin center is changing.</span></span> <span data-ttu-id="25fed-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="25fed-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="25fed-106">Ao comprar produtos ou serviços de negócios da Microsoft, você pode usar um método de pagamento existente ou adicionar um novo.</span><span class="sxs-lookup"><span data-stu-id="25fed-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="25fed-107">Você pode usar um cartão de crédito ou débito ou uma conta bancária para pagar pelas coisas que comprar.</span><span class="sxs-lookup"><span data-stu-id="25fed-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="25fed-108">Se sua conta comercial tiver um perfil de cobrança e você for um proprietário de perfil de cobrança ou um colaborador de perfil de cobrança, você poderá usar o perfil de cobrança que tem o respaldo de um cartão de crédito ou pagamento de fatura para fazer compras ou pagar as contas.</span><span class="sxs-lookup"><span data-stu-id="25fed-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="25fed-109">Se você é um gerente de fatura de cobrança, você só pode usar um perfil de cobrança para pagar as contas.</span><span class="sxs-lookup"><span data-stu-id="25fed-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="25fed-110">Para saber mais sobre perfis e funções de cobrança, confira [gerenciar perfis de cobrança](manage-billing-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="25fed-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="25fed-111">Se sua conta comercial não tiver um perfil de cobrança, qualquer administrador global ou de cobrança poderá gerenciar e usar qualquer conta bancária adicionada à conta comercial.</span><span class="sxs-lookup"><span data-stu-id="25fed-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="25fed-112">No entanto, você só pode gerenciar ou usar cartões de crédito que você adicionar.</span><span class="sxs-lookup"><span data-stu-id="25fed-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="25fed-113">A opção de pagamento com uma conta bancária não está disponível em alguns países ou regiões.</span><span class="sxs-lookup"><span data-stu-id="25fed-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="25fed-114">Você deve usar um método de pagamento emitido do mesmo país do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="25fed-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="25fed-115">Adicionar uma forma de pagamento</span><span class="sxs-lookup"><span data-stu-id="25fed-115">Add a payment method</span></span>

<span data-ttu-id="25fed-116">A adição de um método de pagamento não associa nenhuma assinatura a ela.</span><span class="sxs-lookup"><span data-stu-id="25fed-116">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="25fed-117">Para atribuir uma única assinatura ao método de pagamento, confira [alterar um método de pagamento para uma única assinatura](#change-a-payment-method-for-a-single-subscription).</span><span class="sxs-lookup"><span data-stu-id="25fed-117">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="25fed-118">Para substituir todas as assinaturas que usam outra forma de pagamento com a nova, confira [substituir um método de pagamento](#replace-a-payment-method).</span><span class="sxs-lookup"><span data-stu-id="25fed-118">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="25fed-119">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="25fed-119">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="25fed-120">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="25fed-120">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="25fed-121">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="25fed-121">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="25fed-122">Selecione **Adicionar um método de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="25fed-122">Select **Add a payment method**.</span></span>

3. <span data-ttu-id="25fed-123">Na página **Método de pagamento**, escolha um método de pagamento do menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="25fed-123">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>

4. <span data-ttu-id="25fed-124">Insira as informações para o novo cartão ou conta bancária e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="25fed-124">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="25fed-125">Atualizar detalhes de método de pagamento</span><span class="sxs-lookup"><span data-stu-id="25fed-125">Update payment method details</span></span>

<span data-ttu-id="25fed-126">Você pode alterar o nome no cartão de crédito ou débito, no endereço de cobrança ou na data de vencimento de uma forma de pagamento existente.</span><span class="sxs-lookup"><span data-stu-id="25fed-126">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="25fed-127">No entanto, não é possível alterar o número do cartão ou da conta.</span><span class="sxs-lookup"><span data-stu-id="25fed-127">However, you can't change the card or account number.</span></span> <span data-ttu-id="25fed-128">Se o número da conta tiver sido alterado, [substitua-o por outro método de pagamento](#replace-a-payment-method)e [exclua o antigo](#delete-a-payment-method).</span><span class="sxs-lookup"><span data-stu-id="25fed-128">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="25fed-129">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="25fed-129">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="25fed-130">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="25fed-130">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="25fed-131">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="25fed-131">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="25fed-132">Selecione a linha do método de pagamento a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="25fed-132">Select the row of the payment method to update.</span></span> <span data-ttu-id="25fed-133">No painel direito, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25fed-133">In the right pane, select **Edit**.</span></span>

3. <span data-ttu-id="25fed-134">Atualize suas informações de método de pagamento, inclusive o nome no cartão de crédito ou de débito, no endereço de cobrança ou na data de vencimento e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25fed-134">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="25fed-135">Substituir uma método de pagamento</span><span class="sxs-lookup"><span data-stu-id="25fed-135">Replace a payment method</span></span>

<span data-ttu-id="25fed-136">Ao substituir uma forma de pagamento, você a substitui por todas as assinaturas e perfis de cobrança que usam a mesma forma de pagamento.</span><span class="sxs-lookup"><span data-stu-id="25fed-136">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="25fed-137">A substituição de um método de pagamento não exclui o método de pagamento existente.</span><span class="sxs-lookup"><span data-stu-id="25fed-137">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="25fed-138">Ainda está disponível para você selecionar e usar para outras assinaturas e perfis de cobrança.</span><span class="sxs-lookup"><span data-stu-id="25fed-138">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="25fed-139">Para alterar a forma de pagamento de uma única assinatura, confira [alterar um método de pagamento para uma única assinatura](#change-a-payment-method-for-a-single-subscription).</span><span class="sxs-lookup"><span data-stu-id="25fed-139">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="25fed-140">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="25fed-140">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="25fed-141">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="25fed-141">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="25fed-142">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="25fed-142">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="25fed-143">Selecione a linha do método de pagamento a ser substituído.</span><span class="sxs-lookup"><span data-stu-id="25fed-143">Select the row of the payment method to replace.</span></span> <span data-ttu-id="25fed-144">O painel direito lista todos os perfis de cobrança e assinaturas individuais que usam o método de pagamento selecionado.</span><span class="sxs-lookup"><span data-stu-id="25fed-144">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>

3. <span data-ttu-id="25fed-145">No painel direito, marque **Substituir o método de pagamento para todos os itens**.</span><span class="sxs-lookup"><span data-stu-id="25fed-145">In the right pane, select **Replace payment method for all items**.</span></span>

4. <span data-ttu-id="25fed-146">Para usar um método de pagamento existente, escolha um na lista suspensa e selecione **Substituir**.</span><span class="sxs-lookup"><span data-stu-id="25fed-146">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="25fed-147">Se você tiver assinaturas associadas a um perfil de cobrança, só poderá usar um cartão de crédito ou débito para pagar por eles.</span><span class="sxs-lookup"><span data-stu-id="25fed-147">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="25fed-148">Se você tiver contas bancárias listadas na página **Métodos de pagamento**, elas não estarão disponíveis para seleção na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="25fed-148">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>

5. <span data-ttu-id="25fed-149">Para adicionar um novo método de pagamento, marque**Adicionar método de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="25fed-149">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="25fed-150">No painel **Adicionar um método de pagamento**, insira as informações da conta e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25fed-150">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="25fed-151">Você deve usar um método de pagamento do mesmo país do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="25fed-151">You must use a payment method from the same country as your tenant.</span></span>

7. <span data-ttu-id="25fed-152">O novo método de pagamento já está selecionado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="25fed-152">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="25fed-153">Selecione **Substituir**.</span><span class="sxs-lookup"><span data-stu-id="25fed-153">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="25fed-154">Alterar um método de pagamento para uma única assinatura</span><span class="sxs-lookup"><span data-stu-id="25fed-154">Change a payment method for a single subscription</span></span>

<span data-ttu-id="25fed-155">Você pode alterar o método de pagamento usado para pagar uma única assinatura.</span><span class="sxs-lookup"><span data-stu-id="25fed-155">You can change the payment method used to pay for a single subscription.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="25fed-156">No centro de administração, vá para a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="25fed-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="25fed-157">No centro de administração, vá para a página **Cobrança** > **Seus produtos**.</span><span class="sxs-lookup"><span data-stu-id="25fed-157">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="25fed-158">No centro de administração, vá para a página **Cobrança** > **Seus produtos**.</span><span class="sxs-lookup"><span data-stu-id="25fed-158">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

2. <span data-ttu-id="25fed-159">Na guia **assinaturas** , selecione a assinatura que você deseja pagar com a método de pagamento alternativo.</span><span class="sxs-lookup"><span data-stu-id="25fed-159">On the **Subscriptions** tab, select the subscription that you want to pay for with the alternate payment method.</span></span>

3. <span data-ttu-id="25fed-160">Em **cobrança**, ao lado da forma de pagamento, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25fed-160">Under **Billing**, next to the payment method, select **Edit**.</span></span>

4. <span data-ttu-id="25fed-161">Ao lado de sua método de pagamento existente, selecione **alterar**.</span><span class="sxs-lookup"><span data-stu-id="25fed-161">Next to your existing payment method, select **Change**.</span></span>

5. <span data-ttu-id="25fed-162">Na lista suspensa, escolha uma forma de pagamento alternativa ou escolha Adicionar uma forma de pagamento.</span><span class="sxs-lookup"><span data-stu-id="25fed-162">From the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>

6. <span data-ttu-id="25fed-163">Se você adicionar um método de pagamento, insira os detalhes do cartão ou da conta e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="25fed-163">If you add a payment method, enter the card or account details, then select **Save**.</span></span>

7. <span data-ttu-id="25fed-164">Verifique se o método de pagamento selecionado está correto e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="25fed-164">Verify that the selected payment method is correct, then select **Save**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="25fed-165">Excluir um método de pagamento</span><span class="sxs-lookup"><span data-stu-id="25fed-165">Delete a payment method</span></span>

<span data-ttu-id="25fed-166">Você só pode excluir um método de pagamento que não esteja anexado a uma assinatura ou a um perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="25fed-166">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="25fed-167">Isso se aplica a todas as assinaturas, seja qual for o status.</span><span class="sxs-lookup"><span data-stu-id="25fed-167">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="25fed-168">Excluir um método de pagamento sem assinaturas ou perfis de cobrança anexados</span><span class="sxs-lookup"><span data-stu-id="25fed-168">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="25fed-169">Se um método de pagamento não estiver associado a qualquer assinatura ou perfil de cobrança, você poderá excluí-lo imediatamente.</span><span class="sxs-lookup"><span data-stu-id="25fed-169">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="25fed-170">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="25fed-170">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="25fed-171">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="25fed-171">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="25fed-172">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="25fed-172">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="25fed-173">Encontre o método de pagamento a ser excluído, selecione os três pontos e, em seguida, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="25fed-173">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>

3. <span data-ttu-id="25fed-174">Na parte inferior do painel direito, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="25fed-174">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="25fed-175">Excluir um método de pagamento com assinaturas ou perfis de cobrança anexados</span><span class="sxs-lookup"><span data-stu-id="25fed-175">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="25fed-176">Se um método de pagamento estiver anexado a qualquer assinatura ou perfil de cobrança, primeiro substitua-o por um método de pagamento existente, ou adicione um novo, e exclua o antigo método de pagamento.</span><span class="sxs-lookup"><span data-stu-id="25fed-176">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="25fed-177">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> .</span><span class="sxs-lookup"><span data-stu-id="25fed-177">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="25fed-178">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="25fed-178">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="25fed-179">No centro de administração, vá para a página métodos de pagamento **de faturas** > **& pagamentos** > **Payment methods** .</span><span class="sxs-lookup"><span data-stu-id="25fed-179">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="25fed-180">Selecione a linha para o método de pagamento a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="25fed-180">Select the row for the payment method to delete.</span></span> <span data-ttu-id="25fed-181">O painel direito lista as assinaturas existentes que usam essa forma de pagamento.</span><span class="sxs-lookup"><span data-stu-id="25fed-181">The right pane lists existing subscriptions that use that payment method.</span></span>

3. <span data-ttu-id="25fed-182">No painel direito, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="25fed-182">In the right pane, select **Delete**.</span></span>

4. <span data-ttu-id="25fed-183">Para usar um método de pagamento existente, escolha um na lista suspensa, selecione **Avançar**e, em seguida, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="25fed-183">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="25fed-184">Se você tiver assinaturas associadas a um perfil de cobrança, só poderá usar um cartão de crédito para pagar por elas.</span><span class="sxs-lookup"><span data-stu-id="25fed-184">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="25fed-185">Se você tiver contas bancárias listadas na página **métodos de pagamento** , elas não estarão disponíveis para escolher na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="25fed-185">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>

5. <span data-ttu-id="25fed-186">Para adicionar um novo método de pagamento, marque**Adicionar método de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="25fed-186">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="25fed-187">Escolha o tipo de método de pagamento que você deseja adicionar, insira as informações da conta e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="25fed-187">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>

7. <span data-ttu-id="25fed-188">O novo método de pagamento já está selecionado na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="25fed-188">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="25fed-189">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="25fed-189">Select **Next**.</span></span>

8. <span data-ttu-id="25fed-190">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="25fed-190">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="25fed-191">Solucionar problemas de formas de pagamento</span><span class="sxs-lookup"><span data-stu-id="25fed-191">Troubleshoot payment methods</span></span>

|<span data-ttu-id="25fed-192">**Problema**</span><span class="sxs-lookup"><span data-stu-id="25fed-192">**Issue**</span></span>|<span data-ttu-id="25fed-193">**Etapas de solução de problemas**</span><span class="sxs-lookup"><span data-stu-id="25fed-193">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="25fed-194">**Recebo uma mensagem de erro que diz: "o navegador está definido atualmente para bloquear cookies".**</span><span class="sxs-lookup"><span data-stu-id="25fed-194">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="25fed-195">Configure seu navegador para permitir cookies de terceiros e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="25fed-195">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="25fed-196">**Meu cartão de crédito ou débito foi recusado.**</span><span class="sxs-lookup"><span data-stu-id="25fed-196">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="25fed-197">Se você pagar por cartão de crédito ou débito e seu cartão for recusado, você receberá um email dizendo que a Microsoft não pôde processar o pagamento.</span><span class="sxs-lookup"><span data-stu-id="25fed-197">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="25fed-198">Verifique se o número do cartão de detalhes do cartão &mdash; , a data de vencimento, o nome no cartão e o endereço, incluindo cidade, estado e CEP, &mdash; aparecem exatamente como eles fazem no cartão e na instrução.</span><span class="sxs-lookup"><span data-stu-id="25fed-198">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="25fed-199">Você pode atualizar as informações do cartão e enviar o pagamento imediatamente usando o link de **equilíbrio de liquidação** na seção **cobrança** da página detalhes da assinatura.</span><span class="sxs-lookup"><span data-stu-id="25fed-199">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="25fed-200">Para obter mais informações, consulte e [se meu cartão de crédito foi recusado e se o meu pagamento está](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due) vencido?</span><span class="sxs-lookup"><span data-stu-id="25fed-200">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="25fed-201">Se você continuar a ver a mensagem "recusada", entre em contato com seu banco.</span><span class="sxs-lookup"><span data-stu-id="25fed-201">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="25fed-202">É possível que o cartão não esteja ativo.</span><span class="sxs-lookup"><span data-stu-id="25fed-202">It's possible that your card isn't active.</span></span> <span data-ttu-id="25fed-203">Se você recebeu recentemente o cartão no email com uma data de validade atualizada, verifique se ele está ativado.</span><span class="sxs-lookup"><span data-stu-id="25fed-203">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="25fed-204">Seu banco também pode informá-lo se o cartão não está aprovado para transações online, internacionais ou recorrentes.</span><span class="sxs-lookup"><span data-stu-id="25fed-204">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="25fed-205">**Desejo atualizar um cartão ou número de conta bancária.**</span><span class="sxs-lookup"><span data-stu-id="25fed-205">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="25fed-206">Não é possível alterar o número do cartão ou da conta em um método de pagamento existente.</span><span class="sxs-lookup"><span data-stu-id="25fed-206">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="25fed-207">Se o seu número de cartão ou conta tiver sido alterado, [substitua-o por outro método de pagamento](#replace-a-payment-method), que move todas as assinaturas ativas da forma de pagamento para a nova e, em seguida, [exclua o antigo método de pagamento](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span><span class="sxs-lookup"><span data-stu-id="25fed-207">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="25fed-208">**Só tenho um cartão ou conta bancária em minha conta e desejo removê-lo.**</span><span class="sxs-lookup"><span data-stu-id="25fed-208">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="25fed-209">Se você tiver apenas uma forma de pagamento, deverá [substituí-la por uma nova método de pagamento antes de](#replace-a-payment-method) excluí-la.</span><span class="sxs-lookup"><span data-stu-id="25fed-209">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="25fed-210">**Não consigo adicionar meu cartão ou minha conta bancária.**</span><span class="sxs-lookup"><span data-stu-id="25fed-210">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="25fed-211">Você deve usar um método de pagamento emitido do mesmo país do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="25fed-211">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="25fed-212">Se você tiver problemas para inserir as informações do cartão ou da conta bancária, você pode [entrar em contato com o suporte](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="25fed-212">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-articles"></a><span data-ttu-id="25fed-213">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="25fed-213">Related articles</span></span>

[<span data-ttu-id="25fed-214">Pagar sua assinatura de negócios</span><span class="sxs-lookup"><span data-stu-id="25fed-214">Pay for your business subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="25fed-215">Gerenciar perfis de cobrança</span><span class="sxs-lookup"><span data-stu-id="25fed-215">Manage billing profiles</span></span>](manage-billing-profiles.md)

[<span data-ttu-id="25fed-216">Alterar a frequência de pagamento</span><span class="sxs-lookup"><span data-stu-id="25fed-216">Change your payment frequency</span></span>](change-payment-frequency.md)