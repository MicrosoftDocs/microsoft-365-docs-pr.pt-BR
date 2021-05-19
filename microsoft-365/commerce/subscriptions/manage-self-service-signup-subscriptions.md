---
title: Gerenciar assinaturas de inscrição de autoatend
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Saiba como gerenciar assinaturas de inscrição gratuitas de autoatendir para sua organização.
ms.date: 03/17/2021
ms.openlocfilehash: 741c9e0b45f127ffc0753b34982073f90c525d5b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536065"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="69f60-103">Gerenciar assinaturas de inscrição de autoatend</span><span class="sxs-lookup"><span data-stu-id="69f60-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="69f60-104">O que são assinaturas de inscrição de autoatendidores?</span><span class="sxs-lookup"><span data-stu-id="69f60-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="69f60-105">Há um número limitado de assinaturas de inscrição gratuitas de autoatend., disponíveis para os usuários em sua organização se inscreverem.</span><span class="sxs-lookup"><span data-stu-id="69f60-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="69f60-106">Um usuário só pode se inscrever e usar uma assinatura de inscrição de autoatend nome.</span><span class="sxs-lookup"><span data-stu-id="69f60-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="69f60-107">Você gerencia assinaturas de inscrição de autoatendados bloqueando os usuários de se inscreverem e excluindo assinaturas gratuitas para as que os usuários se inscreveram.</span><span class="sxs-lookup"><span data-stu-id="69f60-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="69f60-108">Para obter mais informações sobre a inscrição no autoatendado e as assinaturas disponíveis, consulte Usando o [autoatendino inscreva-se em sua organização](../../admin/misc/self-service-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="69f60-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="69f60-109">Exibir uma lista de assinaturas de inscrição de autoatend</span><span class="sxs-lookup"><span data-stu-id="69f60-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="69f60-110">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="69f60-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="69f60-111">Na guia **Produtos,** selecione o ícone de filtro e selecione **Livre**.</span><span class="sxs-lookup"><span data-stu-id="69f60-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="69f60-112">Uma lista de todas as assinaturas de inscrição de autoatendido é exibida.</span><span class="sxs-lookup"><span data-stu-id="69f60-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="69f60-113">Como essas assinaturas são diferentes das assinaturas de compra de autoatendidores?</span><span class="sxs-lookup"><span data-stu-id="69f60-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="69f60-114">As assinaturas de inscrição de autoatendados são gratuitas e estão disponíveis para uma lista maior de produtos do que assinaturas de compra de autoatendados.</span><span class="sxs-lookup"><span data-stu-id="69f60-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="69f60-115">Quando um usuário se insinuou em uma assinatura de compra de autoatendam, ele é responsável por pagar por ela.</span><span class="sxs-lookup"><span data-stu-id="69f60-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="69f60-116">As assinaturas de compra de autoatendados estão disponíveis apenas para produtos da Plataforma Power (Power BI, Power Apps e Power Automate), Project e Visio.</span><span class="sxs-lookup"><span data-stu-id="69f60-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="69f60-117">Para obter mais informações, consulte Perguntas frequentes sobre [compra de autoatend.](self-service-purchase-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="69f60-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.yml).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="69f60-118">Impedir que os usuários se insuem</span><span class="sxs-lookup"><span data-stu-id="69f60-118">Block users from signing up</span></span>

<span data-ttu-id="69f60-119">Você usa o cmdlet [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) com o **parâmetro AllowAdHocSubscriptions** para controlar se os usuários podem se inscrever para assinaturas de inscrição de autoatendência.</span><span class="sxs-lookup"><span data-stu-id="69f60-119">You use the [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="69f60-120">Para obter mais informações, consulte [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="69f60-120">For more information, see [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="69f60-121">Excluir uma assinatura de inscrição de autoatendado</span><span class="sxs-lookup"><span data-stu-id="69f60-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69f60-122">Ao excluir uma assinatura de inscrição de autoatendado, você bloqueia todos os usuários de acessar seus dados e emails e excluir todos os dados e emails.</span><span class="sxs-lookup"><span data-stu-id="69f60-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="69f60-123">No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="69f60-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="69f60-124">Na guia **Produtos,** selecione o ícone de filtro e selecione **Livre**.</span><span class="sxs-lookup"><span data-stu-id="69f60-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="69f60-125">Selecione a assinatura de inscrição de autoatendado que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="69f60-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="69f60-126">Na página detalhes da assinatura, na seção **Assinaturas e configurações de** pagamento, selecione **Excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="69f60-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="69f60-127">No painel **Excluir assinatura,** marque a caixa de seleção e selecione **Excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="69f60-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="69f60-128">Tenho uma assinatura de inscrição de autoatendados que bloqueia a exclusão de diretórios</span><span class="sxs-lookup"><span data-stu-id="69f60-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="69f60-129">Os produtos de assinatura de autoatendados que os usuários individuais podem inscrever também criam um usuário convidado para autenticação no diretório do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="69f60-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="69f60-130">Para evitar a perda de dados, esses produtos autoatendados bloqueiam exclusões de diretório até que eles são totalmente excluídos do diretório.</span><span class="sxs-lookup"><span data-stu-id="69f60-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="69f60-131">Eles só podem ser excluídos pelo administrador do Azure AD. Para obter mais informações, [consulte Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="69f60-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>
