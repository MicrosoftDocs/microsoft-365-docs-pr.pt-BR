---
title: Criar, editar ou excluir um grupo de segurança no Microsoft 365 de administração
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Aprenda a criar, editar ou excluir um grupo de segurança.
ms.openlocfilehash: 7887a6371287ebef3a91cc1a37f2ed696df1948d
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623996"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="645f5-103">Criar, editar ou excluir um grupo de segurança no Microsoft 365 de administração</span><span class="sxs-lookup"><span data-stu-id="645f5-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="645f5-104">Na página Microsoft 365 **Grupos,** você pode criar grupos de contas de usuário que você pode usar para atribuir as mesmas permissões ao SharePoint Online e CRM Online.</span><span class="sxs-lookup"><span data-stu-id="645f5-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="645f5-105">Por exemplo, um administrador pode criar um grupo de segurança para conceder a um determinado grupo de pessoas acesso a um site do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="645f5-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="645f5-106">Somente os administradores globais e de gerenciamento de usuários têm permissões para criar, editar ou excluir grupos de segurança; para obter mais informações sobre funções de administrador, consulte [Atribuir funções de administrador](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="645f5-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="645f5-107">Você também pode usar [Grupos do Exchange Online e do SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) para enviar email ou atribuir permissões a um grupo de usuários e [Grupos do Exchange Online e do SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) para conceder aos usuários direitos e acesso a sites e conjuntos de sites.</span><span class="sxs-lookup"><span data-stu-id="645f5-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="645f5-108">Planejando usar caixas de correio de sites?</span><span class="sxs-lookup"><span data-stu-id="645f5-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="645f5-109">Todos os usuários adicionados a um site do SharePoint por meio de um grupo de segurança, em vez de individualmente, podem usar a caixa de correio do site no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="645f5-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="645f5-110">Esses usuários não poderão acessar a caixa de correio do site no Outlook.</span><span class="sxs-lookup"><span data-stu-id="645f5-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="645f5-111">Para obter mais informações, [consulte Use Microsoft 365 Grupos em vez de Caixas de Correio de Site](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span><span class="sxs-lookup"><span data-stu-id="645f5-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="645f5-112">Gerenciar grupos de segurança no centro de administração</span><span class="sxs-lookup"><span data-stu-id="645f5-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="645f5-113">Adicionar um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="645f5-113">Add a security group</span></span>

1. <span data-ttu-id="645f5-114">No centro Microsoft 365 de administração, vá para a página **Grupos**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a></span><span class="sxs-lookup"><span data-stu-id="645f5-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="645f5-115">Na página **Grupos,** selecione **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="645f5-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="645f5-116">Na página **Escolher um tipo de** grupo, escolha **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="645f5-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="645f5-117">Siga as etapas para concluir a criação do grupo.</span><span class="sxs-lookup"><span data-stu-id="645f5-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="645f5-118">Adicionar membros a um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="645f5-118">Add members to a security group</span></span>
    
1. <span data-ttu-id="645f5-119">Selecione o nome do grupo de segurança na página **Grupos** e, na guia **Membros,** selecione **Exibir tudo e gerenciar membros**.</span><span class="sxs-lookup"><span data-stu-id="645f5-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="645f5-120">No painel de grupo, selecione Adicionar membros e escolha a pessoa na lista ou  digite o nome da pessoa que você deseja adicionar na caixa Pesquisa e selecione **Salvar**. </span><span class="sxs-lookup"><span data-stu-id="645f5-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="645f5-121">Para remover membros, selecione o X ao lado de seu nome.</span><span class="sxs-lookup"><span data-stu-id="645f5-121">To remove members, select the X next to their name.</span></span> 
  
### <a name="edit-a-security-group"></a><span data-ttu-id="645f5-122">Editar um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="645f5-122">Edit a security group</span></span>

1. <span data-ttu-id="645f5-123">No centro de administração, vá para a página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a></span><span class="sxs-lookup"><span data-stu-id="645f5-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="645f5-124">Na página **Grupos,** selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="645f5-124">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="645f5-125">No painel de configurações, selecione a guia **Geral** ou a guia **Membros** para editar os detalhes do grupo ou os membros.</span><span class="sxs-lookup"><span data-stu-id="645f5-125">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

### <a name="delete-a-security-group"></a><span data-ttu-id="645f5-126">Excluir um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="645f5-126">Delete a security group</span></span>

1. <span data-ttu-id="645f5-127">No centro de administração, vá para a página **Grupos**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a></span><span class="sxs-lookup"><span data-stu-id="645f5-127">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="645f5-128">Na página **Grupos,** selecione o nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="645f5-128">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="645f5-129">Selecione **Excluir grupo** (ícone de wasetbin) e confirme selecionando **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="645f5-129">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="645f5-130">Selecione **Fechar** quando o grupo for excluído.</span><span class="sxs-lookup"><span data-stu-id="645f5-130">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="645f5-131">Grupos do Exchange Online e do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="645f5-131">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="645f5-132">Se você quiser criar grupos de usuários para que possa enviar emails a todos eles ao mesmo tempo, faça isso no centro de administração do Exchange indo para **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="645f5-132">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="645f5-133">Em seguida, **selecione Novo** ![ Adicionar e selecione o tipo de grupo que você ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) deseja criar:</span><span class="sxs-lookup"><span data-stu-id="645f5-133">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="645f5-134">**Grupo de distribuição**: usado para distribuir mensagens para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="645f5-134">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="645f5-135">Também é chamado de grupo de distribuição habilitado para *email* ou uma lista *de distribuição.*</span><span class="sxs-lookup"><span data-stu-id="645f5-135">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="645f5-136">Para obter mais informações, consulte [Gerenciar grupos de distribuição](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="645f5-136">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="645f5-137">**Grupo de segurança**: pode ser usado para distribuir mensagens para um grupo de usuários ou conceder permissões de acesso a recursos.</span><span class="sxs-lookup"><span data-stu-id="645f5-137">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="645f5-138">Esse grupo também é chamado de grupo de segurança habilitado *para email.*</span><span class="sxs-lookup"><span data-stu-id="645f5-138">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="645f5-139">Para mais informações, consulte [Gerenciar grupos de segurança habilitados para email](/Exchange/recipients/mail-enabled-security-groups).</span><span class="sxs-lookup"><span data-stu-id="645f5-139">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="645f5-140">**Grupo dinâmico de distribuição**: um tipo de grupo de distribuição cuja lista de destinatários é recalculada toda vez que você envia uma mensagem com base nos filtros e nas condições definidos.</span><span class="sxs-lookup"><span data-stu-id="645f5-140">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="645f5-141">Para obter mais informações, consulte [Gerenciar grupos dinâmicos de distribuição](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="645f5-141">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="645f5-142">Depois de criar grupos de distribuição e grupos de segurança habilitados para email no centro de administração Exchange, seus nomes e listas de usuários aparecem na página **Grupos de** segurança.</span><span class="sxs-lookup"><span data-stu-id="645f5-142">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="645f5-143">Você poderá excluir esses grupos em ambos os locais, mas só poderá editá-los no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="645f5-143">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="645f5-144">Grupos dinâmicos de distribuição não aparecem na página **Grupos de** segurança.</span><span class="sxs-lookup"><span data-stu-id="645f5-144">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="645f5-145">Quando você cria um conjunto de sites, grupos do SharePoint são criados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="645f5-145">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="645f5-146">Os grupos padrão usam os níveis de permissão padrão do SharePoint  algumas vezes chamados de funções do SharePoint  para conceder direitos e acesso aos usuários.</span><span class="sxs-lookup"><span data-stu-id="645f5-146">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="645f5-147">Para obter mais informações, consulte [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="645f5-147">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="645f5-148">Como um grupo de segurança é diferente dos grupos de segurança que eu SharePoint?</span><span class="sxs-lookup"><span data-stu-id="645f5-148">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="645f5-149">Os grupos de segurança podem ser usados com SharePoint, Exchange, MDM, Windows e muito mais.</span><span class="sxs-lookup"><span data-stu-id="645f5-149">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="645f5-150">Um grupo de segurança criado em SharePoint é reconhecido apenas por esse conjunto SharePoint site.</span><span class="sxs-lookup"><span data-stu-id="645f5-150">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="645f5-151">Preciso usar grupos de segurança para minha organização ser segura?</span><span class="sxs-lookup"><span data-stu-id="645f5-151">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="645f5-152">Não.</span><span class="sxs-lookup"><span data-stu-id="645f5-152">No.</span></span> <span data-ttu-id="645f5-153">Essa é apenas mais uma maneira de gerenciar a segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="645f5-153">This is just one more way you can manage security for your organization.</span></span> <span data-ttu-id="645f5-154">Você sempre pode conceder permissões de usuário e acesso a sites individualmente.</span><span class="sxs-lookup"><span data-stu-id="645f5-154">You can always grant user permissions and access to sites individually.</span></span> <span data-ttu-id="645f5-155">Mas com grupos de segurança, você pode gerenciar facilmente grupos maiores de usuários.</span><span class="sxs-lookup"><span data-stu-id="645f5-155">But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="645f5-156">Posso enviar emails para um grupo de segurança?</span><span class="sxs-lookup"><span data-stu-id="645f5-156">Can I send email to a security group?</span></span>

<span data-ttu-id="645f5-157">Sim.</span><span class="sxs-lookup"><span data-stu-id="645f5-157">Yes.</span></span> <span data-ttu-id="645f5-158">Mas se você quiser usar grupos para email e colaboração, recomendamos que você crie um Microsoft 365 [grupo.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="645f5-158">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 

## <a name="related-content"></a><span data-ttu-id="645f5-159">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="645f5-159">Related content</span></span>

<span data-ttu-id="645f5-160">[Criar um grupo no Microsoft 365 de administração](../create-groups/create-groups.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="645f5-160">[Create a group in the Microsoft 365 admin center](../create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="645f5-161">[Explicando Microsoft 365 grupos para seus usuários](../create-groups/explain-groups-knowledge-worker.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="645f5-161">[Explaining Microsoft 365 Groups to your users](../create-groups/explain-groups-knowledge-worker.md) (article)</span></span>\
<span data-ttu-id="645f5-162">[Gerenciar um grupo no Microsoft 365 de administração](../create-groups/manage-groups.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="645f5-162">[Manage a group in the Microsoft 365 admin center](../create-groups/manage-groups.md) (article)</span></span>