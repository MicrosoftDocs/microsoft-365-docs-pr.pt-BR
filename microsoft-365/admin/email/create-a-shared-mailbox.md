---
title: Criar uma caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Crie uma caixa de correio compartilhada para permitir que vários usuários da sua empresa compartilhem a responsabilidade de ler e responder a emails enviados para um endereço.
ms.openlocfilehash: 2ceec37928eafab0c4f02382dd24aa3fa91aa9cd
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42362296"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="26964-103">Criar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="26964-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="26964-104">Se a sua organização usa um ambiente híbrido do Exchange, você deverá usar o centro de administração do Exchange (EAC) no local para criar e gerenciar caixas de correio compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="26964-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="26964-105">Ver [Criar caixas de correio compartilhadas no centro de administração do Exchange](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span><span class="sxs-lookup"><span data-stu-id="26964-105">See [Create shared mailboxes in the Exchange admin center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span></span><br><br>
> <span data-ttu-id="26964-106">Se você não tiver certeza se deve criar uma caixa de correio compartilhada ou um Grupo do Office 365 para Outlook, confira [Comparar grupos](../create-groups/compare-groups.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="26964-106">If you're not sure if you should create a shared mailbox or an Office 365 Group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="26964-107">Observe que, no momento, não é possível migrar uma caixa de correio compartilhada para um grupo do Office 365.</span><span class="sxs-lookup"><span data-stu-id="26964-107">Note that currently, it's not possible to migrate a shared mailbox to an Office 365 Group.</span></span> <span data-ttu-id="26964-108">Se isso é algo que você deseja, informe-nos [votando aqui](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="26964-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="26964-p103">É muito fácil criar caixas de correio compartilhadas para que um grupo de pessoas possa monitorar e enviar emails de endereços de email comuns, como info@contoso.com. Quando um membro do grupo responde a uma mensagem enviada para a caixa de correio compartilhada, o email é exibido como sendo da caixa de correio compartilhada, e não do usuário individual.</span><span class="sxs-lookup"><span data-stu-id="26964-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="26964-111">As caixas de correio compartilhadas incluem um calendário compartilhado.</span><span class="sxs-lookup"><span data-stu-id="26964-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="26964-112">Várias empresas de pequeno porte preferem usar os calendários compartilhados como um local em que todos possam inserir compromissos.</span><span class="sxs-lookup"><span data-stu-id="26964-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="26964-113">Por exemplo, se você tem três usuários que fazem atendimento presencial a clientes, todos eles podem usar o calendário compartilhado para inserir os respectivos compromissos.</span><span class="sxs-lookup"><span data-stu-id="26964-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="26964-114">Essa é uma maneira fácil de manter todos informados.</span><span class="sxs-lookup"><span data-stu-id="26964-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="26964-115">Antes de criar uma caixa de correio compartilhada, não deixe de ler [Sobre caixas de correio compartilhadas](about-shared-mailboxes.md) para mais informações.</span><span class="sxs-lookup"><span data-stu-id="26964-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="26964-116">Criar uma caixa de correio compartilhada e adicionar membros</span><span class="sxs-lookup"><span data-stu-id="26964-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="26964-117">Entre com uma conta de administrador global do Office 365 ou conta de administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="26964-117">Sign in with an Office 365 global admin account or Exchange admin account.</span></span> <span data-ttu-id="26964-118">Caso receba a mensagem "**Você não possui permissão para acessar esta página ou realizar esta ação**", então você não é um administrador.</span><span class="sxs-lookup"><span data-stu-id="26964-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="26964-119">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="26964-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="26964-120">No [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=848041), acesse a página **Grupos**\>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="26964-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="26964-121">No [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=850627), acesse a página **Grupos**\>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="26964-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="26964-122">Na página **Caixas de correio compartilhadas**, selecione **+ Adicionar uma caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="26964-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="26964-123">Digite um nome para a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="26964-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="26964-124">Em seguida, o assistente escolhe o endereço de email, mas você pode editá-lo.</span><span class="sxs-lookup"><span data-stu-id="26964-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Nomeie sua caixa de correio compartilhada.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="26964-126">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="26964-126">Select **Add**.</span></span> <span data-ttu-id="26964-127">Pode levar alguns minutos até que você possa adicionar membros.</span><span class="sxs-lookup"><span data-stu-id="26964-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="26964-128">Em **Próximas etapas**, selecione **Adicionar membros a esta caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="26964-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="26964-129">Os membros são as pessoas que poderão visualizar o email de entrada nesta caixa de correio compartilhada e as respostas enviadas.</span><span class="sxs-lookup"><span data-stu-id="26964-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Selecionar Adicionar Membros](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="26964-131">Selecione o botão **+Adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="26964-131">Select the **+Add members** button.</span></span> <span data-ttu-id="26964-132">Marque a caixa de seleção ao lado da pessoa à qual pretende permitir o uso da caixa de correio compartilhada e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="26964-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Atribuir membros à caixa de correio compartilhada](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="26964-134">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="26964-134">Select **Close**.</span></span>

<span data-ttu-id="26964-135">Você tem uma caixa de correio compartilhada e inclui um calendário compartilhado.</span><span class="sxs-lookup"><span data-stu-id="26964-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="26964-136">Agora vá para a próxima etapa: bloqueie a entrada na conta da caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="26964-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="26964-137">Bloquear entrada para a conta de caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="26964-137">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="26964-138">Toda caixa de correio compartilhada tem uma conta de usuário correspondente.</span><span class="sxs-lookup"><span data-stu-id="26964-138">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="26964-139">Observe como você não foi solicitado a fornecer uma senha ao criar a caixa de correio compartilhada?</span><span class="sxs-lookup"><span data-stu-id="26964-139">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="26964-140">A conta tem uma senha, mas é gerada pelo sistema (desconhecido).</span><span class="sxs-lookup"><span data-stu-id="26964-140">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="26964-141">Você não deve usar a conta para fazer logon na caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="26964-141">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="26964-142">Mas e se um administrador simplesmente redefinir a senha da conta de usuário da caixa de correio compartilhada?</span><span class="sxs-lookup"><span data-stu-id="26964-142">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="26964-143">Ou se um invasor obtiver acesso às credenciais da conta de caixa de correio compartilhada?</span><span class="sxs-lookup"><span data-stu-id="26964-143">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="26964-144">Isso permite que a conta de usuário faça logon na caixa de correio compartilhada e envie emails.</span><span class="sxs-lookup"><span data-stu-id="26964-144">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="26964-145">Para evitar isso, é necessário bloquear a entrada para a conta que está associada à caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="26964-145">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="26964-146">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="26964-146">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="26964-147">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="26964-147">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="26964-148">Na lista de contas de usuários, localize a conta da caixa de correio compartilhada (por exemplo, altere o filtro para **Usuários não licenciados**).</span><span class="sxs-lookup"><span data-stu-id="26964-148">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="26964-149">Selecione o usuário para abrir o painel propriedades e, em seguida, selecione o ícone **Bloquear este usuário** ![Captura de tela do ícone Bloquear este usuário](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="26964-149">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="26964-150">**Observação**: Se a conta já estiver bloqueada, a mensagem **Entrada bloqueada** aparecerá na parte superior e o ícone exibirá **Desbloquear este usuário**.</span><span class="sxs-lookup"><span data-stu-id="26964-150">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="26964-151">No painel **Bloquear este usuário?**, selecione **Bloquear a entrada do usuário** e, em seguida, selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="26964-151">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="26964-152">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="26964-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="26964-153">Na lista de contas de usuários, localize a conta da caixa de correio compartilhada (por exemplo, altere o modo de exibição para **Usuários não licenciados**) e selecione a conta.</span><span class="sxs-lookup"><span data-stu-id="26964-153">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="26964-154">No submenu propriedades, selecione **Bloquear entrada**.</span><span class="sxs-lookup"><span data-stu-id="26964-154">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="26964-155">**Observação:** Se a conta já estiver bloqueada, o botão indicará **Desbloquear entrada**.</span><span class="sxs-lookup"><span data-stu-id="26964-155">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="26964-156">No submenu **Editar o status de entrada**, verifique se a opção Bloquear a entrada do usuário está marcada, selecione **Salvar** e, em seguida, **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="26964-156">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="26964-157">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="26964-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="26964-158">Na lista de contas de usuários, localize a conta da caixa de correio compartilhada (por exemplo, altere o modo de exibição para **Usuários não licenciados**) e selecione a conta.</span><span class="sxs-lookup"><span data-stu-id="26964-158">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="26964-159">No submenu propriedades, selecione **Bloquear entrada**.</span><span class="sxs-lookup"><span data-stu-id="26964-159">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="26964-160">**Observação:** Se a conta já estiver bloqueada, o botão indicará **Desbloquear entrada**.</span><span class="sxs-lookup"><span data-stu-id="26964-160">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="26964-161">No submenu **Editar o status de entrada**, verifique se a opção Bloquear a entrada do usuário está marcada, selecione **Salvar** e, em seguida, **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="26964-161">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="26964-162">Para obter instruções sobre como bloquear a entrada de contas usando o Azure AD PowerShell (incluindo várias contas ao mesmo tempo), confira [Bloquear contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="26964-162">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="26964-163">Adicionar a caixa de correio compartilhada ao Outlook</span><span class="sxs-lookup"><span data-stu-id="26964-163">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="26964-164">Se habilitar o mapeamento automático em sua empresa (por padrão, a maioria das pessoas faz isso), a caixa de correio compartilhada será exibida automaticamente no aplicativo Outlook dos usuários, depois que eles fecharem e reiniciarem o Outlook.</span><span class="sxs-lookup"><span data-stu-id="26964-164">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="26964-165">O mapeamento automático é definido na caixa de correio do usuário, não na caixa de correio compartilhada.  </span><span class="sxs-lookup"><span data-stu-id="26964-165">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="26964-166">Isso significa que se você tentar usar o grupo de segurança para gerenciar quem tem acesso à caixa de correio compartilhada, o mapeamento automático não funcionará.</span><span class="sxs-lookup"><span data-stu-id="26964-166">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="26964-167">Portanto, se quiser habilitar o mapeamento automático, atribua permissões.</span><span class="sxs-lookup"><span data-stu-id="26964-167">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="26964-168">O mapeamento automático está ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="26964-168">Automapping is on by default.</span></span> <span data-ttu-id="26964-169">Para saber como desativá-lo, confira [Remover o mapeamento automático de uma caixa de correio compartilhada](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="26964-169">To learn how to turn it off, see [Remove automapping for a shared mailbox](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="26964-170">Para saber mais sobre caixas de correio compartilhadas no Outlook, confira:</span><span class="sxs-lookup"><span data-stu-id="26964-170">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="26964-171"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Abrir e usar uma caixa de correio no Outlook</a></span><span class="sxs-lookup"><span data-stu-id="26964-171"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="26964-172"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Adicionar uma caixa de correio compartilhada ao Outlook na Web</a></span><span class="sxs-lookup"><span data-stu-id="26964-172"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="26964-173"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Adicionar uma caixa de correio compartilhada ao Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="26964-173"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="26964-174"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Abrir uma pasta compartilhada ou caixa de correio no Outlook para Mac</a></span><span class="sxs-lookup"><span data-stu-id="26964-174"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="26964-175"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Adicionar regras para uma caixa de correio compartilhada</a></span><span class="sxs-lookup"><span data-stu-id="26964-175"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="26964-176">Usar uma caixa de correio compartilhada no dispositivo móvel (telefone ou tablet)</span><span class="sxs-lookup"><span data-stu-id="26964-176">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="26964-177">Você pode acessar uma caixa de correio compartilhada em um dispositivo móvel de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="26964-177">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="26964-178">Adicione a caixa de correio compartilhada no <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">aplicativo Outlook para iOS</a> ou no <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">aplicativo móvel Outlook para Android</a>.</span><span class="sxs-lookup"><span data-stu-id="26964-178">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="26964-179">Para obter instruções, confira <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Adicionar uma caixa de correio compartilhada ao Outlook Mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="26964-179">For instructions, see <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="26964-180">Abra o navegador, entre no Office 365 e vá para o Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="26964-180">Open your browser, sign in to Office 365, and then go to Outlook on the web.</span></span> <span data-ttu-id="26964-181">Em Outlook na Web, você poderá acessar a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="26964-181">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="26964-182">Para obter instruções, confira <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Adicionar uma caixa de correio compartilhada ao Outlook na Web</a>.</span><span class="sxs-lookup"><span data-stu-id="26964-182">For instructions, see <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="26964-183">Usar o calendário compartilhado</span><span class="sxs-lookup"><span data-stu-id="26964-183">Use the shared calendar</span></span>

<span data-ttu-id="26964-184">Ao criar a caixa de correio compartilhada, você cria automaticamente um calendário compartilhado.</span><span class="sxs-lookup"><span data-stu-id="26964-184">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="26964-185">Preferimos o calendário da caixa de correio compartilhada a um calendário do SharePoint para acompanhar os compromissos e onde as pessoas estão.</span><span class="sxs-lookup"><span data-stu-id="26964-185">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="26964-186">Um calendário compartilhado é integrado ao Outlook e é muito mais fácil de usar do que um calendário do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="26964-186">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="26964-187">No aplicativo Outlook, vá para o modo de exibição Calendário e selecione a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="26964-187">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="26964-188">Quando você insere compromissos, todos os membros da caixa de correio compartilhada podem vê-los. </span><span class="sxs-lookup"><span data-stu-id="26964-188">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="26964-189">Qualquer membro da caixa de correio compartilhada pode criar, exibir e gerenciar compromissos no calendário da mesma maneira que como é feito com seus compromissos pessoais.</span><span class="sxs-lookup"><span data-stu-id="26964-189">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="26964-190">Todos os membros da caixa de correio compartilhada podem ver as alterações no calendário compartilhado.</span><span class="sxs-lookup"><span data-stu-id="26964-190">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="26964-191">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="26964-191">Related articles</span></span>

[<span data-ttu-id="26964-192">Sobre as caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="26964-192">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="26964-193">Configurar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="26964-193">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

<span data-ttu-id="26964-194">[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="26964-194">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md)</span></span>

[<span data-ttu-id="26964-195">Remover uma licença de uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="26964-195">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="26964-196">Solucionar problemas com caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="26964-196">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)





