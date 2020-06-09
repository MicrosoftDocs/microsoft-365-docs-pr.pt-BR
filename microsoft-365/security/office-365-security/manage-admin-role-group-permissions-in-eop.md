---
title: Gerenciar grupos de função no EOP
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
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Os administradores podem saber como atribuir ou remover permissões no centro de administração do Exchange (Eat) na proteção do Exchange Online.
ms.openlocfilehash: 3555d3bd7fa4c53802eb214747735223cccc21e5
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616509"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Gerenciar grupos de funções no EOP autônomo

Em organizações autônomas de proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, você pode usar o centro de administração do Exchange (Eat) para adicionar usuários aos grupos de função. A adição de um usuário a um grupo de funções permite que as permissões de administrador específicas sejam executadas. Você também pode remover usuários dos grupos de função.

Para obter mais informações sobre funções e grupos de funções, consulte [permissões em EOP autônomo](feature-permissions-in-eop.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o centro de administração do Exchange (Eat), confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).

- Para abrir o EOP PowerShell autônomo, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa receber permissões para executar esses procedimentos. Especificamente, você precisa da função de gerenciamento de função, que é atribuída ao grupo de função gerenciamento (administradores globais) por padrão. Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Está com problemas? Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-manage-role-groups"></a>Usar o Eat para gerenciar grupos de função

### <a name="use-the-eac-to-view-role-groups"></a>Usar o Eat para exibir grupos de função

1. No Eat, acesse funções de administrador de **permissões** \> **Admin roles**. Todos os grupos de função da sua organização estão listados aqui.

2. Selecione um grupo de função. O painel de detalhes mostra o **nome**, a **Descrição**, as **funções atribuídas**e **gerenciado pelo** grupo de função. Você também pode ver essas informações clicando em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>Usar o Eat para criar grupos de função

Ao criar um novo grupo de função, você pode configurar todas as configurações por conta própria (durante a criação do grupo ou após). Ou você pode copiar um grupo de função existente e modificá-lo.

1. No Eat, vá para funções de administrador de **permissões** \> **Admin roles**e execute uma das seguintes etapas:

   - **Crie manualmente um novo grupo de funções**: clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .

   - **Copie um grupo de função existente**: selecione o grupo de função que deseja copiar e clique em **copiar** ![ ícone de cópia ](../../media/ITPro-EAC-CopyIcon.png) .

2. Na janela **novo grupo de função** exibida, defina as seguintes configurações:

    - **Name**: Insira um nome exclusivo para o grupo de função.

    - **Descrição**: Insira uma descrição opcional para o grupo de função.

    - **Funções**: clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) ou **remover** ![ itpro-EAC-RemoveIcon. gif ](../../media/ITPro-EAC-RemoveIcon.gif) para selecionar ou modificar as funções atribuídas ao grupo de funções.

    - **Membros**: clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) ou **remover** ![ itpro-EAC-RemoveIcon. gif ](../../media/ITPro-EAC-RemoveIcon.gif) para modificar a associação ao grupo de funções.

3. Quando tiver terminado, clique em **salvar** para criar o grupo de função.

### <a name="use-the-eac-to-modify-role-groups"></a>Use o Eat para modificar grupos de função

No Eat, vá para funções de administrador de **permissões** \> **Admin roles**, selecione o grupo de função que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) .

As mesmas opções estão disponíveis quando você modifica grupos de função como quando você cria grupos de função. Você pode:

- Altere o nome e a descrição.

- Adicionar e remover funções de gerenciamento (criar ou remover atribuições de função).

- Adicionar e remover membros.

**Observação**: alguns grupos de função (por exemplo, gerenciamento de organização) restringem as funções que podem ser removidas do grupo.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Usar o Eat modificar a lista de membros nos grupos de função

1. No Eat, vá para funções de administrador de **permissões** \> **Admin roles**, selecione o grupo de função que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) .

2. Na página de propriedades do grupo de funções que é aberta, na seção **memebers** , execute uma das seguintes etapas:

   - Clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) . Na página exibida, localize o usuário que wou deseja adicionar e clique em **Adicionar->**. Selecione usuários e clique em **Adicionar->** muitas vezes, conforme necessário. Quando tiver concluído, clique em **OK**.

   - Selecione os usuários que você deseja remover e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Quando concluir, clique em **Salvar**.

   > [!NOTE]
   > Os usuários precisam sair e entrar novamente para ver a alteração em seus diretos administrativos após a adição ou remoção de membros do grupo de funções.

### <a name="use-the-eac-to-remove-role-groups"></a>Usar o Eat para remover grupos de função

Não é possível remover grupos de função internos, mas você pode remover grupos de função personalizados que você criou.

1. No Eat, acesse funções de administrador de **permissões** \> **Admin roles**.

2. Selecione o grupo de função que você deseja remover e clique em **excluir** ![ excluir ícone ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Clique em **Sim** na janela de confirmação que aparece.

## <a name="use-powershell-to-manage-role-groups"></a>Usar o PowerShell para gerenciar grupos de função

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Usar o EOP PowerShell autônomo para exibir grupos de função

Para exibir um grupo de função, use a seguinte sintaxe:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

Este exemplo retorna uma lista resumida de todos os grupos de função.

```PowerShell
Get-RoleGroup
```

Este exemplo retorna informações detalhadas para o grupo de função chamado administradores de destinatário.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

Este exemplo retorna todos os grupos de função onde o usuário Julia é membro. Você precisa usar o valor DistinguishedName (DN) para Julia, que pode ser localizado executando o comando: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Usar o EOP autônomo do PowerShell para criar grupos de função

Ao criar um novo grupo de função, você pode definir todas as configurações manualmente (durante a criação do grupo ou posterior). Ou você pode copiar um grupo de função existente e modificá-lo.

- Para criar manualmente um novo grupo de função, use a seguinte sintaxe:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - O parâmetro _Roles_ especifica as funções de gerenciamento a serem atribuídas ao grupo de função usando a sintaxe a seguir `"Role1","Role1",..."RoleN"` . Você pode ver as funções disponíveis usando o cmdlet **Get-ManagementRole** .

  - O parâmetro _Members_ especifica os membros do grupo de função usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` . Você pode especificar usuários, grupos de segurança universais habilitados para email (USGs) ou outros grupos de função (entidades de segurança).

  Este exemplo cria um novo grupo de função chamado "gerenciamento de destinatário limitado" com as seguintes configurações:

  - A função Destinatários de Email (Mail Recipients) é atribuída ao grupo de função.

  - Os usuários Kim e Martin são adicionados como membros.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Para copiar um grupo de funções existente, siga estas etapas:

  1. Armazene o grupo de funções que deseja copiar em uma variável usando a seguinte sintaxe:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Crie o novo grupo de função usando a seguinte sintaxe:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     O parâmetro _Members_ especifica os membros do grupo de função usando a seguinte sintaxe: `"Member1","Member2",..."MemberN"` . Você pode especificar usuários, grupos de segurança universais habilitados para email (USGs) ou outros grupos de função (entidades de segurança).

     Este exemplo copia o grupo de funções Gerenciamento da organização para o novo grupo de funções chamado "gerenciamento de organização limitado". Os membros do grupo de função são Isabelle, Carter e Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Para informações detalhadas de sintaxes e de parâmetros, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Usar EOP autônomo do PowerShell modificar a lista de membros nos grupos de função

- Os cmdlets **Add-RoleGroupMember** e **Remove-RoleGroupMember** adicionam ou removem membros individuais, um de cada vez. O cmdlet **Update-RoleGroupMember** pode substituir ou modificar a lista de membros existente.

- Os membros de um grupo de função podem ser usuários, grupos de segurança universais habilitados para email (USGs) ou outros grupos de função (entidades de segurança).

Para modificar os membros de um grupo de função, use a seguinte sintaxe:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Para _substituir_ a lista de membros existente pelos valores que você especificar, use a seguinte sintaxe: `"Member1","Member2",..."MemberN"` .

- Para _Modificar seletivamente_ a lista de membros existente, use a seguinte sintaxe: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

Este exemplo substitui todos os membros atuais do grupo de função suporte técnico com os usuários especificados.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

Este exemplo adiciona Daigoro Akai e remove valeria Barrio da lista de membros no grupo de função suporte técnico.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Usar EOP PowerShell autônomo para remover grupos de função

Não é possível remover grupos de função internos, mas você pode remover grupos de função personalizados que você criou.

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

Para verificar se você copiou um grupo de funções com êxito, execute uma das seguintes etapas:

- No Eat, vá para funções de administrador de **permissões** \> **Admin roles**e verifique se o grupo de função está listado (ou não listado). Selecione o grupo de funções e verifique as configurações no painel de detalhes ou clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) para verificar as configurações.

- No PowerShell do Exchange Online, substitua o \<Role Group Name\> nome do grupo de função e execute o seguinte comando para verificar se o grupo de função existe (ou não existe) e verifique as configurações:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
