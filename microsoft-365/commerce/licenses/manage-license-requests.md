---
title: Gerenciar solicitações de licença
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Saiba como revisar e aprovar ou negar solicitações de licença de usuários para sua assinatura do Microsoft 365 for Business.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597646"
---
# <a name="manage-license-requests"></a><span data-ttu-id="ef07c-103">Gerenciar solicitações de licença</span><span class="sxs-lookup"><span data-stu-id="ef07c-103">Manage license requests</span></span>

> [!NOTE]
> <span data-ttu-id="ef07c-104">As informações neste artigo se aplicam somente a produtos comprados por autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="ef07c-104">The information in this article only applies to self-service purchased products.</span></span> <span data-ttu-id="ef07c-105">Para saber mais, confira [perguntas frequentes sobre compras de autoatendimento](../subscriptions/self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="ef07c-105">To learn more, see [Self-service purchase FAQ](../subscriptions/self-service-purchase-faq.md).</span></span>

<span data-ttu-id="ef07c-106">Se você desabilitar compras de autoatendimento em sua organização, poderá usar solicitações de licenças para gerenciar o processo de solicitação de licença para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="ef07c-106">If you disable self-service purchases in your organization, you can use licenses requests to manage the license request process for your users.</span></span> <span data-ttu-id="ef07c-107">Quando um usuário tenta fazer uma compra de autoatendimento para um produto que você bloqueou, ele pode enviar uma solicitação de licença para você, o administrador. Ao fazer uma solicitação, eles podem adicionar os nomes de outros usuários que também precisam de licenças para o produto.</span><span class="sxs-lookup"><span data-stu-id="ef07c-107">When a user tries to make a self-service purchase for a product that you’ve blocked, they can submit a request for a license to you, the admin. When they make a request, they can add the names of other users who also need licenses for the product.</span></span>

> [!NOTE]
> <span data-ttu-id="ef07c-108">Se você impede que os usuários façam compras de autoatendimento, a Microsoft não envia emails de marketing.</span><span class="sxs-lookup"><span data-stu-id="ef07c-108">If you block users from making self-service purchases, Microsoft doesn’t send them marketing emails.</span></span> <span data-ttu-id="ef07c-109">Além disso, se ele estiver usando uma versão de avaliação de um produto, ele não verá prompts para comprá-lo.</span><span class="sxs-lookup"><span data-stu-id="ef07c-109">Also, if they’re using a trial version of a product, they don’t see prompts to buy it.</span></span> <span data-ttu-id="ef07c-110">Para saber mais, confira [gerenciar compras de autoatendimento (administrador)](../subscriptions/manage-self-service-purchases-admins.md).</span><span class="sxs-lookup"><span data-stu-id="ef07c-110">To learn more, see [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).</span></span>

<span data-ttu-id="ef07c-111">Para ver e gerenciar solicitações de licença, o administrador usa a guia **solicitações** na página **Licenciamento** .</span><span class="sxs-lookup"><span data-stu-id="ef07c-111">To see and manage license requests, admin uses the **Requests** tab on the **Licensing** page.</span></span> <span data-ttu-id="ef07c-112">A lista mostra o nome do produto solicitado, o nome da pessoa que está solicitando uma licença, uma data solicitada e o status da solicitação.</span><span class="sxs-lookup"><span data-stu-id="ef07c-112">The list shows the name of the product that is requested, name of the person requesting a license, date requested, and status of the request.</span></span> <span data-ttu-id="ef07c-113">Os administradores podem filtrar a lista para mostrar as solicitações pendentes ou concluídas.</span><span class="sxs-lookup"><span data-stu-id="ef07c-113">Admins can filter the list to show requests that are pending or completed.</span></span> <span data-ttu-id="ef07c-114">As solicitações são mantidas por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="ef07c-114">Requests are held for 30 days.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ef07c-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ef07c-115">Before you begin</span></span>

<span data-ttu-id="ef07c-116">Você deve ser um administrador global para executar as tarefas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ef07c-116">You must be a Global admin to perform the tasks in this article.</span></span> <span data-ttu-id="ef07c-117">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ef07c-117">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="use-your-own-request-process"></a><span data-ttu-id="ef07c-118">Usar seu próprio processo de solicitação</span><span class="sxs-lookup"><span data-stu-id="ef07c-118">Use your own request process</span></span>

<span data-ttu-id="ef07c-119">Se sua organização tiver seu próprio processo de solicitação, você poderá usá-lo.</span><span class="sxs-lookup"><span data-stu-id="ef07c-119">If your organization has its own request process, you can use it instead.</span></span> <span data-ttu-id="ef07c-120">Você cria uma mensagem que é exibida aos usuários quando eles solicitam uma licença.</span><span class="sxs-lookup"><span data-stu-id="ef07c-120">You create a message that is displayed to users when they request a license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef07c-121">Se você usar seu próprio processo de solicitação, nenhuma solicitação será exibida na guia **solicitações** . as solicitações existentes de antes da adição da mensagem continuarão a aparecer até que você as aprove ou recuse.</span><span class="sxs-lookup"><span data-stu-id="ef07c-121">If you use your own request process, no requests are displayed on the **Requests** tab. Existing requests from before you added your message continue to appear until you approve or decline them.</span></span>

1. <span data-ttu-id="ef07c-122">No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de cobrança e, em seguida, selecione a guia **solicitações** .</span><span class="sxs-lookup"><span data-stu-id="ef07c-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="ef07c-123">Selecione **usar seu processo de solicitação existente**.</span><span class="sxs-lookup"><span data-stu-id="ef07c-123">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="ef07c-124">No painel direito, na caixa **mensagem** , digite a mensagem que você deseja que os usuários vejam quando solicitarem uma licença.</span><span class="sxs-lookup"><span data-stu-id="ef07c-124">In the right pane, in the **Message** box, type the message you want users to see when they request a license.</span></span> <span data-ttu-id="ef07c-125">Se você também quiser incluir um link para a política de suas organizações ou outra documentação, digite a URL na caixa de texto **vincular à documentação (opcional)** .</span><span class="sxs-lookup"><span data-stu-id="ef07c-125">If you want to also include a link to your organizations policy or other documentation, enter the URL in the **Link to documentation (optional)** text box.</span></span>
4. <span data-ttu-id="ef07c-126">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ef07c-126">Select **Save**.</span></span>

<span data-ttu-id="ef07c-127">Ao retornar à lista de **solicitações** , você vê a mensagem **que está usando seu próprio processo de solicitação de licença**.</span><span class="sxs-lookup"><span data-stu-id="ef07c-127">When you return to the **Requests** list, you see the message **You’re using your own license request process**.</span></span> <span data-ttu-id="ef07c-128">Para fazer alterações na mensagem que é enviada aos usuários, selecione **usar o processo de solicitação existente**.</span><span class="sxs-lookup"><span data-stu-id="ef07c-128">To make changes to the message that is sent to users, select **Use your existing request process instead**.</span></span>

## <a name="stop-using-your-own-request-process"></a><span data-ttu-id="ef07c-129">Parar de usar seu próprio processo de solicitação</span><span class="sxs-lookup"><span data-stu-id="ef07c-129">Stop using your own request process</span></span>

1. <span data-ttu-id="ef07c-130">No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de cobrança e, em seguida, selecione a guia **solicitações** .</span><span class="sxs-lookup"><span data-stu-id="ef07c-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="ef07c-131">Selecione **usar seu processo de solicitação existente**.</span><span class="sxs-lookup"><span data-stu-id="ef07c-131">Select **Use your existing request process instead**.</span></span>
3. <span data-ttu-id="ef07c-132">No painel direito, desmarque a caixa de seleção **usar o processo de solicitação da minha organização** .</span><span class="sxs-lookup"><span data-stu-id="ef07c-132">In the right pane, clear the **Use my organization’s request process** check box.</span></span>
4. <span data-ttu-id="ef07c-133">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ef07c-133">Select **Save**.</span></span>

## <a name="approve-or-deny-a-license-request"></a><span data-ttu-id="ef07c-134">Aprovar ou negar uma solicitação de licença</span><span class="sxs-lookup"><span data-stu-id="ef07c-134">Approve or deny a license request</span></span>

1. <span data-ttu-id="ef07c-135">No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de cobrança e, em seguida, selecione a guia **solicitações** .</span><span class="sxs-lookup"><span data-stu-id="ef07c-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page, then select the **Requests** tab.</span></span>
2. <span data-ttu-id="ef07c-136">Selecione a linha que contém a solicitação que você deseja revisar.</span><span class="sxs-lookup"><span data-stu-id="ef07c-136">Select the row that contains the request you want to review.</span></span> <span data-ttu-id="ef07c-137">O painel direito mostra detalhes sobre quais usuários desejam licenças para o produto.</span><span class="sxs-lookup"><span data-stu-id="ef07c-137">The right pane shows details about which users want licenses to the product.</span></span>
3. <span data-ttu-id="ef07c-138">Para negar a solicitação inteira, selecione **não aprovar**e, na caixa de diálogo, selecione **não aprovar**.</span><span class="sxs-lookup"><span data-stu-id="ef07c-138">To deny the entire request, select **Don’t approve**, and in the dialog box, select **Don’t approve**.</span></span>
4. <span data-ttu-id="ef07c-139">Para negar alguns usuários para a solicitação, mas aprovar outros, selecione o X pelo nome dos usuários que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="ef07c-139">To deny some users for the request, but approve others, select the X by the name of the users that you want to remove.</span></span> <span data-ttu-id="ef07c-140">Seus nomes são movidos em **não atribuir a estes usuários**.</span><span class="sxs-lookup"><span data-stu-id="ef07c-140">Their names are moved under **Do not assign to these users**.</span></span>
5. <span data-ttu-id="ef07c-141">Se você tiver mais de um produto, em **selecionar um produto**, selecione aquele que você deseja usar para atribuir licenças para o.</span><span class="sxs-lookup"><span data-stu-id="ef07c-141">If you have more than one product, under **Select a product**, select the one that you want to use to assign licenses for.</span></span>
6. <span data-ttu-id="ef07c-142">Para negar o acesso dos usuários a determinados aplicativos e serviços, expanda **Ativar ou desativar os aplicativos e serviços e**desmarque as caixas de seleção para aqueles que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="ef07c-142">To deny users access to certain app and services, expand **Turn apps and services on or off**, then clear the check boxes for the ones you want to exclude.</span></span>
7. <span data-ttu-id="ef07c-143">Na parte inferior do painel, digite uma mensagem opcional na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="ef07c-143">At the bottom of the pane, type an optional message in the text box.</span></span>
8. <span data-ttu-id="ef07c-144">Quando tiver terminado, selecione **aprovar**.</span><span class="sxs-lookup"><span data-stu-id="ef07c-144">When you’re finished, select **Approve**.</span></span> <span data-ttu-id="ef07c-145">O painel direito mostra os detalhes da solicitação.</span><span class="sxs-lookup"><span data-stu-id="ef07c-145">The right pane shows the details of the request.</span></span>
9. <span data-ttu-id="ef07c-146">Feche o painel direito.</span><span class="sxs-lookup"><span data-stu-id="ef07c-146">Close the right pane.</span></span>
    <span data-ttu-id="ef07c-147">Os usuários recebem um email que diz que sua solicitação foi aprovada ou negada.</span><span class="sxs-lookup"><span data-stu-id="ef07c-147">Users receive an email that says their request was approved or denied.</span></span>

## <a name="related-content"></a><span data-ttu-id="ef07c-148">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="ef07c-148">Related content</span></span>

<span data-ttu-id="ef07c-149">[Atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md) (artigo) </span><span class="sxs-lookup"><span data-stu-id="ef07c-149">[Assign licenses to users](../../admin/manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="ef07c-150">[Mover usuários para uma assinatura diferente](../subscriptions/move-users-different-subscription.md) (artigo) </span><span class="sxs-lookup"><span data-stu-id="ef07c-150">[Move users to a different subscription](../subscriptions/move-users-different-subscription.md) (article)</span></span>\
<span data-ttu-id="ef07c-151">[Comprar ou remover licenças de assinatura](buy-licenses.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ef07c-151">[Buy or remove subscription licenses](buy-licenses.md) (article)</span></span>