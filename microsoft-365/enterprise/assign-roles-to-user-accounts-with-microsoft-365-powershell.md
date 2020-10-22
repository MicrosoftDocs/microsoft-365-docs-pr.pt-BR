---
title: Atribuir funções a contas de usuário do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: Neste artigo, saiba como usar com rapidez e facilidade o PowerShell para a Microsoft 365 para atribuir funções de administrador às contas de usuário.
ms.openlocfilehash: 1486c86172cd34e6e88f8cd02d003967518bcdb7
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655942"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Atribuir funções de administrador às contas de usuário do Microsoft 365 com o PowerShell

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Você pode atribuir funções de administrador de forma rápida e fácil às contas de usuário usando o PowerShell para o Microsoft 365.

>[!Note]
>[Saiba como atribuir funções de administrador a contas de usuário](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) com o centro de administração do Microsoft 365. Para obter uma lista de recursos adicionais, consulte [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) usando uma conta de administrador global.
  
Em seguida, determine o nome de entrada da conta de usuário que você deseja adicionar a uma função (exemplo: fredsm@contoso.com). Isso também é conhecido como nome de usuário principal (UPN).

Em seguida, determine o nome da função de administrador. Use essa [lista de permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

>[!Note]
>Preste atenção nas anotações deste artigo. Alguns nomes de função são diferentes para o Azure AD PowerShell. Por exemplo, a função "administrador do SharePoint" no centro de administração do Microsoft 365 é chamada de "administrador de serviços do SharePoint" para o Azure AD PowerShell.
>

Em seguida, preencha os nomes de entrada e de função e execute esses comandos.
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Veja um exemplo de um conjunto de comandos concluído que atribui a função de administrador do administrador de serviços do SharePoint à conta belindan@contoso.com:
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Para exibir a lista de nomes de usuário para uma função de administrador específica, use estes comandos.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) usando uma conta de administrador global.
  
### <a name="for-a-single-role-change"></a>Para uma alteração de função única

As formas mais comuns de uma conta de usuário específica são com seu nome de exibição ou seu nome de email, também conhecido como nome de logon ou nome UPN.

#### <a name="display-names-of-user-accounts"></a>Exibir nomes de contas de usuário

Se você estiver acostumado a trabalhar com os nomes de exibição das contas de usuário, determine o seguinte:
  
- A conta de usuário que você deseja configurar.
    
    Para especificar a conta de usuário, você deve determinar seu nome de exibição. Para obter uma lista completa de contas, use este comando:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Este comando lista o nome de exibição de suas contas de usuário, classificados pelo nome de exibição, uma tela por vez. Você pode filtrar a lista em um conjunto menor usando o cmdlet **Where** . Veja um exemplo:

   >[!Note]
   >O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Este comando lista apenas as contas de usuário para as quais o nome de exibição começa com "John".
    
- A função que você deseja atribuir.
    
    Para exibir a lista de funções de administrador disponíveis que podem ser atribuídas a contas de usuário, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Depois de determinar o nome de exibição da conta e o nome da função de administrador, use estes comandos para atribuir a função à conta:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Copie os comandos e cole-os no bloco de notas. Para as variáveis **$dispName** e **$roleName** , substitua o texto da descrição por seus valores, remova os \< and > caracteres e deixe as aspas. Copie as linhas modificadas e cole-as em sua janela do módulo do Microsoft Azure Active Directory para Windows PowerShell para executá-las. Como alternativa, você pode usar o ambiente de script integrado (ISE) do Windows PowerShell.
  
Veja um exemplo de um conjunto de comandos concluído:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Nomes de entrada de contas de usuário

Se você estiver acostumado a trabalhar com os nomes de entrada ou UPNs de contas de usuário, determine o seguinte:
  
- O UPN da conta do usuário.
    
    Se você ainda não souber o UPN, use este comando:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Este comando lista o UPN de suas contas de usuário, classificados pelo UPN, uma tela por vez. Você pode filtrar a lista em um conjunto menor usando o cmdlet **Where** . Veja um exemplo:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Este comando lista apenas as contas de usuário para as quais o nome de exibição começa com "John".
    
- A função que você deseja atribuir.
    
    Para exibir a lista de funções disponíveis que você pode atribuir às contas de usuário, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Depois de ter o UPN da conta e o nome da função, use estes comandos para atribuir a função à conta:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Copie os comandos e cole-os no bloco de notas. Para as variáveis **$upnName** e **$roleName** , substitua o texto da descrição por seus valores, remova os \< and > caracteres e deixe as aspas. Copie as linhas modificadas e cole-as em sua janela do módulo do Microsoft Azure Active Directory para Windows PowerShell para executá-las. Como alternativa, você pode usar o Windows PowerShell ISE.
  
Veja um exemplo de um conjunto de comandos concluído:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Várias alterações de função

Para várias alterações de função, determine o seguinte:
  
- Quais contas de usuário você deseja configurar. Você pode usar os métodos da seção anterior para coletar o conjunto de nomes de exibição ou UPNs.
    
- Quais funções você deseja atribuir a cada conta de usuário.
    
    Para exibir a lista de funções disponíveis que você pode atribuir às contas de usuário, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Em seguida, crie um arquivo de texto de valor separado por vírgula (CSV) que tenha os campos nome de exibição ou UPN e nome da função. Você pode fazer isso facilmente com o Microsoft Excel.

Veja um exemplo de nomes de exibição:
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

Em seguida, preencha o local do arquivo CSV e execute os comandos resultantes no prompt de comando do PowerShell.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Veja um exemplo de UPNs:
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

Em seguida, preencha o local do arquivo CSV e execute os comandos resultantes no prompt de comando do PowerShell.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>Confira também

- [Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
