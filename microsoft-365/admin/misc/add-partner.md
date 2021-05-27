---
title: Adicionar, mudar ou excluir um parceiro para assessoria de assinaturas
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f86e8177-936e-491e-9024-44dea2b296ff
description: Adicione um parceiro de registro no momento da Microsoft 365, altere o parceiro ou exclua um parceiro de uma assinatura.
ms.openlocfilehash: 4cebbce41cbd2a500cc502b808734f6056271d12
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683338"
---
# <a name="add-change-or-delete-a-subscription-advisor-partner"></a><span data-ttu-id="a2b12-103">Adicionar, mudar ou excluir um parceiro para assessoria de assinaturas</span><span class="sxs-lookup"><span data-stu-id="a2b12-103">Add, change, or delete a subscription advisor partner</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a2b12-104">Este artigo se aplica ao Office 365 operado pela 21Vianet na China.</span><span class="sxs-lookup"><span data-stu-id="a2b12-104">This article applies to Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="a2b12-105">É para organizações que querem permitir que um Parceiro 21Vianet administro sua assinatura Office 365 para elas.</span><span class="sxs-lookup"><span data-stu-id="a2b12-105">It is for organizations who want to allow a 21Vianet Partner to administer their Office 365 subscription for them.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="a2b12-106">Um parceiro autorizado da Microsoft que atua como parceiro para assessoria de assinaturas fornece a experiência técnica, de vendas e de suporte que você precisa para ajudar a configurar e manter sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="a2b12-106">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="a2b12-107">Você pode adicionar um parceiro de consultor de assinatura como parceiro de registro ao comprar Microsoft 365 ou em outro momento.</span><span class="sxs-lookup"><span data-stu-id="a2b12-107">You can add a subscription advisor partner as a partner of record when you purchase Microsoft 365 or at another time.</span></span> <span data-ttu-id="a2b12-108">Se você não estiver trabalhando com um parceiro no momento, também poderá encontrar um no site [do Microsoft Pinpoint.](https://pinpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a2b12-108">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="a2b12-109">Um parceiro autorizado da Microsoft que atua como parceiro para assessoria de assinaturas fornece a experiência técnica, de vendas e de suporte que você precisa para ajudar a configurar e manter sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="a2b12-109">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="a2b12-110">Você pode adicionar um parceiro para assessoria de assinaturas como parceiro de registro ao comprar o Office 365 ou em outra ocasião.</span><span class="sxs-lookup"><span data-stu-id="a2b12-110">You can add a subscription advisor partner as a partner of record when you purchase Office 365 or at another time.</span></span> <span data-ttu-id="a2b12-111">Se você não estiver trabalhando com um parceiro no momento, também poderá encontrar um no site [do Microsoft Pinpoint.](https://pinpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a2b12-111">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="a2b12-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a2b12-112">Before you begin</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="a2b12-113">O parceiro escolhido depende da serviços Microsoft que você usa e do país ou região onde você usará esses serviços.</span><span class="sxs-lookup"><span data-stu-id="a2b12-113">The partner you choose depends on the Microsoft services you use and the country or region where you'll use those services.</span></span> <span data-ttu-id="a2b12-114">Se estiver adicionando um parceiro ou mudando de parceiro para a sua assinatura, primeiro será necessário solicitar e obter a ID de Parceiro Microsoft desse parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-114">If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="a2b12-p105">O parceiro escolhido depende dos serviços do Office 365 em uso e do país ou região onde você irá usar esses serviços. Se estiver adicionando um parceiro ou mudando de parceiro para a sua assinatura, primeiro será necessário solicitar e obter a ID de Parceiro Microsoft desse parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-p105">The partner you choose depends on the Office 365 services you use and the country or region where you'll use those services. If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="a2b12-117">Como administrador do Office 365, você pode criar ou editar usuários, redefinir senhas de usuário, gerenciar licenças de usuário, gerenciar domínios e atribuir permissões de administrador a outros usuários em sua organização, entre outras coisas.</span><span class="sxs-lookup"><span data-stu-id="a2b12-117">As an admin for Office 365, you can create or edit users, reset user passwords, manage user licenses, manage domains, and assign admin permissions to other users in your organization, among other things.</span></span> <span data-ttu-id="a2b12-118">No entanto, se você quiser que outra pessoa faça essas tarefas administrativas, poderá delegar essa função a um parceiro autorizado da 21Vianet criando uma relação de parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-118">However, if you want someone else to do these administrative tasks, you can delegate this role to an authorized partner of 21Vianet by creating a partner relationship.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="a2b12-119">Adicionar um parceiro na ocasião da compra</span><span class="sxs-lookup"><span data-stu-id="a2b12-119">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="a2b12-120">No centro de administração, vá para a página **Serviços de** Compra \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**de**</a> Cobrança.</span><span class="sxs-lookup"><span data-stu-id="a2b12-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**Purchase services**</a> page.</span></span>
2. <span data-ttu-id="a2b12-121">Selecione o produto que você deseja comprar e selecione **Comprar**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-121">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="a2b12-122">Para adicionar um novo parceiro, **expanda Precisa de ajuda com seu pedido?** e selecione **Obter assistência de um Microsoft Partner**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-122">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="a2b12-123">Siga as etapas na página provedores para pesquisar ou para obter uma combinação com um parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-123">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="a2b12-124">Se você já tiver um parceiro, na segunda etapa do assistente de checkout, no painel direito, em Informações do parceiro, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-124">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="a2b12-p107">Digite a ID de Parceiro Microsoft do parceiro que você está adicionando. Para obtê-la, contate o parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-p107">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="a2b12-127">Conclua o restante do assistente para finalizar a compra das suas assinaturas.</span><span class="sxs-lookup"><span data-stu-id="a2b12-127">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="a2b12-128">Adicionar um parceiro na ocasião da compra</span><span class="sxs-lookup"><span data-stu-id="a2b12-128">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="a2b12-129">No centro [de administração,](https://go.microsoft.com/fwlink/p/?linkid=848041)vá para a página **Serviços de** Compra \> **de**  Cobrança.</span><span class="sxs-lookup"><span data-stu-id="a2b12-129">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Billing** \> **Purchase services**  page.</span></span>
2. <span data-ttu-id="a2b12-130">Selecione o produto que você deseja comprar e selecione **Comprar**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-130">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="a2b12-131">Para adicionar um novo parceiro, **expanda Precisa de ajuda com seu pedido?** e selecione **Obter assistência de um Microsoft Partner**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-131">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="a2b12-132">Siga as etapas na página provedores para pesquisar ou para obter uma combinação com um parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-132">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="a2b12-133">Se você já tiver um parceiro, na segunda etapa do assistente de checkout, no painel direito, em Informações do parceiro, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-133">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="a2b12-p108">Digite a ID de Parceiro Microsoft do parceiro que você está adicionando. Para obtê-la, contate o parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-p108">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="a2b12-136">Conclua o restante do assistente para finalizar a compra das suas assinaturas.</span><span class="sxs-lookup"><span data-stu-id="a2b12-136">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

## <a name="add-a-partner-to-an-existing-subscription"></a><span data-ttu-id="a2b12-137">Adicionar um parceiro a uma assinatura existente</span><span class="sxs-lookup"><span data-stu-id="a2b12-137">Add a partner to an existing subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a2b12-138">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="a2b12-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="a2b12-139">Na guia **Produtos,** selecione a assinatura que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="a2b12-139">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="a2b12-140">Na página detalhes da assinatura, em **Informações do parceiro,** digite a **ID da Rede de Parceiros.**</span><span class="sxs-lookup"><span data-stu-id="a2b12-140">On the subscription details page, under **Partner information**, type the **Partner Network ID**.</span></span> <span data-ttu-id="a2b12-141">Você pode obter a ID do Microsoft Partner Network do parceiro solicitando-a ao parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-141">You can get the partner's Microsoft Partner Network ID by asking the partner for it.</span></span>
4. <span data-ttu-id="a2b12-142">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-142">Select **Add**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a2b12-143">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Assinaturas</a>.</span><span class="sxs-lookup"><span data-stu-id="a2b12-143">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="a2b12-144">Se você tiver mais de uma assinatura, selecione a assinatura que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="a2b12-144">If you have more than one subscription, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="a2b12-145">À direita, sob o custo da assinatura, selecione os três pontos (mais ações) > **Adicionar parceiro de registro**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-145">On the right, under the subscription cost, select the three dots (more actions) > **Add partner of record**.</span></span>
4. <span data-ttu-id="a2b12-p110">Digite a ID de parceiro da Microsoft para o parceiro que você está adicionando e selecione **Verificar ID** e, em seguida, **Enviar**. Peça a ID ao parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-p110">Type the Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
5. <span data-ttu-id="a2b12-148">A ID do parceiro é exibida na página **Assinaturas**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-148">The partner ID displays on the **Subscriptions** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="a2b12-149">Esse processo é iniciado pelo parceiro autorizado.</span><span class="sxs-lookup"><span data-stu-id="a2b12-149">This process is initiated by your authorized partner.</span></span> <span data-ttu-id="a2b12-150">O parceiro envia um email para perguntar se você deseja dar a eles permissão para atuar como parceiro de registro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-150">The partner sends you an email to ask you if you want to give them permission to act as a partner of record.</span></span>
  
<span data-ttu-id="a2b12-151">Para aceitar essa oferta</span><span class="sxs-lookup"><span data-stu-id="a2b12-151">To accept this offer</span></span>
  
1. <span data-ttu-id="a2b12-152">Leia os termos do parceiro no email.</span><span class="sxs-lookup"><span data-stu-id="a2b12-152">Read the partner's terms in the email.</span></span>
2. <span data-ttu-id="a2b12-153">Para autorizar o contrato, selecione o link, que vai para uma página de autorização em Office 365.</span><span class="sxs-lookup"><span data-stu-id="a2b12-153">To authorize the agreement, select the link, which goes to an authorization page in Office 365.</span></span>
3. <span data-ttu-id="a2b12-154">Em **Relações de Parceiros,** selecione **Sim** para autorizar o parceiro a ser seu administrador delegado e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-154">Under **Partner Relationships**, select **Yes** to authorize the partner to be your delegated admin, and then select **Next**.</span></span>
4. <span data-ttu-id="a2b12-155">Se a oferta de relacionamento de parceiro veio com uma assinatura de avaliação ou uma oferta de compra, crie sua conta de avaliação ou assinatura.</span><span class="sxs-lookup"><span data-stu-id="a2b12-155">If the offer for partner relationship came with a trial subscription or a purchase offer, create your trial or subscription account.</span></span>

::: moniker-end

## <a name="change-the-partner-for-a-subscription"></a><span data-ttu-id="a2b12-156">Mudar de parceiro para uma assinatura</span><span class="sxs-lookup"><span data-stu-id="a2b12-156">Change the partner for a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a2b12-157">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="a2b12-157">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a2b12-158">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="a2b12-158">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a2b12-159">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="a2b12-159">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end
2. <span data-ttu-id="a2b12-160">Na página detalhes das assinaturas, em **Informações do parceiro,** selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-160">On the subscriptions details page, under **Partner information**, select **Remove**.</span></span>
3. <span data-ttu-id="a2b12-161">Digite a **ID da Rede** de Parceiros da Microsoft para o novo parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-161">Type the **Microsoft Partner Network ID** for the new partner.</span></span> <span data-ttu-id="a2b12-162">Você pode obter a ID de Parceiro da Microsoft, solicitando-a do parceiro.</span><span class="sxs-lookup"><span data-stu-id="a2b12-162">You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
4. <span data-ttu-id="a2b12-163">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-163">Select **Add**.</span></span>
  
## <a name="view-your-partner-relationships"></a><span data-ttu-id="a2b12-164">Exibir suas relações de parceiro</span><span class="sxs-lookup"><span data-stu-id="a2b12-164">View your partner relationships</span></span>

- <span data-ttu-id="a2b12-165">No centro de administração, vá para a página relações **Configurações**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">parceiros.</a></span><span class="sxs-lookup"><span data-stu-id="a2b12-165">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span> <span data-ttu-id="a2b12-166">Seus parceiros estão listados nesta página.</span><span class="sxs-lookup"><span data-stu-id="a2b12-166">Your partners are listed on this page.</span></span>

  <span data-ttu-id="a2b12-167">Se você não tiver um parceiro, verá uma mensagem que diz "Não há nada aqui".</span><span class="sxs-lookup"><span data-stu-id="a2b12-167">If you don't have a partner, you'll see a message that says "There's nothing here."</span></span>
  
## <a name="delete-a-partner-from-a-subscription"></a><span data-ttu-id="a2b12-168">Excluir um parceiro de uma assinatura</span><span class="sxs-lookup"><span data-stu-id="a2b12-168">Delete a partner from a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a2b12-169">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="a2b12-169">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a2b12-170">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="a2b12-170">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a2b12-171">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Seus produtos</a>.</span><span class="sxs-lookup"><span data-stu-id="a2b12-171">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end
2. <span data-ttu-id="a2b12-172">Na guia **Produtos,** selecione a assinatura que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="a2b12-172">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="a2b12-173">Na página detalhes da assinatura, em **Informações do parceiro,** selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="a2b12-173">On the subscription details page, under **Partner information**, select **Remove**.</span></span>

## <a name="remove-a-reseller-relationship"></a><span data-ttu-id="a2b12-174">Remover uma relação de revendedor</span><span class="sxs-lookup"><span data-stu-id="a2b12-174">Remove a reseller relationship</span></span>

<span data-ttu-id="a2b12-175">Você não pode remover um relação de revendedor.</span><span class="sxs-lookup"><span data-stu-id="a2b12-175">You can't remove a reseller relationship yourself.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="a2b12-176">Se você estiver removendo uma relação de revendedor, a opção **Excluir** está acinzenada e você terá que pedir ao parceiro revendedor para seguir estas instruções: Remover uma relação de revendedor com o [parceiro](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="a2b12-176">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>

::: moniker-end

::: moniker range="o365-germany"
  
<span data-ttu-id="a2b12-177">Se você estiver removendo uma relação de revendedor, a opção **Excluir** está acinzenada e você terá que pedir ao parceiro revendedor para seguir estas instruções: Remover uma relação de revendedor com o [parceiro](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="a2b12-177">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"
  
<span data-ttu-id="a2b12-178">Você terá que pedir ao parceiro revendedor para seguir estas instruções: [Remover uma relação de revendedor com o parceiro](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="a2b12-178">You will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

## <a name="related-content"></a><span data-ttu-id="a2b12-179">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="a2b12-179">Related content</span></span>

<span data-ttu-id="a2b12-180">[Encontre seu Microsoft 365 ou revendedor](../manage/find-your-partner-or-reseller.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="a2b12-180">[Find your Microsoft 365 partner or reseller](../manage/find-your-partner-or-reseller.md) (article)</span></span>\
<span data-ttu-id="a2b12-181">[Planejar sua configuração de Microsoft 365 para empresas](../setup/plan-your-setup.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="a2b12-181">[Plan your setup of Microsoft 365 for business](../setup/plan-your-setup.md) (article)</span></span>