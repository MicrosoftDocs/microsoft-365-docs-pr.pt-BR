---
title: Bloquear Microsoft 365 contas de usuário com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Como usar o PowerShell para bloquear e desbloquear o acesso a Microsoft 365 contas.
ms.openlocfilehash: 90d712cdb6eb34d0588fc262e3a02673accfbd9e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287216"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Bloquear Microsoft 365 contas de usuário com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Quando você bloqueia o acesso a uma conta Microsoft 365, impede que qualquer pessoa use a conta para entrar e acessar os serviços e dados em sua Microsoft 365 organização. Você pode usar o PowerShell para bloquear o acesso a contas de usuário individuais ou múltiplas.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="block-access-to-individual-user-accounts"></a>Bloquear o acesso a contas de usuário individuais

Use a seguinte sintaxe para bloquear uma conta de usuário individual:

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> O *parâmetro -ObjectID* no cmdlet **Set-AzureAD** aceita o nome de entrada da conta, também conhecido como Nome principal do usuário ou a ID do objeto da conta.

Este exemplo bloqueia o acesso à conta de *usuário fabricec@litwareinc.com*.

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Para desbloquear essa conta de usuário, execute o seguinte comando:

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

Para exibir o UPN da conta de usuário com base no nome de exibição do usuário, use os seguintes comandos:

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

Este exemplo exibe o UPN da conta de usuário para o usuário  *Caleb Sills*.

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Para bloquear uma conta com base no nome de exibição do usuário, use os seguintes comandos:

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Para verificar o status bloqueado de uma conta de usuário, use o seguinte comando:

```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Bloquear várias contas de usuário

Para bloquear o acesso a várias contas de usuário, crie um arquivo de texto que contenha um nome de entrada de conta em cada linha como esta:

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

Nos comandos a seguir, o arquivo de texto de *exemplo é C:\My Documents\Accounts.txt*. Substitua esse nome de arquivo pelo caminho e o nome do arquivo de texto.

Para bloquear o acesso às contas listadas no arquivo de texto, execute o seguinte comando:

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

Para desbloquear as contas listadas no arquivo de texto, execute o seguinte comando:

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="block-individual-user-accounts"></a>Bloquear contas de usuário individuais

Use a seguinte sintaxe para bloquear o acesso a uma conta de usuário individual:

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>O PowerShell Core não dá suporte ao módulo Microsoft Azure Active Directory para Windows PowerShell e cmdlets que têm *Msol* em seu nome. Você precisa executar esses cmdlets de Windows PowerShell.

Este exemplo bloqueia o acesso ao fabricec da conta *de \@ usuário litwareinc.com*.

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Para desbloquear a conta do usuário, execute o seguinte comando:

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Para verificar o status bloqueado de uma conta de usuário, execute o seguinte comando:

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>Bloquear o acesso a várias contas de usuário

Primeiro, crie um arquivo de texto que contenha uma conta em cada linha como esta:

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

Nos comandos a seguir, o arquivo de texto de *exemplo é C:\My Documents\Accounts.txt*. Substitua esse nome de arquivo pelo caminho e o nome do arquivo de texto.

Para bloquear o acesso às contas listadas no arquivo de texto, execute o seguinte comando:

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Para desbloquear as contas listadas no arquivo de texto, execute o seguinte comando:

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>Veja também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Introdução ao Windows PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
