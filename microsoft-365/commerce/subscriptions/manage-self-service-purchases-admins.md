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
search.appverid:
- MET150
description: Os administradores podem aprender a gerenciar compras de autoatendimento feitas por usuários em sua organização.
ms.openlocfilehash: f3ccd1f8ab5f2f9fc78e2920182155ef7f6f16e3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080328"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="bc739-103">Gerenciar compras de autoatendimento (administrador)</span><span class="sxs-lookup"><span data-stu-id="bc739-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="bc739-104">Como administrador, você pode ver compras de autoatendimento feitas por pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bc739-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="bc739-105">Você pode ver o produto, o nome do comprador, as assinaturas adquiridas, a data de vencimento, o preço de compra e os usuários atribuídos para cada compra de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="bc739-105">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="bc739-106">Se for necessário para sua organização, você poderá desativar a compras de autoatendimento por produto através do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bc739-106">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="bc739-107">Você tem as mesmas políticas de gerenciamento e de acesso a dados sobre produtos comprados por autoatendimento ou de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="bc739-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="bc739-108">Você também pode controlar se os usuários da sua organização podem fazer compras de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="bc739-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="bc739-109">Para obter mais informações, consulte [usar AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="bc739-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="bc739-110">Exibir assinaturas de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="bc739-110">View self-service subscriptions</span></span>

1. <span data-ttu-id="bc739-111">No centro de administração, vá para a página de serviços de **cobrança** > de<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">produtos &</a> .</span><span class="sxs-lookup"><span data-stu-id="bc739-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="bc739-112">Ao lado de **refinar resultados**, no menu suspenso **tipo de conta** , escolha **autoatendimento**.</span><span class="sxs-lookup"><span data-stu-id="bc739-112">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="bc739-113">Para exibir mais detalhes sobre uma assinatura, escolha uma na lista.</span><span class="sxs-lookup"><span data-stu-id="bc739-113">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="bc739-114">Exibir quem possui licenças para uma assinatura de compra de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="bc739-114">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="bc739-115">No centro de administração, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de **cobrança** > .</span><span class="sxs-lookup"><span data-stu-id="bc739-115">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="bc739-116">Escolha o ícone de filtro e, em seguida, escolha **autoatendimento**.</span><span class="sxs-lookup"><span data-stu-id="bc739-116">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="bc739-117">Selecione um produto para ver licenças atribuídas a pessoas.</span><span class="sxs-lookup"><span data-stu-id="bc739-117">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc739-118">Se houver várias compras para um produto, esse produto será listado apenas uma vez, e a coluna **quantidade disponível** mostrará o total de todas as assinaturas compradas para o produto.</span><span class="sxs-lookup"><span data-stu-id="bc739-118">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="bc739-119">A lista de **usuários** é agrupada por nomes de pessoas que fizeram compras de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="bc739-119">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="bc739-120">Para exportar uma lista de usuários com licenças para essas assinaturas, escolha as assinaturas que você deseja exportar e, em seguida, escolha **exportar usuários**.</span><span class="sxs-lookup"><span data-stu-id="bc739-120">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="bc739-121">Desabilitar ou habilitar compras de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="bc739-121">Disable or enable self-service purchases</span></span>

<span data-ttu-id="bc739-122">Você pode desabilitar ou habilitar compras de autoatendimento para usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bc739-122">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="bc739-123">O módulo **MSCommerce** do PowerShell inclui um valor de parâmetro **PolicyId** para **AllowSelfServicePurchase** que permite controlar se os usuários da sua organização podem fazer compras de autoatendimento e para quais produtos.</span><span class="sxs-lookup"><span data-stu-id="bc739-123">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="bc739-124">Você pode usar o módulo do PowerShell do **MSCommerce** para:</span><span class="sxs-lookup"><span data-stu-id="bc739-124">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="bc739-125">Exibir o estado padrão do valor \*\*\*\* &mdash; do parâmetro AllowSelfServicePurchase se ele está habilitado ou desabilitado por produto</span><span class="sxs-lookup"><span data-stu-id="bc739-125">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="bc739-126">Exibir uma lista de produtos aplicáveis e se a compra de autoatendimento está habilitada ou desabilitada</span><span class="sxs-lookup"><span data-stu-id="bc739-126">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="bc739-127">Exibir ou modificar a configuração atual de um produto específico para habilitá-lo ou desabilitá-lo</span><span class="sxs-lookup"><span data-stu-id="bc739-127">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="bc739-128">Para obter mais informações, consulte [usar AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="bc739-128">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="bc739-129">Centralizar licenças sob uma única assinatura</span><span class="sxs-lookup"><span data-stu-id="bc739-129">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="bc739-130">Você pode atribuir licenças existentes ou comprar assinaturas adicionais por meio de acordos existentes para usuários atribuídos a compras de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="bc739-130">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="bc739-131">Depois de atribuir essas licenças de compra central, você pode solicitar que os compradores cancelem as assinaturas existentes.</span><span class="sxs-lookup"><span data-stu-id="bc739-131">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="bc739-132">Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Administração</a> com sua conta de administrador global ou de cobrança.</span><span class="sxs-lookup"><span data-stu-id="bc739-132">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="bc739-133">Vá para a página de<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">serviços de compra</a> de **cobrança** > .</span><span class="sxs-lookup"><span data-stu-id="bc739-133">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="bc739-134">Localize e escolha o produto que você deseja comprar e escolha **comprar**.</span><span class="sxs-lookup"><span data-stu-id="bc739-134">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="bc739-135">Conclua as etapas restantes para concluir sua compra.</span><span class="sxs-lookup"><span data-stu-id="bc739-135">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="bc739-136">Siga as etapas em [Exibir quem possui licenças para uma assinatura adquirida por autoatendimento](#view-who-has-licenses-for-a-self-service-purchase-subscription) para exportar uma lista de usuários para referência na etapa 6.</span><span class="sxs-lookup"><span data-stu-id="bc739-136">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="bc739-137">Atribuir licenças a todas as pessoas que têm uma licença na outra assinatura.</span><span class="sxs-lookup"><span data-stu-id="bc739-137">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="bc739-138">Para ver as etapas completas, confira [atribuir licenças aos usuários](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="bc739-138">For full steps, see [Assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

7. <span data-ttu-id="bc739-139">Entre em contato com a pessoa que comprou a assinatura de compras de autoatendimento e peça que ela seja cancelada.</span><span class="sxs-lookup"><span data-stu-id="bc739-139">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="bc739-140">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="bc739-140">Need help?</span></span> <span data-ttu-id="bc739-141">Entre em contato conosco.</span><span class="sxs-lookup"><span data-stu-id="bc739-141">Contact us.</span></span>

<span data-ttu-id="bc739-142">Para perguntas comuns sobre compras de autoatendimento, consulte [perguntas frequentes sobre compras de autoatendimento](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="bc739-142">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="bc739-143">Se você tiver dúvidas ou precisar de ajuda com compras de autoatendimento, [entre em contato com o suporte](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="bc739-143">If you have questions or need help with self-service purchases, [contact support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
