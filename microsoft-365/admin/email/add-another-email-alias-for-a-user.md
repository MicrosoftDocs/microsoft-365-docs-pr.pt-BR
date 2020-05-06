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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Saiba como você pode ter mais de um endereço de email, chamado alias de email, associado à sua conta do Microsoft 365 for Business. '
ms.openlocfilehash: efd0dbf5ae072c803b52d94dd41f16db9bb0413a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048802"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="00529-103">Adicionar outro alias de email para um usuário</span><span class="sxs-lookup"><span data-stu-id="00529-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="00529-104">Este artigo é para os administradores do Microsoft 365 que têm assinaturas de negócios.</span><span class="sxs-lookup"><span data-stu-id="00529-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="00529-105">Ele não se destina a usuários domésticos.</span><span class="sxs-lookup"><span data-stu-id="00529-105">It's not for home users.</span></span>
  
<span data-ttu-id="00529-106">Um endereço de email principal no Microsoft 365 geralmente é o endereço de email que um usuário recebeu quando a conta foi criada.</span><span class="sxs-lookup"><span data-stu-id="00529-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="00529-107">Quando o usuário envia emails para outras pessoas, o endereço de email principal dele é o que normalmente aparece no campo  *De*  , nos aplicativos de email.</span><span class="sxs-lookup"><span data-stu-id="00529-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="00529-108">Eles também podem ter mais de um endereço de email associado à sua conta do Microsoft 365 for Business.</span><span class="sxs-lookup"><span data-stu-id="00529-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="00529-109">Esses endereços adicionais são chamados também de alias.</span><span class="sxs-lookup"><span data-stu-id="00529-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="00529-110">Por exemplo, digamos que Jenna tenha o endereço de email jenna@contosoco.com, mas ele também deseja receber emails em jen@contosoco.com porque algumas pessoas se referem a ele por esse nome.</span><span class="sxs-lookup"><span data-stu-id="00529-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="00529-111">Você pode criar aliases para que os dois endereços de email vá para a caixa de entrada do Jenna.</span><span class="sxs-lookup"><span data-stu-id="00529-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="00529-112">Você pode criar até 400 aliases para um usuário.</span><span class="sxs-lookup"><span data-stu-id="00529-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="00529-113">Não são necessárias tarifas ou licenças adicionais.</span><span class="sxs-lookup"><span data-stu-id="00529-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="00529-114">Se você quiser que várias pessoas gerenciem emails enviados para um único endereço de email, como info@NodPublishers.com ou sales@NodPublishers.com, crie uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="00529-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="00529-115">Para saber mais, confira [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="00529-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="00529-116">Adicionar aliases de email a um usuário</span><span class="sxs-lookup"><span data-stu-id="00529-116">Add email aliases to a user</span></span>
<span data-ttu-id="00529-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="00529-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="00529-118">Você deve ter [permissões de administrador](../add-users/about-admin-roles.md) para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="00529-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="00529-119">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="00529-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="00529-120">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="00529-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="00529-121">Na página **usuários ativos** , selecione o usuário > **gerenciar aliases de email**.</span><span class="sxs-lookup"><span data-stu-id="00529-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="00529-122">Você não verá essa opção se a pessoa não tiver uma licença atribuída a elas.</span><span class="sxs-lookup"><span data-stu-id="00529-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="00529-123">Selecione **+ Adicionar um alias** e insira um novo alias para o usuário.</span><span class="sxs-lookup"><span data-stu-id="00529-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="00529-124">Se você receber a mensagem de erro "**não é possível localizar um parâmetro que corresponda ao nome de parâmetro" EmailAddresses**", significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado, se você tiver adicionado um pouco mais.</span><span class="sxs-lookup"><span data-stu-id="00529-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="00529-125">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="00529-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="00529-126">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="00529-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="00529-127">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="00529-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="00529-128">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="00529-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="00529-129">O alias de email deve terminar com um domínio da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="00529-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="00529-130">Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="00529-130">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="00529-131">Quando terminar, escolha **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="00529-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="00529-132">Aguarde 24 horas para que os novos aliases sejam populados em todo o Office 365.</span><span class="sxs-lookup"><span data-stu-id="00529-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="00529-133">O usuário agora terá um endereço principal e um alias.</span><span class="sxs-lookup"><span data-stu-id="00529-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="00529-134">Por exemplo, todos os emails enviados para o endereço principal do Eliza Hoffman, o Eliza@NodPublishers.com e o alias, Sales@NodPublishers.com, vão para a caixa de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="00529-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="00529-135">**Quando o usuário responder, o endereço de será seu alias *de* email principal.**</span><span class="sxs-lookup"><span data-stu-id="00529-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="00529-136">Por exemplo, digamos que uma mensagem seja enviada para Sales@NodPublishers.com e chegue na caixa de entrada do Eliza.</span><span class="sxs-lookup"><span data-stu-id="00529-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="00529-137">Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="00529-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="00529-138">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="00529-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="00529-139">Na página **Usuários ativos**, selecione o nome da pessoa que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="00529-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="00529-140">Ao lado de **nome de usuário/alias de email**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="00529-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="00529-141">Se você receber a mensagem de erro "**não é possível localizar um parâmetro que corresponda ao nome de parâmetro" EmailAddresses**", significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado, se você tiver adicionado um pouco mais.</span><span class="sxs-lookup"><span data-stu-id="00529-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="00529-142">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="00529-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="00529-143">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="00529-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="00529-144">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="00529-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="00529-145">Na caixa de texto em **alias**, digite a primeira parte do novo alias de email.</span><span class="sxs-lookup"><span data-stu-id="00529-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="00529-146">Se você adicionou seu próprio domínio ao Office 365, será possível escolher o domínio para o novo alias de email usando a lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="00529-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="00529-147">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="00529-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="00529-148">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="00529-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="00529-149">O alias de email deve terminar com um domínio da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="00529-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="00529-150">Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="00529-150">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="00529-151">Quando terminar, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="00529-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="00529-152">Aguarde 24 horas para que os novos aliases sejam populados em todo o Office 365.</span><span class="sxs-lookup"><span data-stu-id="00529-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="00529-153">O usuário agora terá um endereço principal e um alias.</span><span class="sxs-lookup"><span data-stu-id="00529-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="00529-154">Por exemplo, todos os emails enviados para o endereço principal do Eliza Hoffman, o Eliza@NodPublishers.com e o alias, Sales@NodPublishers.com, vão para a caixa de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="00529-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="00529-155">**Quando o usuário responder, o endereço de será seu alias *de* email principal.**</span><span class="sxs-lookup"><span data-stu-id="00529-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="00529-156">Por exemplo, digamos que uma mensagem seja enviada para Sales@NodPublishers.com e chegue na caixa de entrada do Eliza.</span><span class="sxs-lookup"><span data-stu-id="00529-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="00529-157">Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="00529-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="00529-158">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="00529-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="00529-159">Na página **Usuários ativos**, selecione o nome da pessoa que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="00529-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="00529-160">Ao lado de **nome de usuário/alias de email**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="00529-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="00529-161">Se você receber a mensagem de erro "**não é possível localizar um parâmetro que corresponda ao nome de parâmetro" EmailAddresses**", significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado, se você tiver adicionado um pouco mais.</span><span class="sxs-lookup"><span data-stu-id="00529-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="00529-162">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="00529-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="00529-163">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="00529-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="00529-164">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="00529-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="00529-165">Na caixa de texto em **alias**, digite a primeira parte do novo alias de email.</span><span class="sxs-lookup"><span data-stu-id="00529-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="00529-166">Se você adicionou seu próprio domínio ao Office 365, será possível escolher o domínio para o novo alias de email usando a lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="00529-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="00529-167">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="00529-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="00529-168">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="00529-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="00529-169">O alias de email deve terminar com um domínio da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="00529-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="00529-170">Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="00529-170">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="00529-171">Quando terminar, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="00529-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="00529-172">Aguarde 24 horas para que os novos aliases sejam populados em todo o Office 365.</span><span class="sxs-lookup"><span data-stu-id="00529-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="00529-173">O usuário agora terá um endereço principal e um alias.</span><span class="sxs-lookup"><span data-stu-id="00529-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="00529-174">Por exemplo, todos os emails enviados para o endereço principal do Eliza Hoffman, o Eliza@NodPublishers.com e o alias, Sales@NodPublishers.com, vão para a caixa de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="00529-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="00529-175">**Quando o usuário responder, o endereço de será seu alias *de* email principal.**</span><span class="sxs-lookup"><span data-stu-id="00529-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="00529-176">Por exemplo, digamos que uma mensagem seja enviada para Sales@NodPublishers.com e chegue na caixa de entrada do Eliza.</span><span class="sxs-lookup"><span data-stu-id="00529-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="00529-177">Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="00529-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="00529-178">Você obteve "não foi possível encontrar um parâmetro que corresponda ao nome de parâmetro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="00529-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="00529-179">Se você receber a mensagem de erro "**não é possível localizar um parâmetro que coincida com o nome do parâmetro EmailAddresses**" significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado se você tiver adicionado um pouco mais.</span><span class="sxs-lookup"><span data-stu-id="00529-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="00529-180">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="00529-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="00529-181">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="00529-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="00529-182">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="00529-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="00529-183">Você comprou a assinatura da GoDaddy ou de outro parceiro?</span><span class="sxs-lookup"><span data-stu-id="00529-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="00529-184">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="00529-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="00529-185">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="00529-185">Related articles</span></span>

[<span data-ttu-id="00529-186">Enviar email de um endereço diferente</span><span class="sxs-lookup"><span data-stu-id="00529-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="00529-187">Alterar um nome de usuário e endereço de email</span><span class="sxs-lookup"><span data-stu-id="00529-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

