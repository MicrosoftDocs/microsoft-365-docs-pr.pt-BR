---
title: Configurar uma caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Depois de criar uma caixa de correio compartilhada, convém definir algumas configurações para seus usuários, como encaminhamento de email e respostas automáticas. Posteriormente, talvez você queira alterar outras configurações, como os membros ou o nome da caixa de correio.
ms.openlocfilehash: 63d3d0a5867875344ff4635071bbbad69e02eadc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629042"
---
# <a name="configure-a-shared-mailbox"></a><span data-ttu-id="a5dc4-104">Configurar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="a5dc4-104">Configure a shared mailbox</span></span>

<span data-ttu-id="a5dc4-105">Depois de [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md), convém definir algumas configurações para os usuários de caixa de correio, como encaminhamento de email e respostas automáticas.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="a5dc4-106">Posteriormente, talvez você queira alterar outras configurações, como o nome da caixa de correio, membros ou permissões de membro.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="a5dc4-107">Alterar o nome ou o alias de email de uma caixa de correio compartilhada ou alterar o endereço de email principal</span><span class="sxs-lookup"><span data-stu-id="a5dc4-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5dc4-108">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="a5dc4-109">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-109">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5dc4-110">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-110">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="a5dc4-111">Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione **Editar** ao lado de **nome, email, aliases de email**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-111">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="a5dc4-112">Insira um novo nome ou adicione outro alias.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-112">Enter a new name, or add another alias.</span></span> <span data-ttu-id="a5dc4-113">Se você deseja alterar o endereço de email principal, sua caixa de correio deve ter mais de um alias de email.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-113">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="a5dc4-114">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-114">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="a5dc4-115">Encaminhar emails enviados para uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="a5dc4-115">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="a5dc4-116">Você não precisa atribuir uma licença à caixa de correio compartilhada para encaminhar emails enviados a ela.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-116">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="a5dc4-117">Você pode encaminhar as mensagens para qualquer endereço de email ou lista de distribuição válida.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-117">You can forward the messages to any valid email address or distribution list.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5dc4-118">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-118">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="a5dc4-119">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-119">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5dc4-120">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="a5dc4-121">Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione **edição**de **encaminhamento** \> de email.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-121">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="a5dc4-122">Defina **a opção**ativar e digite um endereço de email para encaminhar as mensagens.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-122">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="a5dc4-123">Pode ser qualquer endereço de email válido.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-123">It can be any valid email address.</span></span> <span data-ttu-id="a5dc4-124">Para encaminhar para vários endereços, você precisa [criar um grupo de distribuição](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) para os endereços e, em seguida, inserir o nome do grupo nessa caixa.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-124">To forward to multiple addresses, you need to [create a distribution group](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="a5dc4-125">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-125">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="a5dc4-126">Enviar respostas automáticas de uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="a5dc4-126">Send automatic replies from a shared mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5dc4-127">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-127">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="a5dc4-128">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-128">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5dc4-129">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-129">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="a5dc4-130">Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione \> **Editar** **respostas automáticas** .</span><span class="sxs-lookup"><span data-stu-id="a5dc4-130">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="a5dc4-131">Defina a opção Ativar **e escolha**se deseja enviar a resposta para pessoas dentro da sua organização ou fora da organização.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-131">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="a5dc4-132">Digite a resposta que deseja enviar para as pessoas da organização.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-132">Enter the reply you want to send to people inside your organization.</span></span> <span data-ttu-id="a5dc4-133">Não é possível adicionar imagens, apenas texto.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-133">You can't add images, only text.</span></span>

5. <span data-ttu-id="a5dc4-134">Se você deseja *também* enviar uma resposta para pessoas de fora da sua organização, marque a caixa de seleção, quem deseja obter a resposta e digite o texto.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-134">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="a5dc4-135">Não é possível enviar apenas para as pessoas de fora da organização, sem enviar também para as pessoas da organização.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-135">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="a5dc4-136">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-136">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="a5dc4-137">Permitir que todos vejam os Emails enviados (as respostas)</span><span class="sxs-lookup"><span data-stu-id="a5dc4-137">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="a5dc4-p108">Por padrão, as mensagens enviadas da caixa de correio compartilhada não são salvas na sua pasta Itens enviados. Em vez disso, elas são salvas na pasta Itens enviados da pessoa que enviou a mensagem.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="a5dc4-140">Se quiser permitir que todos vejam os emails enviados, no centro de administração, edite as configurações da caixa de correio compartilhada e selecione \> **Editar** **itens enviados** .</span><span class="sxs-lookup"><span data-stu-id="a5dc4-140">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="a5dc4-141">Escolha os aplicativos que uma caixa de correio compartilhada pode usar para acessar o email da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a5dc4-141">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5dc4-142">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="a5dc4-143">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-143">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5dc4-144">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-144">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="a5dc4-145">Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione **Editar** **aplicativos** \> de email.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-145">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="a5dc4-146">Defina ativar/desativar **para todos** os aplicativos que você deseja que os membros possam usar para acessar a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-146">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="a5dc4-147">Defina a **opção** de alternância para qualquer aplicativo que você não deseja que eles usem.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-147">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="a5dc4-148">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-148">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="a5dc4-149">Colocar uma caixa de correio compartilhada em retenção de litígio</span><span class="sxs-lookup"><span data-stu-id="a5dc4-149">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="a5dc4-150">Para saber mais sobre a retenção de litígio, confira [criar uma retenção de litígio](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="a5dc4-150">To learn more about litigation hold, see [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5dc4-151">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-151">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="a5dc4-152">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-152">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5dc4-153">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="a5dc4-154">Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione **Editar**a **retenção** \> de litígio.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-154">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="a5dc4-155">Defina a opção Toggle como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-155">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="a5dc4-156">Opcionalmente, insira uma duração, nota sobre a isenção e uma URL com mais informações.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-156">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="a5dc4-157">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-157">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="a5dc4-158">Adicionar ou remover membros</span><span class="sxs-lookup"><span data-stu-id="a5dc4-158">Add or remove members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5dc4-159">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="a5dc4-160">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-160">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5dc4-161">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-161">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="a5dc4-162">Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione **Membros** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-162">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="a5dc4-163">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="a5dc4-163">Do one of the following:</span></span>
   - <span data-ttu-id="a5dc4-164">Para adicionar membros, selecione **adicionar membros**, Pesquisar ou selecionar um membro a ser adicionado e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-164">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="a5dc4-165">Para remover membros, use a caixa de pesquisa para pesquisar o membro, se necessário, selecione o **X** ao lado do nome do membro e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-165">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="a5dc4-166">Selecione **salvar** novamente.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-166">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="a5dc4-167">Adicionar ou remover permissões de membros</span><span class="sxs-lookup"><span data-stu-id="a5dc4-167">Add or remove permissions of members</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5dc4-168">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-168">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="a5dc4-169">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5dc4-170">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="a5dc4-171">Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione **Membros** \> **Personalizar permissões**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-171">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="a5dc4-172">Selecione **Editar** ao lado da permissão que você deseja alterar para um membro.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-172">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="a5dc4-173">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="a5dc4-173">Do one of the following:</span></span>
   - <span data-ttu-id="a5dc4-174">Para conceder essa permissão a um membro adicional, selecione **adicionar permissões**, Pesquisar ou selecionar um membro a ser adicionado e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-174">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="a5dc4-175">Para remover a permissão de um membro, use a caixa de pesquisa para pesquisar o membro, se necessário, selecione o **X** ao lado do nome do membro e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-175">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="a5dc4-176">Selecione **salvar** novamente.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-176">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="a5dc4-177">Mostrar ou ocultar uma caixa de correio compartilhada na lista de endereços global</span><span class="sxs-lookup"><span data-stu-id="a5dc4-177">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="a5dc4-178">Se você optar por não mostrar a caixa de correio compartilhada na lista de endereços global, a caixa de correio não aparecerá na lista de endereços da sua organização, mas ainda receberá emails enviados para ele.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-178">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a5dc4-179">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-179">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end 

::: moniker range="o365-germany"

1. <span data-ttu-id="a5dc4-180">No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-180">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a5dc4-181">No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, acesse a página **Grupos**>**Caixas de correio compartilhadas**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-181">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** > **Shared mailboxes** page.</span></span> 

::: moniker-end

2. <span data-ttu-id="a5dc4-182">Selecione a caixa de correio compartilhada que você deseja editar e, em seguida, selecione \> **Mostrar na edição da lista de endereços global** . **Edit**</span><span class="sxs-lookup"><span data-stu-id="a5dc4-182">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="a5dc4-183">Define a opção Ativar **ou** **desativar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-183">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="a5dc4-184">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-184">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="a5dc4-185">Ocultar uma caixa de correio compartilhada da lista de endereços impossibilitará que novos membros da caixa de correio compartilhada adicionem a caixa de correio oculta ao seu perfil do Outlook até que a caixa de correio compartilhada seja exibida novamente na lista de endereços.</span><span class="sxs-lookup"><span data-stu-id="a5dc4-185">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="a5dc4-186">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="a5dc4-186">Related articles</span></span>

[<span data-ttu-id="a5dc4-187">Sobre as caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="a5dc4-187">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="a5dc4-188">Criar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="a5dc4-188">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

<span data-ttu-id="a5dc4-189">[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="a5dc4-189">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md)</span></span>

[<span data-ttu-id="a5dc4-190">Remover uma licença de uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="a5dc4-190">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="a5dc4-191">Solucionar problemas com caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="a5dc4-191">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
