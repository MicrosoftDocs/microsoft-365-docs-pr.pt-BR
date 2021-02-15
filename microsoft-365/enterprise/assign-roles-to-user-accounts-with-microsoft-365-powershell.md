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
description: Neste artigo, saiba com que rapidez e facilidade use o PowerShell para Microsoft 365 para atribuir funções de administrador a contas de usuário.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754193"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Atribuir funções de administrador a contas de usuário do Microsoft 365 com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode facilmente atribuir funções a contas de usuário usando o PowerShell para o Microsoft 365.

>[!Note]
>Saiba como atribuir  [funções de administrador a](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) contas de usuário com o Centro de administração do Microsoft 365.
>
>Para obter uma lista de recursos adicionais, consulte [Gerenciar usuários e grupos.](https://docs.microsoft.com/microsoft-365/admin/add-users/)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, use uma conta de administrador global para [se conectar ao seu locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Em seguida, identifique o nome de entrada da conta de usuário que você deseja adicionar a uma função (exemplo: fredsm \@ contoso.com). Isso também é conhecido como nome UPN.

Em seguida, determine o nome da função. Confira [as permissões de função de administrador no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

>[!Note]
>Preste atenção às observações neste artigo. Alguns nomes de função são diferentes para o Azure Active Directory (Azure AD) PowerShell. Por exemplo, a função de Administrador do *SharePoint* no centro de administração do Microsoft 365 é Administrador de Serviços do *SharePoint* no Azure AD PowerShell.
>

Em seguida, preencha os nomes de login e função e execute estes comandos:
  
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

Aqui está um exemplo de um conjunto de comandos concluído que atribui a função de Administrador de Serviços do SharePoint à conta contoso.com *usuário: \@*
  
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

Primeiro, use uma conta de administrador global para [se conectar ao seu locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
### <a name="for-a-single-role-change"></a>Para uma única alteração de função

As maneiras mais comuns de especificar a conta de usuário são usando seu nome de exibição ou seu nome de email, também conhecido como nome de logon ou nome UPN.

#### <a name="display-names-of-user-accounts"></a>Exibir nomes de contas de usuário

Se você estiver acostumado a trabalhar com os nomes de exibição de contas de usuário, determine as seguintes informações:
  
- A conta de usuário que você deseja configurar
    
    Para especificar a conta de usuário, você deve determinar seu Nome de Exibição. Para obter uma lista completa de contas, use este comando:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Esse comando lista o Nome de Exibição de suas contas de usuário, organizado pelo Nome de Exibição, uma tela por vez. Você pode filtrar a lista para um conjunto menor usando o cmdlet **Where.** Confira o seguinte exemplo:

   >[!Note]
   >O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes. Execute esses cmdlets do Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Esse comando lista apenas as contas de usuário para as quais o Nome de Exibição começa com "John".
    
- A função que você deseja atribuir
    
    Para exibir a lista de funções de administrador disponíveis que você pode atribuir a contas de usuário, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Depois de determinar o Nome de Exibição da conta e o nome da função, use estes comandos para atribuir a função à conta:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Colar os comandos no Bloco de Notas. Para as *variáveis $dispName* *e $roleName,* substitua o texto de descrição por seus valores. Remova os \< and > caracteres, mas mantenha as aspas. Colar as linhas modificadas no Módulo Microsoft Azure Active Directory para janela do Windows PowerShell para executar as linhas. Como alternativa, você pode usar o Ambiente de Script Integrado (ISE) do Windows PowerShell.
  
Aqui está um exemplo de um conjunto de comandos concluído:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Nomes de login de contas de usuário

Se você estiver acostumado a trabalhar com os nomes de logon ou UPNs de contas de usuário, determine as seguintes informações:
  
- UPN da conta de usuário
    
    Se você não conhece o UPN, use este comando:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Esse comando lista o UPN de suas contas de usuário, organizado por UPN, uma tela por vez. Você pode usar o cmdlet **Where** para filtrar a lista. Exemplo:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Esse comando lista apenas as contas de usuário para as quais o Nome de Exibição começa com "John".
    
- A função que você deseja atribuir
    
    Para exibir a lista de funções disponíveis que você pode atribuir a contas de usuário, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Depois de ter o UPN da conta e o nome da função, use estes comandos para atribuir a função à conta:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Copie os comandos e os colar no Bloco de Notas. Para as **$upnName** e **$roleName** variáveis. Substitua o texto de descrição por seus valores. Remova os \< and > caracteres, mas mantenha as aspas. Colar as linhas modificadas no Módulo Microsoft Azure Active Directory para janela do Windows PowerShell para executar. Como alternativa, você pode usar o ISE do Windows PowerShell.
  
Aqui está um exemplo de um conjunto de comandos concluído:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Várias alterações de função

Para várias alterações de função, determine as seguintes informações:
  
- Quais contas de usuário você deseja configurar. Você pode usar os métodos na seção anterior para coletar o conjunto de nomes de exibição ou UPNs.
    
- Quais funções você deseja atribuir a cada conta de usuário. Para exibir a lista de funções disponíveis que você pode atribuir a contas de usuário, use este comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Em seguida, crie um arquivo de texto de valores separados por vírgula (CSV) que tenha o nome de exibição ou UPN e campos de nome de função. Você pode fazer isso facilmente no Microsoft Excel.

Veja um exemplo de nomes para exibição:
  
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
- [Introdução ao Windows PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
