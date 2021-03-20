---
title: Criar, editar ou excluir um grupo de segurança no Centro de administração do Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Aprenda a criar, editar ou excluir um grupo de segurança.
ms.openlocfilehash: d2cc749acaf7b2e23674156f6ad9a200ec7b386d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915813"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="77ccb-103">Criar, editar ou excluir um grupo de segurança no Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="77ccb-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="77ccb-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="77ccb-104">The admin center is changing.</span></span> <span data-ttu-id="77ccb-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="77ccb-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="77ccb-106">Na página Grupos do  Microsoft 365, você pode criar grupos de contas de usuário que você pode usar para atribuir as mesmas permissões no SharePoint Online e no CRM Online.</span><span class="sxs-lookup"><span data-stu-id="77ccb-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="77ccb-107">Por exemplo, um administrador pode criar um grupo de segurança para conceder a um determinado grupo de pessoas acesso a um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="77ccb-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="77ccb-108">Somente os administradores globais e de gerenciamento de usuários têm permissões para criar, editar ou excluir grupos de segurança; para obter mais informações sobre funções de administrador, consulte [Atribuir funções de administrador](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="77ccb-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="77ccb-109">Você também pode usar [Grupos do Exchange Online e do SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) para enviar email ou atribuir permissões a um grupo de usuários e [Grupos do Exchange Online e do SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) para conceder aos usuários direitos e acesso a sites e conjuntos de sites.</span><span class="sxs-lookup"><span data-stu-id="77ccb-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="77ccb-110">Planejando usar caixas de correio de sites?</span><span class="sxs-lookup"><span data-stu-id="77ccb-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="77ccb-111">Todos os usuários adicionados a um site do SharePoint por meio de um grupo de segurança, em vez de individualmente, podem usar a caixa de correio do site no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="77ccb-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="77ccb-112">Esses usuários não poderão acessar a caixa de correio do site no Outlook.</span><span class="sxs-lookup"><span data-stu-id="77ccb-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="77ccb-113">Para obter mais informações, consulte Usar grupos do [Microsoft 365 em vez de Caixas de Correio de Site.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="77ccb-113">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="77ccb-114">Gerenciar grupos de segurança no centro de administração</span><span class="sxs-lookup"><span data-stu-id="77ccb-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="77ccb-115">Adicionar um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="77ccb-115">Add a security group</span></span>

1. <span data-ttu-id="77ccb-116">No Centro de administração do Microsoft 365, vá para a página **Grupos**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a></span><span class="sxs-lookup"><span data-stu-id="77ccb-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="77ccb-117">Na página **Grupos,** selecione **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="77ccb-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="77ccb-118">Na página **Escolher um tipo de** grupo, escolha **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="77ccb-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="77ccb-119">Siga as etapas para concluir a criação do grupo.</span><span class="sxs-lookup"><span data-stu-id="77ccb-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="77ccb-120">Adicionar membros a um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="77ccb-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="77ccb-121">Selecione o nome do grupo de segurança na página **Grupos** e, na guia **Membros,** selecione **Exibir tudo e gerenciar membros**.</span><span class="sxs-lookup"><span data-stu-id="77ccb-121">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="77ccb-122">No painel de grupo, selecione Adicionar membros e escolha a pessoa na lista ou  digite o nome da pessoa que você deseja adicionar na caixa Pesquisa e selecione **Salvar**. </span><span class="sxs-lookup"><span data-stu-id="77ccb-122">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="77ccb-123">Para remover membros, selecione o X ao lado de seu nome.</span><span class="sxs-lookup"><span data-stu-id="77ccb-123">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="77ccb-124">Selecione o nome do grupo de segurança na página **Grupos** e selecione **Editar** ao lado de **Membros**.</span><span class="sxs-lookup"><span data-stu-id="77ccb-124">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="77ccb-125">No painel de grupo, selecione Adicionar membros e escolha a pessoa na lista ou  digite o nome da pessoa que você deseja adicionar na caixa Pesquisa e selecione **Salvar**. </span><span class="sxs-lookup"><span data-stu-id="77ccb-125">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="77ccb-126">Para remover membros, selecione o X ao lado de seu nome.</span><span class="sxs-lookup"><span data-stu-id="77ccb-126">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="77ccb-127">Selecione o nome do grupo de segurança na página **Grupos** e selecione **Editar** ao lado de **Membros**.</span><span class="sxs-lookup"><span data-stu-id="77ccb-127">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="77ccb-128">No painel de grupo, selecione Adicionar membros e escolha a pessoa na lista ou  digite o nome da pessoa que você deseja adicionar na caixa Pesquisa e selecione **Salvar**. </span><span class="sxs-lookup"><span data-stu-id="77ccb-128">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="77ccb-129">Para remover membros, selecione o X ao lado de seu nome.</span><span class="sxs-lookup"><span data-stu-id="77ccb-129">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="77ccb-130">Editar um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="77ccb-130">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="77ccb-131">No centro de administração, vá para a página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a></span><span class="sxs-lookup"><span data-stu-id="77ccb-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="77ccb-132">Na página **Grupos,** selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="77ccb-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="77ccb-133">No painel de configurações, selecione a guia **Geral** ou a guia **Membros** para editar os detalhes do grupo ou os membros.</span><span class="sxs-lookup"><span data-stu-id="77ccb-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="77ccb-134">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Grupos** \> **grupos.**</span><span class="sxs-lookup"><span data-stu-id="77ccb-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="77ccb-135">Na página **Grupos,** selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="77ccb-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="77ccb-136">No painel grupo de segurança, selecione **Editar** ao lado da guia **Nome** ou **Membros** para editar os detalhes do grupo ou membros.</span><span class="sxs-lookup"><span data-stu-id="77ccb-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="77ccb-137">Depois de fazer alterações, selecione **Salvar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="77ccb-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="77ccb-138">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página **Grupos** \> **grupos.**</span><span class="sxs-lookup"><span data-stu-id="77ccb-138">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="77ccb-139">Na página **Grupos,** selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="77ccb-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="77ccb-140">No painel grupo de segurança, selecione **Editar** ao lado da guia **Nome** ou **Membros** para editar os detalhes do grupo ou membros.</span><span class="sxs-lookup"><span data-stu-id="77ccb-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="77ccb-141">Depois de fazer alterações, selecione **Salvar** > **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="77ccb-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="77ccb-142">Excluir um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="77ccb-142">Delete a security group</span></span>

1. <span data-ttu-id="77ccb-143">No centro de administração, vá para a página **Grupos**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a></span><span class="sxs-lookup"><span data-stu-id="77ccb-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="77ccb-144">Na página **Grupos,** selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="77ccb-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="77ccb-145">Selecione **Excluir grupo** (ícone de wasetbin) e confirme selecionando **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="77ccb-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="77ccb-146">Selecione **Fechar** quando o grupo for excluído.</span><span class="sxs-lookup"><span data-stu-id="77ccb-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="77ccb-147">Grupos do Exchange Online e do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="77ccb-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="77ccb-148">Se você quiser criar grupos de usuários para que possa enviar emails a todos eles ao mesmo tempo, você pode fazer isso no Centro de administração do Exchange, indo para **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="77ccb-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="77ccb-149">Em seguida, **selecione Novo** ![ Adicionar e selecione o tipo de grupo que você ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) deseja criar:</span><span class="sxs-lookup"><span data-stu-id="77ccb-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="77ccb-150">**Grupo de distribuição**: usado para distribuir mensagens para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="77ccb-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="77ccb-151">Também é chamado de grupo de distribuição habilitado para *email* ou uma lista *de distribuição.*</span><span class="sxs-lookup"><span data-stu-id="77ccb-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="77ccb-152">Para obter mais informações, consulte [Gerenciar grupos de distribuição](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="77ccb-152">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="77ccb-153">**Grupo de segurança**: pode ser usado para distribuir mensagens para um grupo de usuários ou conceder permissões de acesso a recursos.</span><span class="sxs-lookup"><span data-stu-id="77ccb-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="77ccb-154">Esse grupo também é chamado de grupo de segurança habilitado *para email.*</span><span class="sxs-lookup"><span data-stu-id="77ccb-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="77ccb-155">Para mais informações, consulte [Gerenciar grupos de segurança habilitados para email](/Exchange/recipients/mail-enabled-security-groups).</span><span class="sxs-lookup"><span data-stu-id="77ccb-155">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="77ccb-156">**Grupo dinâmico de distribuição**: um tipo de grupo de distribuição cuja lista de destinatários é recalculada toda vez que você envia uma mensagem com base nos filtros e nas condições definidos.</span><span class="sxs-lookup"><span data-stu-id="77ccb-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="77ccb-157">Para obter mais informações, consulte [Gerenciar grupos dinâmicos de distribuição](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="77ccb-157">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="77ccb-158">Depois de criar grupos de distribuição e grupos de segurança habilitados para email no Centro de administração do Exchange, seus nomes e listas de usuários aparecem na página **Grupos de** segurança.</span><span class="sxs-lookup"><span data-stu-id="77ccb-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="77ccb-159">Você poderá excluir esses grupos em ambos os locais, mas só poderá editá-los no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="77ccb-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="77ccb-160">Grupos dinâmicos de distribuição não aparecem na página **Grupos de** segurança.</span><span class="sxs-lookup"><span data-stu-id="77ccb-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="77ccb-161">Quando você cria um conjunto de sites, grupos do SharePoint são criados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="77ccb-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="77ccb-162">Os grupos padrão usam os níveis de permissão padrão do SharePoint  algumas vezes chamados de funções do SharePoint  para conceder direitos e acesso aos usuários.</span><span class="sxs-lookup"><span data-stu-id="77ccb-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="77ccb-163">Para obter mais informações, consulte [Grupos padrão do SharePoint no SharePoint Online](/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="77ccb-163">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="77ccb-164">Como um grupo de segurança é diferente dos grupos de segurança que eu criar no SharePoint?</span><span class="sxs-lookup"><span data-stu-id="77ccb-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="77ccb-165">Os grupos de segurança podem ser usados com SharePoint, Exchange, MDM, Windows e muito mais.</span><span class="sxs-lookup"><span data-stu-id="77ccb-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="77ccb-166">Um grupo de segurança criado no SharePoint só é reconhecido por esse conjunto de sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="77ccb-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="77ccb-167">Preciso usar grupos de segurança para minha organização ser segura?</span><span class="sxs-lookup"><span data-stu-id="77ccb-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="77ccb-168">Não.</span><span class="sxs-lookup"><span data-stu-id="77ccb-168">No.</span></span> <span data-ttu-id="77ccb-169">Essa é apenas mais uma maneira de gerenciar a segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="77ccb-169">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="77ccb-170">Você sempre pode conceder permissões de usuário e acesso a sites individualmente.</span><span class="sxs-lookup"><span data-stu-id="77ccb-170">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="77ccb-171">Mas com grupos de segurança, você pode gerenciar facilmente grupos maiores de usuários.</span><span class="sxs-lookup"><span data-stu-id="77ccb-171">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="77ccb-172">Posso enviar emails para um grupo de segurança?</span><span class="sxs-lookup"><span data-stu-id="77ccb-172">Can I send email to a security group?</span></span>

<span data-ttu-id="77ccb-173">Sim.</span><span class="sxs-lookup"><span data-stu-id="77ccb-173">Yes.</span></span> <span data-ttu-id="77ccb-174">Mas se você quiser usar grupos para email e colaboração, recomendamos que você crie um [grupo do Microsoft 365.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="77ccb-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
