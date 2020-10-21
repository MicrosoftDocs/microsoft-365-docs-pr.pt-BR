---
title: Permitir que os usuários redefinam as próprias senhas
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Saiba como você pode redefinir suas senhas usando a ferramenta de redefinição de senha autoatendimento.
ms.openlocfilehash: 7ecadaa42610e0b77dc1727c11140080bd7b1779
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646674"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="09a26-103">Permitir que os usuários redefinam as próprias senhas</span><span class="sxs-lookup"><span data-stu-id="09a26-103">Let users reset their own passwords</span></span>

<span data-ttu-id="09a26-104">Como o Microsoft 365 admin, você pode permitir que as pessoas usem a [ferramenta de redefinição de senha de autoatendimento](https://go.microsoft.com/fwlink/p/?LinkId=522677) para que você não precise redefinir senhas para elas.</span><span class="sxs-lookup"><span data-stu-id="09a26-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="09a26-105">Menos trabalho para você!</span><span class="sxs-lookup"><span data-stu-id="09a26-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="09a26-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="09a26-106">Before you begin</span></span>
  
- <span data-ttu-id="09a26-107">Você obtém redefinição de senha de autoatendimento para usuários em nuvem **gratuitamente** com qualquer plano pago de negócios, educação ou sem fins lucrativos da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09a26-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="09a26-108">Ele não funciona com a avaliação da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09a26-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="09a26-p103">Ela usa o Azure. Você obterá automaticamente esse recurso no Azure **gratuitamente** quando realizar essas etapas. Não haverá custos para habilitar a redefinição de senha de autoatendimento se você não usar outros recursos do Azure.</span><span class="sxs-lookup"><span data-stu-id="09a26-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="09a26-112">**Se você estiver usando um Active Directory local**, os dois pontos acima não se aplicam.</span><span class="sxs-lookup"><span data-stu-id="09a26-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="09a26-113">Em vez disso, você pode configurar isso, mas **requer uma assinatura paga do Azure ad Premium**.</span><span class="sxs-lookup"><span data-stu-id="09a26-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="09a26-114">Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="09a26-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="09a26-115">Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09a26-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="09a26-116">O que é uma conta de administrador?</span><span class="sxs-lookup"><span data-stu-id="09a26-116">What's an admin account?</span></span>](../admin-overview/admin-overview.md)

<span data-ttu-id="09a26-117">Você deve ser um [administrador de administrador ou de senha global](about-admin-roles.md) para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="09a26-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="09a26-118">Watch: permitir que os usuários redefinam suas próprias senhas</span><span class="sxs-lookup"><span data-stu-id="09a26-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="09a26-119">Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="09a26-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="09a26-120">Etapas: permitir que as pessoas redefinam suas próprias senhas</span><span class="sxs-lookup"><span data-stu-id="09a26-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="09a26-121">Estas etapas habilitam a redefinição de senhas de autoatendimento para todas as pessoas da empresa.</span><span class="sxs-lookup"><span data-stu-id="09a26-121">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="09a26-122">No <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração</a>, vá para a página Configurações da organização de **configurações** > **Org settings** .</span><span class="sxs-lookup"><span data-stu-id="09a26-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="09a26-123">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, vá para a página **configurações** de \> \*\* &amp; privacidade de segurança\*\* .</span><span class="sxs-lookup"><span data-stu-id="09a26-123">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="09a26-124">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, vá para a **Settings** \> página de privacidade de segurança **das configurações** de configurações \> \*\* &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="09a26-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="09a26-125">Na parte superior da página **configurações da organização** , selecione a guia **privacidade & segurança** .</span><span class="sxs-lookup"><span data-stu-id="09a26-125">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="09a26-126">Selecione **redefinição de senha de autoatendimento**.</span><span class="sxs-lookup"><span data-stu-id="09a26-126">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="09a26-127">Em **redefinição de senha de autoatendimento**, selecione **ir para o portal do Azure para ativar a redefinição de senha de autoatendimento**.</span><span class="sxs-lookup"><span data-stu-id="09a26-127">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="09a26-128">No painel de navegação esquerdo, selecione **usuários**e, em seguida, em **usuários | Página todos os usuários** , selecione **redefinição de senha**.</span><span class="sxs-lookup"><span data-stu-id="09a26-128">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="09a26-129">Na página **Propriedades** , selecione **tudo** para habilitá-lo para todas as pessoas em sua empresa e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="09a26-129">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="09a26-130">Quando seus usuários entrarem, eles serão solicitados a inserir informações de contato adicionais que os ajudarão a redefinir sua senha no futuro.</span><span class="sxs-lookup"><span data-stu-id="09a26-130">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="09a26-131">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="09a26-131">Related content</span></span>

[<span data-ttu-id="09a26-132">Definir a política de expiração de senha para sua organização</span><span class="sxs-lookup"><span data-stu-id="09a26-132">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)

[<span data-ttu-id="09a26-133">Definir a senha de um usuário individual para nunca expirar</span><span class="sxs-lookup"><span data-stu-id="09a26-133">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="09a26-134">Vídeos de treinamento do Microsoft 365 Business </span><span class="sxs-lookup"><span data-stu-id="09a26-134">Microsoft 365 Business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
