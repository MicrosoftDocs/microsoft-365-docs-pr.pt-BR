---
title: Configurar a autenticação multifator para usuários
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
description: Saiba como usar os padrões de segurança para configurar a autenticação multifator para os usuários.
monikerRange: o365-worldwide
ms.openlocfilehash: c4ea6037b34d29f2d1e05e248e03e49ee6b06f56
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262370"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="54c37-103">Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="54c37-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="54c37-104">Se você comprou sua assinatura ou avaliação após 21 de outubro de 2019 e estiver inesperadamente solicitado pela autenticação multifator (MFA), [os padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) foram automaticamente habilitados para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="54c37-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="54c37-105">Todas as novas assinaturas do Microsoft 365 terão automaticamente [os padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) ativados.</span><span class="sxs-lookup"><span data-stu-id="54c37-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="54c37-106">Isso significa que cada usuário terá que configurar a MFA (autenticação multifator) e instalar o aplicativo Microsoft Authenticator em seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="54c37-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="54c37-107">Para obter mais informações, consulte [set up MFA for a Microsoft 365 Account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="54c37-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="54c37-108">As nove funções de administrador a seguir serão necessárias para executar uma autenticação adicional sempre que entrarem:</span><span class="sxs-lookup"><span data-stu-id="54c37-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="54c37-109">Administrador global</span><span class="sxs-lookup"><span data-stu-id="54c37-109">Global administrator</span></span>
- <span data-ttu-id="54c37-110">Administrador do SharePoint</span><span class="sxs-lookup"><span data-stu-id="54c37-110">SharePoint administrator</span></span>
- <span data-ttu-id="54c37-111">Administrador do Exchange</span><span class="sxs-lookup"><span data-stu-id="54c37-111">Exchange administrator</span></span>
- <span data-ttu-id="54c37-112">Administrador de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="54c37-112">Conditional Access administrator</span></span>
- <span data-ttu-id="54c37-113">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="54c37-113">Security administrator</span></span>
- <span data-ttu-id="54c37-114">Administrador de assistência técnica ou administrador de senha</span><span class="sxs-lookup"><span data-stu-id="54c37-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="54c37-115">Administrador de cobrança</span><span class="sxs-lookup"><span data-stu-id="54c37-115">Billing administrator</span></span>
- <span data-ttu-id="54c37-116">Administrador de usuários</span><span class="sxs-lookup"><span data-stu-id="54c37-116">User administrator</span></span>
- <span data-ttu-id="54c37-117">Administrador de Autenticação</span><span class="sxs-lookup"><span data-stu-id="54c37-117">Authentication administrator</span></span>

<span data-ttu-id="54c37-118">Todos os outros usuários serão solicitados a executar uma autenticação adicional quando necessário.</span><span class="sxs-lookup"><span data-stu-id="54c37-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="54c37-119">Você deve ser um administrador global para configurar ou modificar a MFA</span><span class="sxs-lookup"><span data-stu-id="54c37-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="54c37-120">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="54c37-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="54c37-121">Se você já configurou a MFA com políticas de linha de base, [você deve desativá-las para ativar os padrões de segurança](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="54c37-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="54c37-122">No entanto, se você tiver o Microsoft 365 Business ou sua assinatura incluir o [Azure Active Directory Premium P1 ou o Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), você também pode configurar as políticas de [acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) .</span><span class="sxs-lookup"><span data-stu-id="54c37-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="54c37-123">Para usar as políticas de acesso condicional, você precisa certificar-se de que os padrões de segurança estão desabilitados e que a [autenticação moderna](#enable-modern-authentication-for-your-organization) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="54c37-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="54c37-124">Para explicar aos usuários como configurar o aplicativo Microsoft Authenticator, confira usar o [Microsoft Authenticator com o Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span><span class="sxs-lookup"><span data-stu-id="54c37-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="54c37-125">Gerenciar padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="54c37-125">Manage security defaults</span></span>

1. <span data-ttu-id="54c37-126">Acesse o [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822) com credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="54c37-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="54c37-127">Vá para a [página Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="54c37-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="54c37-128">Na parte inferior da página, clique em **Gerenciar padrões de segurança**.</span><span class="sxs-lookup"><span data-stu-id="54c37-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="54c37-129">Escolha **Sim** para habilitar os padrões de segurança e **não** para desabilitar os padrões de segurança e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="54c37-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="54c37-130">Mover das políticas de linha de base para padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="54c37-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="54c37-131">Vá para a [página de políticas de acesso condicional](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="54c37-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="54c37-132">Escolha cada política de linha de base que está **ativada** e defina **habilitar política** como **desativado**.</span><span class="sxs-lookup"><span data-stu-id="54c37-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="54c37-133">Vá para a [página Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="54c37-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="54c37-134">Na parte inferior da página, escolha **gerenciar padrões de segurança**e, no painel **habilitar padrões de segurança** , defina **habilitar padrões de segurança** alterne para **Sim**e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="54c37-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="54c37-135">Habilitar a autenticação moderna para sua organização</span><span class="sxs-lookup"><span data-stu-id="54c37-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="54c37-136">Todos os aplicativos cliente do Office 2016 oferecem suporte à MFA por meio do uso da ADAL (Biblioteca de Autenticação do Active Directory).</span><span class="sxs-lookup"><span data-stu-id="54c37-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="54c37-137">Isso significa que as senhas de aplicativo não são obrigatórias para os clientes do Office 2016.</span><span class="sxs-lookup"><span data-stu-id="54c37-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="54c37-138">Confira [Este artigo](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="54c37-138">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>

<span data-ttu-id="54c37-139">No entanto, você precisa certificar-se de que sua assinatura do Microsoft 365 está habilitada para ADAL ou autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="54c37-139">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="54c37-140">Para habilitar a autenticação moderna, no [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), **Settings** selecione configurações da \> **organização** configurações e, em seguida, na guia **Serviços** , escolha **autenticação moderna** na lista.</span><span class="sxs-lookup"><span data-stu-id="54c37-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Org Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="54c37-141">Marque a caixa **habilitar autenticação moderna (recomendada)** no painel **autenticação moderna** e, em seguida, escolha **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="54c37-141">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Painel de autenticação moderna com a caixa de seleção Habilitar marcada.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="54c37-143">A partir de agosto de 2017, todas as novas assinaturas do Microsoft 365 que incluem o Skype for Business Online e o Exchange Online têm a autenticação moderna habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="54c37-143">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="54c37-144">Para verificar o status de autenticação moderna do Skype for Business Online, você pode usar o Skype for Business via PowerShell com credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="54c37-144">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="54c37-145">Execute Get-CsOAuthConfiguration para verificar o resultado de -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="54c37-145">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="54c37-146">Se -ClientADALAuthOverride for ‘Allowed’, a autenticação moderna está ativada.</span><span class="sxs-lookup"><span data-stu-id="54c37-146">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="54c37-147">Para verificar o status do seu MA no Exchange Online, visite [Habilitar a autenticação moderna no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="54c37-147">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="54c37-148">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="54c37-148">Related articles</span></span>

[<span data-ttu-id="54c37-149">As 10 maneiras principais de proteger os planos do Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="54c37-149">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="54c37-150">Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="54c37-150">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
