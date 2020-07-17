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
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780596"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="152a1-104">Conceder permissões de caixa de correio para outro usuário - Ajuda para administradores</span><span class="sxs-lookup"><span data-stu-id="152a1-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="152a1-105">Como administrador, talvez você tenha requisitos da empresa para permitir que alguns usuários acessem a caixa de correio de outro usuário.</span><span class="sxs-lookup"><span data-stu-id="152a1-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="152a1-106">Por exemplo, talvez você queira habilitar um assistente para enviar ou ler emails da caixa de correio do gerente ou habilitar um dos usuários para enviar emails em nome de outro usuário.</span><span class="sxs-lookup"><span data-stu-id="152a1-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="152a1-107">Este tópico mostra como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="152a1-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="152a1-108">Se você estiver procurando informações sobre como criar e gerenciar caixas de correio compartilhadas, confira o artigo [Criar uma caixa de correio compartilhada](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="152a1-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="152a1-109">Deseja configurar permissões de caixa de correio?</span><span class="sxs-lookup"><span data-stu-id="152a1-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="152a1-p103">Com as permissões da caixa de correio, você dá acesso de leitura/gravação de uma caixa de correio a outro usuário. Os artigos a seguir ajudam você a configurar e usar esse recurso:</span><span class="sxs-lookup"><span data-stu-id="152a1-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="152a1-112">**Configurando as permissões:**</span><span class="sxs-lookup"><span data-stu-id="152a1-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="152a1-p104">a primeira etapa para configurar permissões é decidir quais ações você deseja permitir que o outro usuário realize em determinada caixa de correio. Você pode permitir que um usuário leia os emails na caixa de correio, envie emails em nome de outro usuário e envie emails como se eles fossem enviados por essa caixa de correio. Confira os seguintes artigos sobre a configuração de cada tipo de permissão:</span><span class="sxs-lookup"><span data-stu-id="152a1-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="152a1-116">Ler emails da caixa de correio de outro usuário</span><span class="sxs-lookup"><span data-stu-id="152a1-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="152a1-117">Enviar emails da caixa de correio de outro usuário</span><span class="sxs-lookup"><span data-stu-id="152a1-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="152a1-118">Enviar emails em nome de outro usuário</span><span class="sxs-lookup"><span data-stu-id="152a1-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="152a1-119">**Propagação das alterações:**</span><span class="sxs-lookup"><span data-stu-id="152a1-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="152a1-120">depois de configurar as permissões, pode levar até 60 minutos para que as alterações se propaguem pelo sistema e entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="152a1-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="152a1-121">**Como usá-la após as permissões serem definidas:**</span><span class="sxs-lookup"><span data-stu-id="152a1-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="152a1-p105">depois de receber o acesso, existem algumas maneiras diferentes de acessar uma caixa de correio. Encontre ajuda neste artigo: [Acessar a caixa de correio de outra pessoa](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span><span class="sxs-lookup"><span data-stu-id="152a1-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="152a1-124">Enviar emails da caixa de correio de outro usuário</span><span class="sxs-lookup"><span data-stu-id="152a1-124">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="152a1-125">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="152a1-125">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="152a1-126">Selecione o nome do usuário (do qual você pretende fornecer uma permissão de envio) para abrir o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="152a1-126">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="152a1-127">Na guia **email**, selecione**gerenciar permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="152a1-127">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="152a1-128">Ao lado de **enviar como**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-128">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="152a1-129">Marque **adicionar permissões**, em seguida, escolha o nome da pessoa para a qual você deseja que esse usuário possa enviar.</span><span class="sxs-lookup"><span data-stu-id="152a1-129">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="152a1-130">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-130">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="152a1-131">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="152a1-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="152a1-132">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="152a1-132">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="152a1-133">Ao lado de **enviar como**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-133">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="152a1-134">Marque **adicionar permissões**, em seguida, escolha o nome da pessoa para a qual você deseja que esse usuário possa enviar.</span><span class="sxs-lookup"><span data-stu-id="152a1-134">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="152a1-135">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-135">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="152a1-136">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="152a1-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="152a1-137">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="152a1-137">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="152a1-138">Ao lado de **enviar como**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-138">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="152a1-139">Marque **adicionar permissões**, em seguida, escolha o nome da pessoa para a qual você deseja que esse usuário possa enviar.</span><span class="sxs-lookup"><span data-stu-id="152a1-139">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="152a1-140">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-140">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="152a1-141">Ler emails na caixa de correio de outro usuário</span><span class="sxs-lookup"><span data-stu-id="152a1-141">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="152a1-142">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="152a1-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="152a1-143">Selecione o nome do usuário (cuja caixa de correio deseja permitir a leitura) para abrir o painel propriedades dela.</span><span class="sxs-lookup"><span data-stu-id="152a1-143">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="152a1-144">Na guia **email**, selecione**gerenciar permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="152a1-144">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="152a1-145">Ao lado de **ler e gerenciar**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-145">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="152a1-146">Selecione **Adicionar permissões**, digite o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="152a1-146">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="152a1-147">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-147">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="152a1-148">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="152a1-148">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="152a1-149">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="152a1-149">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="152a1-150">Ao lado de **ler e gerenciar**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-150">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="152a1-151">Selecione **Adicionar permissões**, digite o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="152a1-151">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="152a1-152">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-152">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="152a1-153">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="152a1-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="152a1-154">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="152a1-154">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="152a1-155">Ao lado de **ler e gerenciar**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-155">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="152a1-156">Selecione **Adicionar permissões**, digite o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="152a1-156">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="152a1-157">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-157">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="152a1-158">Enviar emails em nome de outro usuário</span><span class="sxs-lookup"><span data-stu-id="152a1-158">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="152a1-159">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="152a1-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="152a1-160">Selecione o nome do usuário (do qual você planeja atribuir uma **permissão de envio**) para abrir o painel Propriedades.</span><span class="sxs-lookup"><span data-stu-id="152a1-160">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="152a1-161">Na guia **email**, selecione**gerenciar permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="152a1-161">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="152a1-162">Ao lado de **enviar em nome**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-162">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="152a1-163">Selecione **Adicionar permissões**, em seguida escolha o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="152a1-163">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="152a1-164">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-164">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="152a1-165">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="152a1-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="152a1-166">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="152a1-166">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="152a1-167">Ao lado de **enviar em nome**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-167">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="152a1-168">Selecione **Adicionar permissões**, em seguida escolha o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="152a1-168">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="152a1-169">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-169">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="152a1-170">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="152a1-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="152a1-171">Selecione o usuário desejado, expanda **configurações de email** e, em seguida, selecione **editar** ao lado de **permissões de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="152a1-171">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="152a1-172">Ao lado de **enviar em nome**, selecione **editar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-172">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="152a1-173">Selecione **Adicionar permissões**, em seguida escolha o nome do usuário ou usuários para os quais você deseja conceder permissões para enviar emails a partir dessa caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="152a1-173">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="152a1-174">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="152a1-174">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="152a1-175">Enviar e ler pelo Outlook e pelo Outlook na Web para empresas</span><span class="sxs-lookup"><span data-stu-id="152a1-175">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="152a1-p106">Deseja saber como enviar emails da caixa de correio de outro usuário? Confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="152a1-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="152a1-178">Gerenciar o email e os itens de calendário de outra pessoa</span><span class="sxs-lookup"><span data-stu-id="152a1-178">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="152a1-179">Enviar emails de outra pessoa ou grupo</span><span class="sxs-lookup"><span data-stu-id="152a1-179">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
