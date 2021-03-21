---
title: Gerenciar grupos de funções no EOP
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
description: Os administradores podem aprender a atribuir ou remover permissões no Centro de administração do Exchange (EAC) na Proteção do Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926875"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="20ab7-103">Gerenciar grupos de funções no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="20ab7-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="20ab7-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="20ab7-104">**Applies to**</span></span>
-  [<span data-ttu-id="20ab7-105">Proteção autônoma do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20ab7-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="20ab7-106">Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode usar o Centro de administração do Exchange (EAC) para adicionar usuários a grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="20ab7-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="20ab7-107">Adicionar um usuário a um grupo de funções dá ao usuário permissões para realizar tarefas de administrador específicas.</span><span class="sxs-lookup"><span data-stu-id="20ab7-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="20ab7-108">Você também pode remover usuários de grupos de função.</span><span class="sxs-lookup"><span data-stu-id="20ab7-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="20ab7-109">Para obter mais informações sobre funções e grupos de funções, consulte [Permissões no EOP](feature-permissions-in-eop.md)autônomo .</span><span class="sxs-lookup"><span data-stu-id="20ab7-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20ab7-110">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="20ab7-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20ab7-111">Para abrir o Centro de administração do Exchange (EAC), consulte Centro de administração [do Exchange no EOP](exchange-admin-center-in-exchange-online-protection-eop.md)autônomo .</span><span class="sxs-lookup"><span data-stu-id="20ab7-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="20ab7-112">Para abrir o EOP PowerShell autônomo, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="20ab7-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="20ab7-113">Você precisa ter permissões atribuídas no Exchange Online Protection antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="20ab7-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="20ab7-114">Especificamente, você precisa da **função Gerenciamento de** Função, que é atribuída ao grupo de função **Gerenciamento** da Organização por padrão.</span><span class="sxs-lookup"><span data-stu-id="20ab7-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="20ab7-115">Para obter mais informações, consulte [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="20ab7-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="20ab7-116">Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o centro de administração do Exchange no Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="20ab7-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="20ab7-117">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="20ab7-117">Having problems?</span></span> <span data-ttu-id="20ab7-118">Peça ajuda no fórum [Proteção do Exchange Online](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="20ab7-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="20ab7-119">Usar o EAC para gerenciar grupos de funções</span><span class="sxs-lookup"><span data-stu-id="20ab7-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="20ab7-120">Usar o EAC para exibir grupos de funções</span><span class="sxs-lookup"><span data-stu-id="20ab7-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="20ab7-121">No EAC, vá para **Permissões Funções de** \> **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="20ab7-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="20ab7-122">Todos os grupos de função em sua organização estão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="20ab7-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="20ab7-123">Selecione um grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="20ab7-123">Select a role group.</span></span> <span data-ttu-id="20ab7-124">O painel Detalhes mostra o **Nome,** **Descrição,** **Funções Atribuídas** e **Gerenciado pelo** grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="20ab7-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="20ab7-125">Você também pode ver essas informações clicando em **Editar** ![ ícone editar ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="20ab7-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="20ab7-126">Usar o EAC para criar grupos de função</span><span class="sxs-lookup"><span data-stu-id="20ab7-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="20ab7-127">Ao criar um novo grupo de funções, você pode configurar todas as configurações por conta própria (durante a criação do grupo ou depois).</span><span class="sxs-lookup"><span data-stu-id="20ab7-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="20ab7-128">Ou você pode copiar um grupo de funções existente e modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="20ab7-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="20ab7-129">No EAC, vá para **Funções** de Administrador de Permissões e, em \> seguida, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="20ab7-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="20ab7-130">**Criar manualmente um novo grupo de função:** clique **em Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="20ab7-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="20ab7-131">**Copie um grupo de funções existente:** selecione o grupo de funções que você deseja copiar e clique em **Copiar** ![ ícone de ](../../media/ITPro-EAC-CopyIcon.png) cópia.</span><span class="sxs-lookup"><span data-stu-id="20ab7-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="20ab7-132">Na janela **Novo grupo de** função que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="20ab7-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="20ab7-133">**Nome**: Insira um nome exclusivo para o grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="20ab7-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="20ab7-134">**Descrição**: insira uma descrição opcional para o grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="20ab7-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="20ab7-135">**Funções**: clique **em Adicionar** ícone ou Remover Ícone remover para selecionar ou modificar as funções ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) atribuídas ao grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="20ab7-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="20ab7-136">**Membros**: clique **em Adicionar** ícone adicionar ![ ou ](../../media/ITPro-EAC-AddIcon.png) **remover** ícone remover para modificar a associação do grupo ![ de ](../../media/ITPro-EAC-RemoveIcon.gif) funções.</span><span class="sxs-lookup"><span data-stu-id="20ab7-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="20ab7-137">Quando terminar, clique em **Salvar** para criar o grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="20ab7-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="20ab7-138">Usar o EAC para modificar grupos de função</span><span class="sxs-lookup"><span data-stu-id="20ab7-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="20ab7-139">No EAC, vá para **Permissões** Funções de Administrador , selecione o grupo de função que você deseja modificar e clique \> em **Editar** Ícone ![ editar ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="20ab7-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="20ab7-140">As mesmas opções estão disponíveis quando você modifica grupos de função como quando você cria grupos de função.</span><span class="sxs-lookup"><span data-stu-id="20ab7-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="20ab7-141">Você pode:</span><span class="sxs-lookup"><span data-stu-id="20ab7-141">You can:</span></span>

- <span data-ttu-id="20ab7-142">Altere o nome e a descrição.</span><span class="sxs-lookup"><span data-stu-id="20ab7-142">Change the name and description.</span></span>

- <span data-ttu-id="20ab7-143">Adicionar e remover funções de gerenciamento (criar ou remover atribuições de função).</span><span class="sxs-lookup"><span data-stu-id="20ab7-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="20ab7-144">Adicionar e remover membros.</span><span class="sxs-lookup"><span data-stu-id="20ab7-144">Add and remove members.</span></span>

<span data-ttu-id="20ab7-145">**Observação**: Alguns grupos de função (por exemplo, Gerenciamento da Organização) restringem as funções que você pode remover do grupo.</span><span class="sxs-lookup"><span data-stu-id="20ab7-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="20ab7-146">Usar o EAC modificar a lista de membros em grupos de função</span><span class="sxs-lookup"><span data-stu-id="20ab7-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="20ab7-147">No EAC, vá para **Permissões** Funções de Administrador , selecione o grupo de funções que você deseja modificar e clique \> em **Editar** Ícone ![ editar ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="20ab7-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="20ab7-148">Na página propriedades do grupo de função que é aberta, na seção **Membros,** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="20ab7-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="20ab7-149">Clique **em Adicionar** Ícone ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="20ab7-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="20ab7-150">Na página exibida, encontre o usuário que deseja adicionar e clique **em adicionar ->**.</span><span class="sxs-lookup"><span data-stu-id="20ab7-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="20ab7-151">Selecione usuários e clique **em adicionar ->** quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="20ab7-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="20ab7-152">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="20ab7-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="20ab7-153">Selecione os usuários que você deseja remover e clique em **Remover** ![ ícone remover ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="20ab7-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="20ab7-154">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="20ab7-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="20ab7-155">Os usuários precisam sair e entrar novamente para ver a alteração em seus diretos administrativos após a adição ou remoção de membros do grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="20ab7-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="20ab7-156">Usar o EAC para remover grupos de função</span><span class="sxs-lookup"><span data-stu-id="20ab7-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="20ab7-157">Não é possível remover grupos de função integrados, mas é possível remover grupos de função personalizados criados.</span><span class="sxs-lookup"><span data-stu-id="20ab7-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="20ab7-158">No EAC, vá para **Permissões Funções de** \> **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="20ab7-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="20ab7-159">Selecione o grupo de função que você deseja remover e clique em **Excluir** ![ ícone ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="20ab7-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="20ab7-160">Clique **em Sim** na janela de confirmação exibida.</span><span class="sxs-lookup"><span data-stu-id="20ab7-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="20ab7-161">Usar o PowerShell para gerenciar grupos de função</span><span class="sxs-lookup"><span data-stu-id="20ab7-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="20ab7-162">Usar o EOP PowerShell autônomo para exibir grupos de funções</span><span class="sxs-lookup"><span data-stu-id="20ab7-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="20ab7-163">Para exibir um grupo de funções, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="20ab7-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="20ab7-164">Este exemplo retorna uma lista resumida de todos os grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="20ab7-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="20ab7-165">Este exemplo retorna informações detalhadas para o grupo de função chamado Administradores de Destinatários.</span><span class="sxs-lookup"><span data-stu-id="20ab7-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="20ab7-166">Este exemplo retorna todos os grupos de função onde a usuária Julia é membro.</span><span class="sxs-lookup"><span data-stu-id="20ab7-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="20ab7-167">Você precisa usar o valor DistinguishedName (DN) para a Julia, que você pode encontrar executando o comando: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="20ab7-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="20ab7-168">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="20ab7-168">For detailed syntax and parameter information, see [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="20ab7-169">Usar o EOP PowerShell autônomo para criar grupos de função</span><span class="sxs-lookup"><span data-stu-id="20ab7-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="20ab7-170">Ao criar um novo grupo de funções, você pode configurar todas as configurações manualmente (durante a criação do grupo ou depois).</span><span class="sxs-lookup"><span data-stu-id="20ab7-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="20ab7-171">Ou você pode copiar um grupo de funções existente e modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="20ab7-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="20ab7-172">Para criar manualmente um novo grupo de funções, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="20ab7-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="20ab7-173">O _parâmetro Roles_ especifica as funções de gerenciamento a atribuir ao grupo de funções usando a sintaxe a seguir `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="20ab7-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="20ab7-174">Você pode ver as funções disponíveis usando o cmdlet **Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="20ab7-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="20ab7-175">O _parâmetro Members_ especifica os membros do grupo de funções usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="20ab7-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="20ab7-176">Você pode especificar usuários, USGs (grupos de segurança universal) habilitados para email ou outros grupos de função (entidades de segurança).</span><span class="sxs-lookup"><span data-stu-id="20ab7-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="20ab7-177">Este exemplo cria um novo grupo de funções chamado "Gerenciamento limitado de destinatários" com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="20ab7-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="20ab7-178">A função Destinatários de Email (Mail Recipients) é atribuída ao grupo de função.</span><span class="sxs-lookup"><span data-stu-id="20ab7-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="20ab7-179">Os usuários Kim e Martin são adicionados como membros.</span><span class="sxs-lookup"><span data-stu-id="20ab7-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="20ab7-180">Para copiar um grupo de funções existente, faça as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="20ab7-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="20ab7-181">Armazene o grupo de funções que deseja copiar em uma variável usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="20ab7-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="20ab7-182">Crie o novo grupo de funções usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="20ab7-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="20ab7-183">O _parâmetro Members_ especifica os membros do grupo de funções usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="20ab7-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="20ab7-184">Você pode especificar usuários, USGs (grupos de segurança universal) habilitados para email ou outros grupos de função (entidades de segurança).</span><span class="sxs-lookup"><span data-stu-id="20ab7-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="20ab7-185">Este exemplo copia o grupo de função Gerenciamento da Organização para o novo grupo de funções chamado "Gerenciamento limitado da organização".</span><span class="sxs-lookup"><span data-stu-id="20ab7-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="20ab7-186">Os membros do grupo de função são Isabel, Carter e Lukas.</span><span class="sxs-lookup"><span data-stu-id="20ab7-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="20ab7-187">Para obter informações detalhadas sobre sintaxes e parâmetros, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="20ab7-187">For detailed syntax and parameter information, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="20ab7-188">Usar o EOP PowerShell autônomo modificar a lista de membros em grupos de função</span><span class="sxs-lookup"><span data-stu-id="20ab7-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="20ab7-189">Os cmdlets **Add-RoleGroupMember** e **Remove-RoleGroupMember** adicionam ou removem membros individuais um por vez.</span><span class="sxs-lookup"><span data-stu-id="20ab7-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="20ab7-190">O cmdlet **Update-RoleGroupMember** pode substituir ou modificar a lista de membros existente.</span><span class="sxs-lookup"><span data-stu-id="20ab7-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="20ab7-191">Os membros de um grupo de funções podem ser usuários, USGs (grupos de segurança universal habilitados para email) ou outros grupos de função (entidades de segurança).</span><span class="sxs-lookup"><span data-stu-id="20ab7-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="20ab7-192">Para modificar os membros de um grupo de funções, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="20ab7-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="20ab7-193">Para _substituir_ a lista de membros existente pelos valores especificados, use a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="20ab7-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="20ab7-194">Para _modificar seletivamente_ a lista de membros existente, use a seguinte sintaxe: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="20ab7-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="20ab7-195">Este exemplo substitui todos os membros atuais do grupo de funções do Help Desk pelos usuários especificados.</span><span class="sxs-lookup"><span data-stu-id="20ab7-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="20ab7-196">Este exemplo adiciona Daigoro Akai e remove Valéria Barrio da lista de membros no grupo de funções do Help Desk.</span><span class="sxs-lookup"><span data-stu-id="20ab7-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="20ab7-197">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="20ab7-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="20ab7-198">Usar o EOP PowerShell autônomo para remover grupos de função</span><span class="sxs-lookup"><span data-stu-id="20ab7-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="20ab7-199">Não é possível remover grupos de função integrados, mas é possível remover grupos de função personalizados criados.</span><span class="sxs-lookup"><span data-stu-id="20ab7-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="20ab7-200">Para remover um grupo de função personalizado, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="20ab7-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="20ab7-201">Este exemplo remove o grupo de funções Training Administrators.</span><span class="sxs-lookup"><span data-stu-id="20ab7-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="20ab7-202">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="20ab7-202">For detailed syntax and parameter information, see [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="20ab7-203">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="20ab7-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="20ab7-204">Para verificar se você copiou com êxito um grupo de funções, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="20ab7-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="20ab7-205">No EAC, vá para **Permissões** Funções de Administrador e verifique se o grupo de funções \> está listado (ou não listado).</span><span class="sxs-lookup"><span data-stu-id="20ab7-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="20ab7-206">Selecione o grupo de funções e verifique as configurações no painel Detalhes ou clique em **Editar** Ícone editar ![ para verificar as ](../../media/ITPro-EAC-EditIcon.png) configurações.</span><span class="sxs-lookup"><span data-stu-id="20ab7-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="20ab7-207">No PowerShell do Exchange Online, substitua pelo nome do grupo de funções e execute o seguinte comando para verificar se o grupo de funções existe (ou não existe) e verificar as \<Role Group Name\> configurações:</span><span class="sxs-lookup"><span data-stu-id="20ab7-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```