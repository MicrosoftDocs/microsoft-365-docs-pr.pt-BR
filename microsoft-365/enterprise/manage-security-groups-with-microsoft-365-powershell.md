---
title: Gerenciar grupos de segurança com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: Saiba como usar o PowerShell para gerenciar grupos de segurança.
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073185"
---
# <a name="manage-security-groups-with-powershell"></a>Gerenciar grupos de segurança com o PowerShell

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Você pode usar o PowerShell para Microsoft 365 como uma alternativa para o centro de administração do Microsoft 365 para gerenciar grupos de segurança. 

Este artigo descreve a listagem, a criação, a alteração das configurações e a remoção de grupos de segurança. 

Quando um bloco de comando neste artigo requer que você especifique valores de variáveis, use estas etapas.

1. Copie o bloco de comando para a área de transferência e cole-o no bloco de notas ou no ambiente de script integrado (ISE) do PowerShell.
2. Preencha os valores de variáveis e remova os caracteres "<" e ">".
3. Execute os comandos na janela do PowerShell ou no ISE do PowerShell.

Confira [manter a associação de grupo de segurança](maintain-group-membership-with-microsoft-365-powershell.md) para gerenciar a associação de grupo com o PowerShell.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="list-your-groups"></a>Listar seus grupos

Use este comando para listar todos os seus grupos.

```powershell
Get-AzureADGroup
```
Use estes comandos para exibir as configurações de um grupo específico por seu nome de exibição.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Criar um novo grupo

Use este comando para criar um novo grupo de segurança.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>Alterar as configurações em um grupo

Exibir as configurações do grupo com estes comandos.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Em seguida, use o artigo [set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) para determinar como alterar uma configuração.

### <a name="remove-a-security-group"></a>Remover um grupo de segurança

Use estes comandos para remover um grupo de segurança.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>Gerenciar os proprietários de um grupo de segurança

Use estes comandos para exibir os proprietários atuais de um grupo de segurança.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
Use estes comandos para adicionar uma conta de usuário pelo **nome principal do usuário (UPN)** aos proprietários atuais de um grupo de segurança.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Use estes comandos para adicionar uma conta de usuário pelo **nome de exibição** aos proprietários atuais de um grupo de segurança.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Use estes comandos para remover uma conta de usuário por seu **UPN** para os proprietários atuais de um grupo de segurança.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Use estes comandos para remover uma conta de usuário pelo **nome de exibição** para os proprietários atuais de um grupo de segurança.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="list-your-groups"></a>Listar seus grupos

Use este comando para listar todos os seus grupos.

```powershell
Get-MsolGroup
```
Use estes comandos para exibir as configurações de um grupo específico por seu nome de exibição.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Criar um novo grupo

Use este comando para criar um novo grupo de segurança.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>Alterar as configurações em um grupo

Exibir as configurações do grupo com estes comandos.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Em seguida, use o artigo [set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) para determinar como alterar uma configuração.

### <a name="remove-a-security-group"></a>Remover um grupo de segurança

Use estes comandos para remover um grupo de segurança.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)

