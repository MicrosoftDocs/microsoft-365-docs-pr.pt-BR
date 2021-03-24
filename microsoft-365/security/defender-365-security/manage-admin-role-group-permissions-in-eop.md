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
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054148"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Gerenciar grupos de funções no EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção autônoma do Exchange Online](exchange-online-protection-overview.md)

Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode usar o Centro de administração do Exchange (EAC) para adicionar usuários a grupos de funções. Adicionar um usuário a um grupo de funções dá ao usuário permissões para realizar tarefas de administrador específicas. Você também pode remover usuários de grupos de função.

Para obter mais informações sobre funções e grupos de funções, consulte [Permissões no EOP](feature-permissions-in-eop.md)autônomo .

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o Centro de administração do Exchange (EAC), consulte Centro de administração [do Exchange no EOP](exchange-admin-center-in-exchange-online-protection-eop.md)autônomo .

- Para abrir o EOP PowerShell autônomo, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa ter permissões atribuídas no Exchange Online Protection antes de poder fazer os procedimentos neste artigo. Especificamente, você precisa da **função Gerenciamento de** Função, que é atribuída ao grupo de função **Gerenciamento** da Organização por padrão. Para obter mais informações, consulte [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o centro de administração do Exchange no Exchange Online .

> [!TIP]
> Está com problemas? Peça ajuda no fórum [Proteção do Exchange Online](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="use-the-eac-to-manage-role-groups"></a>Usar o EAC para gerenciar grupos de funções

### <a name="use-the-eac-to-view-role-groups"></a>Usar o EAC para exibir grupos de funções

1. No EAC, vá para **Permissões Funções de** \> **Administrador**. Todos os grupos de função em sua organização estão listados aqui.

2. Selecione um grupo de funções. O painel Detalhes mostra o **Nome,** **Descrição,** **Funções Atribuídas** e **Gerenciado pelo** grupo de funções. Você também pode ver essas informações clicando em **Editar** ![ ícone editar ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>Usar o EAC para criar grupos de função

Ao criar um novo grupo de funções, você pode configurar todas as configurações por conta própria (durante a criação do grupo ou depois). Ou você pode copiar um grupo de funções existente e modificá-lo.

1. No EAC, vá para **Funções** de Administrador de Permissões e, em \> seguida, faça uma das seguintes etapas:

   - **Criar manualmente um novo grupo de função:** clique **em Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) .

   - **Copie um grupo de funções existente:** selecione o grupo de funções que você deseja copiar e clique em **Copiar** ![ ícone de ](../../media/ITPro-EAC-CopyIcon.png) cópia.

2. Na janela **Novo grupo de** função que aparece, configure as seguintes configurações:

    - **Nome**: Insira um nome exclusivo para o grupo de funções.

    - **Descrição**: insira uma descrição opcional para o grupo de funções.

    - **Funções**: clique **em Adicionar** ícone ou Remover Ícone remover para selecionar ou modificar as funções ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) atribuídas ao grupo de funções.

    - **Membros**: clique **em Adicionar** ícone adicionar ![ ou ](../../media/ITPro-EAC-AddIcon.png) **remover** ícone remover para modificar a associação do grupo ![ de ](../../media/ITPro-EAC-RemoveIcon.gif) funções.

3. Quando terminar, clique em **Salvar** para criar o grupo de funções.

### <a name="use-the-eac-to-modify-role-groups"></a>Usar o EAC para modificar grupos de função

No EAC, vá para **Permissões** Funções de Administrador , selecione o grupo de função que você deseja modificar e clique \> em **Editar** Ícone ![ editar ](../../media/ITPro-EAC-EditIcon.png) .

As mesmas opções estão disponíveis quando você modifica grupos de função como quando você cria grupos de função. Você pode:

- Altere o nome e a descrição.

- Adicionar e remover funções de gerenciamento (criar ou remover atribuições de função).

- Adicionar e remover membros.

**Observação**: Alguns grupos de função (por exemplo, Gerenciamento da Organização) restringem as funções que você pode remover do grupo.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Usar o EAC modificar a lista de membros em grupos de função

1. No EAC, vá para **Permissões** Funções de Administrador , selecione o grupo de funções que você deseja modificar e clique \> em **Editar** Ícone ![ editar ](../../media/ITPro-EAC-EditIcon.png) .

2. Na página propriedades do grupo de função que é aberta, na seção **Membros,** faça uma das seguintes etapas:

   - Clique **em Adicionar** Ícone ![ ](../../media/ITPro-EAC-AddIcon.png) . Na página exibida, encontre o usuário que deseja adicionar e clique **em adicionar ->**. Selecione usuários e clique **em adicionar ->** quantas vezes for necessário. Quando terminar, clique em **OK**.

   - Selecione os usuários que você deseja remover e clique em **Remover** ![ ícone remover ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Quando concluir, clique em **Salvar**.

   > [!NOTE]
   > Os usuários precisam sair e entrar novamente para ver a alteração em seus diretos administrativos após a adição ou remoção de membros do grupo de funções.

### <a name="use-the-eac-to-remove-role-groups"></a>Usar o EAC para remover grupos de função

Não é possível remover grupos de função integrados, mas é possível remover grupos de função personalizados criados.

1. No EAC, vá para **Permissões Funções de** \> **Administrador**.

2. Selecione o grupo de função que você deseja remover e clique em **Excluir** ![ ícone ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Clique **em Sim** na janela de confirmação exibida.

## <a name="use-powershell-to-manage-role-groups"></a>Usar o PowerShell para gerenciar grupos de função

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Usar o EOP PowerShell autônomo para exibir grupos de funções

Para exibir um grupo de funções, use a seguinte sintaxe:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

Este exemplo retorna uma lista resumida de todos os grupos de funções.

```PowerShell
Get-RoleGroup
```

Este exemplo retorna informações detalhadas para o grupo de função chamado Administradores de Destinatários.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

Este exemplo retorna todos os grupos de função onde a usuária Julia é membro. Você precisa usar o valor DistinguishedName (DN) para a Julia, que você pode encontrar executando o comando: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Usar o EOP PowerShell autônomo para criar grupos de função

Ao criar um novo grupo de funções, você pode configurar todas as configurações manualmente (durante a criação do grupo ou depois). Ou você pode copiar um grupo de funções existente e modificá-lo.

- Para criar manualmente um novo grupo de funções, use a seguinte sintaxe:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - O _parâmetro Roles_ especifica as funções de gerenciamento a atribuir ao grupo de funções usando a sintaxe a seguir `"Role1","Role1",..."RoleN"` . Você pode ver as funções disponíveis usando o cmdlet **Get-ManagementRole.**

  - O _parâmetro Members_ especifica os membros do grupo de funções usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` . Você pode especificar usuários, USGs (grupos de segurança universal) habilitados para email ou outros grupos de função (entidades de segurança).

  Este exemplo cria um novo grupo de funções chamado "Gerenciamento limitado de destinatários" com as seguintes configurações:

  - A função Destinatários de Email (Mail Recipients) é atribuída ao grupo de função.

  - Os usuários Kim e Martin são adicionados como membros.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Para copiar um grupo de funções existente, faça as seguintes etapas:

  1. Armazene o grupo de funções que deseja copiar em uma variável usando a seguinte sintaxe:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Crie o novo grupo de funções usando a seguinte sintaxe:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     O _parâmetro Members_ especifica os membros do grupo de funções usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` . Você pode especificar usuários, USGs (grupos de segurança universal) habilitados para email ou outros grupos de função (entidades de segurança).

     Este exemplo copia o grupo de função Gerenciamento da Organização para o novo grupo de funções chamado "Gerenciamento limitado da organização". Os membros do grupo de função são Isabel, Carter e Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Para obter informações detalhadas sobre sintaxes e parâmetros, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Usar o EOP PowerShell autônomo modificar a lista de membros em grupos de função

- Os cmdlets **Add-RoleGroupMember** e **Remove-RoleGroupMember** adicionam ou removem membros individuais um por vez. O cmdlet **Update-RoleGroupMember** pode substituir ou modificar a lista de membros existente.

- Os membros de um grupo de funções podem ser usuários, USGs (grupos de segurança universal habilitados para email) ou outros grupos de função (entidades de segurança).

Para modificar os membros de um grupo de funções, use a seguinte sintaxe:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Para _substituir_ a lista de membros existente pelos valores especificados, use a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .

- Para _modificar seletivamente_ a lista de membros existente, use a seguinte sintaxe: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

Este exemplo substitui todos os membros atuais do grupo de funções do Help Desk pelos usuários especificados.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

Este exemplo adiciona Daigoro Akai e remove Valéria Barrio da lista de membros no grupo de funções do Help Desk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Usar o EOP PowerShell autônomo para remover grupos de função

Não é possível remover grupos de função integrados, mas é possível remover grupos de função personalizados criados.

Para remover um grupo de função personalizado, use a seguinte sintaxe:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

Este exemplo remove o grupo de funções Training Administrators.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você copiou com êxito um grupo de funções, faça uma das seguintes etapas:

- No EAC, vá para **Permissões** Funções de Administrador e verifique se o grupo de funções \> está listado (ou não listado). Selecione o grupo de funções e verifique as configurações no painel Detalhes ou clique em **Editar** Ícone editar ![ para verificar as ](../../media/ITPro-EAC-EditIcon.png) configurações.

- No PowerShell do Exchange Online, substitua pelo nome do grupo de funções e execute o seguinte comando para verificar se o grupo de funções existe (ou não existe) e verificar as \<Role Group Name\> configurações:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```