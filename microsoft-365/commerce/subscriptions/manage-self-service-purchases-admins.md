---
title: Gerenciar compras de autoatendimento (administradores)
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
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Os administradores podem aprender a gerenciar compras de autoatendimento feitas por usuários em sua organização.
ms.openlocfilehash: 562e0e26d9ca7d10d71a46b8cf2d87c487c1b529
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403265"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="bd96e-103">Gerenciar compras de autoatendimento (Administrador)</span><span class="sxs-lookup"><span data-stu-id="bd96e-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="bd96e-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="bd96e-104">The admin center is changing.</span></span> <span data-ttu-id="bd96e-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="bd96e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="bd96e-106">Como administrador, você pode ver compras de autoatendimento feitas por pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd96e-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="bd96e-107">Você pode ver o produto, o nome do comprador, as assinaturas adquiridas, a data de vencimento, o preço de compra e os usuários atribuídos para cada compra de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="bd96e-107">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="bd96e-108">Se for necessário para sua organização, você poderá desativar a compras de autoatendimento por produto através do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd96e-108">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="bd96e-109">Você tem as mesmas políticas de gerenciamento e de acesso a dados sobre produtos comprados por autoatendimento ou de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="bd96e-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="bd96e-110">Você também pode controlar se os usuários da sua organização podem fazer compras de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="bd96e-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="bd96e-111">Para obter mais informações, consulte [usar AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="bd96e-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="bd96e-112">Exibir assinaturas de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="bd96e-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="bd96e-113">No centro de administração, vá para a página **cobrança**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de seus produtos</a> .</span><span class="sxs-lookup"><span data-stu-id="bd96e-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="bd96e-114">Ao lado de **refinar resultados**, no menu suspenso **tipo de conta** , escolha **autoatendimento**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-114">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="bd96e-115">Para exibir mais detalhes sobre uma assinatura, escolha uma na lista.</span><span class="sxs-lookup"><span data-stu-id="bd96e-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="bd96e-116">Exibir quem possui licenças para uma assinatura de compra de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="bd96e-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="bd96e-117">No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de cobrança.</span><span class="sxs-lookup"><span data-stu-id="bd96e-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="bd96e-118">Escolha o ícone de filtro e, em seguida, escolha **autoatendimento**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-118">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="bd96e-119">Selecione um produto para ver licenças atribuídas a pessoas.</span><span class="sxs-lookup"><span data-stu-id="bd96e-119">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd96e-120">Se houver várias compras para um produto, esse produto será listado apenas uma vez, e a coluna **quantidade disponível** mostrará o total de todas as assinaturas compradas para o produto.</span><span class="sxs-lookup"><span data-stu-id="bd96e-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="bd96e-121">A lista de **usuários** é agrupada por nomes de pessoas que fizeram compras de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="bd96e-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="bd96e-122">Para exportar uma lista de usuários com licenças para essas assinaturas, escolha as assinaturas que você deseja exportar e, em seguida, escolha **exportar usuários**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="bd96e-123">Desabilitar ou habilitar compras de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="bd96e-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="bd96e-124">Você pode desabilitar ou habilitar compras de autoatendimento para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd96e-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="bd96e-125">O módulo **MSCommerce** do PowerShell inclui um valor de parâmetro **PolicyId** para **AllowSelfServicePurchase** que permite controlar se os usuários da sua organização podem fazer compras de autoatendimento e para quais produtos.</span><span class="sxs-lookup"><span data-stu-id="bd96e-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="bd96e-126">Você pode usar o módulo do PowerShell do **MSCommerce** para:</span><span class="sxs-lookup"><span data-stu-id="bd96e-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="bd96e-127">Exibir o estado padrão do valor **AllowSelfServicePurchase** do parâmetro AllowSelfServicePurchase &mdash; se ele está habilitado ou desabilitado por produto</span><span class="sxs-lookup"><span data-stu-id="bd96e-127">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="bd96e-128">Exibir uma lista de produtos aplicáveis e se a compra de autoatendimento está habilitada ou desabilitada</span><span class="sxs-lookup"><span data-stu-id="bd96e-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="bd96e-129">Exibir ou modificar a configuração atual de um produto específico para habilitá-lo ou desabilitá-lo</span><span class="sxs-lookup"><span data-stu-id="bd96e-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="bd96e-130">Para obter mais informações, consulte [usar AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="bd96e-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="bd96e-131">Centralizar licenças sob uma única assinatura</span><span class="sxs-lookup"><span data-stu-id="bd96e-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="bd96e-132">Você pode atribuir licenças existentes ou comprar assinaturas adicionais por meio de acordos existentes para usuários atribuídos a compras de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="bd96e-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="bd96e-133">Depois de atribuir essas licenças de compra central, você pode solicitar que os compradores cancelem as assinaturas existentes.</span><span class="sxs-lookup"><span data-stu-id="bd96e-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="bd96e-134">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Administração</a> com sua conta de administrador global ou de cobrança.</span><span class="sxs-lookup"><span data-stu-id="bd96e-134">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="bd96e-135">Vá para a **Billing**  >  página de<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">serviços de compra</a> de cobrança.</span><span class="sxs-lookup"><span data-stu-id="bd96e-135">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="bd96e-136">Localize e escolha o produto que você deseja comprar e escolha **comprar**.</span><span class="sxs-lookup"><span data-stu-id="bd96e-136">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="bd96e-137">Conclua as etapas restantes para concluir sua compra.</span><span class="sxs-lookup"><span data-stu-id="bd96e-137">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="bd96e-138">Siga as etapas em [Exibir quem possui licenças para uma assinatura adquirida por autoatendimento](#view-who-has-licenses-for-a-self-service-purchase-subscription) para exportar uma lista de usuários para referência na etapa 6.</span><span class="sxs-lookup"><span data-stu-id="bd96e-138">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="bd96e-139">Atribuir licenças a todas as pessoas que têm uma licença na outra assinatura.</span><span class="sxs-lookup"><span data-stu-id="bd96e-139">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="bd96e-140">Para ver as etapas completas, confira [atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="bd96e-140">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

7. <span data-ttu-id="bd96e-141">Entre em contato com a pessoa que comprou a assinatura de compras de autoatendimento e peça que ela seja cancelada.</span><span class="sxs-lookup"><span data-stu-id="bd96e-141">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="bd96e-142">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="bd96e-142">Need help?</span></span> <span data-ttu-id="bd96e-143">Entre em contato conosco.</span><span class="sxs-lookup"><span data-stu-id="bd96e-143">Contact us.</span></span>

<span data-ttu-id="bd96e-144">Para perguntas comuns sobre compras de autoatendimento, consulte [perguntas frequentes sobre compras de autoatendimento](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="bd96e-144">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="bd96e-145">Se você tiver dúvidas ou precisar de ajuda com compras de autoatendimento, [entre em contato com o suporte](../../admin/contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="bd96e-145">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>
