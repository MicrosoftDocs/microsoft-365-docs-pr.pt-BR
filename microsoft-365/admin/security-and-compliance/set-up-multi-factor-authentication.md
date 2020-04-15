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
ms.openlocfilehash: 7e48f72f2fd8cfc5042bd15f994cc98bfa5fca8c
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503966"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="58f63-103">Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="58f63-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="58f63-104">Se você comprou sua assinatura ou avaliação após 21 de outubro de 2019 e estiver inesperadamente solicitado pela autenticação multifator (MFA), [os padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) foram automaticamente habilitados para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="58f63-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="58f63-105">Todas as novas assinaturas do Office 365 para empresas ou do Microsoft 365 Business terão automaticamente os padrões de segurança ativados.</span><span class="sxs-lookup"><span data-stu-id="58f63-105">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="58f63-106">Isso significa que cada usuário terá que configurar a MFA e instalar o aplicativo Microsoft Authenticator em seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="58f63-106">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="58f63-107">Para obter mais informações, confira [Configurar a verificação em duas etapas do Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="58f63-107">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="58f63-108">As nove funções de administrador a seguir serão necessárias para executar uma autenticação adicional sempre que entrarem:</span><span class="sxs-lookup"><span data-stu-id="58f63-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="58f63-109">Administrador global</span><span class="sxs-lookup"><span data-stu-id="58f63-109">Global administrator</span></span>
- <span data-ttu-id="58f63-110">Administrador do SharePoint</span><span class="sxs-lookup"><span data-stu-id="58f63-110">SharePoint administrator</span></span>
- <span data-ttu-id="58f63-111">Administrador do Exchange</span><span class="sxs-lookup"><span data-stu-id="58f63-111">Exchange administrator</span></span>
- <span data-ttu-id="58f63-112">Administrador de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="58f63-112">Conditional Access administrator</span></span>
- <span data-ttu-id="58f63-113">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="58f63-113">Security administrator</span></span>
- <span data-ttu-id="58f63-114">Administrador de assistência técnica ou administrador de senha</span><span class="sxs-lookup"><span data-stu-id="58f63-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="58f63-115">Administrador de cobrança</span><span class="sxs-lookup"><span data-stu-id="58f63-115">Billing administrator</span></span>
- <span data-ttu-id="58f63-116">Administrador de usuários</span><span class="sxs-lookup"><span data-stu-id="58f63-116">User administrator</span></span>
- <span data-ttu-id="58f63-117">Administrador de Autenticação</span><span class="sxs-lookup"><span data-stu-id="58f63-117">Authentication administrator</span></span>

<span data-ttu-id="58f63-118">Todos os outros usuários serão solicitados a executar uma autenticação adicional quando necessário.</span><span class="sxs-lookup"><span data-stu-id="58f63-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="58f63-119">Para obter mais informações, consulte [o que são padrões de segurança?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="58f63-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="58f63-120">Você deve ser um administrador global do Office 365 para configurar ou modificar a MFA.</span><span class="sxs-lookup"><span data-stu-id="58f63-120">You must be an Office 365 global admin to set up or modify MFA.</span></span> <br><br>
> <span data-ttu-id="58f63-121">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="58f63-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="58f63-122">Se você já configurou a MFA com políticas de linha de base, [será necessário desativá-las e habilitar o de padrões de segurança](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="58f63-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="58f63-123">No entanto, se você tiver o Microsoft 365 Business ou sua assinatura incluir o [Azure Active Directory Premium P1 ou o Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), você também pode configurar as políticas de [acesso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) .</span><span class="sxs-lookup"><span data-stu-id="58f63-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="58f63-124">Para usar as políticas de acesso condicional, você precisa certificar-se de que a [autenticação moderna](#enable-modern-authentication-for-your-organization) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="58f63-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="58f63-125">Para explicar aos usuários como configurar o aplicativo autenticador, visite [Usar o Microsoft Authenticator com o Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="58f63-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="58f63-126">Gerenciar padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="58f63-126">Manage security defaults</span></span>

1. <span data-ttu-id="58f63-127">Entre no [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822) com as suas credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="58f63-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="58f63-128">Vá para [Propriedades do Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="58f63-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="58f63-129">Na parte inferior da página, clique em **Gerenciar padrões de segurança**.</span><span class="sxs-lookup"><span data-stu-id="58f63-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="58f63-130">Escolha **Sim** para habilitar os padrões de segurança ou **não** para desabilitar os padrões de segurança e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="58f63-130">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="58f63-131">Mover das políticas de linha de base para padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="58f63-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="58f63-132">No [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), selecione **Mostrar todos**e, em seguida, **Azure Active Directory** em **centros de administração**.</span><span class="sxs-lookup"><span data-stu-id="58f63-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Show all**, and then **Azure Active Directory** under **Admin centers**.</span></span>

2. <span data-ttu-id="58f63-133">No **centro de administração do Azure Active Directory** , escolha**segurança** **do Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="58f63-133">In the  **Azure Active Directory admin center** choose **Azure Active Directory** > **Security**.</span></span>

3. <span data-ttu-id="58f63-134">Na **| segurança | Página Introdução** , escolha **acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="58f63-134">On the **Security | Getting started** page, choose **Conditional Access**.</span></span> 

4. <span data-ttu-id="58f63-135">Na página **acesso condicional-diretivas** , escolha cada diretiva de linha de base que está **ativada**e defina-as como **desativado**.</span><span class="sxs-lookup"><span data-stu-id="58f63-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="58f63-136">Vá para a página [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="58f63-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="58f63-137">Na parte inferior da página, escolha **gerenciar padrões de segurança**e, no painel **habilitar padrões de segurança** , defina **habilitar padrões de segurança** alterne para **Sim**e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="58f63-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="58f63-138">Habilitar a autenticação moderna para sua organização</span><span class="sxs-lookup"><span data-stu-id="58f63-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="58f63-139">Todos os aplicativos cliente do Office 2016 oferecem suporte à MFA por meio do uso da ADAL (Biblioteca de Autenticação do Active Directory).</span><span class="sxs-lookup"><span data-stu-id="58f63-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="58f63-140">Isso significa que as senhas de aplicativo não são obrigatórias para os clientes do Office 2016.</span><span class="sxs-lookup"><span data-stu-id="58f63-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="58f63-141">No entanto, você precisa verificar se a sua assinatura do Office 365 está habilitada para ADAL ou autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="58f63-141">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="58f63-142">Para habilitar a autenticação moderna, no [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), selecione **Configurações**\>**Configurações** e na guia **Serviços**, escolha **Autenticação moderna** na lista.</span><span class="sxs-lookup"><span data-stu-id="58f63-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="58f63-143">Marque a caixa **habilitar autenticação moderna (recomendada)** no painel **autenticação moderna** e, em seguida, escolha **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="58f63-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Painel de autenticação moderna com a caixa de seleção Habilitar marcada.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="58f63-145">A partir de agosto de 2017, todos os novos locatários do Office 365, que inclui o Skype for Business e o Exchange Online, têm autenticação moderna habilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="58f63-145">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="58f63-146">Para verificar o status de autenticação moderna do Skype for Business Online, você pode usar o Skype for Business via PowerShell com credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="58f63-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="58f63-147">Execute Get-CsOAuthConfiguration para verificar o resultado de -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="58f63-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="58f63-148">Se -ClientADALAuthOverride for ‘Allowed’, a autenticação moderna está ativada.</span><span class="sxs-lookup"><span data-stu-id="58f63-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>

<span data-ttu-id="58f63-149">Para verificar o status do seu MA no Exchange Online, visite [Habilitar a autenticação moderna no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="58f63-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="58f63-150">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="58f63-150">Related articles</span></span>

[<span data-ttu-id="58f63-151">10 principais formas de proteger planos corporativos do Office 365 e do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58f63-151">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="58f63-152">Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="58f63-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
