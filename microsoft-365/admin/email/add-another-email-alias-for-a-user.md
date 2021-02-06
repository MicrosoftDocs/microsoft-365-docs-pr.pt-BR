---
title: Adicionar outro alias de email para um usuário
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Saiba como você pode ter mais de um endereço de email, chamado alias de email, associado à sua conta do Microsoft 365 para empresas. '
ms.openlocfilehash: 3c97640f4bb16876ec028a1af2b361a21a0decab
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126400"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="04775-103">Adicionar outro alias de email para um usuário</span><span class="sxs-lookup"><span data-stu-id="04775-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="04775-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="04775-104">The admin center is changing.</span></span> <span data-ttu-id="04775-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="04775-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end
  
<span data-ttu-id="04775-106">Este artigo é destinado a administradores do Microsoft 365 que têm assinaturas comerciais.</span><span class="sxs-lookup"><span data-stu-id="04775-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="04775-107">Ele não se destina a usuários domésticos.</span><span class="sxs-lookup"><span data-stu-id="04775-107">It's not for home users.</span></span>
  
<span data-ttu-id="04775-108">Um endereço de email principal no Microsoft 365 geralmente é o endereço de email atribuído a um usuário quando sua conta foi criada.</span><span class="sxs-lookup"><span data-stu-id="04775-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="04775-109">Quando o usuário envia emails para outras pessoas, o endereço de email principal dele é o que normalmente aparece no campo  *De*  , nos aplicativos de email.</span><span class="sxs-lookup"><span data-stu-id="04775-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="04775-110">Eles também podem ter mais de um endereço de email associado à conta do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="04775-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="04775-111">Esses endereços adicionais são chamados também de alias.</span><span class="sxs-lookup"><span data-stu-id="04775-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="04775-112">Por exemplo, digamos que Mila tenha o endereço de email jenna@contosoco.com, mas também deseja receber emails no jen@contosoco.com porque algumas pessoas se referem a ela por esse nome.</span><span class="sxs-lookup"><span data-stu-id="04775-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="04775-113">Você pode criar aliases para ela para que ambos os endereços de email acessem a caixa de entrada deIa.</span><span class="sxs-lookup"><span data-stu-id="04775-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="04775-114">Você pode criar até 400 aliases para um usuário.</span><span class="sxs-lookup"><span data-stu-id="04775-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="04775-115">Não são necessárias tarifas ou licenças adicionais.</span><span class="sxs-lookup"><span data-stu-id="04775-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="04775-116">Se você quiser que várias pessoas gerenciem emails enviados para um único endereço de email, como info@NodPublishers.com ou sales@NodPublishers.com, crie uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="04775-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="04775-117">Para saber mais, consulte [Criar uma caixa de correio compartilhada.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="04775-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="04775-118">Adicionar aliases de email a um usuário</span><span class="sxs-lookup"><span data-stu-id="04775-118">Add email aliases to a user</span></span>
<span data-ttu-id="04775-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="04775-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="04775-120">Você deve ter [permissões de administrador](../add-users/about-admin-roles.md) para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="04775-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="04775-121">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="04775-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="04775-122">Na página **Usuários Ativos,** selecione o usuário que > **aliases de email.**</span><span class="sxs-lookup"><span data-stu-id="04775-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="04775-123">Você não verá essa opção se a pessoa não tiver uma licença atribuída a ela.</span><span class="sxs-lookup"><span data-stu-id="04775-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="04775-124">Selecione **+ Adicionar um alias** e insira um novo alias para o usuário.</span><span class="sxs-lookup"><span data-stu-id="04775-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="04775-125">Se você receber a mensagem de erro " Um parâmetro que corresponde ao nome do parâmetro **'EmailAddresses**", significa que está demorando um pouco mais para concluir a configuração do locatário ou seu domínio personalizado se você adicionou um recentemente.</span><span class="sxs-lookup"><span data-stu-id="04775-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="04775-126">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="04775-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="04775-127">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="04775-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="04775-128">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="04775-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="04775-129">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="04775-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="04775-130">O alias de email deve terminar com um domínio da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="04775-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="04775-131">Para adicionar outro nome de domínio à lista, confira [Adicionar um domínio ao Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="04775-131">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="04775-132">Quando terminar, escolha **Salvar alterações.**</span><span class="sxs-lookup"><span data-stu-id="04775-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="04775-133">Aguarde 24 horas para que os novos aliases preencham todo o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04775-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="04775-134">O usuário agora terá um endereço principal e um alias.</span><span class="sxs-lookup"><span data-stu-id="04775-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="04775-135">Por exemplo, todos os emails enviados para o endereço principal, Eliza@NodPublishers.com e seu alias, Sales@NodPublishers.com, serão enviados para a Caixa de Entrada da Filha.</span><span class="sxs-lookup"><span data-stu-id="04775-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="04775-136">**Quando o usuário responder, o *endereço De*  será seu alias de email principal.**</span><span class="sxs-lookup"><span data-stu-id="04775-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="04775-137">Por exemplo, digamos que uma mensagem é enviada para Sales@NodPublishers.com e ela chega na caixa de entrada da Clara.</span><span class="sxs-lookup"><span data-stu-id="04775-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="04775-138">Quando Clara responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="04775-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="04775-139">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="04775-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="04775-140">Na página **Usuários ativos**, selecione o nome da pessoa que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="04775-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="04775-141">Ao lado de **Nome de Usuário/Aliases de Email,** selecione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="04775-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="04775-142">Se você receber a mensagem de erro " Um parâmetro que corresponde ao nome do parâmetro **'EmailAddresses**", significa que está demorando um pouco mais para concluir a configuração do locatário ou seu domínio personalizado se você adicionou um recentemente.</span><span class="sxs-lookup"><span data-stu-id="04775-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="04775-143">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="04775-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="04775-144">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="04775-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="04775-145">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="04775-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="04775-146">Na caixa de texto em **Alias,** digite a primeira parte do novo alias de email.</span><span class="sxs-lookup"><span data-stu-id="04775-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="04775-147">Se você adicionou seu próprio domínio ao Microsoft 365, é possível escolher o domínio para o novo alias de email usando a lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="04775-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="04775-148">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="04775-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="04775-149">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="04775-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="04775-150">O alias de email deve terminar com um domínio da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="04775-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="04775-151">Para adicionar outro nome de domínio à lista, confira [Adicionar um domínio ao Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="04775-151">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="04775-152">Quando terminar, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="04775-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="04775-153">Aguarde 24 horas para que os novos aliases preencham todo o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04775-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="04775-154">O usuário agora terá um endereço principal e um alias.</span><span class="sxs-lookup"><span data-stu-id="04775-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="04775-155">Por exemplo, todos os emails enviados para o endereço principal, Eliza@NodPublishers.com e seu alias, Sales@NodPublishers.com, serão enviados para a Caixa de Entrada da Filha.</span><span class="sxs-lookup"><span data-stu-id="04775-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="04775-156">**Quando o usuário responder, o *endereço De*  será seu alias de email principal.**</span><span class="sxs-lookup"><span data-stu-id="04775-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="04775-157">Por exemplo, digamos que uma mensagem é enviada para Sales@NodPublishers.com e ela chega na caixa de entrada da Clara.</span><span class="sxs-lookup"><span data-stu-id="04775-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="04775-158">Quando Clara responder à mensagem, seu endereço de email principal aparecerá como remetente, não Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="04775-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="04775-159">No centro de administração, acesse a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="04775-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="04775-160">Na página **Usuários ativos**, selecione o nome da pessoa que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="04775-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="04775-161">Ao lado de **Nome de Usuário/Aliases de Email,** selecione **Editar.**</span><span class="sxs-lookup"><span data-stu-id="04775-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="04775-162">Se você receber a mensagem de erro " Um parâmetro que corresponde ao nome do parâmetro **'EmailAddresses**", significa que está demorando um pouco mais para concluir a configuração do locatário ou seu domínio personalizado se você adicionou um recentemente.</span><span class="sxs-lookup"><span data-stu-id="04775-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="04775-163">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="04775-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="04775-164">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="04775-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="04775-165">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="04775-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="04775-166">Na caixa de texto em **Alias,** digite a primeira parte do novo alias de email.</span><span class="sxs-lookup"><span data-stu-id="04775-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="04775-167">Se você adicionou seu próprio domínio ao Microsoft 365, é possível escolher o domínio para o novo alias de email usando a lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="04775-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="04775-168">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="04775-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="04775-169">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="04775-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="04775-170">O alias de email deve terminar com um domínio da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="04775-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="04775-171">Para adicionar outro nome de domínio à lista, confira [Adicionar um domínio ao Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="04775-171">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="04775-172">Quando terminar, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="04775-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="04775-173">Aguarde 24 horas para que os novos aliases preencham todo o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04775-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="04775-174">O usuário agora terá um endereço principal e um alias.</span><span class="sxs-lookup"><span data-stu-id="04775-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="04775-175">Por exemplo, todos os emails enviados para o endereço principal, Eliza@NodPublishers.com e seu alias, Sales@NodPublishers.com, serão enviados para a Caixa de Entrada da Dra.</span><span class="sxs-lookup"><span data-stu-id="04775-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="04775-176">**Quando o usuário responder, o *endereço De*  será seu alias de email principal.**</span><span class="sxs-lookup"><span data-stu-id="04775-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="04775-177">Por exemplo, digamos que uma mensagem é enviada para Sales@NodPublishers.com e ela chega na caixa de entrada da Clara.</span><span class="sxs-lookup"><span data-stu-id="04775-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="04775-178">Quando Clara responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="04775-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="04775-179">Você conseguiu "Não foi encontrado um parâmetro que corresponde ao nome do parâmetro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="04775-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="04775-180">Se você receber a mensagem de erro " Um parâmetro que corresponde ao nome do parâmetro **EmailAddresses**" significa que está demorando um pouco mais para concluir a configuração do locatário ou seu domínio personalizado se você adicionou um recentemente.</span><span class="sxs-lookup"><span data-stu-id="04775-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="04775-181">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="04775-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="04775-182">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="04775-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="04775-183">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="04775-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="04775-184">Você comprou a assinatura da GoDaddy ou de outro parceiro?</span><span class="sxs-lookup"><span data-stu-id="04775-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="04775-185">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="04775-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="04775-186">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="04775-186">Related articles</span></span>

[<span data-ttu-id="04775-187">Enviar email de um endereço diferente</span><span class="sxs-lookup"><span data-stu-id="04775-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="04775-188">Alterar um nome de usuário e endereço de email</span><span class="sxs-lookup"><span data-stu-id="04775-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

