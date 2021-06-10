---
title: Excluir Microsoft 365 de usuário com o PowerShell
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
description: Saiba como usar diferentes módulos no PowerShell para excluir Microsoft 365 de usuário.
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919135"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Excluir Microsoft 365 de usuário com o PowerShell

Você pode usar o PowerShell para Microsoft 365 excluir e restaurar contas de usuário.

>[!Note]
>Saiba como restaurar [uma conta de usuário](../admin/add-users/restore-user.md) usando o Microsoft 365 de administração.
>
>Para obter uma lista de recursos adicionais, consulte [Gerenciar usuários e grupos.](../admin/add-users/index.yml)
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Depois de se conectar, use a seguinte sintaxe para remover uma conta de usuário individual:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

Este exemplo remove o fabricec da conta *de \@ usuário litwareinc.com*.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> O parâmetro *-ObjectID* no cmdlet **Remove-AzureADUser** aceita o nome de entrada da conta, também conhecido como Nome principal do usuário ou A ID do objeto da conta.
  
Para exibir o nome da conta com base no nome do usuário, use os seguintes comandos:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Este exemplo exibe o nome da conta do usuário *Caleb Sills*.
  
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

Quando você exclui uma conta de usuário por meio Microsoft Azure Active Directory módulo para Windows PowerShell, a conta não é excluída permanentemente. Você pode restaurar a conta de usuário excluída no prazo de 30 dias.

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Para excluir uma conta de usuário, use a seguinte sintaxe:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes. Execute esses cmdlets do Windows PowerShell.
>

Este exemplo exclui a conta de usuário *BelindaN@litwareinc.com*.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Para restaurar uma conta de usuário excluída no período de tolerância de 30 dias, use a seguinte sintaxe:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

Este exemplo restaura a conta excluída *BelindaN \@ litwareinc.com*.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> Para ver a lista de usuários excluídos que pode ser restaurados, execute o seguinte comando:
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> Se o nome UPN (nome principal do usuário) original da conta de usuário for usado por outra conta, use o parâmetro _NewUserPrincipalName_ no lugar de _UserPrincipalName_ para especificar um UPN diferente ao restaurar a conta de usuário.


## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao Windows PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)