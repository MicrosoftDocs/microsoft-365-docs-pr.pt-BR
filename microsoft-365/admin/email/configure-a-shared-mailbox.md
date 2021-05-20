---
title: Configurar caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
description: Crie uma caixa de correio compartilhada e configure algumas configurações para seus usuários, como encaminhamento de email e respostas automáticas.
ms.openlocfilehash: ab23353f07a24f06d43172e8087819dd915ab720
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582663"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="51a21-103">Configurar caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="51a21-103">Configure shared mailbox settings</span></span>

<span data-ttu-id="51a21-104">Depois de criar [uma caixa](create-a-shared-mailbox.md)de correio compartilhada, você vai querer configurar algumas configurações para os usuários da caixa de correio, como encaminhamento de email e respostas automáticas.</span><span class="sxs-lookup"><span data-stu-id="51a21-104">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="51a21-105">Mais tarde, talvez você queira alterar outras configurações, como o nome da caixa de correio, membros ou permissões de membro.</span><span class="sxs-lookup"><span data-stu-id="51a21-105">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="51a21-106">Alterar o nome ou o alias de email de uma caixa de correio compartilhada ou alterar o endereço de email principal</span><span class="sxs-lookup"><span data-stu-id="51a21-106">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="51a21-107">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="51a21-107">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="51a21-108">Selecione a caixa de correio compartilhada que você deseja editar e selecione **Editar** ao lado de **Nome, Email, Aliases de Email.**</span><span class="sxs-lookup"><span data-stu-id="51a21-108">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="51a21-109">Insira um novo nome ou adicione outro alias.</span><span class="sxs-lookup"><span data-stu-id="51a21-109">Enter a new name, or add another alias.</span></span> <span data-ttu-id="51a21-110">Se você quiser alterar o endereço de email principal, sua caixa de correio deve ter mais de um alias de email.</span><span class="sxs-lookup"><span data-stu-id="51a21-110">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="51a21-111">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-111">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="51a21-112">Encaminhar emails enviados para uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="51a21-112">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="51a21-113">Não é necessário atribuir uma licença à caixa de correio compartilhada para encaminhar emails enviados a ela.</span><span class="sxs-lookup"><span data-stu-id="51a21-113">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="51a21-114">Você pode encaminhar as mensagens para qualquer endereço de email válido ou lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="51a21-114">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="51a21-115">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="51a21-115">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="51a21-116">Selecione a caixa de correio compartilhada que você deseja editar e selecione **Editar encaminhamento de** \> **email.**</span><span class="sxs-lookup"><span data-stu-id="51a21-116">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="51a21-117">De definir a alternância **como On** e insira um endereço de email para o qual encaminhar as mensagens.</span><span class="sxs-lookup"><span data-stu-id="51a21-117">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="51a21-118">Pode ser qualquer endereço de email válido.</span><span class="sxs-lookup"><span data-stu-id="51a21-118">It can be any valid email address.</span></span> <span data-ttu-id="51a21-119">Para encaminhar para vários endereços, você precisa [criar](/office365/admin/setup/create-distribution-lists) um grupo de distribuição para os endereços e, em seguida, inserir o nome do grupo nesta caixa.</span><span class="sxs-lookup"><span data-stu-id="51a21-119">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="51a21-120">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-120">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="51a21-121">Enviar respostas automáticas de uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="51a21-121">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="51a21-122">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="51a21-122">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="51a21-123">Selecione a caixa de correio compartilhada que você deseja editar e selecione **Respostas automáticas** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-123">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="51a21-124">De definir a alternância como On e escolha se a resposta deve ser enviada para pessoas dentro da sua organização ou fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="51a21-124">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="51a21-p105">Digite a resposta que deseja enviar para as pessoas da organização. Não é possível adicionar imagens, apenas texto.</span><span class="sxs-lookup"><span data-stu-id="51a21-p105">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="51a21-127">Se você quiser também *enviar* uma resposta para pessoas de fora da sua organização, selecione a caixa de seleção, quem você deseja obter a resposta e digite o texto.</span><span class="sxs-lookup"><span data-stu-id="51a21-127">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="51a21-128">Não é possível enviar apenas para as pessoas de fora da organização, sem enviar também para as pessoas da organização.</span><span class="sxs-lookup"><span data-stu-id="51a21-128">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="51a21-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-129">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="51a21-130">Permitir que todos vejam os Emails enviados (as respostas)</span><span class="sxs-lookup"><span data-stu-id="51a21-130">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="51a21-p107">Por padrão, as mensagens enviadas da caixa de correio compartilhada não são salvas na sua pasta Itens enviados. Em vez disso, elas são salvas na pasta Itens enviados da pessoa que enviou a mensagem.</span><span class="sxs-lookup"><span data-stu-id="51a21-p107">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="51a21-133">Se você quiser permitir que todos vejam o email enviado, no centro de administração, edite as configurações de caixa de correio compartilhadas e selecione **Itens enviados** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-133">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="51a21-134">Escolha os aplicativos que uma caixa de correio compartilhada pode usar para acessar email da Microsoft</span><span class="sxs-lookup"><span data-stu-id="51a21-134">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="51a21-135">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="51a21-135">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="51a21-136">Selecione a caixa de correio compartilhada que você deseja editar e selecione **Aplicativos de email** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-136">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="51a21-137">De definir a alternância como **On** para todos os aplicativos que você deseja que os membros sejam capazes de usar para acessar a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="51a21-137">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="51a21-138">De definir a alternância **como Off** para todos os aplicativos que você não deseja que eles usem.</span><span class="sxs-lookup"><span data-stu-id="51a21-138">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="51a21-139">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-139">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="51a21-140">Colocar uma caixa de correio compartilhada em espera de litígio</span><span class="sxs-lookup"><span data-stu-id="51a21-140">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="51a21-141">Para saber mais sobre a ressarção de litígio, consulte [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span><span class="sxs-lookup"><span data-stu-id="51a21-141">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="51a21-142">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="51a21-142">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="51a21-143">Selecione a caixa de correio compartilhada que você deseja editar e selecione **Contencioso de espera** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-143">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="51a21-144">De definir a alternância como **On**.</span><span class="sxs-lookup"><span data-stu-id="51a21-144">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="51a21-145">Opcionalmente, insira uma duração, uma observação s sobre a espera e uma URL com mais informações.</span><span class="sxs-lookup"><span data-stu-id="51a21-145">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="51a21-146">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-146">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="51a21-147">Adicionar ou remover membros</span><span class="sxs-lookup"><span data-stu-id="51a21-147">Add or remove members</span></span>

1. <span data-ttu-id="51a21-148">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="51a21-148">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="51a21-149">Selecione a caixa de correio compartilhada que você deseja editar e selecione **Membros** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-149">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="51a21-150">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="51a21-150">Do one of the following:</span></span>
   - <span data-ttu-id="51a21-151">Para adicionar membros, selecione **Adicionar membros,** procure ou selecione um membro para adicionar e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-151">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="51a21-152">Para remover membros, use a caixa Pesquisar para pesquisar o membro, se necessário, selecione **o X** ao lado do nome do membro e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-152">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="51a21-153">Selecione **Salvar** novamente.</span><span class="sxs-lookup"><span data-stu-id="51a21-153">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="51a21-154">Adicionar ou remover permissões de membros</span><span class="sxs-lookup"><span data-stu-id="51a21-154">Add or remove permissions of members</span></span>

1. <span data-ttu-id="51a21-155">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="51a21-155">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="51a21-156">Selecione a caixa de correio compartilhada que você deseja editar e selecione **Membros** \> **Personalizar permissões**.</span><span class="sxs-lookup"><span data-stu-id="51a21-156">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="51a21-157">Selecione **Editar** ao lado da permissão que você deseja alterar para um membro.</span><span class="sxs-lookup"><span data-stu-id="51a21-157">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="51a21-158">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="51a21-158">Do one of the following:</span></span>
   - <span data-ttu-id="51a21-159">Para dar essa permissão a um membro adicional, selecione **Adicionar** permissões, procure ou selecione um membro a adicionar e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-159">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="51a21-160">Para remover a permissão de um membro, use a caixa Pesquisar para pesquisar o membro, se necessário, selecione **o X** ao lado do nome do membro e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-160">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="51a21-161">Selecione **Salvar** novamente.</span><span class="sxs-lookup"><span data-stu-id="51a21-161">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="51a21-162">Mostrar ou ocultar uma caixa de correio compartilhada na lista de endereços global</span><span class="sxs-lookup"><span data-stu-id="51a21-162">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="51a21-163">Se você optar por não mostrar a caixa de correio compartilhada na lista de endereços global, a caixa de correio não aparecerá na lista de endereços da sua organização, mas ainda receberá emails enviados a ela.</span><span class="sxs-lookup"><span data-stu-id="51a21-163">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="51a21-164">No centro de administração, vá para a página **Grupos** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Caixas de correio compartilhadas</a>.</span><span class="sxs-lookup"><span data-stu-id="51a21-164">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="51a21-165">Selecione a caixa de correio compartilhada que você deseja editar e selecione **Mostrar na lista de endereços global** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-165">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="51a21-166">De definir a alternância **como On**  ou **Off**.</span><span class="sxs-lookup"><span data-stu-id="51a21-166">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="51a21-167">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="51a21-167">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="51a21-168">Ocultar uma caixa de correio compartilhada da lista de endereços inviabilizará que novos membros de caixa de correio compartilhada adicionem a caixa de correio oculta ao perfil de Outlook até que a caixa de correio compartilhada seja novamente mostrada na lista de endereços.</span><span class="sxs-lookup"><span data-stu-id="51a21-168">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="51a21-169">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="51a21-169">Related content</span></span>

<span data-ttu-id="51a21-170">[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="51a21-170">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="51a21-171">[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="51a21-171">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="51a21-172">[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="51a21-172">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="51a21-173">[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="51a21-173">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="51a21-174">[Resolver problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="51a21-174">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>