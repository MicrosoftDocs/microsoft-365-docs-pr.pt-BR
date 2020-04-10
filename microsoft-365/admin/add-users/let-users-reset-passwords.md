---
title: Permitir que os usuários redefinam as próprias senhas no Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Saiba como você pode redefinir suas senhas usando a ferramenta de redefinição de senha autoatendimento.
ms.openlocfilehash: 666d3843f7917cf9bd5718c0ce29f87f93d6effe
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211890"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="e5f3f-103">Permitir que os usuários redefinam as próprias senhas</span><span class="sxs-lookup"><span data-stu-id="e5f3f-103">Let users reset their own passwords</span></span>

<span data-ttu-id="e5f3f-104">Obter Crushed com pessoas solicitando que você redefina suas senhas?</span><span class="sxs-lookup"><span data-stu-id="e5f3f-104">Getting crushed with people asking you to reset their passwords?</span></span> <span data-ttu-id="e5f3f-105">Como o Microsoft 365 admin, você pode permitir que as pessoas usem a [ferramenta de redefinição de senha de autoatendimento](https://go.microsoft.com/fwlink/p/?LinkId=522677) para que você não precise redefinir senhas para elas.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-105">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="e5f3f-106">Menos trabalho para você!</span><span class="sxs-lookup"><span data-stu-id="e5f3f-106">Less work for you!</span></span> 
  
<span data-ttu-id="e5f3f-107">Aqui estão algumas coisas que você precisa saber:</span><span class="sxs-lookup"><span data-stu-id="e5f3f-107">Here are a few things you need to know:</span></span>
  
- <span data-ttu-id="e5f3f-p102">Você obtém a redefinição de senhas de autoatendimento para usuários de nuvem **gratuitamente** com qualquer plano pago do Office 365 para empresas, educação ou instituições sem fins lucrativos. Ela não funciona com a avaliação do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-p102">You get self-service password reset for cloud users **free** with any Office 365 business, education, or nonprofit paid plan. It doesn't work with Office 365 trial.</span></span> 
    
- <span data-ttu-id="e5f3f-p103">Ela usa o Azure. Você obterá automaticamente esse recurso no Azure **gratuitamente** quando realizar essas etapas. Não haverá custos para habilitar a redefinição de senha de autoatendimento se você não usar outros recursos do Azure.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span> 
    
- <span data-ttu-id="e5f3f-113">**Se você estiver usando um Active Directory local**, os dois pontos acima não se aplicam.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-113">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="e5f3f-114">Em vez disso, você pode configurar isso, mas **requer uma assinatura paga do Azure ad Premium**.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-114">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span> 

<span data-ttu-id="e5f3f-115">Assista a um pequeno vídeo sobre como permitir que os usuários redefinam suas próprias senhas.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-115">Watch a short video about letting users reset their own passwords.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

<span data-ttu-id="e5f3f-116">Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="e5f3f-116">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

## <a name="let-people-reset-their-own-passwords"></a><span data-ttu-id="e5f3f-117">Permitir que as pessoas redefinam suas próprias senhas</span><span class="sxs-lookup"><span data-stu-id="e5f3f-117">Let people reset their own passwords</span></span> 

<span data-ttu-id="e5f3f-118">Estas etapas habilitam a redefinição de senhas de autoatendimento para todas as pessoas da empresa.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-118">These steps turn on self-service password reset for everyone in your business.</span></span>
  
::: moniker range="o365-worldwide"
1.  <span data-ttu-id="e5f3f-119">No centro de administração, vá para a página **configurações** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">segurança & privacidade</a> .</span><span class="sxs-lookup"><span data-stu-id="e5f3f-119">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e5f3f-120">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, vá para a página **configurações** \> de privacidade de \*\*segurança &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="e5f3f-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e5f3f-121">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, vá para a página **configurações** \> de privacidade de \*\*segurança &amp; \*\* .</span><span class="sxs-lookup"><span data-stu-id="e5f3f-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Settings** \> **Security &amp; privacy** page.</span></span>

::: moniker-end

   
2. <span data-ttu-id="e5f3f-122">Em **permitir que as pessoas redefinam suas próprias senhas**, selecione o link para o **centro de administração do Azure ad**.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-122">Under **Let your people reset their own passwords**, select the link for the **Azure AD admin center**.</span></span> <span data-ttu-id="e5f3f-123">Você receberá o Azure gratuitamente!</span><span class="sxs-lookup"><span data-stu-id="e5f3f-123">You'll get Azure for free!</span></span>
  
3. <span data-ttu-id="e5f3f-124">Selecione **usuários** na navegação à esquerda e, em seguida, selecione **Redefinir senha**.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-124">Select **Users** in the left navigation, and then select **Password reset**.</span></span>
  
4. <span data-ttu-id="e5f3f-125">Na página Propriedades, selecione **tudo** para habilitá-lo para todas as pessoas em sua empresa e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-125">On the Properties page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
5. <span data-ttu-id="e5f3f-126">Quando os usuários entram no Office 365, devem inserir informações de contato adicionais que ajudarão a redefinir a senha deles no futuro.</span><span class="sxs-lookup"><span data-stu-id="e5f3f-126">When your users sign in to Office 365, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e5f3f-127">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="e5f3f-127">Related articles</span></span>

[<span data-ttu-id="e5f3f-128">Definir a política de expiração de senha para sua organização</span><span class="sxs-lookup"><span data-stu-id="e5f3f-128">Set the password expiration policy for your organization</span></span>](../manage/set-password-expiration-policy.md)
  
[<span data-ttu-id="e5f3f-129">Definir a senha de um usuário individual para nunca expirar</span><span class="sxs-lookup"><span data-stu-id="e5f3f-129">Set an individual user's password to never expire</span></span>](set-password-to-never-expire.md)

[<span data-ttu-id="e5f3f-130">Vídeos de treinamento do Microsoft 365 Business </span><span class="sxs-lookup"><span data-stu-id="e5f3f-130">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
