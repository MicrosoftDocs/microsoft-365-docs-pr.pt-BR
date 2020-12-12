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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Os administradores podem saber como atribuir ou remover permissões no centro de administração do Exchange (Eat) na proteção do Exchange Online.
ms.openlocfilehash: 4a1353963e5e3eadc1a07f8b4aa3a765b06c86ec
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659287"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="f46e0-103">Gerenciar grupos de funções no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="f46e0-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f46e0-104">Em organizações autônomas de proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, você pode usar o centro de administração do Exchange (Eat) para adicionar usuários aos grupos de função.</span><span class="sxs-lookup"><span data-stu-id="f46e0-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="f46e0-105">A adição de um usuário a um grupo de funções permite que as permissões de administrador específicas sejam executadas.</span><span class="sxs-lookup"><span data-stu-id="f46e0-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="f46e0-106">Você também pode remover usuários dos grupos de função.</span><span class="sxs-lookup"><span data-stu-id="f46e0-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="f46e0-107">Para obter mais informações sobre funções e grupos de funções, consulte [permissões em EOP autônomo](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f46e0-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f46e0-108">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="f46e0-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f46e0-109">Para abrir o centro de administração do Exchange (Eat), confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f46e0-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="f46e0-110">Para abrir o EOP PowerShell autônomo, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f46e0-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f46e0-111">Você precisa receber permissões na proteção do Exchange Online antes de poder executar os procedimentos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="f46e0-111">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="f46e0-112">Especificamente, você precisará da função de **Gerenciamento de função** , que é atribuída ao grupo de função de **Gerenciamento da organização** por padrão.</span><span class="sxs-lookup"><span data-stu-id="f46e0-112">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="f46e0-113">Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="f46e0-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="f46e0-114">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste artigo, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="f46e0-114">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="f46e0-115">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="f46e0-115">Having problems?</span></span> <span data-ttu-id="f46e0-116">Peça ajuda no fórum [Proteção do Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="f46e0-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="f46e0-117">Usar o Eat para gerenciar grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="f46e0-118">Usar o Eat para exibir grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="f46e0-119">No Eat, acesse funções de administrador de **permissões** \> .</span><span class="sxs-lookup"><span data-stu-id="f46e0-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="f46e0-120">Todos os grupos de função da sua organização estão listados aqui.</span><span class="sxs-lookup"><span data-stu-id="f46e0-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="f46e0-121">Selecione um grupo de função.</span><span class="sxs-lookup"><span data-stu-id="f46e0-121">Select a role group.</span></span> <span data-ttu-id="f46e0-122">O painel de detalhes mostra o **nome**, a **Descrição**, as **funções atribuídas** e **gerenciado pelo** grupo de função.</span><span class="sxs-lookup"><span data-stu-id="f46e0-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="f46e0-123">Você também pode ver essas informações clicando em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="f46e0-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="f46e0-124">Usar o Eat para criar grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="f46e0-125">Ao criar um novo grupo de função, você pode configurar todas as configurações por conta própria (durante a criação do grupo ou após).</span><span class="sxs-lookup"><span data-stu-id="f46e0-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="f46e0-126">Ou você pode copiar um grupo de função existente e modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="f46e0-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="f46e0-127">No Eat, vá para funções de administrador de **permissões** \> e execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f46e0-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="f46e0-128">**Crie manualmente um novo grupo de funções**: clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="f46e0-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="f46e0-129">**Copie um grupo de função existente**: selecione o grupo de função que deseja copiar e clique em **copiar** ![ ícone de cópia ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="f46e0-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="f46e0-130">Na janela **novo grupo de função** exibida, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="f46e0-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="f46e0-131">**Name**: Insira um nome exclusivo para o grupo de função.</span><span class="sxs-lookup"><span data-stu-id="f46e0-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="f46e0-132">**Descrição**: Insira uma descrição opcional para o grupo de função.</span><span class="sxs-lookup"><span data-stu-id="f46e0-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="f46e0-133">**Funções**: clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) de adicionar ou **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) para selecionar ou modificar as funções atribuídas ao grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="f46e0-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="f46e0-134">**Membros**: clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) de adicionar ou **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) para modificar a associação ao grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="f46e0-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="f46e0-135">Quando tiver terminado, clique em **salvar** para criar o grupo de função.</span><span class="sxs-lookup"><span data-stu-id="f46e0-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="f46e0-136">Use o Eat para modificar grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="f46e0-137">No Eat, vá para funções de administrador de **permissões** \> , selecione o grupo de função que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="f46e0-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="f46e0-138">As mesmas opções estão disponíveis quando você modifica grupos de função como quando você cria grupos de função.</span><span class="sxs-lookup"><span data-stu-id="f46e0-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="f46e0-139">Você pode:</span><span class="sxs-lookup"><span data-stu-id="f46e0-139">You can:</span></span>

- <span data-ttu-id="f46e0-140">Altere o nome e a descrição.</span><span class="sxs-lookup"><span data-stu-id="f46e0-140">Change the name and description.</span></span>

- <span data-ttu-id="f46e0-141">Adicionar e remover funções de gerenciamento (criar ou remover atribuições de função).</span><span class="sxs-lookup"><span data-stu-id="f46e0-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="f46e0-142">Adicionar e remover membros.</span><span class="sxs-lookup"><span data-stu-id="f46e0-142">Add and remove members.</span></span>

<span data-ttu-id="f46e0-143">**Observação**: alguns grupos de função (por exemplo, gerenciamento de organização) restringem as funções que podem ser removidas do grupo.</span><span class="sxs-lookup"><span data-stu-id="f46e0-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="f46e0-144">Usar o Eat modificar a lista de membros nos grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="f46e0-145">No Eat, vá para funções de administrador de **permissões** \> , selecione o grupo de função que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="f46e0-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="f46e0-146">Na página de propriedades do grupo de funções que é aberta, na seção **Membros** , execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f46e0-146">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="f46e0-147">Clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="f46e0-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="f46e0-148">Na página exibida, localize o usuário que wou deseja adicionar e clique em **Adicionar->**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="f46e0-149">Selecione usuários e clique em **Adicionar->** muitas vezes, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f46e0-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="f46e0-150">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="f46e0-151">Selecione os usuários que você deseja remover e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="f46e0-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="f46e0-152">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f46e0-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f46e0-153">Os usuários precisam sair e entrar novamente para ver a alteração em seus diretos administrativos após a adição ou remoção de membros do grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="f46e0-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="f46e0-154">Usar o Eat para remover grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="f46e0-155">Não é possível remover grupos de função internos, mas você pode remover grupos de função personalizados que você criou.</span><span class="sxs-lookup"><span data-stu-id="f46e0-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="f46e0-156">No Eat, acesse funções de administrador de **permissões** \> .</span><span class="sxs-lookup"><span data-stu-id="f46e0-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="f46e0-157">Selecione o grupo de função que você deseja remover e clique em **excluir** ![ excluir ícone ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="f46e0-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="f46e0-158">Clique em **Sim** na janela de confirmação que aparece.</span><span class="sxs-lookup"><span data-stu-id="f46e0-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="f46e0-159">Usar o PowerShell para gerenciar grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="f46e0-160">Usar o EOP PowerShell autônomo para exibir grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="f46e0-161">Para exibir um grupo de função, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f46e0-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="f46e0-162">Este exemplo retorna uma lista resumida de todos os grupos de função.</span><span class="sxs-lookup"><span data-stu-id="f46e0-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="f46e0-163">Este exemplo retorna informações detalhadas para o grupo de função chamado administradores de destinatário.</span><span class="sxs-lookup"><span data-stu-id="f46e0-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="f46e0-164">Este exemplo retorna todos os grupos de função onde o usuário Julia é membro.</span><span class="sxs-lookup"><span data-stu-id="f46e0-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="f46e0-165">Você precisa usar o valor DistinguishedName (DN) para Julia, que pode ser localizado executando o comando: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="f46e0-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="f46e0-166">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="f46e0-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="f46e0-167">Usar o EOP autônomo do PowerShell para criar grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="f46e0-168">Ao criar um novo grupo de função, você pode definir todas as configurações manualmente (durante a criação do grupo ou posterior).</span><span class="sxs-lookup"><span data-stu-id="f46e0-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="f46e0-169">Ou você pode copiar um grupo de função existente e modificá-lo.</span><span class="sxs-lookup"><span data-stu-id="f46e0-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="f46e0-170">Para criar manualmente um novo grupo de função, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f46e0-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="f46e0-171">O parâmetro _Roles_ especifica as funções de gerenciamento a serem atribuídas ao grupo de função usando a sintaxe a seguir `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="f46e0-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="f46e0-172">Você pode ver as funções disponíveis usando o cmdlet **Get-ManagementRole** .</span><span class="sxs-lookup"><span data-stu-id="f46e0-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="f46e0-173">O parâmetro _Members_ especifica os membros do grupo de função usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="f46e0-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="f46e0-174">Você pode especificar usuários, grupos de segurança universais habilitados para email (USGs) ou outros grupos de função (entidades de segurança).</span><span class="sxs-lookup"><span data-stu-id="f46e0-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="f46e0-175">Este exemplo cria um novo grupo de função chamado "gerenciamento de destinatário limitado" com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="f46e0-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="f46e0-176">A função Destinatários de Email (Mail Recipients) é atribuída ao grupo de função.</span><span class="sxs-lookup"><span data-stu-id="f46e0-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="f46e0-177">Os usuários Kim e Martin são adicionados como membros.</span><span class="sxs-lookup"><span data-stu-id="f46e0-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="f46e0-178">Para copiar um grupo de funções existente, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="f46e0-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="f46e0-179">Armazene o grupo de funções que deseja copiar em uma variável usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f46e0-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="f46e0-180">Crie o novo grupo de função usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f46e0-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="f46e0-181">O parâmetro _Members_ especifica os membros do grupo de função usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="f46e0-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="f46e0-182">Você pode especificar usuários, grupos de segurança universais habilitados para email (USGs) ou outros grupos de função (entidades de segurança).</span><span class="sxs-lookup"><span data-stu-id="f46e0-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="f46e0-183">Este exemplo copia o grupo de funções Gerenciamento da organização para o novo grupo de funções chamado "gerenciamento de organização limitado".</span><span class="sxs-lookup"><span data-stu-id="f46e0-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="f46e0-184">Os membros do grupo de função são Isabelle, Carter e Lukas.</span><span class="sxs-lookup"><span data-stu-id="f46e0-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="f46e0-185">Para informações detalhadas de sintaxes e de parâmetros, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="f46e0-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="f46e0-186">Usar EOP autônomo do PowerShell modificar a lista de membros nos grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="f46e0-187">Os cmdlets **Add-RoleGroupMember** e **Remove-RoleGroupMember** adicionam ou removem membros individuais, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="f46e0-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="f46e0-188">O cmdlet **Update-RoleGroupMember** pode substituir ou modificar a lista de membros existente.</span><span class="sxs-lookup"><span data-stu-id="f46e0-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="f46e0-189">Os membros de um grupo de função podem ser usuários, grupos de segurança universais habilitados para email (USGs) ou outros grupos de função (entidades de segurança).</span><span class="sxs-lookup"><span data-stu-id="f46e0-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="f46e0-190">Para modificar os membros de um grupo de função, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f46e0-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="f46e0-191">Para _substituir_ a lista de membros existente pelos valores que você especificar, use a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="f46e0-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="f46e0-192">Para _Modificar seletivamente_ a lista de membros existente, use a seguinte sintaxe: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="f46e0-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="f46e0-193">Este exemplo substitui todos os membros atuais do grupo de função suporte técnico com os usuários especificados.</span><span class="sxs-lookup"><span data-stu-id="f46e0-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="f46e0-194">Este exemplo adiciona Daigoro Akai e remove valeria Barrio da lista de membros no grupo de função suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="f46e0-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="f46e0-195">Para informações detalhadas de sintaxes e de parâmetros, consulte [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="f46e0-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="f46e0-196">Usar EOP PowerShell autônomo para remover grupos de função</span><span class="sxs-lookup"><span data-stu-id="f46e0-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="f46e0-197">Não é possível remover grupos de função internos, mas você pode remover grupos de função personalizados que você criou.</span><span class="sxs-lookup"><span data-stu-id="f46e0-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="f46e0-198">Para remover um grupo de função personalizado, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f46e0-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="f46e0-199">Este exemplo remove o grupo de funções Training Administrators.</span><span class="sxs-lookup"><span data-stu-id="f46e0-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="f46e0-200">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="f46e0-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f46e0-201">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="f46e0-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="f46e0-202">Para verificar se você copiou um grupo de funções com êxito, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="f46e0-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="f46e0-203">No Eat, vá para funções de administrador de **permissões** \> e verifique se o grupo de função está listado (ou não listado).</span><span class="sxs-lookup"><span data-stu-id="f46e0-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="f46e0-204">Selecione o grupo de funções e verifique as configurações no painel de detalhes ou clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) para verificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="f46e0-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="f46e0-205">No PowerShell do Exchange Online, substitua o \<Role Group Name\> nome do grupo de função e execute o seguinte comando para verificar se o grupo de função existe (ou não existe) e verifique as configurações:</span><span class="sxs-lookup"><span data-stu-id="f46e0-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
