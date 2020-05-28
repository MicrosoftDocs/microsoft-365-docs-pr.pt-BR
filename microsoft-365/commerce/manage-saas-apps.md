---
title: Gerenciar aplicativos de software como serviço para sua organização
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Saiba como ativar e gerenciar aplicativos de terceiros no centro de administração do Microsoft 365.
ms.openlocfilehash: ed1a88345ae5cc135a43f4297ce518b444eaabe7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402577"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="e673f-103">Gerenciar assinaturas de aplicativos de terceiros para sua organização</span><span class="sxs-lookup"><span data-stu-id="e673f-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e673f-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="e673f-104">The admin center is changing.</span></span> <span data-ttu-id="e673f-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e673f-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e673f-106">Você pode gerenciar licenças e cobrança para aplicativos de terceiros no centro de administração do Microsoft 365 com o modo de visualização ativado.</span><span class="sxs-lookup"><span data-stu-id="e673f-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="e673f-107">Os recursos atualizados incluem gerenciamento avançado de assinatura, acesso melhorado às informações de cobrança e maior flexibilidade para gerenciar contas.</span><span class="sxs-lookup"><span data-stu-id="e673f-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="e673f-108">O gerenciamento de assinatura é baseado na plataforma comercial atualizada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e673f-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="e673f-109">Isso se aplica a aplicativos de software como serviço que os clientes adquirem diretamente ou de provedor de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e673f-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="e673f-110">Como obter aplicativos de software como serviço</span><span class="sxs-lookup"><span data-stu-id="e673f-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="e673f-111">Há algumas maneiras de comprar aplicativos de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e673f-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="e673f-112">**Compra direta** – os clientes podem comprar diretamente assinaturas do [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)ou do [AppSource](https://www.appsource.com/).</span><span class="sxs-lookup"><span data-stu-id="e673f-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="e673f-113">**Compra de parceiro** – trabalhe com um parceiro por meio do Partner Center para comprar assinaturas.</span><span class="sxs-lookup"><span data-stu-id="e673f-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="e673f-114">**Proposta da Microsoft** – responder a uma proposta da Microsoft Sales que inclui aplicativos de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e673f-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="e673f-115">Depois que os clientes comprarem os aplicativos e aceitarem o contrato do cliente da Microsoft, eles poderão gerenciá-los no centro de administração do Microsoft 365 ou na Microsoft Store para empresas.</span><span class="sxs-lookup"><span data-stu-id="e673f-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="e673f-116">Os provedores de aplicativos vendem seus aplicativos a uma taxa simples ou comprando licenças para usuários.</span><span class="sxs-lookup"><span data-stu-id="e673f-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="e673f-117">**Taxa plana** – também chamados de preços baseados em site, os aplicativos têm preços mensais ou anuais.</span><span class="sxs-lookup"><span data-stu-id="e673f-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="e673f-118">Na página aplicativo, a quantidade de licença é listada em ilimitado.</span><span class="sxs-lookup"><span data-stu-id="e673f-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="e673f-119">**Licenças** – os aplicativos têm o preço da licença.</span><span class="sxs-lookup"><span data-stu-id="e673f-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="e673f-120">Os clientes atribuem licenças a cada usuário de sua organização</span><span class="sxs-lookup"><span data-stu-id="e673f-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="e673f-121">Regiões com suporte</span><span class="sxs-lookup"><span data-stu-id="e673f-121">Supported regions</span></span>

<span data-ttu-id="e673f-122">O suporte para aplicativos de terceiros está disponível nestas regiões:</span><span class="sxs-lookup"><span data-stu-id="e673f-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="e673f-123">Argentina</span><span class="sxs-lookup"><span data-stu-id="e673f-123">Argentina</span></span>
- <span data-ttu-id="e673f-124">Austrália</span><span class="sxs-lookup"><span data-stu-id="e673f-124">Australia</span></span>
- <span data-ttu-id="e673f-125">Canadá</span><span class="sxs-lookup"><span data-stu-id="e673f-125">Canada</span></span>
- <span data-ttu-id="e673f-126">Chile</span><span class="sxs-lookup"><span data-stu-id="e673f-126">Chile</span></span>
- <span data-ttu-id="e673f-127">França</span><span class="sxs-lookup"><span data-stu-id="e673f-127">France</span></span>
- <span data-ttu-id="e673f-128">Alemanha</span><span class="sxs-lookup"><span data-stu-id="e673f-128">Germany</span></span>
- <span data-ttu-id="e673f-129">Grécia</span><span class="sxs-lookup"><span data-stu-id="e673f-129">Greece</span></span>
- <span data-ttu-id="e673f-130">Porto Rico</span><span class="sxs-lookup"><span data-stu-id="e673f-130">Puerto Rico</span></span>
- <span data-ttu-id="e673f-131">África do Sul</span><span class="sxs-lookup"><span data-stu-id="e673f-131">South Africa</span></span>
- <span data-ttu-id="e673f-132">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="e673f-132">United Kingdom</span></span>
- <span data-ttu-id="e673f-133">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="e673f-133">United States</span></span>
- <span data-ttu-id="e673f-134">Europa Ocidental</span><span class="sxs-lookup"><span data-stu-id="e673f-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="e673f-135">Ativar aplicativos de terceiros</span><span class="sxs-lookup"><span data-stu-id="e673f-135">Activate third-party apps</span></span>

<span data-ttu-id="e673f-136">Os administradores devem ativar aplicativos de terceiros antes de atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="e673f-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="e673f-137">Esses aplicativos são ativados no portal do fornecedor de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e673f-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="e673f-138">No centro de administração, vá para a página **cobrança**de  >  **seus**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">aplicativos</a> de produtos.</span><span class="sxs-lookup"><span data-stu-id="e673f-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e673f-139">Localize e selecione o aplicativo que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="e673f-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e673f-140">Em **configurações & ações**, selecione **gerenciar no portal do Publisher**.</span><span class="sxs-lookup"><span data-stu-id="e673f-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="e673f-141">Você será direcionado para o site do fornecedor do aplicativo onde é possível ativar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e673f-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="e673f-142">Gerenciar aplicativos de terceiros</span><span class="sxs-lookup"><span data-stu-id="e673f-142">Manage third-party apps</span></span>

<span data-ttu-id="e673f-143">Os administradores gerenciam aplicativos de terceiros em dois locais: centro de administração do Microsoft 365 e portal do provedor de aplicativos terceirizado.</span><span class="sxs-lookup"><span data-stu-id="e673f-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="e673f-144">Veja aqui o que você pode fazer em cada portal.</span><span class="sxs-lookup"><span data-stu-id="e673f-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="e673f-145">Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e673f-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="e673f-146">Portal do fornecedor do aplicativo</span><span class="sxs-lookup"><span data-stu-id="e673f-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="e673f-147">Alterar a quantidade de licenças</span><span class="sxs-lookup"><span data-stu-id="e673f-147">Change license quantity</span></span> <br> <span data-ttu-id="e673f-148">Gerenciar como pagar sua cobrança</span><span class="sxs-lookup"><span data-stu-id="e673f-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="e673f-149">Gerenciar como pagar sua cobrança</span><span class="sxs-lookup"><span data-stu-id="e673f-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="e673f-150">Alterar método de pagamento (cartão de crédito)</span><span class="sxs-lookup"><span data-stu-id="e673f-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="e673f-151">Exibir fatura</span><span class="sxs-lookup"><span data-stu-id="e673f-151">View invoice</span></span> <br> <span data-ttu-id="e673f-152">Cancelar assinatura do aplicativo</span><span class="sxs-lookup"><span data-stu-id="e673f-152">Cancel app subscription</span></span> | <span data-ttu-id="e673f-153">Configurar o aplicativo (uma vez para cada aplicativo)</span><span class="sxs-lookup"><span data-stu-id="e673f-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="e673f-154">Atribuir licenças aos usuários</span><span class="sxs-lookup"><span data-stu-id="e673f-154">Assign licenses to users</span></span> <br> <span data-ttu-id="e673f-155">Suporte técnico</span><span class="sxs-lookup"><span data-stu-id="e673f-155">Technical support</span></span> |

<span data-ttu-id="e673f-156">Depois que o aplicativo é ativado, ele permanece ativo, a menos que seja cancelado, expira ou se o pagamento não for mantido atual.</span><span class="sxs-lookup"><span data-stu-id="e673f-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="e673f-157">Esses eventos alteram o status do aplicativo para desabilitado.</span><span class="sxs-lookup"><span data-stu-id="e673f-157">These events change the app status to disabled.</span></span> <span data-ttu-id="e673f-158">Depois que um aplicativo é desabilitado, ele não pode ser reativado.</span><span class="sxs-lookup"><span data-stu-id="e673f-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="e673f-159">Para continuar usando o aplicativo, compre outra cópia dele.</span><span class="sxs-lookup"><span data-stu-id="e673f-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="e673f-160">Atribua licenças</span><span class="sxs-lookup"><span data-stu-id="e673f-160">Assign licenses</span></span>

<span data-ttu-id="e673f-161">Os administradores precisam ativar aplicativos de terceiros antes de atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="e673f-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="e673f-162">Eles são ativados no portal do fornecedor de terceiros.</span><span class="sxs-lookup"><span data-stu-id="e673f-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="e673f-163">Na página aplicativo, em **configurações & ações**, selecione o link para atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="e673f-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="e673f-164">No centro de administração, vá para a página **cobrança**de  >  **seus**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">aplicativos</a> de produtos.</span><span class="sxs-lookup"><span data-stu-id="e673f-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e673f-165">Localize e selecione o aplicativo que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="e673f-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e673f-166">Em **configurações & ações**, selecione o link para **gerenciar no portal do Publisher**.</span><span class="sxs-lookup"><span data-stu-id="e673f-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="e673f-167">Alterar a quantidade de licenças</span><span class="sxs-lookup"><span data-stu-id="e673f-167">Change license quantity</span></span>

<span data-ttu-id="e673f-168">Os administradores podem alterar o número de licenças pertencentes à sua organização.</span><span class="sxs-lookup"><span data-stu-id="e673f-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="e673f-169">Isso aplica-se apenas aos aplicativos adquiridos com o preço baseado em assento.</span><span class="sxs-lookup"><span data-stu-id="e673f-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="e673f-170">No centro de administração, vá para a página **cobrança**de  >  **seus**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">aplicativos</a> de produtos.</span><span class="sxs-lookup"><span data-stu-id="e673f-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e673f-171">Localize e selecione o aplicativo que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="e673f-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e673f-172">Selecione **Alterar quantidade de licenças**.</span><span class="sxs-lookup"><span data-stu-id="e673f-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="e673f-173">Gerenciar métodos de pagamento</span><span class="sxs-lookup"><span data-stu-id="e673f-173">Manage payment methods</span></span>

<span data-ttu-id="e673f-174">Os aplicativos de software como serviço têm um perfil de cobrança atribuído a eles.</span><span class="sxs-lookup"><span data-stu-id="e673f-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="e673f-175">Os perfis de cobrança permitem que você personalize quais produtos estão incluídos em sua fatura e como você paga suas faturas.</span><span class="sxs-lookup"><span data-stu-id="e673f-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="e673f-176">Elas incluem:</span><span class="sxs-lookup"><span data-stu-id="e673f-176">They include:</span></span>

- <span data-ttu-id="e673f-177">**Métodos de pagamento** – cartões de crédito ou transferência por fio/cheque</span><span class="sxs-lookup"><span data-stu-id="e673f-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="e673f-178">**Informações de contato** – endereço de cobrança e nome de um contato</span><span class="sxs-lookup"><span data-stu-id="e673f-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="e673f-179">**Funções** – funções que permitem alterar o perfil de cobrança, pagar contas ou usar a forma de pagamento no perfil de cobrança para fazer a compra.</span><span class="sxs-lookup"><span data-stu-id="e673f-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="e673f-180">Para obter mais informações sobre perfis de cobrança, consulte [entender perfis de cobrança](https://docs.microsoft.com/microsoft-store/billing-profile).</span><span class="sxs-lookup"><span data-stu-id="e673f-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="e673f-181">Alterar o perfil de cobrança em uma assinatura de aplicativo de software como serviço</span><span class="sxs-lookup"><span data-stu-id="e673f-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="e673f-182">No centro de administração, vá para a página **cobrança**de  >  **seus**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">aplicativos</a> de produtos.</span><span class="sxs-lookup"><span data-stu-id="e673f-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e673f-183">Localize e selecione o aplicativo que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="e673f-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e673f-184">Ao lado de **perfil de cobrança**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e673f-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="e673f-185">Para obter mais informações sobre faturas, confira [entender sua fatura ou fatura](billing-and-payments/understand-your-invoice.md).</span><span class="sxs-lookup"><span data-stu-id="e673f-185">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="e673f-186">Cancelar uma assinatura de aplicativo de software como serviço</span><span class="sxs-lookup"><span data-stu-id="e673f-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="e673f-187">Você pode cancelar um aplicativo de software como serviço na página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e673f-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="e673f-188">No centro de administração, vá para a página **cobrança**de  >  **seus**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">aplicativos</a> de produtos.</span><span class="sxs-lookup"><span data-stu-id="e673f-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="e673f-189">Localize e selecione o aplicativo que você deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="e673f-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="e673f-190">Em **configurações & ações**, selecione **cancelar assinatura**.</span><span class="sxs-lookup"><span data-stu-id="e673f-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>
