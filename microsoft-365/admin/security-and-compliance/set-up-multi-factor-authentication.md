---
title: Configurar a autenticação multifator para usuários do Office 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Aprenda a usar padrões de segurança para configurar a autenticação multifator para usuários do Office 365.
monikerRange: o365-worldwide
ms.openlocfilehash: cb2205e5f5b7df4f6e7d8f7263a91fb2f0f4d3e2
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341253"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="d474f-103">Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="d474f-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="d474f-104">Todas as novas assinaturas do Office 365 para empresas ou do Microsoft 365 Business terão automaticamente os padrões de segurança ativados.</span><span class="sxs-lookup"><span data-stu-id="d474f-104">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="d474f-105">Isso significa que todos os usuários terão que configurar a MFA (autenticação multifator) e instalar o aplicativo autenticador em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="d474f-105">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="d474f-106">Para obter mais informações, confira [Configurar a verificação em duas etapas do Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="d474f-106">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="d474f-107">As nove funções de administrador a seguir serão necessárias para executar uma autenticação adicional sempre que entrarem:</span><span class="sxs-lookup"><span data-stu-id="d474f-107">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="d474f-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="d474f-108">Global administrator</span></span>
- <span data-ttu-id="d474f-109">Administrador do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d474f-109">SharePoint administrator</span></span>
- <span data-ttu-id="d474f-110">Administrador do Exchange</span><span class="sxs-lookup"><span data-stu-id="d474f-110">Exchange administrator</span></span>
- <span data-ttu-id="d474f-111">Administrador de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="d474f-111">Conditional Access administrator</span></span>
- <span data-ttu-id="d474f-112">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="d474f-112">Security administrator</span></span>
- <span data-ttu-id="d474f-113">Administrador de assistência técnica ou administrador de senha</span><span class="sxs-lookup"><span data-stu-id="d474f-113">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="d474f-114">Administrador de cobrança</span><span class="sxs-lookup"><span data-stu-id="d474f-114">Billing administrator</span></span>
- <span data-ttu-id="d474f-115">Administrador de usuários</span><span class="sxs-lookup"><span data-stu-id="d474f-115">User administrator</span></span>
- <span data-ttu-id="d474f-116">Administrador de Autenticação</span><span class="sxs-lookup"><span data-stu-id="d474f-116">Authentication administrator</span></span>

<span data-ttu-id="d474f-117">Todos os outros usuários serão solicitados a executar uma autenticação adicional quando necessário.</span><span class="sxs-lookup"><span data-stu-id="d474f-117">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="d474f-118">Para saber mais, confira [Quais são os padrões de segurança?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="d474f-118">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="d474f-p103">Você deve ser um administrador global do Office 365 para configurar ou modificar a autenticação multifator. </span><span class="sxs-lookup"><span data-stu-id="d474f-p103">You must be an Office 365 global admin to set up or modify multi-factor authentication. </span></span><br><br>
> <span data-ttu-id="d474f-120">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="d474f-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="d474f-121">Se você já configurou a MFA com políticas de linha de base, [será necessário desativá-las e habilitar o de padrões de segurança](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="d474f-121">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="d474f-122">No entanto, se você tiver o Microsoft 365 Business ou sua assinatura incluir o [do Azure Active Directory Premium 1 ou do Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), também será possível configurar [as políticas de](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="d474f-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="d474f-123">Para usar políticas de acesso condicional, você precisa ter certeza de que a [autenticação moderna está habilitada](#enable-multi-factor-authentication-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="d474f-123">To use conditional access policies, you need to make sure [modern authentication is enabled](#enable-multi-factor-authentication-for-your-organization).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="d474f-124">Gerenciar padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="d474f-124">Manage security defaults</span></span>

1. <span data-ttu-id="d474f-125">Acesse o [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822) com credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="d474f-125">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="d474f-126">Vá para [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="d474f-126">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="d474f-127">Na parte inferior da página, clique em **Gerenciar padrões de segurança**.</span><span class="sxs-lookup"><span data-stu-id="d474f-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="d474f-128">Clique em **Sim** para habilitar os padrões de segurança e em **Não** para desabilitar o padrão de segurança.</span><span class="sxs-lookup"><span data-stu-id="d474f-128">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="d474f-129">Mover das políticas de linha de base para padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="d474f-129">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="d474f-130">No [Centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="d474f-130">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="d474f-131">Ao lado de **Entrada e segurança**, em **Tornar a entrada mais segura**, selecione **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="d474f-131">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="d474f-132">Em **Tornar a entrada mais segura**, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="d474f-132">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="d474f-133">Na página **de políticas de acesso condicional do portal do Azure** escolha cada política de linha de base que esta **ligada**, e configure-as para **desligada**.</span><span class="sxs-lookup"><span data-stu-id="d474f-133">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="d474f-134">Vá para a página [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="d474f-134">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="d474f-135">Na parte inferior da página, escolha **gerenciar padrões de segurança**e, no painel **habilitar padrões de segurança**, defina **habilite o padrão de segurança** alterne para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d474f-135">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="d474f-136">Habilitar a autenticação moderna para sua organização</span><span class="sxs-lookup"><span data-stu-id="d474f-136">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="d474f-137">Todos os aplicativos cliente do Office 2016 oferecem suporte à MFA por meio do uso da ADAL (Biblioteca de Autenticação do Active Directory).</span><span class="sxs-lookup"><span data-stu-id="d474f-137">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="d474f-138">Isso significa que as senhas de aplicativo não são obrigatórias para os clientes do Office 2016.</span><span class="sxs-lookup"><span data-stu-id="d474f-138">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="d474f-139">No entanto, você precisa verificar se a sua assinatura do Office 365 está habilitada para ADAL ou autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="d474f-139">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="d474f-140">Para habilitar a autenticação moderna, no [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), selecione **Configurações**\>**Configurações** e na guia **Serviços**, escolha **Autenticação moderna** na lista.</span><span class="sxs-lookup"><span data-stu-id="d474f-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="d474f-141">Marque a caixa **Habilitar autenticação moderna**, no painel da **Autenticação moderna**.</span><span class="sxs-lookup"><span data-stu-id="d474f-141">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![Painel de autenticação moderna com a caixa de seleção Habilitar marcada.](../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a><span data-ttu-id="d474f-143">Ativar a autenticação multifator da sua organização</span><span class="sxs-lookup"><span data-stu-id="d474f-143">Enable multi-factor authentication for your organization</span></span>
    
1. <span data-ttu-id="d474f-144">No [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), selecione **usuários** e **usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="d474f-144">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Users** and **Active Users**.</span></span>

2. <span data-ttu-id="d474f-145">Na seção **usuários ativos** , clique em **autenticação multifator**.</span><span class="sxs-lookup"><span data-stu-id="d474f-145">In the **Active Users** section, Click on  **multi-factor authentication**.</span></span>

3. <span data-ttu-id="d474f-146">Na página **autenticação multifator** , selecione **usuário** se estiver habilitando-o para um usuário ou selecione **atualização em massa** para habilitar vários usuários.</span><span class="sxs-lookup"><span data-stu-id="d474f-146">On the **Multi-factor authentication** page, select **user** if you are enabling this for one user or select **Bulk Update** to enable multiple users.</span></span>

4. <span data-ttu-id="d474f-147">Clique em **habilitar** em **etapas rápidas**.</span><span class="sxs-lookup"><span data-stu-id="d474f-147">CLick on **Enable** under **Quick Steps**.</span></span>

5. <span data-ttu-id="d474f-148">Na janela pop-up, clique em **habilitar autenticação multifator**.</span><span class="sxs-lookup"><span data-stu-id="d474f-148">In the Pop-up window, Click on **Enable Multi-Factor Authentication**.</span></span>

<span data-ttu-id="d474f-149">Após configurar a autenticação multifator da sua organização, os usuários precisarão configurar a verificação em duas etapas em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d474f-149">After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices.</span></span> <span data-ttu-id="d474f-150">Para obter mais informações, confira [Configurar a verificação em duas etapas do Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="d474f-150">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>
    
> [!TIP]
> <span data-ttu-id="d474f-151">Para explicar aos usuários como configurar o aplicativo autenticador, visite [Usar o Microsoft Authenticator com o Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="d474f-151">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="d474f-152">A partir de agosto de 2017, todos os novos locatários do Office 365, que inclui o Skype for Business e o Exchange Online, têm autenticação moderna habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="d474f-152">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="d474f-153">Para verificar o status de autenticação moderna do Skype for Business Online, você pode usar o Skype for Business via PowerShell com credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="d474f-153">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="d474f-154">Execute Get-CsOAuthConfiguration para verificar o resultado de -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="d474f-154">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="d474f-155">Se -ClientADALAuthOverride for ‘Allowed’, a autenticação moderna está ativada.</span><span class="sxs-lookup"><span data-stu-id="d474f-155">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="d474f-156">Para verificar o status do seu MA no Exchange Online, visite [Habilitar a autenticação moderna no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="d474f-156">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="d474f-157">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="d474f-157">Related articles</span></span>

[<span data-ttu-id="d474f-158">10 principais formas de proteger planos corporativos do Office 365 e do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d474f-158">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="d474f-159">Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="d474f-159">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
