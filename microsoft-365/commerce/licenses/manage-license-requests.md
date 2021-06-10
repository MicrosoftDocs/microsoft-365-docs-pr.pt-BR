---
title: Gerenciar solicitações de licença
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Saiba como revisar e aprovar ou negar solicitações de licença de usuários para sua assinatura Microsoft 365 para empresas.
ms.date: 08/07/2020
ms.openlocfilehash: 6cbfd81f4f6deba642729f1fef0b826b07a99f56
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535669"
---
# <a name="manage-license-requests"></a><span data-ttu-id="70397-103">Gerenciar solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="70397-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="70397-104">As informações neste artigo só se aplica a produtos comprados por autoatendados.</span><span class="sxs-lookup"><span data-stu-id="70397-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="70397-105">Para saber mais, confira Perguntas frequentes sobre [compra de autoatend.](../subscriptions/self-service-purchase-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="70397-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.yml).</span></span>

<span data-ttu-id="70397-106">Se você desabilitar as compras de autoatendito em sua organização, poderá usar solicitações de licença para gerenciar o processo de solicitação de licença para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="70397-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="70397-107">Quando um usuário tenta fazer uma compra de autoatendito para um produto que você bloqueou, ele pode enviar uma solicitação para uma licença para você, o administrador. Quando eles fazem uma solicitação, eles podem adicionar os nomes de outros usuários que também precisam de licenças para o produto.</span><span class="sxs-lookup"><span data-stu-id="70397-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="70397-108">Se você impedir que os usuários comprem autoatendam, a Microsoft não enviará emails de marketing para eles.</span><span class="sxs-lookup"><span data-stu-id="70397-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="70397-109">Além disso, se eles estão usando uma versão de avaliação de um produto, eles não veem prompts para comprá-lo.</span><span class="sxs-lookup"><span data-stu-id="70397-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="70397-110">Para saber mais, consulte [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span><span class="sxs-lookup"><span data-stu-id="70397-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="70397-111">Para ver e gerenciar solicitações de licença, o administrador usa a guia **Solicitações** na página **Licenciamento.**</span><span class="sxs-lookup"><span data-stu-id="70397-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="70397-112">A lista mostra o nome do produto solicitado, o nome da pessoa que está solicitando uma licença, a data solicitada e o status da solicitação.</span><span class="sxs-lookup"><span data-stu-id="70397-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="70397-113">Os administradores podem filtrar a lista para mostrar solicitações pendentes ou concluídas.</span><span class="sxs-lookup"><span data-stu-id="70397-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="70397-114">As solicitações são mantidas por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="70397-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="70397-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="70397-115">Before you begin</span></span>

<span data-ttu-id="70397-116">Você deve ser um administrador global para executar as tarefas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="70397-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="70397-117">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="70397-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="70397-118">Usar seu próprio processo de solicitação</span><span class="sxs-lookup"><span data-stu-id="70397-118">Use your own request process</span></span>

<span data-ttu-id="70397-119">Se sua organização tiver seu próprio processo de solicitação, você poderá usá-lo.</span><span class="sxs-lookup"><span data-stu-id="70397-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="70397-120">Você cria uma mensagem que é exibida para os usuários quando eles solicitam uma licença.</span><span class="sxs-lookup"><span data-stu-id="70397-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70397-121">Se você usar seu próprio processo de solicitação, nenhuma solicitação será exibida na guia **Solicitações.** As solicitações existentes de antes de você adicionar sua mensagem continuam a aparecer até que você as aprove ou as decline.</span><span class="sxs-lookup"><span data-stu-id="70397-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="70397-122">No centro de administração, vá para a página **Licenças de** Cobrança  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> e selecione a **guia Solicitações.**</span><span class="sxs-lookup"><span data-stu-id="70397-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="70397-123">Selecione **Usar seu processo de solicitação existente.**</span><span class="sxs-lookup"><span data-stu-id="70397-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="70397-124">No painel direito, na **caixa** Mensagem, digite a mensagem que você deseja que os usuários vejam quando solicitarem uma licença.</span><span class="sxs-lookup"><span data-stu-id="70397-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="70397-125">Se você também quiser incluir um link para sua política de organizações ou outra documentação, insira a URL na caixa de texto **Link to documentation (opcional).**</span><span class="sxs-lookup"><span data-stu-id="70397-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="70397-126">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="70397-126">Select **Save**.</span></span>

<span data-ttu-id="70397-127">Ao retornar à lista **Solicitações,** você verá a mensagem **Você está usando seu próprio processo de solicitação de licença.**</span><span class="sxs-lookup"><span data-stu-id="70397-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="70397-128">Para fazer alterações na mensagem enviada aos usuários, selecione Usar seu processo de solicitação **existente.**</span><span class="sxs-lookup"><span data-stu-id="70397-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="70397-129">Pare de usar seu próprio processo de solicitação</span><span class="sxs-lookup"><span data-stu-id="70397-129">Stop using your own request process</span></span>

1. <span data-ttu-id="70397-130">No centro de administração, vá para a página **Licenças de** Cobrança  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> e selecione a **guia Solicitações.**</span><span class="sxs-lookup"><span data-stu-id="70397-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="70397-131">Selecione **Usar seu processo de solicitação existente.**</span><span class="sxs-lookup"><span data-stu-id="70397-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="70397-132">No painel direito, desimpe a caixa de seleção **Usar o processo de** solicitação da minha organização.</span><span class="sxs-lookup"><span data-stu-id="70397-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="70397-133">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="70397-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="70397-134">Aprovar ou negar uma solicitação de licença</span><span class="sxs-lookup"><span data-stu-id="70397-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="70397-135">No centro de administração, vá para a página **Licenças de** Cobrança  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> e selecione a **guia Solicitações.**</span><span class="sxs-lookup"><span data-stu-id="70397-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="70397-136">Selecione a linha que contém a solicitação que você deseja revisar.</span><span class="sxs-lookup"><span data-stu-id="70397-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="70397-137">O painel direito mostra detalhes sobre quais usuários querem licenças para o produto.</span><span class="sxs-lookup"><span data-stu-id="70397-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="70397-138">Para negar toda a solicitação, selecione **Não aprovar** e, na caixa de diálogo, selecione **Não aprovar**.</span><span class="sxs-lookup"><span data-stu-id="70397-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="70397-139">Para negar a solicitação a alguns usuários, mas aprovar outros, selecione o X pelo nome dos usuários que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="70397-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="70397-140">Seus nomes são movidos em **Não atribuir a esses usuários**.</span><span class="sxs-lookup"><span data-stu-id="70397-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="70397-141">Se você tiver mais de um produto, em **Selecionar um** produto, selecione o que deseja usar para atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="70397-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="70397-142">Para negar aos usuários o acesso a determinados aplicativos e serviços, expanda **Ativar** ou desativar aplicativos e serviços e desempurar as caixas de seleção dos que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="70397-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="70397-143">Na parte inferior do painel, digite uma mensagem opcional na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="70397-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="70397-144">Quando terminar, selecione **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="70397-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="70397-145">O painel direito mostra os detalhes da solicitação.</span><span class="sxs-lookup"><span data-stu-id="70397-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="70397-146">Feche o painel direito.</span><span class="sxs-lookup"><span data-stu-id="70397-146">Close the right pane.</span></span>
    <span data-ttu-id="70397-147">Os usuários recebem um email que diz que sua solicitação foi aprovada ou negada.</span><span class="sxs-lookup"><span data-stu-id="70397-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="70397-148">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="70397-148">Related content</span></span>

<span data-ttu-id="70397-149">[Atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md) (artigo) </span><span class="sxs-lookup"><span data-stu-id="70397-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="70397-150">[Mover usuários para uma assinatura diferente](../subscriptions/move-users-different-subscription.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="70397-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="70397-151">[Comprar ou remover licenças de assinatura](buy-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="70397-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>
