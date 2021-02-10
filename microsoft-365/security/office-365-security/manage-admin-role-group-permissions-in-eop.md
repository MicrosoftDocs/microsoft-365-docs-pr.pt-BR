---
title: Gerenciar grupos de função no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Os administradores podem aprender a atribuir ou remover permissões no Centro de administração do Exchange (EAC) no Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b53023521f477b5e864424ec648ccf7e5b749d0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166982"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="4c50b-103">Gerenciar grupos de funções no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="4c50b-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4c50b-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="4c50b-104">**Applies to**</span></span>
-  [<span data-ttu-id="4c50b-105">Proteção do Exchange Online autônoma</span><span class="sxs-lookup"><span data-stu-id="4c50b-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="4c50b-106">Em organizações autônomas do Proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, você pode usar o Centro de administração do Exchange (EAC) para adicionar usuários a grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="4c50b-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="4c50b-107">A adição de usuários a um grupo de funções concede ao usuário permissões para realizar tarefas administrativas específicas.</span><span class="sxs-lookup"><span data-stu-id="4c50b-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="4c50b-108">Você também pode remover usuários de grupos de função.</span><span class="sxs-lookup"><span data-stu-id="4c50b-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="4c50b-109">Para obter mais informações sobre funções e grupos de funções, consulte [Permissões no EOP autônomo.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="4c50b-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4c50b-110">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="4c50b-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4c50b-111">Para abrir o Centro de administração do Exchange (EAC), confira o Centro de administração [do Exchange no EOP autônomo.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="4c50b-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="4c50b-112">Para abrir o PowerShell do EOP autônomo, consulte [Conectar-se ao PowerShell da Proteção do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="4c50b-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4c50b-113">Para fazer os procedimentos deste artigo, você precisa ter permissões no Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="4c50b-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="4c50b-114">Especificamente, você precisa da **função Gerenciamento de** Função, que é atribuída ao grupo **de** função Gerenciamento da Organização por padrão.</span><span class="sxs-lookup"><span data-stu-id="4c50b-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="4c50b-115">Para obter mais informações, [consulte Permissões no EOP](feature-permissions-in-eop.md) autônomo e use o EAC modificar a lista de [membros em grupos de função.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="4c50b-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="4c50b-116">Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o Centro de administração do Exchange no Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="4c50b-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="4c50b-117">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="4c50b-117">Having problems?</span></span> <span data-ttu-id="4c50b-118">Peça ajuda no fórum [Proteção do Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="4c50b-118">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="4c50b-119">Usar o EAC para gerenciar grupos de funções</span><span class="sxs-lookup"><span data-stu-id="4c50b-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="4c50b-120">Usar o EAC para exibir grupos de função</span><span class="sxs-lookup"><span data-stu-id="4c50b-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="4c50b-121">No EAC, vá para funções **de Administrador** \> **de Permissões.**</span><span class="sxs-lookup"><span data-stu-id="4c50b-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="4c50b-122">Todos os grupos de função em sua organização estão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="4c50b-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="4c50b-123">Selecione um grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="4c50b-123">Select a role group.</span></span> <span data-ttu-id="4c50b-124">O painel Detalhes mostra o **nome**, **descrição**, funções **atribuídas** e **gerenciado pelo** grupo de função.</span><span class="sxs-lookup"><span data-stu-id="4c50b-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="4c50b-125">Você também pode ver essas informações clicando no **ícone** ![ Editar ](../../media/ITPro-EAC-EditIcon.png) Edição.</span><span class="sxs-lookup"><span data-stu-id="4c50b-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="4c50b-126">Usar o EAC para criar grupos de função</span><span class="sxs-lookup"><span data-stu-id="4c50b-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="4c50b-127">Ao criar um novo grupo de funções, você pode definir todas as configurações por conta própria (durante a criação do grupo ou depois).</span><span class="sxs-lookup"><span data-stu-id="4c50b-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="4c50b-128">Ou você pode copiar um grupo de função existente e modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="4c50b-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="4c50b-129">No EAC, vá para funções **de** Administrador de Permissões e, em \> seguida, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4c50b-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="4c50b-130">**Crie manualmente um novo grupo de funções:** clique **no ícone** ![ ](../../media/ITPro-EAC-AddIcon.png) Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4c50b-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="4c50b-131">**Copie um grupo de funções existente:** selecione o grupo de funções que você deseja copiar e clique no ícone **Copiar** ![ ](../../media/ITPro-EAC-CopyIcon.png) Cópia.</span><span class="sxs-lookup"><span data-stu-id="4c50b-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="4c50b-132">Na janela **Novo grupo de** funções exibida, de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="4c50b-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="4c50b-133">**Nome:** insira um nome exclusivo para o grupo de função.</span><span class="sxs-lookup"><span data-stu-id="4c50b-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="4c50b-134">**Descrição:** insira uma descrição opcional para o grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="4c50b-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="4c50b-135">**Funções:** clique **no ícone** Adicionar ou Remover ícone Remover para selecionar ou modificar as funções atribuídas ![ ao grupo de ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) funções.</span><span class="sxs-lookup"><span data-stu-id="4c50b-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="4c50b-136">**Membros:** clique no **ícone Adicionar** adicionar ![ ou ](../../media/ITPro-EAC-AddIcon.png) **remover** ícone para modificar a associação do grupo ![ de ](../../media/ITPro-EAC-RemoveIcon.gif) função.</span><span class="sxs-lookup"><span data-stu-id="4c50b-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="4c50b-137">Quando terminar, clique em **Salvar para** criar o grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="4c50b-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="4c50b-138">Usar o EAC para modificar grupos de função</span><span class="sxs-lookup"><span data-stu-id="4c50b-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="4c50b-139">No EAC, vá para **funções** de Administrador de Permissões, selecione o grupo de funções que você deseja modificar e clique em \>  **Editar** ![ ](../../media/ITPro-EAC-EditIcon.png) ícone.</span><span class="sxs-lookup"><span data-stu-id="4c50b-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="4c50b-140">As mesmas opções estão disponíveis quando você modifica grupos de função como quando você cria grupos de função.</span><span class="sxs-lookup"><span data-stu-id="4c50b-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="4c50b-141">Você pode:</span><span class="sxs-lookup"><span data-stu-id="4c50b-141">You can:</span></span>

- <span data-ttu-id="4c50b-142">Altere o nome e a descrição.</span><span class="sxs-lookup"><span data-stu-id="4c50b-142">Change the name and description.</span></span>

- <span data-ttu-id="4c50b-143">Adicionar e remover funções de gerenciamento (criar ou remover atribuições de função).</span><span class="sxs-lookup"><span data-stu-id="4c50b-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="4c50b-144">Adicionar e remover membros.</span><span class="sxs-lookup"><span data-stu-id="4c50b-144">Add and remove members.</span></span>

<span data-ttu-id="4c50b-145">**Observação:** alguns grupos de função (por exemplo, Gerenciamento da Organização) restringem as funções que você pode remover do grupo.</span><span class="sxs-lookup"><span data-stu-id="4c50b-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="4c50b-146">Usar o EAC para modificar a lista de membros em grupos de função</span><span class="sxs-lookup"><span data-stu-id="4c50b-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="4c50b-147">No EAC, vá  para funções de Administrador de Permissões, selecione o grupo de funções que você deseja modificar e clique em \>  **Editar** ![ ](../../media/ITPro-EAC-EditIcon.png) ícone.</span><span class="sxs-lookup"><span data-stu-id="4c50b-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="4c50b-148">Na página de propriedades do grupo de funções que é aberta, na seção **Membros,** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4c50b-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="4c50b-149">Clique **em Adicionar** Ícone ![ ](../../media/ITPro-EAC-AddIcon.png) Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4c50b-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="4c50b-150">Na página exibida, encontre o usuário que deseja adicionar e clique em **add ->**.</span><span class="sxs-lookup"><span data-stu-id="4c50b-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="4c50b-151">Selecione usuários e clique **em adicionar ->** quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="4c50b-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="4c50b-152">Quando terminar, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="4c50b-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="4c50b-153">Selecione os usuários que você deseja  remover e clique no ícone ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.</span><span class="sxs-lookup"><span data-stu-id="4c50b-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="4c50b-154">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4c50b-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4c50b-155">Os usuários precisam sair e entrar novamente para ver a alteração em seus diretos administrativos após a adição ou remoção de membros do grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="4c50b-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="4c50b-156">Usar o EAC para remover grupos de função</span><span class="sxs-lookup"><span data-stu-id="4c50b-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="4c50b-157">Não é possível remover grupos de função integrados, mas você pode remover grupos de função personalizados que você criou.</span><span class="sxs-lookup"><span data-stu-id="4c50b-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="4c50b-158">No EAC, vá para funções **de Administrador** \> **de Permissões.**</span><span class="sxs-lookup"><span data-stu-id="4c50b-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="4c50b-159">Selecione o grupo de funções que você deseja remover e clique em **Excluir** ![ ](../../media/ITPro-EAC-DeleteIcon.png) ícone.</span><span class="sxs-lookup"><span data-stu-id="4c50b-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="4c50b-160">Clique **em Sim** na janela de confirmação exibida.</span><span class="sxs-lookup"><span data-stu-id="4c50b-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="4c50b-161">Usar o PowerShell para gerenciar grupos de funções</span><span class="sxs-lookup"><span data-stu-id="4c50b-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="4c50b-162">Usar o EOP PowerShell autônomo para exibir grupos de funções</span><span class="sxs-lookup"><span data-stu-id="4c50b-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="4c50b-163">Para exibir um grupo de funções, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4c50b-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="4c50b-164">Este exemplo retorna uma lista resumida de todos os grupos de função.</span><span class="sxs-lookup"><span data-stu-id="4c50b-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="4c50b-165">Este exemplo retorna informações detalhadas para o grupo de função chamado Recipient Administrators.</span><span class="sxs-lookup"><span data-stu-id="4c50b-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="4c50b-166">Este exemplo retorna todos os grupos de função em que a usuária Julia é membro.</span><span class="sxs-lookup"><span data-stu-id="4c50b-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="4c50b-167">Você precisa usar o valor distinguishedName (DN) para Julia, que você pode encontrar executando o comando: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="4c50b-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="4c50b-168">Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="4c50b-168">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="4c50b-169">Usar o EOP PowerShell autônomo para criar grupos de função</span><span class="sxs-lookup"><span data-stu-id="4c50b-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="4c50b-170">Ao criar um novo grupo de função, você pode definir todas as configurações manualmente (durante a criação do grupo ou depois).</span><span class="sxs-lookup"><span data-stu-id="4c50b-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="4c50b-171">Ou você pode copiar um grupo de função existente e modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="4c50b-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="4c50b-172">Para criar manualmente um novo grupo de funções, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4c50b-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="4c50b-173">O _parâmetro Roles_ especifica as funções de gerenciamento a atribuir ao grupo de funções usando a sintaxe a `"Role1","Role1",..."RoleN"` seguir.</span><span class="sxs-lookup"><span data-stu-id="4c50b-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="4c50b-174">Você pode ver as funções disponíveis usando o cmdlet **Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="4c50b-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="4c50b-175">O _parâmetro_ Members especifica os membros do grupo de função usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="4c50b-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="4c50b-176">Você pode especificar usuários, grupos de segurança universal habilitados para email (USGs) ou outros grupos de função (entidades de segurança).</span><span class="sxs-lookup"><span data-stu-id="4c50b-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="4c50b-177">Este exemplo cria um novo grupo de funções chamado "Gerenciamento limitado de destinatários" com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="4c50b-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="4c50b-178">A função Destinatários de Email (Mail Recipients) é atribuída ao grupo de função.</span><span class="sxs-lookup"><span data-stu-id="4c50b-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="4c50b-179">Os usuários Kim e Martin são adicionados como membros.</span><span class="sxs-lookup"><span data-stu-id="4c50b-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="4c50b-180">Para copiar um grupo de funções existente, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4c50b-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="4c50b-181">Armazene o grupo de funções que deseja copiar em uma variável usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4c50b-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="4c50b-182">Crie o novo grupo de funções usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4c50b-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="4c50b-183">O _parâmetro_ Members especifica os membros do grupo de função usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="4c50b-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="4c50b-184">Você pode especificar usuários, grupos de segurança universal habilitados para email (USGs) ou outros grupos de função (entidades de segurança).</span><span class="sxs-lookup"><span data-stu-id="4c50b-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="4c50b-185">Este exemplo copia o grupo de função Gerenciamento da Organização para o novo grupo de funções chamado "Gerenciamento limitado da organização".</span><span class="sxs-lookup"><span data-stu-id="4c50b-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="4c50b-186">Os membros do grupo de funções são Mila, Carter e Carters.</span><span class="sxs-lookup"><span data-stu-id="4c50b-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="4c50b-187">Para informações detalhadas de sintaxes e de parâmetros, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="4c50b-187">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="4c50b-188">Usar o EOP PowerShell autônomo para modificar a lista de membros em grupos de função</span><span class="sxs-lookup"><span data-stu-id="4c50b-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="4c50b-189">Os cmdlets **Add-RoleGroupMember** e **Remove-RoleGroupMember** adicionam ou removem membros individuais, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="4c50b-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="4c50b-190">O cmdlet **Update-RoleGroupMember** pode substituir ou modificar a lista de membros existente.</span><span class="sxs-lookup"><span data-stu-id="4c50b-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="4c50b-191">Os membros de um grupo de função podem ser usuários, grupos de segurança universal habilitados para email (USGs) ou outros grupos de função (entidades de segurança).</span><span class="sxs-lookup"><span data-stu-id="4c50b-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="4c50b-192">Para modificar os membros de um grupo de função, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4c50b-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="4c50b-193">Para _substituir_ a lista de membros existente pelos valores especificados, use a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="4c50b-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="4c50b-194">Para _modificar seletivamente_ a lista de membros existente, use a seguinte sintaxe: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="4c50b-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="4c50b-195">Este exemplo substitui todos os membros atuais do grupo de função Help Desk pelos usuários especificados.</span><span class="sxs-lookup"><span data-stu-id="4c50b-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="4c50b-196">Este exemplo adiciona Daigoro Akai e remove Mila Barrio da lista de membros no grupo de funções Help Desk.</span><span class="sxs-lookup"><span data-stu-id="4c50b-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="4c50b-197">Para informações detalhadas de sintaxes e de parâmetros, consulte [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="4c50b-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="4c50b-198">Usar o EOP PowerShell autônomo para remover grupos de função</span><span class="sxs-lookup"><span data-stu-id="4c50b-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="4c50b-199">Não é possível remover grupos de função integrados, mas você pode remover grupos de função personalizados que você criou.</span><span class="sxs-lookup"><span data-stu-id="4c50b-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="4c50b-200">Para remover um grupo de função personalizado, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4c50b-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="4c50b-201">Este exemplo remove o grupo de funções Training Administrators.</span><span class="sxs-lookup"><span data-stu-id="4c50b-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="4c50b-202">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="4c50b-202">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4c50b-203">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="4c50b-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="4c50b-204">Para verificar se você copiou com êxito um grupo de funções, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4c50b-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="4c50b-205">No EAC, vá para funções **de** Administrador de Permissões e verifique se \> o grupo de funções está listado (ou não listado).</span><span class="sxs-lookup"><span data-stu-id="4c50b-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="4c50b-206">Selecione o grupo de funções e verifique as configurações no painel Detalhes ou clique no ícone Editar  ![ para verificar as ](../../media/ITPro-EAC-EditIcon.png) configurações.</span><span class="sxs-lookup"><span data-stu-id="4c50b-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="4c50b-207">No PowerShell do Exchange Online, substitua pelo nome do grupo de funções e execute o seguinte comando para verificar se o grupo de funções existe (ou não existe) e verificar as \<Role Group Name\> configurações:</span><span class="sxs-lookup"><span data-stu-id="4c50b-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
