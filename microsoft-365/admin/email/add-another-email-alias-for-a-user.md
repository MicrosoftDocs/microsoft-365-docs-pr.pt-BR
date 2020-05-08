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
ms.openlocfilehash: 603b2f42d603ae5172c66b6f78bc55f8d44c81f5
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140507"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="4e7d5-103">Adicionar outro alias de email para um usuário</span><span class="sxs-lookup"><span data-stu-id="4e7d5-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4e7d5-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-104">The admin center is changing.</span></span> <span data-ttu-id="4e7d5-105">Se sua experiência não corresponder aos detalhes apresentados aqui, consulte [sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="4e7d5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="4e7d5-106">Este artigo é para os administradores do Microsoft 365 que têm assinaturas de negócios.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="4e7d5-107">Ele não se destina a usuários domésticos.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-107">It's not for home users.</span></span>
  
<span data-ttu-id="4e7d5-108">Um endereço de email principal no Microsoft 365 geralmente é o endereço de email que um usuário recebeu quando a conta foi criada.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="4e7d5-109">Quando o usuário envia emails para outras pessoas, o endereço de email principal dele é o que normalmente aparece no campo  *De*  , nos aplicativos de email.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="4e7d5-110">Eles também podem ter mais de um endereço de email associado à sua conta do Microsoft 365 for Business.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="4e7d5-111">Esses endereços adicionais são chamados também de alias.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="4e7d5-112">Por exemplo, digamos que Jenna tenha o endereço de email jenna@contosoco.com, mas ele também deseja receber emails em jen@contosoco.com porque algumas pessoas se referem a ele por esse nome.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="4e7d5-113">Você pode criar aliases para que os dois endereços de email vá para a caixa de entrada do Jenna.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="4e7d5-114">Você pode criar até 400 aliases para um usuário.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="4e7d5-115">Não são necessárias tarifas ou licenças adicionais.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="4e7d5-116">Se você quiser que várias pessoas gerenciem emails enviados para um único endereço de email, como info@NodPublishers.com ou sales@NodPublishers.com, crie uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="4e7d5-117">Para saber mais, confira [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="4e7d5-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="4e7d5-118">Adicionar aliases de email a um usuário</span><span class="sxs-lookup"><span data-stu-id="4e7d5-118">Add email aliases to a user</span></span>
<span data-ttu-id="4e7d5-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="4e7d5-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="4e7d5-120">Você deve ter [permissões de administrador](../add-users/about-admin-roles.md) para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4e7d5-121">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="4e7d5-122">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="4e7d5-123">Na página **usuários ativos** , selecione o usuário > **gerenciar aliases de email**.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-123">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="4e7d5-124">Você não verá essa opção se a pessoa não tiver uma licença atribuída a elas.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-124">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="4e7d5-125">Selecione **+ Adicionar um alias** e insira um novo alias para o usuário.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-125">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="4e7d5-126">Se você receber a mensagem de erro "**não é possível localizar um parâmetro que corresponda ao nome de parâmetro" EmailAddresses**", significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado, se você tiver adicionado um pouco mais.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-126">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="4e7d5-127">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-127">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="4e7d5-128">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-128">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="4e7d5-129">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-129">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="4e7d5-130">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-130">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="4e7d5-131">O alias de email deve terminar com um domínio da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-131">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="4e7d5-132">Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="4e7d5-132">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="4e7d5-133">Quando terminar, escolha **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-133">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="4e7d5-134">Aguarde 24 horas para que os novos aliases sejam populados em todo o Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-134">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="4e7d5-135">O usuário agora terá um endereço principal e um alias.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-135">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="4e7d5-136">Por exemplo, todos os emails enviados para o endereço principal do Eliza Hoffman, o Eliza@NodPublishers.com e o alias, Sales@NodPublishers.com, vão para a caixa de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-136">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="4e7d5-137">**Quando o usuário responder, o endereço de será seu alias *de* email principal.**</span><span class="sxs-lookup"><span data-stu-id="4e7d5-137">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="4e7d5-138">Por exemplo, digamos que uma mensagem seja enviada para Sales@NodPublishers.com e chegue na caixa de entrada do Eliza.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-138">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="4e7d5-139">Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-139">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="4e7d5-140">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="4e7d5-141">Na página **Usuários ativos**, selecione o nome da pessoa que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-141">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="4e7d5-142">Ao lado de **nome de usuário/alias de email**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-142">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="4e7d5-143">Se você receber a mensagem de erro "**não é possível localizar um parâmetro que corresponda ao nome de parâmetro" EmailAddresses**", significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado, se você tiver adicionado um pouco mais.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-143">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="4e7d5-144">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-144">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="4e7d5-145">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-145">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="4e7d5-146">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-146">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="4e7d5-147">Na caixa de texto em **alias**, digite a primeira parte do novo alias de email.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-147">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="4e7d5-148">Se você adicionou seu próprio domínio ao Office 365, será possível escolher o domínio para o novo alias de email usando a lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-148">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="4e7d5-149">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-149">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4e7d5-150">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-150">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="4e7d5-151">O alias de email deve terminar com um domínio da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-151">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="4e7d5-152">Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="4e7d5-152">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="4e7d5-153">Quando terminar, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-153">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="4e7d5-154">Aguarde 24 horas para que os novos aliases sejam populados em todo o Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-154">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="4e7d5-155">O usuário agora terá um endereço principal e um alias.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-155">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="4e7d5-156">Por exemplo, todos os emails enviados para o endereço principal do Eliza Hoffman, o Eliza@NodPublishers.com e o alias, Sales@NodPublishers.com, vão para a caixa de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-156">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="4e7d5-157">**Quando o usuário responder, o endereço de será seu alias *de* email principal.**</span><span class="sxs-lookup"><span data-stu-id="4e7d5-157">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="4e7d5-158">Por exemplo, digamos que uma mensagem seja enviada para Sales@NodPublishers.com e chegue na caixa de entrada do Eliza.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-158">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="4e7d5-159">Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-159">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4e7d5-160">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="4e7d5-161">Na página **Usuários ativos**, selecione o nome da pessoa que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-161">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="4e7d5-162">Ao lado de **nome de usuário/alias de email**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-162">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="4e7d5-163">Se você receber a mensagem de erro "**não é possível localizar um parâmetro que corresponda ao nome de parâmetro" EmailAddresses**", significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado, se você tiver adicionado um pouco mais.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-163">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="4e7d5-164">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-164">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="4e7d5-165">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-165">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="4e7d5-166">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-166">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="4e7d5-167">Na caixa de texto em **alias**, digite a primeira parte do novo alias de email.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-167">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="4e7d5-168">Se você adicionou seu próprio domínio ao Office 365, será possível escolher o domínio para o novo alias de email usando a lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-168">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="4e7d5-169">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-169">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4e7d5-170">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-170">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="4e7d5-171">O alias de email deve terminar com um domínio da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-171">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="4e7d5-172">Para adicionar outro nome de domínio à lista, consulte [Adicionar um domínio ao Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="4e7d5-172">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="4e7d5-173">Quando terminar, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-173">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="4e7d5-174">Aguarde 24 horas para que os novos aliases sejam populados em todo o Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-174">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="4e7d5-175">O usuário agora terá um endereço principal e um alias.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-175">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="4e7d5-176">Por exemplo, todos os emails enviados para o endereço principal do Eliza Hoffman, o Eliza@NodPublishers.com e o alias, Sales@NodPublishers.com, vão para a caixa de entrada de Eliza.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-176">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="4e7d5-177">**Quando o usuário responder, o endereço de será seu alias *de* email principal.**</span><span class="sxs-lookup"><span data-stu-id="4e7d5-177">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="4e7d5-178">Por exemplo, digamos que uma mensagem seja enviada para Sales@NodPublishers.com e chegue na caixa de entrada do Eliza.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-178">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="4e7d5-179">Quando Eliza responder à mensagem, seu endereço de email principal aparecerá como o remetente, não Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-179">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="4e7d5-180">Você obteve "não foi possível encontrar um parâmetro que corresponda ao nome de parâmetro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="4e7d5-180">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="4e7d5-181">Se você receber a mensagem de erro "**não é possível localizar um parâmetro que coincida com o nome do parâmetro EmailAddresses**" significa que está demorando muito mais para concluir a configuração do seu locatário ou do seu domínio personalizado se você tiver adicionado um pouco mais.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-181">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="4e7d5-182">O processo de configuração pode levar até quatro horas para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-182">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="4e7d5-183">Aguarde um pouco até ele terminar e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-183">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="4e7d5-184">Se o problema persistir, peça ao Suporte para fazer uma sincronização completa para você.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-184">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="4e7d5-185">Você comprou a assinatura da GoDaddy ou de outro parceiro?</span><span class="sxs-lookup"><span data-stu-id="4e7d5-185">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="4e7d5-186">Se você comprou a assinatura da GoDaddy ou de outro parceiro, vá até o respectivo console de gerenciamento para definir o novo alias como principal.</span><span class="sxs-lookup"><span data-stu-id="4e7d5-186">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="4e7d5-187">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="4e7d5-187">Related articles</span></span>

[<span data-ttu-id="4e7d5-188">Enviar email de um endereço diferente</span><span class="sxs-lookup"><span data-stu-id="4e7d5-188">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="4e7d5-189">Alterar um nome de usuário e endereço de email</span><span class="sxs-lookup"><span data-stu-id="4e7d5-189">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

