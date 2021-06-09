---
title: Permitir que os usuários redefinam as próprias senhas
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Saiba como você pode definir uma política para permitir que os usuários redefinir suas próprias senhas usando a ferramenta de redefinição de senha de autoatendados.
ms.openlocfilehash: 81fbe1949b8d5e4a601411703d86165f95cc7b7f
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634263"
---
# <a name="let-users-reset-their-own-passwords"></a><span data-ttu-id="f408a-103">Permitir que os usuários redefinam as próprias senhas</span><span class="sxs-lookup"><span data-stu-id="f408a-103">Let users reset their own passwords</span></span>

<span data-ttu-id="f408a-104">Como administrador Microsoft 365, você pode permitir que [](https://go.microsoft.com/fwlink/p/?LinkId=522677) as pessoas usem a ferramenta de redefinição de senha de autoatendados para que você não tenha que redefinir senhas para elas.</span><span class="sxs-lookup"><span data-stu-id="f408a-104">As the Microsoft 365 admin, you can let people use the [self-service password reset tool](https://go.microsoft.com/fwlink/p/?LinkId=522677) so you don't have to reset passwords for them.</span></span> <span data-ttu-id="f408a-105">Menos trabalho para você!</span><span class="sxs-lookup"><span data-stu-id="f408a-105">Less work for you!</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="f408a-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f408a-106">Before you begin</span></span>
  
- <span data-ttu-id="f408a-107">Você recebe a redefinição de  senha de autoatendente para usuários de nuvem gratuitamente com qualquer plano pago Microsoft 365 negócios, educação ou sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="f408a-107">You get self-service password reset for cloud users **free** with any Microsoft 365 business, education, or nonprofit paid plan.</span></span> <span data-ttu-id="f408a-108">Ele não funciona com Microsoft 365 avaliação.</span><span class="sxs-lookup"><span data-stu-id="f408a-108">It doesn't work with Microsoft 365 trial.</span></span>

- <span data-ttu-id="f408a-p103">Ela usa o Azure. Você obterá automaticamente esse recurso no Azure **gratuitamente** quando realizar essas etapas. Não haverá custos para habilitar a redefinição de senha de autoatendimento se você não usar outros recursos do Azure.</span><span class="sxs-lookup"><span data-stu-id="f408a-p103">It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.</span></span>

- <span data-ttu-id="f408a-112">**Se você estiver usando um Active Directory local,** os dois pontos acima não se aplicam.</span><span class="sxs-lookup"><span data-stu-id="f408a-112">**If you're using an on-premises Active Directory**, the above two points don't apply.</span></span> <span data-ttu-id="f408a-113">Em vez disso, você pode configurar isso, **mas exige uma assinatura paga do Azure AD Premium**.</span><span class="sxs-lookup"><span data-stu-id="f408a-113">Rather, you can set this up but **it requires a paid subscription to Azure AD Premium**.</span></span>

<span data-ttu-id="f408a-114">Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="f408a-114">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="f408a-115">Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f408a-115">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="f408a-116">O que é uma conta de administrador?</span><span class="sxs-lookup"><span data-stu-id="f408a-116">What's an admin account?</span></span>](../../business-video/admin-center-overview.md)

<span data-ttu-id="f408a-117">Você deve ser um [administrador global ou administrador de senha](about-admin-roles.md) para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="f408a-117">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

## <a name="watch-let-users-reset-their-own-passwords"></a><span data-ttu-id="f408a-118">Assista: permitir que os usuários redefinir suas próprias senhas</span><span class="sxs-lookup"><span data-stu-id="f408a-118">Watch: Let users reset their own passwords</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

<span data-ttu-id="f408a-119">Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="f408a-119">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="steps-let-people-reset-their-own-passwords"></a><span data-ttu-id="f408a-120">Etapas: Permitir que as pessoas redefinir suas próprias senhas</span><span class="sxs-lookup"><span data-stu-id="f408a-120">Steps: Let people reset their own passwords</span></span>

<span data-ttu-id="f408a-121">Estas etapas habilitam a redefinição de senhas de autoatendimento para todas as pessoas da empresa.</span><span class="sxs-lookup"><span data-stu-id="f408a-121">These steps turn on self-service password reset for everyone in your business.</span></span>

1. <span data-ttu-id="f408a-122">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">de administração,</a>vá para a página de configurações **Configurações**  >  **Org.**</span><span class="sxs-lookup"><span data-stu-id="f408a-122">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>, go to the **Settings** > **Org settings** page.</span></span>

2. <span data-ttu-id="f408a-123">Na parte superior da página **Configurações da Organização,** selecione a guia **Segurança & Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="f408a-123">At the top of the **Org settings** page, select the **Security & Privacy** tab.</span></span>
  
3. <span data-ttu-id="f408a-124">Selecione **Redefinição de Senha de Autoatendados**.</span><span class="sxs-lookup"><span data-stu-id="f408a-124">Select **Self-service Password Reset**.</span></span>

4. <span data-ttu-id="f408a-125">Em **Redefinição de senha de** autoatenduro, selecione Ir para o portal do Azure para ativar a redefinição de senha de **autoatendados.**</span><span class="sxs-lookup"><span data-stu-id="f408a-125">Under **Self-service password reset**, select **Go to the Azure portal to turn on self-service password reset**.</span></span>

5. <span data-ttu-id="f408a-126">No painel de navegação esquerdo, selecione **Usuários** e, em seguida, no **painel Usuários | Página Todos os** usuários, selecione **Redefinição de senha**.</span><span class="sxs-lookup"><span data-stu-id="f408a-126">In the left navigation pane, select **Users**, and then, on the **Users | All users** page, select **Password reset**.</span></span>
  
6. <span data-ttu-id="f408a-127">Na página **Propriedades,** selecione **Tudo para** habilita-lo para todos em sua empresa e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f408a-127">On the **Properties** page, select **All** to enable it for everyone in your business, and then select **Save**.</span></span>
  
7. <span data-ttu-id="f408a-128">Quando seus usuários entrarem, eles serão solicitados a inserir informações de contato adicionais que os ajudarão a redefinir sua senha no futuro.</span><span class="sxs-lookup"><span data-stu-id="f408a-128">When your users sign in, they will be prompted to enter additional contact information that will help them reset their password in the future.</span></span>

## <a name="related-content"></a><span data-ttu-id="f408a-129">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="f408a-129">Related content</span></span>

<span data-ttu-id="f408a-130">[Definir a política de expiração de senha para sua](../manage/set-password-expiration-policy.md) organização (artigo)</span><span class="sxs-lookup"><span data-stu-id="f408a-130">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>\
<span data-ttu-id="f408a-131">[Definir a senha de um usuário individual para nunca expirar](set-password-to-never-expire.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="f408a-131">[Set an individual user's password to never expire](set-password-to-never-expire.md) (article)</span></span>\
<span data-ttu-id="f408a-132">[Microsoft 365 Business vídeos de treinamento](../../business-video/index.yml) (página de link)</span><span class="sxs-lookup"><span data-stu-id="f408a-132">[Microsoft 365 Business training videos](../../business-video/index.yml) (link page)</span></span>
