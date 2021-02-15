---
title: Gerenciar assinaturas de inscrição de autoatendir
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
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Saiba como gerenciar assinaturas de inscrição de autoatendir gratuitas para sua organização.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376300"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="b6326-103">Gerenciar assinaturas de inscrição de autoatendir</span><span class="sxs-lookup"><span data-stu-id="b6326-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="b6326-104">O que são assinaturas de inscrição self-service?</span><span class="sxs-lookup"><span data-stu-id="b6326-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="b6326-105">Há um número limitado de assinaturas gratuitas de inscrição de autoatend sorte disponíveis para os usuários em sua organização se inscreverem.</span><span class="sxs-lookup"><span data-stu-id="b6326-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="b6326-106">Um usuário só pode se inscrever e usar uma assinatura de inscrição self-service para si mesmo.</span><span class="sxs-lookup"><span data-stu-id="b6326-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="b6326-107">Você gerencia assinaturas de inscrição de autoatendida, impedindo que os usuários se inscrevam e excluindo assinaturas gratuitas para as que os usuários se inscreveram.</span><span class="sxs-lookup"><span data-stu-id="b6326-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="b6326-108">Para obter mais informações sobre a inscrição de autoatendado e as assinaturas disponíveis, consulte Usando a inscrição de [autoatendado em sua organização.](../../admin/misc/self-service-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="b6326-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="b6326-109">Exibir uma lista de assinaturas de inscrição self-service</span><span class="sxs-lookup"><span data-stu-id="b6326-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="b6326-110">No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="b6326-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="b6326-111">Na guia **Produtos,** selecione o ícone de filtro e selecione **Livre.**</span><span class="sxs-lookup"><span data-stu-id="b6326-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="b6326-112">Uma lista de todas as assinaturas de inscrição de autoatendido é exibida.</span><span class="sxs-lookup"><span data-stu-id="b6326-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="b6326-113">De que forma essas assinaturas são diferentes das assinaturas de compra self-service?</span><span class="sxs-lookup"><span data-stu-id="b6326-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="b6326-114">As assinaturas de inscrição de autoatendínio são gratuitas e estão disponíveis para uma lista maior de produtos do que as assinaturas de compra de autoatendínio.</span><span class="sxs-lookup"><span data-stu-id="b6326-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="b6326-115">Quando um usuário se instrua para uma assinatura de compra de autoatend pena, ele é responsável por pagar por ela.</span><span class="sxs-lookup"><span data-stu-id="b6326-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="b6326-116">Assinaturas de compra de autoatendínio só estão disponíveis para produtos da Plataforma Power (Power BI, Power Apps e Power Automate), Project e Visio.</span><span class="sxs-lookup"><span data-stu-id="b6326-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="b6326-117">Para obter mais informações, consulte [Perguntas frequentes sobre compra de autoatend saiba](self-service-purchase-faq.md)mais.</span><span class="sxs-lookup"><span data-stu-id="b6326-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="b6326-118">Impedir que os usuários se insuem</span><span class="sxs-lookup"><span data-stu-id="b6326-118">Block users from signing up</span></span>

<span data-ttu-id="b6326-119">Use o cmdlet [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) com o parâmetro **AllowAdHocSubscriptions** para controlar se os usuários podem se inscrever para assinaturas de inscrição de autoatendente.</span><span class="sxs-lookup"><span data-stu-id="b6326-119">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="b6326-120">Para obter mais informações, [consulte Como faço para controlar as configurações de autoatend site?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="b6326-120">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="b6326-121">Excluir uma assinatura de inscrição de autoatendado</span><span class="sxs-lookup"><span data-stu-id="b6326-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6326-122">Ao excluir uma assinatura de inscrição self-service, você bloqueia todos os usuários de acessar seus dados e emails e excluir todos os dados e emails.</span><span class="sxs-lookup"><span data-stu-id="b6326-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="b6326-123">No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="b6326-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="b6326-124">Na guia **Produtos,** selecione o ícone de filtro e selecione **Livre.**</span><span class="sxs-lookup"><span data-stu-id="b6326-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="b6326-125">Selecione a assinatura de inscrição self-service que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="b6326-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="b6326-126">Na página de detalhes da assinatura, na seção Assinaturas e **configurações de pagamento,** selecione **Excluir assinatura.**</span><span class="sxs-lookup"><span data-stu-id="b6326-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="b6326-127">No painel **Excluir assinatura,** marque a caixa de seleção e selecione **Excluir assinatura.**</span><span class="sxs-lookup"><span data-stu-id="b6326-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="b6326-128">Eu tenho uma assinatura de inscrição de autoatendário que bloqueia a exclusão de diretórios</span><span class="sxs-lookup"><span data-stu-id="b6326-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="b6326-129">Os produtos de assinatura self-service que usuários individuais podem se inscrever também criam um usuário convidado para autenticação em seu diretório do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b6326-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="b6326-130">Para evitar a perda de dados, esses produtos pessoais bloqueiam exclusões de diretórios até que eles são totalmente excluídos do diretório.</span><span class="sxs-lookup"><span data-stu-id="b6326-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="b6326-131">Eles só podem ser excluídos pelo administrador do Azure AD. Para saber mais, confira [Excluir um diretório no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)</span><span class="sxs-lookup"><span data-stu-id="b6326-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>