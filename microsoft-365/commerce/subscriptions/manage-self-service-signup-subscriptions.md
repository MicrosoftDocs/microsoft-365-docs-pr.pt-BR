---
title: Gerenciar assinaturas de inscrição de autoatendimento
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
description: Saiba como gerenciar assinaturas gratuitas de inscrição de autoatendimento para sua organização.
ms.openlocfilehash: fb70d0c40d4358abc227c8f6ff4a0e0dce1a7265
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647826"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="43311-103">Gerenciar assinaturas de inscrição de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="43311-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="43311-104">O que são assinaturas de inscrição de autoatendimento?</span><span class="sxs-lookup"><span data-stu-id="43311-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="43311-105">Há um número limitado de assinaturas gratuitas de inscrição de autoatendimento que os usuários em sua organização podem se inscrever.</span><span class="sxs-lookup"><span data-stu-id="43311-105">There are a limited number of free self-service sign-up subscriptions that users in your organization can sign up for.</span></span> <span data-ttu-id="43311-106">Um usuário só pode se inscrever para e usar uma assinatura de inscrição autoatendimento por conta própria.</span><span class="sxs-lookup"><span data-stu-id="43311-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="43311-107">Essas assinaturas são exibidas na página **seus produtos** , são marcadas como **livres**e você tem uma nota que diz: "esta é uma assinatura gratuita ativada pelos usuários da sua empresa."</span><span class="sxs-lookup"><span data-stu-id="43311-107">These subscriptions appear on the **Your products** page, are marked as **Free**, and have a note that says, "This is a free subscription activated by users in your company."</span></span> <span data-ttu-id="43311-108">Você pode gerenciar assinaturas de inscrição de autoatendimento, bloqueando os usuários de se inscrever e excluindo assinaturas gratuitas para as quais os usuários se inscreveram.</span><span class="sxs-lookup"><span data-stu-id="43311-108">You can manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="43311-109">Para obter mais informações sobre a inscrição de autoatendimento e as assinaturas disponíveis, consulte usar a inscrição de autoatendimento [em sua organização](../../admin/misc/self-service-sign-up.md).</span><span class="sxs-lookup"><span data-stu-id="43311-109">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="43311-110">Como essas assinaturas são diferentes das assinaturas de compras de autoatendimento?</span><span class="sxs-lookup"><span data-stu-id="43311-110">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="43311-111">As assinaturas de inscrição de autoatendimento são gratuitas e estão disponíveis para uma lista maior de produtos do que as assinaturas de compras de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="43311-111">Self-service sign-up subscriptions are free, and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="43311-112">Quando um usuário se inscreve em uma assinatura de compra de autoatendimento, ele é responsável por pagar por ela.</span><span class="sxs-lookup"><span data-stu-id="43311-112">When a user signs up for a self-service purchase subscription, they are responsible for paying for it.</span></span> <span data-ttu-id="43311-113">Além disso, as assinaturas de compras de autoatendimento estão disponíveis apenas para produtos de plataforma de alimentação (Power BI, aplicativos de energia e automatização de energia).</span><span class="sxs-lookup"><span data-stu-id="43311-113">Also, self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate).</span></span> <span data-ttu-id="43311-114">Para obter mais informações, consulte [perguntas frequentes sobre compras de autoatendimento](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="43311-114">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="43311-115">Bloquear a inscrição de usuários</span><span class="sxs-lookup"><span data-stu-id="43311-115">Block users from signing up</span></span>

<span data-ttu-id="43311-116">Use o cmdlet [**set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) com o parâmetro **AllowAdHocSubscriptions** para controlar se os usuários podem se inscrever em assinaturas de inscrição de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="43311-116">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="43311-117">Para obter mais informações, consulte [como controlar as configurações de autoatendimento?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="43311-117">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="43311-118">Excluir uma assinatura de inscrição de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="43311-118">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43311-119">Quando você exclui uma assinatura de inscrição de autoatendimento, impede que todos os usuários acessem seus dados e emails e exclua todos os dados e email.</span><span class="sxs-lookup"><span data-stu-id="43311-119">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="43311-120">No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="43311-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="43311-121">Encontre a assinatura de inscrição de autoatendimento que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="43311-121">Find the self-service sign-up subscription that you want to delete.</span></span> <span data-ttu-id="43311-122">Na seção **configurações & ações** , selecione **excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="43311-122">In the **Settings & Actions** section, select **Delete subscription**.</span></span>
3. <span data-ttu-id="43311-123">No painel **excluir assinatura** , marque a caixa de seleção e, em seguida, selecione **excluir assinatura**.</span><span class="sxs-lookup"><span data-stu-id="43311-123">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="43311-124">Tenho uma assinatura de inscrição de autoatendimento que bloqueia a exclusão de diretórios</span><span class="sxs-lookup"><span data-stu-id="43311-124">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="43311-125">Os produtos de inscrição de autoatendimento que os usuários individuais podem se inscrever para também criar um usuário convidado para autenticação no seu diretório do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="43311-125">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="43311-126">Para evitar a perda de dados, esses produtos de autoatendimento bloqueiam exclusões de diretório até que sejam totalmente excluídos do diretório.</span><span class="sxs-lookup"><span data-stu-id="43311-126">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="43311-127">Eles podem ser excluídos apenas pelo administrador do Azure AD. Para obter mais informações, consulte [excluir um diretório no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span><span class="sxs-lookup"><span data-stu-id="43311-127">They can be deleted only by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>