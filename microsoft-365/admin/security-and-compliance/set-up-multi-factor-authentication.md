---
title: Configurar a autenticação multifator para usuários
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Saiba como configurar a autenticação multifator para a sua organização.
monikerRange: o365-worldwide
ms.openlocfilehash: d08ef54c545809bbb2277f8d0a8471245400a3ac
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2021
ms.locfileid: "50514963"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="b501f-103">Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="b501f-103">Set up multi-factor authentication</span></span>

<span data-ttu-id="b501f-104">Com base no seu conhecimento de [MFA (autenticação multifator) e seu suporte no Microsoft 365](multi-factor-authentication-microsoft-365.md), é hora de configurá-la e distribuí-la para a organização.</span><span class="sxs-lookup"><span data-stu-id="b501f-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it's time to set it up and roll it out to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b501f-105">Se você comprou a sua assinatura ou a versão de avaliação após 21 de outubro de 2019 e for solicitado a executar a MFA ao entrar, [os padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) foram automaticamente habilitados para a sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="b501f-105">If you purchased your subscription or trial after October 21, 2019, and you're prompted for MFA when you sign in, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b501f-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b501f-106">Before you begin</span></span>

- <span data-ttu-id="b501f-107">Você deve ser um administrador Global para gerenciar a MFA.</span><span class="sxs-lookup"><span data-stu-id="b501f-107">You must be a Global admin to manage MFA.</span></span> <span data-ttu-id="b501f-108">Para obter mais informações, confira o artigo [Sobre funções de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b501f-108">For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="b501f-109">Se você tiver a MFA herdada por usuário, [Desative a MFA herdada por usuário](#turn-off-legacy-per-user-mfa).</span><span class="sxs-lookup"><span data-stu-id="b501f-109">If you have legacy per-user MFA turned on, [Turn off legacy per-user MFA](#turn-off-legacy-per-user-mfa).</span></span>
- <span data-ttu-id="b501f-110">Se você tem clientes do Office 2013 em dispositivos Windows, [ative a Autenticação moderna para clientes do Office 2013](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="b501f-110">If you have Office 2013 clients on Windows devices, [turn on Modern Authentication for Office 2013 clients](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>
- <span data-ttu-id="b501f-111">Avançado: se você tiver serviços de diretório de terceiros com o AD FS (Serviços de Federação do Active Directory), configure o Servidor do Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="b501f-111">Advanced: If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="b501f-112">Confira [cenários avançados com a Autenticação Multifator do Microsoft Azure Active Directory e soluções VPN de terceiros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b501f-112">See [advanced scenarios with Azure AD Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="turn-security-defaults-on-or-off"></a><span data-ttu-id="b501f-113">Ativar ou desativar o padrão de Segurança</span><span class="sxs-lookup"><span data-stu-id="b501f-113">Turn Security defaults on or off</span></span>

<span data-ttu-id="b501f-114">Para a maioria das organizações, os padrões de segurança oferecem um bom nível de segurança adicional de entrada.</span><span class="sxs-lookup"><span data-stu-id="b501f-114">For most organizations, Security defaults offer a good level of additional sign-in security.</span></span> <span data-ttu-id="b501f-115">Para saber mais, confira [Quais são os padrões de segurança?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="b501f-115">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="b501f-116">Se a sua assinatura for nova, os padrões de Segurança já poderão estar habilitados para você automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b501f-116">If your subscription is new, Security defaults might already be turned on for you automatically.</span></span>

<span data-ttu-id="b501f-117">Habilite ou desabilite as opções de segurança no painel de **Propriedades** para o Azure Active Directory (Azure AD) no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b501f-117">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1. <span data-ttu-id="b501f-118">Acessar o [Centro de administração do Microsoft 365](https://admin.microsoft.com) com credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b501f-118">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2. <span data-ttu-id="b501f-119">Na barra de navegação à esquerda, escolha **Mostrar Tudo** e em **Centro de administração**, escolha **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b501f-119">In the left nav choose **Show All** and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="b501f-120">No **centro de administração do Azure Active Directory** escolha **Azure Active Directory** \> **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b501f-120">In the **Azure Active Directory admin center** choose **Azure Active Directory** \> **Properties**.</span></span>
4. <span data-ttu-id="b501f-121">Na parte inferior da página, clique em **Gerenciar Padrões de segurança**.</span><span class="sxs-lookup"><span data-stu-id="b501f-121">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="b501f-122">Clique em **Sim** para habilitar os padrões de segurança ou **Não** para desabilitar o padrão de segurança e, em seguida, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b501f-122">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="b501f-123">Se você estiver usando [políticas de Acesso Condicional da linha de base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), você será instruído a desativá-las antes de mover para usar os padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="b501f-123">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), you will be prompted to turn them off before you move to using security defaults.</span></span>

1. <span data-ttu-id="b501f-124">Vá para a página [Acesso Condicional - página Políticas](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="b501f-124">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="b501f-125">Escolha cada política de linha de base que esteja **Ativada** e defina **Permitir que a política** seja **Desativada**.</span><span class="sxs-lookup"><span data-stu-id="b501f-125">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="b501f-126">Vá para [Azure Active Directory - Página Propriedades](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="b501f-126">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="b501f-127">Na parte inferior da página, clique em **Gerenciar Padrões de segurança**.</span><span class="sxs-lookup"><span data-stu-id="b501f-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5. <span data-ttu-id="b501f-128">Clique em **Sim** para habilitar os padrões de segurança e em **Não** para desabilitar o padrão de segurança e, em seguida, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b501f-128">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="use-conditional-access-policies"></a><span data-ttu-id="b501f-129">Usar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="b501f-129">Use Conditional Access policies</span></span>

<span data-ttu-id="b501f-130">Se a sua organização tiver necessidades de segurança de entrada mais granulares, as políticas de acesso condicional poderão oferecer mais controle.</span><span class="sxs-lookup"><span data-stu-id="b501f-130">If your organization has more granular sign-in security needs, Conditional Access policies can offer you more control.</span></span> <span data-ttu-id="b501f-131">O Acesso Condicional permite que você crie e define políticas que reagem a eventos de entrada e solicite ações adicionais antes que um usuário receba acesso a um aplicativo ou serviço.</span><span class="sxs-lookup"><span data-stu-id="b501f-131">Conditional Access lets you create and define policies that react to sign in events and request additional actions before a user is granted access to an application or service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b501f-132">Desabilite tanto a MFA por usuário quanto os padrões de Segurança antes de habilitar as políticas de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="b501f-132">Turn off both per-user MFA and Security defaults before you enable Conditional Access policies.</span></span>

<span data-ttu-id="b501f-133">O Acesso Condicional está disponível para clientes que compraram o Azure Active Directory Premium P1 ou licenças que incluem isso, como o Microsoft 365 Business Premium e o Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="b501f-133">Conditional Access is available for customers who have purchased Azure AD Premium P1, or licenses that include this, such as Microsoft 365 Business Premium, and Microsoft 365 E3.</span></span> <span data-ttu-id="b501f-134">Para obter mais informações, confira [criar uma política de Acesso Condicional](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span><span class="sxs-lookup"><span data-stu-id="b501f-134">For more information, see [create a Conditional Access policy](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).</span></span>

<span data-ttu-id="b501f-135">O acesso condicional baseado em risco está disponível por meio da licença do Azure AD Premium P2 ou de licenças que incluem isso, como o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b501f-135">Risk-based conditional access is available through Azure AD Premium P2 license, or licenses that include this, such as Microsoft 365 E5.</span></span> <span data-ttu-id="b501f-136">Para mais informações, confira [Acesso Condicional baseado em risco](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span><span class="sxs-lookup"><span data-stu-id="b501f-136">For more information, see [risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).</span></span>

<span data-ttu-id="b501f-137">Para obter mais informações sobre o Azure Active Directory P1 e P2, confira [Preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="b501f-137">For more information about the Azure AD P1 and P2, see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

### <a name="turn-on-modern-authentication-for-your-organization"></a><span data-ttu-id="b501f-138">Habilitar a autenticação moderna para a sua organização</span><span class="sxs-lookup"><span data-stu-id="b501f-138">Turn on Modern authentication for your organization</span></span>

<span data-ttu-id="b501f-139">Para a maioria das assinaturas, a autenticação moderna é ativada automaticamente, mas se você adquiriu sua assinatura antes de agosto de 2017, é provável que precise ativar a Autenticação Moderna para que recursos como a Autenticação Multifator funcionem em clientes Windows como o Outlook.</span><span class="sxs-lookup"><span data-stu-id="b501f-139">For most subscriptions modern authentication is automatically turned on, but if you purchased your subscription before August 2017, it is likely that you will need to turn on Modern Authentication in order to get features like Multi-Factor Authentication to work in Windows clients like Outlook.</span></span>


1. <span data-ttu-id="b501f-140">No centro de administração do Microsoft 365, no painel de navegação esquerdo, escolha **Configurações** \> **Configurações da organização**.</span><span class="sxs-lookup"><span data-stu-id="b501f-140">In the Microsoft 365 admin center, in the left nav choose **Settings** \> **Org settings**.</span></span>
2. <span data-ttu-id="b501f-141">Debaixo de **Serviços** guia, escolher **Autenticação Moderna**, e no **Autenticação Moderna** painel, certifique-se **Habilitar Autenticação Moderna** é selecionado.</span><span class="sxs-lookup"><span data-stu-id="b501f-141">Under the **Services** tab, choose **Modern authentication**, and in the **Modern authentication** pane, make sure **Enable Modern authentication** is selected.</span></span> <span data-ttu-id="b501f-142">Escolha **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="b501f-142">Choose **Save changes**.</span></span>

### <a name="turn-off-legacy-per-user-mfa"></a><span data-ttu-id="b501f-143">Desabilitar a MFA herdada por usuário</span><span class="sxs-lookup"><span data-stu-id="b501f-143">Turn off legacy per-user MFA</span></span>

<span data-ttu-id="b501f-144">Se você já habilitou a MFA por usuário, é necessário desabilitá-lo antes de habilitar o padrão de segurança.</span><span class="sxs-lookup"><span data-stu-id="b501f-144">If you have previously turned on per-user MFA, you must turn it off before enabling Security defaults.</span></span>

1. <span data-ttu-id="b501f-145">No Centro de administração do Microsoft 365, na barra de navegação esquerda, escolha **Usuários** \> **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="b501f-145">In the Microsoft 365 admin center, in the left nav choose **Users** \> **Active users**.</span></span>
1. <span data-ttu-id="b501f-146">Na página **Usuários ativos**, escolha **Autenticação multifator**.</span><span class="sxs-lookup"><span data-stu-id="b501f-146">On the **Active users** page, choose **Multi-factor authentication**.</span></span>
1. <span data-ttu-id="b501f-147">Na página da autenticação multifator, selecione cada usuário e defina o status de autenticação multifator como **Desabilitado**.</span><span class="sxs-lookup"><span data-stu-id="b501f-147">On the multi-factor authentication page, select each user and set their Multi-Factor auth status to **Disabled**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b501f-148">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b501f-148">Next steps</span></span>

- [<span data-ttu-id="b501f-149">Como se inscrever para obter o método de verificação adicional</span><span class="sxs-lookup"><span data-stu-id="b501f-149">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="b501f-150">O que é: Autenticação Multifator</span><span class="sxs-lookup"><span data-stu-id="b501f-150">What is: Multifactor Authentication</span></span>](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [<span data-ttu-id="b501f-151">Como entrar após o registro</span><span class="sxs-lookup"><span data-stu-id="b501f-151">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="b501f-152">Como alterar o método de verificação adicional</span><span class="sxs-lookup"><span data-stu-id="b501f-152">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-topics"></a><span data-ttu-id="b501f-153">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b501f-153">Related topics</span></span>

[<span data-ttu-id="b501f-154">Vídeo: Ativar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="b501f-154">Video: Turn on multi-factor authentication</span></span>](https://docs.microsoft.com/microsoft-365/business-video/turn-on-mfa)

[<span data-ttu-id="b501f-155">Vídeo: Ativar a autenticação multifator para seu telefone</span><span class="sxs-lookup"><span data-stu-id="b501f-155">Video: Turn on multi-factor authentication for your phone</span></span>](https://docs.microsoft.com/microsoft-365/business-video/set-up-mfa)
