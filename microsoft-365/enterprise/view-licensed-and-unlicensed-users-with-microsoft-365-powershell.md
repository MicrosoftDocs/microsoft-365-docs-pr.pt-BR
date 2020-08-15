---
title: Exibir usuários do Microsoft 365 licenciados e não licenciados com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: Este artigo explica como usar o PowerShell para exibir contas de usuário licenciadas e não licenciadas do Microsoft 365.
ms.openlocfilehash: 8a99ba2a80f1d814ec5268c4f8f479837eb54dc0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687096"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a>Exibir usuários do Microsoft 365 licenciados e não licenciados com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

As contas de usuário na sua organização do Microsoft 365 podem ter algumas, todas ou nenhuma das licenças disponíveis atribuídas a eles dos planos de licenciamento disponíveis em sua organização. Você pode usar o PowerShell para a Microsoft 365 para encontrar rapidamente os usuários licenciados e não licenciados em sua organização.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
Para exibir a lista de todas as contas de usuário em sua organização que não tenham sido atribuídos a nenhum dos seus planos de licenciamento (usuários não licenciados), execute o seguinte comando:
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

Para exibir a lista de todas as contas de usuário em sua organização que foram atribuídas a qualquer um dos seus planos de licenciamento (usuários licenciados), execute o seguinte comando:
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
>Para listar todos os usuários em sua assinatura, use o `Get-AzureAdUser -All $true` comando.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Para exibir a lista de todas as contas de usuário e seu status de licenciamento em sua organização, execute o seguinte comando no PowerShell:
  
```powershell
Get-MsolUser -All
```

>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

Para visualizar a lista de todas as contas de usuários não licenciados em sua organização, execute o seguinte comando:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Para visualizar a lista de todas as contas de usuários licenciados em sua organização, execute o seguinte comando:
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
