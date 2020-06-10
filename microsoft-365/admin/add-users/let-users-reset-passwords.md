---
title: Permitir que os usuários redefinam as próprias senhas
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
ms.openlocfilehash: 40f094489a1981302e97043b019e8c90a52ffc55
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44678677"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="34153-103">Permitir que os usuários redefinam as próprias senhas</span><span class="sxs-lookup"><span data-stu-id="34153-103">Let users reset their own passwords</span></span>

<span data-ttu-id="34153-104">Obter Crushed com pessoas solicitando que você redefina suas senhas?</span><span class="sxs-lookup"><span data-stu-id="34153-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="34153-105">Como o Microsoft 365 admin, você pode permitir que as pessoas usem a [ferramenta de redefinição de senha de autoatendimento](https://go.microsoft.com/fwlink/p/?LinkId=522677) para que você não precise redefinir senhas para elas.</span><span class="sxs-lookup"><span data-stu-id="34153-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="34153-106">Menos trabalho para você!</span><span class="sxs-lookup"><span data-stu-id="34153-106">Less work for you!</span></span> 
  
<span data-ttu-id="34153-107">Aqui estão algumas coisas que você precisa saber:</span><span class="sxs-lookup"><span data-stu-id="34153-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="34153-108">Você obtém redefinição de senha de autoatendimento para usuários em nuvem **gratuitamente** com qualquer plano pago de negócios, educação ou sem fins lucrativos da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34153-108">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="34153-109">Ele não funciona com a avaliação da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34153-109">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="34153-p103">Ela usa o Azure. Você obterá automaticamente esse recurso no Azure **gratuitamente** quando realizar essas etapas. Não haverá custos para habilitar a redefinição de senha de autoatendimento se você não usar outros recursos do Azure.</span><span class="sxs-lookup"><span data-stu-id="34153-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="34153-113">**Se você estiver usando um Active Directory local**, os dois pontos acima não se aplicam.</span><span class="sxs-lookup"><span data-stu-id="34153-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="34153-114">Em vez disso, você pode configurar isso, mas **requer uma assinatura paga do Azure ad Premium**.</span><span class="sxs-lookup"><span data-stu-id="34153-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="34153-115">Assista a um pequeno vídeo sobre como permitir que os usuários redefinam suas próprias senhas.</span><span class="sxs-lookup"><span data-stu-id="34153-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="34153-116">Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="34153-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="34153-117">Permitir que as pessoas redefinam suas próprias senhas</span><span class="sxs-lookup"><span data-stu-id="34153-117">Let people reset their own passwords</span></span>

<span data-ttu-id="34153-118">Estas etapas habilitam a redefinição de senhas de autoatendimento para todas as pessoas da empresa.</span><span class="sxs-lookup"><span data-stu-id="34153-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="34153-119">No <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração</a>, vá para a página Configurações da organização de **configurações** > **Org settings** .</span><span class="sxs-lookup"><span data-stu-id="34153-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="34153-120">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, vá para a página **configurações** de \> \*\* &amp; privacidade de segurança\*\* .</span><span class="sxs-lookup"><span data-stu-id="34153-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="34153-121">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, vá para a **Settings** \> página de privacidade de segurança **das configurações** de configurações \> \*\* &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="34153-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \>**Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

2. <span data-ttu-id="34153-122">Na parte superior da página **configurações da organização** , selecione a guia **privacidade & segurança** .</span><span class="sxs-lookup"><span data-stu-id="34153-122">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="34153-123">Selecione **redefinição de senha de autoatendimento**.</span><span class="sxs-lookup"><span data-stu-id="34153-123">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="34153-124">Em **redefinição de senha de autoatendimento**, selecione **ir para o portal do Azure para ativar a redefinição de senha de autoatendimento**.</span><span class="sxs-lookup"><span data-stu-id="34153-124">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="34153-125">No painel de navegação esquerdo, selecione **usuários**e, em seguida, em **usuários | Página todos os usuários** , selecione **redefinição de senha**.</span><span class="sxs-lookup"><span data-stu-id="34153-125">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="34153-126">Na página **Propriedades** , selecione **tudo** para habilitá-lo para todas as pessoas em sua empresa e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="34153-126">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="34153-127">Quando seus usuários entrarem, eles serão solicitados a inserir informações de contato adicionais que os ajudarão a redefinir sua senha no futuro.</span><span class="sxs-lookup"><span data-stu-id="34153-127">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="34153-128">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="34153-128">Related articles</span></span>

[<span data-ttu-id="34153-129">Definir a política de expiração de senha para sua organização</span><span class="sxs-lookup"><span data-stu-id="34153-129">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="34153-130">Definir a senha de um usuário individual para nunca expirar</span><span class="sxs-lookup"><span data-stu-id="34153-130">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="34153-131">Vídeos de treinamento do Microsoft 365 Business </span><span class="sxs-lookup"><span data-stu-id="34153-131">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
