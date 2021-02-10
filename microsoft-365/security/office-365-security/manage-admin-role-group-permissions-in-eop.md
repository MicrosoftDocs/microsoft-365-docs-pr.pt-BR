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
# <a name="manage-role-groups-in-standalone-eop"></a>Gerenciar grupos de funções no EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção do Exchange Online autônoma](https://go.microsoft.com/fwlink/?linkid=2148611)

Em organizações autônomas do Proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, você pode usar o Centro de administração do Exchange (EAC) para adicionar usuários a grupos de funções. A adição de usuários a um grupo de funções concede ao usuário permissões para realizar tarefas administrativas específicas. Você também pode remover usuários de grupos de função.

Para obter mais informações sobre funções e grupos de funções, consulte [Permissões no EOP autônomo.](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o Centro de administração do Exchange (EAC), confira o Centro de administração [do Exchange no EOP autônomo.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Para abrir o PowerShell do EOP autônomo, consulte [Conectar-se ao PowerShell da Proteção do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

- Para fazer os procedimentos deste artigo, você precisa ter permissões no Exchange Online Protection. Especificamente, você precisa da **função Gerenciamento de** Função, que é atribuída ao grupo **de** função Gerenciamento da Organização por padrão. Para obter mais informações, [consulte Permissões no EOP](feature-permissions-in-eop.md) autônomo e use o EAC modificar a lista de [membros em grupos de função.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o Centro de administração do Exchange no Exchange Online .

> [!TIP]
> Está com problemas? Peça ajuda no fórum [Proteção do Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="use-the-eac-to-manage-role-groups"></a>Usar o EAC para gerenciar grupos de funções

### <a name="use-the-eac-to-view-role-groups"></a>Usar o EAC para exibir grupos de função

1. No EAC, vá para funções **de Administrador** \> **de Permissões.** Todos os grupos de função em sua organização estão listados aqui.

2. Selecione um grupo de funções. O painel Detalhes mostra o **nome**, **descrição**, funções **atribuídas** e **gerenciado pelo** grupo de função. Você também pode ver essas informações clicando no **ícone** ![ Editar ](../../media/ITPro-EAC-EditIcon.png) Edição.

### <a name="use-the-eac-to-create-role-groups"></a>Usar o EAC para criar grupos de função

Ao criar um novo grupo de funções, você pode definir todas as configurações por conta própria (durante a criação do grupo ou depois). Ou você pode copiar um grupo de função existente e modificá-lo.

1. No EAC, vá para funções **de** Administrador de Permissões e, em \> seguida, faça uma das seguintes etapas:

   - **Crie manualmente um novo grupo de funções:** clique **no ícone** ![ ](../../media/ITPro-EAC-AddIcon.png) Adicionar.

   - **Copie um grupo de funções existente:** selecione o grupo de funções que você deseja copiar e clique no ícone **Copiar** ![ ](../../media/ITPro-EAC-CopyIcon.png) Cópia.

2. Na janela **Novo grupo de** funções exibida, de configure as seguintes configurações:

    - **Nome:** insira um nome exclusivo para o grupo de função.

    - **Descrição:** insira uma descrição opcional para o grupo de funções.

    - **Funções:** clique **no ícone** Adicionar ou Remover ícone Remover para selecionar ou modificar as funções atribuídas ![ ao grupo de ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) funções.

    - **Membros:** clique no **ícone Adicionar** adicionar ![ ou ](../../media/ITPro-EAC-AddIcon.png) **remover** ícone para modificar a associação do grupo ![ de ](../../media/ITPro-EAC-RemoveIcon.gif) função.

3. Quando terminar, clique em **Salvar para** criar o grupo de funções.

### <a name="use-the-eac-to-modify-role-groups"></a>Usar o EAC para modificar grupos de função

No EAC, vá para **funções** de Administrador de Permissões, selecione o grupo de funções que você deseja modificar e clique em \>  **Editar** ![ ](../../media/ITPro-EAC-EditIcon.png) ícone.

As mesmas opções estão disponíveis quando você modifica grupos de função como quando você cria grupos de função. Você pode:

- Altere o nome e a descrição.

- Adicionar e remover funções de gerenciamento (criar ou remover atribuições de função).

- Adicionar e remover membros.

**Observação:** alguns grupos de função (por exemplo, Gerenciamento da Organização) restringem as funções que você pode remover do grupo.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Usar o EAC para modificar a lista de membros em grupos de função

1. No EAC, vá  para funções de Administrador de Permissões, selecione o grupo de funções que você deseja modificar e clique em \>  **Editar** ![ ](../../media/ITPro-EAC-EditIcon.png) ícone.

2. Na página de propriedades do grupo de funções que é aberta, na seção **Membros,** faça uma das seguintes etapas:

   - Clique **em Adicionar** Ícone ![ ](../../media/ITPro-EAC-AddIcon.png) Adicionar. Na página exibida, encontre o usuário que deseja adicionar e clique em **add ->**. Selecione usuários e clique **em adicionar ->** quantas vezes for necessário. Quando terminar, clique em **OK.**

   - Selecione os usuários que você deseja  remover e clique no ícone ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.

3. Quando concluir, clique em **Salvar**.

   > [!NOTE]
   > Os usuários precisam sair e entrar novamente para ver a alteração em seus diretos administrativos após a adição ou remoção de membros do grupo de funções.

### <a name="use-the-eac-to-remove-role-groups"></a>Usar o EAC para remover grupos de função

Não é possível remover grupos de função integrados, mas você pode remover grupos de função personalizados que você criou.

1. No EAC, vá para funções **de Administrador** \> **de Permissões.**

2. Selecione o grupo de funções que você deseja remover e clique em **Excluir** ![ ](../../media/ITPro-EAC-DeleteIcon.png) ícone.

3. Clique **em Sim** na janela de confirmação exibida.

## <a name="use-powershell-to-manage-role-groups"></a>Usar o PowerShell para gerenciar grupos de funções

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Usar o EOP PowerShell autônomo para exibir grupos de funções

Para exibir um grupo de funções, use a seguinte sintaxe:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

Este exemplo retorna uma lista resumida de todos os grupos de função.

```PowerShell
Get-RoleGroup
```

Este exemplo retorna informações detalhadas para o grupo de função chamado Recipient Administrators.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

Este exemplo retorna todos os grupos de função em que a usuária Julia é membro. Você precisa usar o valor distinguishedName (DN) para Julia, que você pode encontrar executando o comando: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Usar o EOP PowerShell autônomo para criar grupos de função

Ao criar um novo grupo de função, você pode definir todas as configurações manualmente (durante a criação do grupo ou depois). Ou você pode copiar um grupo de função existente e modificá-lo.

- Para criar manualmente um novo grupo de funções, use a seguinte sintaxe:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - O _parâmetro Roles_ especifica as funções de gerenciamento a atribuir ao grupo de funções usando a sintaxe a `"Role1","Role1",..."RoleN"` seguir. Você pode ver as funções disponíveis usando o cmdlet **Get-ManagementRole.**

  - O _parâmetro_ Members especifica os membros do grupo de função usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` . Você pode especificar usuários, grupos de segurança universal habilitados para email (USGs) ou outros grupos de função (entidades de segurança).

  Este exemplo cria um novo grupo de funções chamado "Gerenciamento limitado de destinatários" com as seguintes configurações:

  - A função Destinatários de Email (Mail Recipients) é atribuída ao grupo de função.

  - Os usuários Kim e Martin são adicionados como membros.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Para copiar um grupo de funções existente, faça o seguinte:

  1. Armazene o grupo de funções que deseja copiar em uma variável usando a seguinte sintaxe:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Crie o novo grupo de funções usando a seguinte sintaxe:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     O _parâmetro_ Members especifica os membros do grupo de função usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` . Você pode especificar usuários, grupos de segurança universal habilitados para email (USGs) ou outros grupos de função (entidades de segurança).

     Este exemplo copia o grupo de função Gerenciamento da Organização para o novo grupo de funções chamado "Gerenciamento limitado da organização". Os membros do grupo de funções são Mila, Carter e Carters.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Para informações detalhadas de sintaxes e de parâmetros, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Usar o EOP PowerShell autônomo para modificar a lista de membros em grupos de função

- Os cmdlets **Add-RoleGroupMember** e **Remove-RoleGroupMember** adicionam ou removem membros individuais, um de cada vez. O cmdlet **Update-RoleGroupMember** pode substituir ou modificar a lista de membros existente.

- Os membros de um grupo de função podem ser usuários, grupos de segurança universal habilitados para email (USGs) ou outros grupos de função (entidades de segurança).

Para modificar os membros de um grupo de função, use a seguinte sintaxe:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Para _substituir_ a lista de membros existente pelos valores especificados, use a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .

- Para _modificar seletivamente_ a lista de membros existente, use a seguinte sintaxe: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

Este exemplo substitui todos os membros atuais do grupo de função Help Desk pelos usuários especificados.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

Este exemplo adiciona Daigoro Akai e remove Mila Barrio da lista de membros no grupo de funções Help Desk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Usar o EOP PowerShell autônomo para remover grupos de função

Não é possível remover grupos de função integrados, mas você pode remover grupos de função personalizados que você criou.

Para remover um grupo de função personalizado, use a seguinte sintaxe:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

Este exemplo remove o grupo de funções Training Administrators.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você copiou com êxito um grupo de funções, faça uma das seguintes etapas:

- No EAC, vá para funções **de** Administrador de Permissões e verifique se \> o grupo de funções está listado (ou não listado). Selecione o grupo de funções e verifique as configurações no painel Detalhes ou clique no ícone Editar  ![ para verificar as ](../../media/ITPro-EAC-EditIcon.png) configurações.

- No PowerShell do Exchange Online, substitua pelo nome do grupo de funções e execute o seguinte comando para verificar se o grupo de funções existe (ou não existe) e verificar as \<Role Group Name\> configurações:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
