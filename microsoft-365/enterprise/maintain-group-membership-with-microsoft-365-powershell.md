---
title: Manter a associação de grupo do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Saiba como usar o PowerShell para manter a associação nos grupos do Microsoft 365.
ms.openlocfilehash: 61bdcb96433f4f384033768debf416900a305624
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687412"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a>Manter a associação de grupo do Microsoft 365 com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Você pode usar o PowerShell para o Microsoft 365 como uma alternativa para o centro de administração do Microsoft 365 para manter a associação de grupo no Microsoft 365. 

> [!TIP]
> Para gerar comandos do PowerShell prontos para execução especificando os nomes de conta e de grupo do usuário, use esta [pasta de trabalho de manutenção de grupo do Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx). 

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico
Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Adicionar ou remover contas de usuário como membros de um grupo

**Para adicionar uma conta de usuário por seu UPN**, preencha o nome principal do usuário (UPN) da conta de usuário (exemplo: belindan@contoso.com) e o nome de exibição do grupo, removendo os caracteres "<" e ">" e execute esses comandos na janela do PowerShell ou no ISE (ambiente de script integrado) do PowerShell.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Para adicionar uma conta de usuário pelo seu nome de exibição**, preencha o nome de exibição da conta de usuário (exemplo: Belinda Newman) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Para remover uma conta de usuário por seu UPN**, preencha o UPN da conta de usuário (exemplo: belindan@contoso.com) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Para remover uma conta de usuário pelo seu nome de exibição**, preencha o nome de exibição da conta de usuário (exemplo: Belinda Newman) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Adicionar ou remover grupos como membros de um grupo

Os grupos de segurança podem conter outros grupos como membros. Os grupos do Microsoft 365, no entanto, não podem. Esta seção contém comandos do PowerShell para adicionar ou remover grupos apenas de um grupo de segurança.

**Para adicionar um grupo por seu nome de exibição**, preencha o nome de exibição do grupo que você adicionará e o nome de exibição do grupo que conterá o grupo de membros e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Para remover um grupo por seu nome de exibição**, preencha o nome de exibição do grupo que você vai remover e o nome de exibição do grupo que conterá o grupo de membros e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Adicionar ou remover contas de usuário como membros de um grupo

**Para adicionar uma conta de usuário por seu UPN**, preencha o nome principal do usuário (UPN) da conta de usuário (exemplo: belindan@contoso.com) e o nome de exibição do grupo, removendo os caracteres "<" e ">" e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Para adicionar uma conta de usuário pelo seu nome de exibição**, preencha o nome de exibição da conta de usuário (exemplo: Belinda Newman) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Para remover uma conta de usuário por seu UPN**, preencha o UPN da conta de usuário (exemplo: belindan@contoso.com) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Para remover uma conta de usuário pelo seu nome de exibição**, preencha o nome de exibição da conta de usuário (exemplo: Belinda Newman) e o nome de exibição do grupo e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Adicionar ou remover grupos como membros de um grupo

Os grupos de segurança podem conter outros grupos como membros. Os grupos do Microsoft 365, no entanto, não podem. Esta seção contém comandos do PowerShell para adicionar ou remover grupos apenas de um grupo de segurança.

**Para adicionar um grupo por seu nome de exibição**, preencha o nome de exibição do grupo que você adicionará e o nome de exibição do grupo que conterá o grupo de membros e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

**Para remover um grupo por seu nome de exibição**, preencha o nome de exibição do grupo que você vai remover e o nome de exibição do grupo que conterá o grupo de membros e execute esses comandos na janela do PowerShell ou no ISE do PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)

