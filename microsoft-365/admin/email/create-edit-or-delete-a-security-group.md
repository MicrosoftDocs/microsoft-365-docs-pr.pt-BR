---
title: Criar, editar ou excluir um grupo de segurança no centro de administração do Microsoft 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Saiba como criar, editar ou excluir um grupo de segurança.
ms.openlocfilehash: 26b431a65035f2546bb44af2ecf31bfd327e53b6
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42250669"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b80a9-103">Criar, editar ou excluir um grupo de segurança no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b80a9-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b80a9-104">Na página **grupos** do Office 365, você pode criar grupos de contas de usuário que você pode usar para atribuir as mesmas permissões no SharePoint Online e no CRM Online.</span><span class="sxs-lookup"><span data-stu-id="b80a9-104">On the Office 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="b80a9-105">Por exemplo, um administrador pode criar um grupo de segurança para conceder a um determinado grupo de pessoas acesso a um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b80a9-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="b80a9-106">Somente os administradores globais e de gerenciamento de usuários têm permissões para criar, editar ou excluir grupos de segurança; para obter mais informações sobre funções de administrador, consulte [Atribuir funções de administrador](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b80a9-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="b80a9-107">Você também pode usar [Grupos do Exchange Online e do SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) para enviar email ou atribuir permissões a um grupo de usuários e [Grupos do Exchange Online e do SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) para conceder aos usuários direitos e acesso a sites e conjuntos de sites.</span><span class="sxs-lookup"><span data-stu-id="b80a9-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="b80a9-108">Planejando usar caixas de correio de sites?</span><span class="sxs-lookup"><span data-stu-id="b80a9-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="b80a9-109">Todos os usuários adicionados a um site do SharePoint por meio de um grupo de segurança, em vez de individualmente, podem usar a caixa de correio do site no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b80a9-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="b80a9-110">Esses usuários não poderão acessar a caixa de correio do site no Outlook.</span><span class="sxs-lookup"><span data-stu-id="b80a9-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="b80a9-111">Para obter mais informações, consulte [usar grupos do Office 365 em vez de caixas de correio de site](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span><span class="sxs-lookup"><span data-stu-id="b80a9-111">For more information, see [Use Office 365 Groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="b80a9-112">Gerenciar grupos de segurança no centro de administração</span><span class="sxs-lookup"><span data-stu-id="b80a9-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="b80a9-113">Adicionar um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b80a9-113">Add a security group</span></span>

1. <span data-ttu-id="b80a9-114">No centro de administração, vá para <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">a página grupos</a> de **grupos** \> .</span><span class="sxs-lookup"><span data-stu-id="b80a9-114">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b80a9-115">Na página **grupos** , selecione **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="b80a9-116">Na página **escolher um tipo de grupo** , escolha **segurança**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="b80a9-117">Siga as etapas para concluir a criação do grupo.</span><span class="sxs-lookup"><span data-stu-id="b80a9-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="b80a9-118">Adicionar membros a um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b80a9-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="b80a9-119">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="b80a9-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="b80a9-120">Selecione o nome do grupo de segurança na página **grupos** e, na guia **Membros** , selecione **Exibir todos e gerenciar Membros**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-120">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="b80a9-121">No painel de grupo, selecione **adicionar membros** e escolha a pessoa na lista ou digite o nome da pessoa que você deseja adicionar na caixa de **pesquisa** e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-121">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="b80a9-122">Para remover membros, selecione o X ao lado do nome.</span><span class="sxs-lookup"><span data-stu-id="b80a9-122">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b80a9-123">Selecione o nome do grupo de segurança na página **grupos** e, em seguida, selecione **Editar** ao lado de **Membros**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-123">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="b80a9-124">No painel de grupo, selecione **adicionar membros** e escolha a pessoa na lista ou digite o nome da pessoa que você deseja adicionar na caixa de **pesquisa** e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-124">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="b80a9-125">Para remover membros, selecione o X ao lado do nome.</span><span class="sxs-lookup"><span data-stu-id="b80a9-125">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="b80a9-126">Selecione o nome do grupo de segurança na página **grupos** e, em seguida, selecione **Editar** ao lado de **Membros**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-126">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="b80a9-127">No painel de grupo, selecione **adicionar membros** e escolha a pessoa na lista ou digite o nome da pessoa que você deseja adicionar na caixa de **pesquisa** e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-127">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="b80a9-128">Para remover membros, selecione o X ao lado do nome.</span><span class="sxs-lookup"><span data-stu-id="b80a9-128">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="b80a9-129">Editar um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b80a9-129">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="b80a9-130">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="b80a9-130">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="b80a9-131">No centro de administração, vá para <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">a página grupos</a> de **grupos** \> .</span><span class="sxs-lookup"><span data-stu-id="b80a9-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b80a9-132">Na página **grupos** , selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="b80a9-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b80a9-133">No painel configurações, selecione a guia **geral** ou a guia **Membros** para editar detalhes ou membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="b80a9-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b80a9-134">No centro de administração, vá para <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">a página grupos</a> de **grupos** \> .</span><span class="sxs-lookup"><span data-stu-id="b80a9-134">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b80a9-135">Na página **grupos** , selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="b80a9-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b80a9-136">No painel grupo de segurança, selecione **Editar** ao lado da guia **nome** ou **Membros** para editar detalhes ou membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="b80a9-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="b80a9-137">Após fazer as alterações, selecione **salvar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b80a9-138">No centro de administração, vá para <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">a página grupos</a> de **grupos** \> .</span><span class="sxs-lookup"><span data-stu-id="b80a9-138">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="b80a9-139">Na página **grupos** , selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="b80a9-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b80a9-140">No painel grupo de segurança, selecione **Editar** ao lado da guia **nome** ou **Membros** para editar detalhes ou membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="b80a9-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="b80a9-141">Após fazer as alterações, selecione **salvar** \> **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-141">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="b80a9-142">Excluir um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b80a9-142">Delete a security group</span></span>

1. <span data-ttu-id="b80a9-143">No centro de administração, vá para <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">a página grupos</a> de **grupos** \> .</span><span class="sxs-lookup"><span data-stu-id="b80a9-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="b80a9-144">Na página **grupos** , selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="b80a9-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="b80a9-145">Selecione **excluir grupo** (ícone wasetbin) e, em seguida, confirme, selecionando **excluir**.</span><span class="sxs-lookup"><span data-stu-id="b80a9-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="b80a9-146">Selecione **fechar** depois que o grupo for excluído.</span><span class="sxs-lookup"><span data-stu-id="b80a9-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="b80a9-147">Grupos do Exchange Online e do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b80a9-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="b80a9-148">Se você quiser criar grupos de usuários para que possa enviar emails ao mesmo tempo, é possível fazer isso no centro de administração do Exchange em **grupos**de **destinatários** \> do **Exchange** \> **admin** \> .</span><span class="sxs-lookup"><span data-stu-id="b80a9-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="b80a9-149">Em seguida, \*\*\*\*![selecione novo](../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png)adicionar e selecione o tipo de grupo que você deseja criar:</span><span class="sxs-lookup"><span data-stu-id="b80a9-149">Next, select **New**![Add](../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="b80a9-150">**Grupo de distribuição**: usado para distribuir mensagens para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="b80a9-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="b80a9-151">Também é chamado de *grupo de distribuição habilitado para email*ou, no Office 365, uma *lista de distribuição*.</span><span class="sxs-lookup"><span data-stu-id="b80a9-151">It's also called a  *mail-enabled distribution group*, or, in Office 365, a  *distribution list*.</span></span> <span data-ttu-id="b80a9-152">Para obter mais informações, consulte [Gerenciar grupos de distribuição](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="b80a9-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="b80a9-153">**Grupo de segurança**: pode ser usado para distribuir mensagens para um grupo de usuários ou conceder permissões de acesso a recursos.</span><span class="sxs-lookup"><span data-stu-id="b80a9-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="b80a9-154">Esse grupo também é chamado de *grupo de segurança habilitado para email*.</span><span class="sxs-lookup"><span data-stu-id="b80a9-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="b80a9-155">Para mais informações, consulte [Gerenciar grupos de segurança habilitados para email](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="b80a9-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="b80a9-156">**Grupo dinâmico de distribuição**: um tipo de grupo de distribuição cuja lista de destinatários é recalculada toda vez que você envia uma mensagem com base nos filtros e nas condições definidos.</span><span class="sxs-lookup"><span data-stu-id="b80a9-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="b80a9-157">Para obter mais informações, consulte [Manage Dynamic Distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span><span class="sxs-lookup"><span data-stu-id="b80a9-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="b80a9-p107">Depois que os grupos de distribuição e os grupos de segurança habilitados para email forem criados no centro de administração do Exchange, seus nomes e as respectivas listas de usuários serão exibidos na página **Grupos de segurança** do Office 365. Você poderá excluir esses grupos em ambos os locais, mas só poderá editá-los no centro de administração do Exchange. Os grupos dinâmicos de distribuição não são exibidos na página **Grupos de segurança** do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b80a9-p107">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the Office 365 **Security groups** page. You can delete these groups in both locations, but you can edit them only in the Exchange admin center. Dynamic distribution groups don't show up on the Office 365 **Security groups** page.</span></span> 
  
 <span data-ttu-id="b80a9-161">Quando você cria um conjunto de sites, grupos do SharePoint são criados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b80a9-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="b80a9-162">Os grupos padrão usam os níveis de permissão padrão do SharePoint  algumas vezes chamados de funções do SharePoint  para conceder direitos e acesso aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b80a9-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="b80a9-163">Para obter mais informações, consulte [grupos padrão do SharePoint no SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span><span class="sxs-lookup"><span data-stu-id="b80a9-163">For more information, see [Default SharePoint groups in SharePoint Online](https://support.office.com/article/13bb2b6b-dd8c-447e-b71b-0e4bb9efe1d3.aspx).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="b80a9-164">Como um grupo de segurança é diferente dos grupos de segurança criados no SharePoint?</span><span class="sxs-lookup"><span data-stu-id="b80a9-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="b80a9-165">Os grupos de segurança podem ser usados com o SharePoint, Exchange, MDM, Windows e muito mais.</span><span class="sxs-lookup"><span data-stu-id="b80a9-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="b80a9-166">Um grupo de segurança que você cria no SharePoint é reconhecido apenas por esse conjunto de sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b80a9-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="b80a9-167">Tenho que usar grupos de segurança para que minha organização seja segura?</span><span class="sxs-lookup"><span data-stu-id="b80a9-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="b80a9-168">Não.</span><span class="sxs-lookup"><span data-stu-id="b80a9-168">No.</span></span> <span data-ttu-id="b80a9-169">Essa é apenas uma maneira de gerenciar a segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b80a9-169">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="b80a9-170">Você sempre pode conceder permissões de usuário e acessar sites individualmente.</span><span class="sxs-lookup"><span data-stu-id="b80a9-170">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="b80a9-171">Mas com grupos de segurança, você pode gerenciar facilmente grupos de usuários maiores.</span><span class="sxs-lookup"><span data-stu-id="b80a9-171">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="b80a9-172">Posso enviar emails para um grupo de segurança?</span><span class="sxs-lookup"><span data-stu-id="b80a9-172">Can I send email to a security group?</span></span>

<span data-ttu-id="b80a9-173">Sim.</span><span class="sxs-lookup"><span data-stu-id="b80a9-173">Yes.</span></span> <span data-ttu-id="b80a9-174">Mas se você quiser usar grupos para email e colaboração, recomendamos que você [crie um grupo do Office 365](../create-groups/create-groups.md) .</span><span class="sxs-lookup"><span data-stu-id="b80a9-174">But if you want to use groups for email and collaboration, we recommend that you [create an Office 365 group](../create-groups/create-groups.md) instead.</span></span> 
  