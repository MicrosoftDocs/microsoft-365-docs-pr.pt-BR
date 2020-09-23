---
title: Excluir contas de usuário do Microsoft 365 com o PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Neste artigo, saiba como usar módulos diferentes no PowerShell para excluir contas de usuário do Microsoft 365.
ms.openlocfilehash: 0c13b57c13fb3d01d648438a5d6973fea8b9db67
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235437"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Excluir contas de usuário do Microsoft 365 com o PowerShell

Você pode usar o PowerShell para Microsoft 365 para excluir e restaurar uma conta de usuário.

>[!Note]
>[Saiba como restaurar uma conta de usuário](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) com o centro de administração do Microsoft 365. Para obter uma lista de recursos adicionais, consulte [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Após a conexão, use a seguinte sintaxe para remover uma conta de usuário individual:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

Este exemplo remove a conta de usuário ricardoc@litwareinc.com.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> O parâmetro **-ObjectID** no cmdlet **Remove-AzureADUser** aceita o nome de entrada da conta, também conhecido como o nome principal do usuário, ou a ID de objeto da conta.
  
Para exibir o nome da conta com base no nome do usuário, use os seguintes comandos:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Este exemplo exibe o nome da conta do usuário Carlos Lima.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Para remover uma conta com base no nome de exibição do usuário, use os seguintes comandos:
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Quando você exclui uma conta de usuário com o Módulo Microsoft Azure Active Directory para Windows PowerShell, ela não é excluída permanentemente. Você pode restaurar a conta de usuário excluída no prazo de 30 dias.

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Para excluir uma conta de usuário, use a seguinte sintaxe:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

Este exemplo exclui a conta de usuário BrendaF@litwareinc.com.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Para restaurar uma conta de usuário excluída no período de tolerância de 30 dias, use a seguinte sintaxe:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

Este exemplo restaura a conta excluída BrendaF@litwareinc.com.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 **Observações:**
  
- Para ver a lista de usuários excluídos que pode ser restaurados, execute o seguinte comando:
    
  ```powershell
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- Se o nome UPN (nome principal do usuário) original da conta de usuário for usado por outra conta, use o parâmetro _NewUserPrincipalName_ no lugar de _UserPrincipalName_ para especificar um UPN diferente ao restaurar a conta de usuário.


## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
