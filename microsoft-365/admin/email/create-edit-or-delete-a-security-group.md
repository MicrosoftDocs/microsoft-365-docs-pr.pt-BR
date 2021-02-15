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
ms.openlocfilehash: df3d8fde0c487663237b3858aa0bf049ba4db045
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114040"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b78af-103">Criar, editar ou excluir um grupo de segurança no Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b78af-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b78af-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="b78af-104">The admin center is changing.</span></span> <span data-ttu-id="b78af-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="b78af-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="b78af-106">Na página grupos do  Microsoft 365, você pode criar grupos de contas de usuário que você pode usar para atribuir as mesmas permissões no SharePoint Online e CRM Online.</span><span class="sxs-lookup"><span data-stu-id="b78af-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="b78af-107">Por exemplo, um administrador pode criar um grupo de segurança para conceder a um determinado grupo de pessoas acesso a um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b78af-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="b78af-108">Somente os administradores globais e de gerenciamento de usuários têm permissões para criar, editar ou excluir grupos de segurança; para obter mais informações sobre funções de administrador, consulte [Atribuir funções de administrador](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b78af-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="b78af-109">Você também pode usar [Grupos do Exchange Online e do SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) para enviar email ou atribuir permissões a um grupo de usuários e [Grupos do Exchange Online e do SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) para conceder aos usuários direitos e acesso a sites e conjuntos de sites.</span><span class="sxs-lookup"><span data-stu-id="b78af-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="b78af-110">Planejando usar caixas de correio de sites?</span><span class="sxs-lookup"><span data-stu-id="b78af-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="b78af-111">Todos os usuários adicionados a um site do SharePoint por meio de um grupo de segurança, em vez de individualmente, podem usar a caixa de correio do site no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b78af-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="b78af-112">Esses usuários não poderão acessar a caixa de correio do site no Outlook.</span><span class="sxs-lookup"><span data-stu-id="b78af-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="b78af-113">Para saber mais, confira [Usar grupos do Microsoft 365 em vez de caixas de correio de site.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="b78af-113">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="b78af-114">Gerenciar grupos de segurança no centro de administração</span><span class="sxs-lookup"><span data-stu-id="b78af-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="b78af-115">Adicionar um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b78af-115">Add a security group</span></span>

1. <span data-ttu-id="b78af-116">No centro de administração do Microsoft 365, vá para a página **Grupos**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">de</a> Grupos.</span><span class="sxs-lookup"><span data-stu-id="b78af-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b78af-117">Na página **Grupos,** selecione **Adicionar um grupo.**</span><span class="sxs-lookup"><span data-stu-id="b78af-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="b78af-118">Na página **Escolher um tipo de** grupo, escolha **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="b78af-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="b78af-119">Siga as etapas para concluir a criação do grupo.</span><span class="sxs-lookup"><span data-stu-id="b78af-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="b78af-120">Adicionar membros a um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b78af-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="b78af-121">Selecione o nome do grupo de segurança  na **página Grupos** e, na guia Membros, selecione Exibir tudo e **gerenciar membros.**</span><span class="sxs-lookup"><span data-stu-id="b78af-121">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="b78af-122">No painel de grupo, selecione Adicionar membros e escolha a pessoa na lista ou  digite o nome da pessoa que você deseja adicionar na caixa de pesquisa e, em seguida, selecione **Salvar**. </span><span class="sxs-lookup"><span data-stu-id="b78af-122">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="b78af-123">Para remover membros, selecione o X ao lado do nome.</span><span class="sxs-lookup"><span data-stu-id="b78af-123">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b78af-124">Selecione o nome do grupo de segurança na **página Grupos** e, em seguida, **selecione Editar** ao lado de **Membros**.</span><span class="sxs-lookup"><span data-stu-id="b78af-124">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="b78af-125">No painel de grupo, selecione Adicionar membros e escolha a pessoa na lista ou  digite o nome da pessoa que você deseja adicionar na caixa de pesquisa e, em seguida, selecione **Salvar**. </span><span class="sxs-lookup"><span data-stu-id="b78af-125">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="b78af-126">Para remover membros, selecione o X ao lado do nome.</span><span class="sxs-lookup"><span data-stu-id="b78af-126">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="b78af-127">Selecione o nome do grupo de segurança na **página Grupos** e, em seguida, **selecione Editar** ao lado de **Membros**.</span><span class="sxs-lookup"><span data-stu-id="b78af-127">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="b78af-128">No painel de grupo, selecione Adicionar membros e escolha a pessoa na lista ou  digite o nome da pessoa que você deseja adicionar na caixa de pesquisa e, em seguida, selecione **Salvar**. </span><span class="sxs-lookup"><span data-stu-id="b78af-128">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="b78af-129">Para remover membros, selecione o X ao lado do nome.</span><span class="sxs-lookup"><span data-stu-id="b78af-129">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="b78af-130">Editar um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b78af-130">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b78af-131">No centro de administração, vá para a página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">de</a> Grupos.</span><span class="sxs-lookup"><span data-stu-id="b78af-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b78af-132">Na página **Grupos,** selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="b78af-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b78af-133">No painel de configurações, selecione a guia **Geral** ou a **guia** Membros para editar os detalhes ou membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="b78af-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b78af-134">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página  \> **Grupos.**</span><span class="sxs-lookup"><span data-stu-id="b78af-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="b78af-135">Na página **Grupos,** selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="b78af-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b78af-136">No painel do grupo de segurança,  selecione  **Editar** ao lado da guia Nome ou Membros para editar os detalhes ou membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="b78af-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="b78af-137">Depois de fazer alterações, selecione **Salvar** \> **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="b78af-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b78af-138">No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página  \> **Grupos.**</span><span class="sxs-lookup"><span data-stu-id="b78af-138">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="b78af-139">Na página **Grupos,** selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="b78af-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b78af-140">No painel do grupo de segurança, selecione  **Editar** ao lado da guia **Nome** ou Membros para editar os detalhes ou membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="b78af-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="b78af-141">Depois de fazer alterações, selecione **Salvar** > **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="b78af-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="b78af-142">Excluir um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b78af-142">Delete a security group</span></span>

1. <span data-ttu-id="b78af-143">No centro de administração, vá para a página **Grupos**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">de</a> Grupos.</span><span class="sxs-lookup"><span data-stu-id="b78af-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="b78af-144">Na página **Grupos,** selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="b78af-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b78af-145">Selecione **Excluir grupo** (ícone wasetbin) e confirme selecionando **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b78af-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="b78af-146">Selecione **Fechar** depois que o grupo for excluído.</span><span class="sxs-lookup"><span data-stu-id="b78af-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="b78af-147">Grupos do Exchange Online e do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b78af-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="b78af-148">Se você quiser criar grupos de usuários para que possa enviar emails para todos eles ao mesmo  tempo, você pode fazer isso no Centro de administração do Exchange, indo para Grupos de Destinatários do Exchange de \>  \>  \> Administração.</span><span class="sxs-lookup"><span data-stu-id="b78af-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="b78af-149">Em seguida, **selecione Novo** ![ Adicionar e selecione o tipo de grupo que você ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) deseja criar:</span><span class="sxs-lookup"><span data-stu-id="b78af-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="b78af-150">**Grupo de distribuição**: usado para distribuir mensagens para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="b78af-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="b78af-151">Também é chamado de grupo de distribuição habilitado *para email* ou uma lista *de distribuição.*</span><span class="sxs-lookup"><span data-stu-id="b78af-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="b78af-152">Para obter mais informações, consulte [Gerenciar grupos de distribuição](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="b78af-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="b78af-153">**Grupo de segurança**: pode ser usado para distribuir mensagens para um grupo de usuários ou conceder permissões de acesso a recursos.</span><span class="sxs-lookup"><span data-stu-id="b78af-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="b78af-154">Esse grupo também é chamado de grupo *de segurança habilitado para email.*</span><span class="sxs-lookup"><span data-stu-id="b78af-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="b78af-155">Para mais informações, consulte [Gerenciar grupos de segurança habilitados para email](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="b78af-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="b78af-156">**Grupo dinâmico de distribuição**: um tipo de grupo de distribuição cuja lista de destinatários é recalculada toda vez que você envia uma mensagem com base nos filtros e nas condições definidos.</span><span class="sxs-lookup"><span data-stu-id="b78af-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="b78af-157">Para obter mais informações, consulte [Gerenciar grupos dinâmicos de distribuição.](https://technet.microsoft.com/library/bb123722.aspx)</span><span class="sxs-lookup"><span data-stu-id="b78af-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="b78af-158">Depois de criar grupos de distribuição e grupos de segurança habilitados para email no Centro de administração do Exchange, seus nomes e listas de usuários aparecem na página **Grupos de** segurança.</span><span class="sxs-lookup"><span data-stu-id="b78af-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="b78af-159">Você poderá excluir esses grupos em ambos os locais, mas só poderá editá-los no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="b78af-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="b78af-160">Os grupos dinâmicos de distribuição não aparecem na página **Grupos de** segurança.</span><span class="sxs-lookup"><span data-stu-id="b78af-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="b78af-161">Quando você cria um conjunto de sites, grupos do SharePoint são criados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b78af-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="b78af-162">Os grupos padrão usam os níveis de permissão padrão do SharePoint  algumas vezes chamados de funções do SharePoint  para conceder direitos e acesso aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b78af-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="b78af-163">Para saber mais, confira [Grupos padrão do SharePoint no SharePoint Online.](https://docs.microsoft.com/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="b78af-163">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="b78af-164">De que forma um grupo de segurança é diferente dos grupos de segurança que eu criar no SharePoint?</span><span class="sxs-lookup"><span data-stu-id="b78af-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="b78af-165">Os grupos de segurança podem ser usados com o SharePoint, Exchange, MDM, Windows e muito mais.</span><span class="sxs-lookup"><span data-stu-id="b78af-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="b78af-166">Um grupo de segurança criado no SharePoint é reconhecido apenas por esse conjunto de sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b78af-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="b78af-167">Preciso usar grupos de segurança para minha organização ser segura?</span><span class="sxs-lookup"><span data-stu-id="b78af-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="b78af-168">Não.</span><span class="sxs-lookup"><span data-stu-id="b78af-168">No.</span></span> <span data-ttu-id="b78af-169">Esta é apenas mais uma maneira de gerenciar a segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b78af-169">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="b78af-170">Você sempre pode conceder permissões de usuário e acesso a sites individualmente.</span><span class="sxs-lookup"><span data-stu-id="b78af-170">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="b78af-171">Porém, com grupos de segurança, você pode gerenciar facilmente grupos maiores de usuários.</span><span class="sxs-lookup"><span data-stu-id="b78af-171">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="b78af-172">Posso enviar emails para um grupo de segurança?</span><span class="sxs-lookup"><span data-stu-id="b78af-172">Can I send email to a security group?</span></span>

<span data-ttu-id="b78af-173">Sim.</span><span class="sxs-lookup"><span data-stu-id="b78af-173">Yes.</span></span> <span data-ttu-id="b78af-174">Mas se você quiser usar grupos para email e colaboração, recomendamos criar um [grupo do Microsoft 365.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="b78af-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
