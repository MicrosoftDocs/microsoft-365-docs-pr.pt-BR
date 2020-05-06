---
title: Gerenciar grupos no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a criar e gerenciar grupos habilitados para email para uma organização do Exchange no Exchange Online Protection (EOP).
ms.openlocfilehash: 37825175e3332e975065a3807c6ed9d5096b1a7f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034397"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="e94ab-103">Gerenciar grupos no EOP</span><span class="sxs-lookup"><span data-stu-id="e94ab-103">Manage groups in EOP</span></span>

 <span data-ttu-id="e94ab-p101">Você pode usar o Proteção do Exchange Online (EOP) para criar grupos habilitados para email para uma organização do Exchange. Você também pode usar o EOP para definir ou atualizar propriedades de grupo que especificam associação, endereços de email e outros aspectos de grupos. Você pode criar grupos de distribuição e grupos de segurança, dependendo das suas necessidades. Esses grupos podem ser criados usando o Centro de administração do Exchange (EAC) ou pelo Windows PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="e94ab-p101">You can use Exchange Online Protection (EOP) to create mail-enabled groups for an Exchange organization. You can also use EOP to define or update group properties that specify membership, email addresses, and other aspects of groups. You can create distribution groups and security groups, depending on your needs. These groups can be created by using the Exchange admin center (EAC) or via remote Windows PowerShell.</span></span>

## <a name="types-of-mail-enabled-groups"></a><span data-ttu-id="e94ab-108">Tipos de grupos habilitados para email</span><span class="sxs-lookup"><span data-stu-id="e94ab-108">Types of mail-enabled groups</span></span>

<span data-ttu-id="e94ab-109">Você pode criar dois tipos de grupos para sua organização do Exchange:</span><span class="sxs-lookup"><span data-stu-id="e94ab-109">You can create two types of groups for your Exchange organization:</span></span>

- <span data-ttu-id="e94ab-110">Os grupos de distribuição são conjuntos de usuários de email, como uma equipe ou outro grupo ad hoc, que precisa receber ou enviar emails sobre uma área de interesse comum.</span><span class="sxs-lookup"><span data-stu-id="e94ab-110">Distribution groups are collections of email users, such as a team or other ad hoc group, who need to receive or send email regarding a common area of interest.</span></span> <span data-ttu-id="e94ab-111">Os grupos de distribuição destinam-se exclusivamente à distribuição de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="e94ab-111">Distribution groups are exclusively for distributing email messages.</span></span> <span data-ttu-id="e94ab-112">No EOP, um grupo de distribuição refere-se a qualquer grupo habilitado para email, esteja ou não em um contexto de segurança.</span><span class="sxs-lookup"><span data-stu-id="e94ab-112">In EOP, a distribution group refers to any mail-enabled group, whether or not it has a security context.</span></span>

- <span data-ttu-id="e94ab-113">Grupos de segurança são conjuntos de usuários de email que precisam de permissões de acesso para funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="e94ab-113">Security groups are collections of email users who need access permissions for Admin roles.</span></span> <span data-ttu-id="e94ab-114">Por exemplo, talvez você queira fornecer permissões de função de administrador a um grupo específico de usuários para que eles possam definir configurações antispam e antimalware.</span><span class="sxs-lookup"><span data-stu-id="e94ab-114">For example, you might want to give specific group of users admin role permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e94ab-p104">Por padrão, todos os novos grupos de segurança habilitados para email exigem que todos os remetentes sejam autenticados. Isso evita que remetentes externos enviem mensagens para grupos de segurança habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="e94ab-p104">By default, all new mail-enabled security groups require that all senders be authenticated. This prevents external senders from sending messages to mail-enabled security groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e94ab-117">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="e94ab-117">Before you begin</span></span>

- <span data-ttu-id="e94ab-p105">Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Entrada "Grupos de Distribuição e Grupos de Segurança" no tópico [Permissões de recurso no EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="e94ab-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Distribution Groups and Security Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="e94ab-120">Para abrir o centro de administração do Exchange, confira [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="e94ab-120">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="e94ab-121">Lembre-se de que durante a criação e o gerenciamento de grupos usando os cmdlets do PowerShell do Exchange Online Protection, você pode encontrar limitação.</span><span class="sxs-lookup"><span data-stu-id="e94ab-121">Be aware that when creating and managing groups by using Exchange Online Protection PowerShell cmdlets, you may encounter throttling.</span></span>

- <span data-ttu-id="e94ab-122">Os procedimentos do PowerShell neste tópico usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos fiquem visíveis.</span><span class="sxs-lookup"><span data-stu-id="e94ab-122">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="e94ab-123">Para saber como usar o Windows PowerShell para se conectar à Proteção do Exchange Online, confira [Conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e94ab-123">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e94ab-124">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="e94ab-124">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="e94ab-125">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="e94ab-125">Having problems?</span></span> <span data-ttu-id="e94ab-126">Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="e94ab-126">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="create-a-group-in-the-eac"></a><span data-ttu-id="e94ab-127">Criar um grupo no EAC</span><span class="sxs-lookup"><span data-stu-id="e94ab-127">Create a group in the EAC</span></span>

1. <span data-ttu-id="e94ab-128">No Eat, vá para **grupos**de **destinatários** \> .</span><span class="sxs-lookup"><span data-stu-id="e94ab-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="e94ab-129">Clique em **novo** ![ícone](../../media/ITPro-EAC-AddIcon.gif)de adição e, em seguida, clique em **grupo de distribuição** ou grupo de **segurança**, dependendo de suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="e94ab-129">Click **New** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif), and then click **Distribution group** or **Security group**, depending on your needs.</span></span>

3. <span data-ttu-id="e94ab-130">Na página **novo grupo de distribuição** ou **novo grupo de segurança** , defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e94ab-130">On the **New distribution group** or **New security group** page, configure the following settings:</span></span>

   - <span data-ttu-id="e94ab-131">**Nome para exibição**: digite um nome de exibição exclusivo para sua organização e significativo para os usuários do EOP.</span><span class="sxs-lookup"><span data-stu-id="e94ab-131">**Display name**: Type a display name that's unique to your organization and meaningful to EOP users.</span></span> <span data-ttu-id="e94ab-132">O nome para exibição é necessário.</span><span class="sxs-lookup"><span data-stu-id="e94ab-132">The display name is required.</span></span>

   - <span data-ttu-id="e94ab-133">**Alias**: digite um alias de grupo de até 64 caracteres que seja exclusivo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e94ab-133">**Alias**: Type a group alias of up to 64 characters that's unique to your organization.</span></span> <span data-ttu-id="e94ab-134">Os usuários do EOP digitam o alias na linha Para: de uma mensagem de email; então ele é convertido para o nome para exibição do grupo.</span><span class="sxs-lookup"><span data-stu-id="e94ab-134">EOP users type the alias in the To: line of email messages and the alias resolves to the group's display name.</span></span> <span data-ttu-id="e94ab-135">Se você alterar o alias, o endereço SMTP principal do grupo também será alterado e conterá o novo alias.</span><span class="sxs-lookup"><span data-stu-id="e94ab-135">If you change the alias, the primary SMTP address for the group also changes and will contain the new alias.</span></span> <span data-ttu-id="e94ab-136">O alias é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="e94ab-136">The alias is required.</span></span>

   - <span data-ttu-id="e94ab-137">**Descrição**: digite uma descrição do grupo para que as pessoas saibam a finalidade do grupo.</span><span class="sxs-lookup"><span data-stu-id="e94ab-137">**Description**: Type a description of the group so that people will know the purpose of the group.</span></span>

   - <span data-ttu-id="e94ab-138">**Proprietários**: por padrão, a pessoa que cria o grupo é o proprietário.</span><span class="sxs-lookup"><span data-stu-id="e94ab-138">**Owners**: By default, the person who creates the group is the owner.</span></span> <span data-ttu-id="e94ab-139">Você pode adicionar um proprietário escolhendo **Adicionar** ![ícone](../../media/ITPro-EAC-AddIcon.gif)de adição.</span><span class="sxs-lookup"><span data-stu-id="e94ab-139">You can add an owner by choosing **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="e94ab-140">Todos os grupos devem ter no mínimo um proprietário.</span><span class="sxs-lookup"><span data-stu-id="e94ab-140">All groups must have at least one owner.</span></span>

     > [!NOTE]
     > <span data-ttu-id="e94ab-141">Os proprietários do grupo não precisam ser membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="e94ab-141">Owners don't have to be members of the group.</span></span>

   - <span data-ttu-id="e94ab-142">**Membros**: Use esta seção para adicionar membros do grupo e especificar se a aprovação é necessária para que as pessoas ingressem ou saiam do grupo.</span><span class="sxs-lookup"><span data-stu-id="e94ab-142">**Members**: Use this section to add group members and to specify whether approval is required for people to join or leave the group.</span></span> <span data-ttu-id="e94ab-143">Para adicionar membros ao grupo, clique em **Adicionar** ![ícone](../../media/ITPro-EAC-AddIcon.gif)de adição.</span><span class="sxs-lookup"><span data-stu-id="e94ab-143">To add members to the group, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.gif).</span></span>

4. <span data-ttu-id="e94ab-144">Clique em **OK** para retornar à página original.</span><span class="sxs-lookup"><span data-stu-id="e94ab-144">Click **OK** to return to the original page.</span></span>

5. <span data-ttu-id="e94ab-p111">Quando você tiver terminado, clique em **Salvar** para criar o grupo. O novo grupo deve aparecer na lista de grupos.</span><span class="sxs-lookup"><span data-stu-id="e94ab-p111">When you've finished, click **Save** to create the group. The new group should appear in the list of groups.</span></span>

## <a name="edit-or-remove-a-group-in-the-eac"></a><span data-ttu-id="e94ab-147">Editar ou remover um grupo no EAC</span><span class="sxs-lookup"><span data-stu-id="e94ab-147">Edit or remove a group in the EAC</span></span>

1. <span data-ttu-id="e94ab-148">Na EAC, navegue até **Destinatários** \> **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="e94ab-148">In the EAC, navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="e94ab-149">Execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e94ab-149">Do one of the following steps:</span></span>

   - <span data-ttu-id="e94ab-150">Para editar um grupo: na lista de grupos, clique no grupo que você deseja exibir ou alterar e, em seguida, clique em **Editar** ![ícone](../../media/ITPro-EAC-EditIcon.gif)de edição.</span><span class="sxs-lookup"><span data-stu-id="e94ab-150">To edit a group: In the list of groups, click the group that you want to view or change, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.gif).</span></span> <span data-ttu-id="e94ab-151">Você pode atualizar as configurações gerais, adicionar ou remover proprietários de grupo e adicionar ou remover membros do grupo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e94ab-151">You can update general settings, add or remove group owners, and add or remove group members as needed.</span></span>

   - <span data-ttu-id="e94ab-152">Para remover um grupo: selecione o grupo e clique em **remover** ![ícone](../../media/ITPro-EAC-RemoveIcon.gif)de remoção.</span><span class="sxs-lookup"><span data-stu-id="e94ab-152">To remove a group: Select the group and click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="e94ab-153">Ao terminar de fazer as alterações, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e94ab-153">When you're finished making your changes, click **Save**.</span></span>

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="e94ab-154">Criar, editar ou remover um grupo usando o Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="e94ab-154">Create, edit, or remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="e94ab-155">Esta seção fornece informações sobre como criar grupos e alterar suas propriedades no PowerShell do Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="e94ab-155">This section provides information about creating groups and changing their properties in Exchange Online Protection PowerShell.</span></span> <span data-ttu-id="e94ab-156">Também mostra como remover um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="e94ab-156">It also shows how to remove an existing group.</span></span>

### <a name="create-a-group-using-remote-windows-powershell"></a><span data-ttu-id="e94ab-157">Criar um grupo usando o Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="e94ab-157">Create a group using remote Windows PowerShell</span></span>

<span data-ttu-id="e94ab-p114">Este exemplo usa o cmdlet [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) para criar um grupo de distribuição com um alias itadmin e o nome IT Administrators (Administradores de TI). Também adiciona usuários como membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="e94ab-p114">This example uses the [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) cmdlet to create a distribution group with an alias of itadmin and the name IT Administrators. It also adds users as members of the group.</span></span>

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

<span data-ttu-id="e94ab-160">**Observação**: para criar um grupo de segurança em vez de um grupo de distribuição, `Security` use o valor para o parâmetro *Type* .</span><span class="sxs-lookup"><span data-stu-id="e94ab-160">**Note**: To create a security group instead of a distribution group, use the value `Security` for the *Type* parameter.</span></span>

<span data-ttu-id="e94ab-161">Para verificar se você criou o grupo Administradores de ti com êxito, execute o seguinte comando para exibir informações sobre o novo grupo:</span><span class="sxs-lookup"><span data-stu-id="e94ab-161">To verify that you've successfully created the IT Administrators group, run the following command to display information about the new group:</span></span>

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

<span data-ttu-id="e94ab-162">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span><span class="sxs-lookup"><span data-stu-id="e94ab-162">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).</span></span>

<span data-ttu-id="e94ab-163">Para obter uma lista de membros no grupo, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e94ab-163">To get a list of members in the group, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

<span data-ttu-id="e94ab-164">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="e94ab-164">For detailed syntax and parameter information, see [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

<span data-ttu-id="e94ab-165">Para obter uma lista completa de todos os seus grupos, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e94ab-165">To get a full list of all your groups, run the following command:</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a><span data-ttu-id="e94ab-166">Alterar as propriedades de um grupo usando o Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="e94ab-166">Change the properties of a group using remote Windows PowerShell</span></span>

<span data-ttu-id="e94ab-167">Uma vantagem de usar o PowerShell em vez da Eat é a capacidade de alterar as propriedades de vários grupos.</span><span class="sxs-lookup"><span data-stu-id="e94ab-167">An advantage of using PowerShell instead of the EAC is the ability to change properties for multiple groups.</span></span>

<span data-ttu-id="e94ab-168">Aqui estão alguns exemplos de como usar o PowerShell do Exchange Online Protection para alterar as propriedades do grupo.</span><span class="sxs-lookup"><span data-stu-id="e94ab-168">Here are some examples of using Exchange Online Protection PowerShell to change group properties.</span></span>

<span data-ttu-id="e94ab-169">Este exemplo usa as alterações do endereço SMTP principal (também chamado de endereço de resposta) do grupo de Seattle Employees para sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e94ab-169">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="e94ab-170">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="e94ab-170">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).</span></span>

<span data-ttu-id="e94ab-171">Para verificar se você alterou com êxito as propriedades do grupo, execute o seguinte comando para verificar o novo valor:</span><span class="sxs-lookup"><span data-stu-id="e94ab-171">To verify that you've successfully changed the properties for the group, run the following command to verify the new value:</span></span>

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

<span data-ttu-id="e94ab-172">Este exemplo atualiza todos os membros do grupo de Seattle Employees.</span><span class="sxs-lookup"><span data-stu-id="e94ab-172">This example updates all the members of the Seattle Employees group.</span></span> <span data-ttu-id="e94ab-173">Use uma vírgula para separar todos os membros.</span><span class="sxs-lookup"><span data-stu-id="e94ab-173">Use a comma to separate all members.</span></span>

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

<span data-ttu-id="e94ab-174">Para informações detalhadas de sintaxes e de parâmetros, consulte [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="e94ab-174">For detailed syntax and parameter information, see [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

<span data-ttu-id="e94ab-175">Para obter a lista de todos os membros no grupo de Seattle Employees, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e94ab-175">To get the list of all the members in the group Seattle Employees, run the following command:</span></span>

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="e94ab-176">Remover um grupo usando o Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="e94ab-176">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="e94ab-177">Este exemplo usa remove o grupo de distribuição chamado administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="e94ab-177">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="e94ab-178">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="e94ab-178">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

<span data-ttu-id="e94ab-179">Para verificar se o grupo foi removido, execute o seguinte comando e confirme se o grupo (neste caso, "administradores de ti") foi excluído.</span><span class="sxs-lookup"><span data-stu-id="e94ab-179">To verify that the group was removed, run the following command, and confirm that the group (in this case "It Administrators") was deleted.</span></span>

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
