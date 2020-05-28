---
title: Conceder permissões de caixa de correio para outro usuário - Ajuda para administradores
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: 'Saiba como oferecer ao usuário o direito de acessar a caixa de correio de outro usuário. Isso dará ao usuário o direito de ler e enviar emails da caixa de correio do outro usuário. '
ms.openlocfilehash: 51de5f4e2b134a503ec935b1f1d0ec6519d2c229
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387172"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="23947-104">Conceder permissões de caixa de correio para outro usuário - Ajuda para administradores</span><span class="sxs-lookup"><span data-stu-id="23947-104">Give mailbox permissions to another user - Admin Help</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="23947-105">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="23947-105">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="23947-106">Como administrador, talvez você tenha requisitos da empresa para permitir que alguns usuários acessem a caixa de correio de outro usuário.</span><span class="sxs-lookup"><span data-stu-id="23947-106">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="23947-107">Por exemplo, talvez você queira habilitar um assistente para enviar ou ler emails da caixa de correio do gerente ou habilitar um dos usuários para enviar emails em nome de outro usuário.</span><span class="sxs-lookup"><span data-stu-id="23947-107">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="23947-108">Este tópico mostra como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="23947-108">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="23947-109">Se você estiver procurando informações sobre como criar e gerenciar caixas de correio compartilhadas, confira o artigo [Criar uma caixa de correio compartilhada](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="23947-109">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="23947-110">Deseja configurar permissões de caixa de correio?</span><span class="sxs-lookup"><span data-stu-id="23947-110">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="23947-p103">Com as permissões da caixa de correio, você dá acesso de leitura/gravação de uma caixa de correio a outro usuário. Os artigos a seguir ajudam você a configurar e usar esse recurso:</span><span class="sxs-lookup"><span data-stu-id="23947-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="23947-113">**Configurando as permissões:**</span><span class="sxs-lookup"><span data-stu-id="23947-113">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="23947-p104">a primeira etapa para configurar permissões é decidir quais ações você deseja permitir que o outro usuário realize em determinada caixa de correio. Você pode permitir que um usuário leia os emails na caixa de correio, envie emails em nome de outro usuário e envie emails como se eles fossem enviados por essa caixa de correio. Confira os seguintes artigos sobre a configuração de cada tipo de permissão:</span><span class="sxs-lookup"><span data-stu-id="23947-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="23947-117">Ler emails da caixa de correio de outro usuário</span><span class="sxs-lookup"><span data-stu-id="23947-117">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="23947-118">Enviar emails da caixa de correio de outro usuário</span><span class="sxs-lookup"><span data-stu-id="23947-118">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="23947-119">Enviar emails em nome de outro usuário</span><span class="sxs-lookup"><span data-stu-id="23947-119">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="23947-120">**Propagação das alterações:**</span><span class="sxs-lookup"><span data-stu-id="23947-120">**Changing propagation:**</span></span>
  
<span data-ttu-id="23947-121">depois de configurar as permissões, pode levar até 60 minutos para que as alterações se propaguem pelo sistema e entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="23947-121">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="23947-122">**Como usá-la após as permissões serem definidas:**</span><span class="sxs-lookup"><span data-stu-id="23947-122">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="23947-p105">depois de receber o acesso, existem algumas maneiras diferentes de acessar uma caixa de correio. Encontre ajuda neste artigo: [Acessar a caixa de correio de outra pessoa](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span><span class="sxs-lookup"><span data-stu-id="23947-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="23947-125">Enviar emails da caixa de correio de outro usuário</span><span class="sxs-lookup"><span data-stu-id="23947-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23947-126">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="23947-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="23947-127">Selecione o nome do usuário (do qual você pretende fornecer uma permissão de envio) para abrir o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="23947-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="23947-128">Na guia **email**, selecione**gerenciar permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="23947-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="23947-129">Ao lado de **enviar como**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="23947-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="23947-130">Marque **adicionar permissões**, em seguida, escolha o nome da pessoa para a qual você deseja que esse usuário possa enviar.</span><span class="sxs-lookup"><span data-stu-id="23947-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="23947-131">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="23947-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="23947-132">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="23947-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="23947-133">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="23947-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="23947-134">Ao lado de **enviar como**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="23947-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="23947-135">Marque **adicionar permissões**, em seguida, escolha o nome da pessoa para a qual você deseja que esse usuário possa enviar.</span><span class="sxs-lookup"><span data-stu-id="23947-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="23947-136">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="23947-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23947-137">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="23947-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="23947-138">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="23947-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="23947-139">Ao lado de **enviar como**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="23947-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="23947-140">Marque **adicionar permissões**, em seguida, escolha o nome da pessoa para a qual você deseja que esse usuário possa enviar.</span><span class="sxs-lookup"><span data-stu-id="23947-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="23947-141">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="23947-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="23947-142">Ler emails na caixa de correio de outro usuário</span><span class="sxs-lookup"><span data-stu-id="23947-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23947-143">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="23947-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="23947-144">Selecione o nome do usuário (cuja caixa de correio deseja permitir a leitura) para abrir o painel propriedades dela.</span><span class="sxs-lookup"><span data-stu-id="23947-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="23947-145">Na guia **email**, selecione**gerenciar permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="23947-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="23947-146">Ao lado de **ler e gerenciar**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="23947-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="23947-147">Selecione **Adicionar permissões**, digite o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="23947-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="23947-148">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="23947-148">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="23947-149">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="23947-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="23947-150">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="23947-150">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="23947-151">Ao lado de **ler e gerenciar**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="23947-151">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="23947-152">Selecione **Adicionar permissões**, digite o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="23947-152">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="23947-153">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="23947-153">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23947-154">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="23947-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="23947-155">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="23947-155">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="23947-156">Ao lado de **ler e gerenciar**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="23947-156">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="23947-157">Selecione **Adicionar permissões**, digite o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="23947-157">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="23947-158">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="23947-158">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="23947-159">Enviar emails em nome de outro usuário</span><span class="sxs-lookup"><span data-stu-id="23947-159">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="23947-160">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="23947-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="23947-161">Selecione o nome do usuário (do qual você planeja atribuir uma **permissão de envio**) para abrir o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="23947-161">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="23947-162">Na guia **email**, selecione**gerenciar permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="23947-162">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="23947-163">Ao lado de **enviar em nome**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="23947-163">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="23947-164">Selecione **Adicionar permissões**, em seguida escolha o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="23947-164">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="23947-165">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="23947-165">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="23947-166">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="23947-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="23947-167">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="23947-167">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="23947-168">Ao lado de **enviar em nome**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="23947-168">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="23947-169">Selecione **Adicionar permissões**, em seguida escolha o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="23947-169">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="23947-170">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="23947-170">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="23947-171">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="23947-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="23947-172">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="23947-172">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="23947-173">Ao lado de **enviar em nome**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="23947-173">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="23947-174">Selecione **Adicionar permissões**, em seguida escolha o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="23947-174">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="23947-175">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="23947-175">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="23947-176">Enviar e ler pelo Outlook e pelo Outlook na Web para empresas</span><span class="sxs-lookup"><span data-stu-id="23947-176">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="23947-p106">Deseja saber como enviar emails da caixa de correio de outro usuário? Confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="23947-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="23947-179">Gerenciar o email e os itens de calendário de outra pessoa</span><span class="sxs-lookup"><span data-stu-id="23947-179">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="23947-180">Enviar emails de outra pessoa ou grupo</span><span class="sxs-lookup"><span data-stu-id="23947-180">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
