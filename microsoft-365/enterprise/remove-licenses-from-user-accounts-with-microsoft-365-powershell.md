---
title: Remover licenças do Microsoft 365 de contas de usuário com o PowerShell
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: Explica como usar o PowerShell para remover licenças do Microsoft 365 que foram atribuídas anteriormente aos usuários.
ms.openlocfilehash: 7651f300dbf7a57ce163096d500401365e624663
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235449"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a>Remover licenças do Microsoft 365 das contas de usuário com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

>[!Note]
>[Saiba como remover licenças de contas de usuário](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) com o Centro de administração do Microsoft 365. Para obter uma lista de recursos adicionais, consulte [Gerenciar usuários e grupos.](https://docs.microsoft.com/microsoft-365/admin/add-users/)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

Em seguida, liste os planos de licença para seu locatário com este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Em seguida, obter o nome de logon da conta para a qual você deseja remover uma licença, também conhecida como nome UPN.

Por fim, especifique os nomes dos planos de licença e de login do usuário, remova os caracteres "<" e ">" e execute estes comandos.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

Para remover todas as licenças de uma conta de usuário específica, especifique o nome de login do usuário, remova os caracteres "<" e ">" e execute estes comandos.

```powershell
$userUPN="<user sign-in name (UPN)>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
if($userList -is [array]) {
for ($i=0; $i -lt $userList.Count; $i++) {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList[$i].SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList[$i].SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}
} else {
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = $userList.SkuId
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$Licenses.AddLicenses = @()
$Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $userList.SkuId -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
}}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
   
Para exibir as informações do plano de licenciamento (**AccountSkuID**) em sua organização, confira os tópicos a seguir:
    
  - [Exibir licenças e serviços com o PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [Exibir detalhes de licença de conta e serviço com o PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Se você usar o cmdlet **Get-MsolUser** sem usar o parâmetro _-All_, somente as primeiras 500 contas serão retornadas.
    
### <a name="removing-licenses-from-user-accounts"></a>Removendo licenças de contas de usuário

Para remover licenças de uma conta de usuário existente, use a seguinte sintaxe:
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

Este exemplo remove a **licença litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) da conta de usuário BelindaN@litwareinc.com.
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
>Não é possível usar `Set-MsolUserLicense` o cmdlet para cancelar a asignção de usuários *de licenças canceladas.* Você deve fazer isso individualmente para cada conta de usuário no Centro de administração do Microsoft 365.
>

Para remover todas as licenças de um grupo de usuários licenciados existentes, use um dos seguintes métodos:
  
- **Filtrar as contas com base em um atributo de conta existente** Para fazer isso, use a seguinte sintaxe:
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

Este exemplo remove todas as licenças de todas as contas de usuário no departamento de vendas nos Estados Unidos.
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- **Usar uma lista de contas específicas para uma licença específica** Para fazer isso, execute as seguintes etapas:
    
1. Crie e salve um arquivo de texto que contenha uma conta em cada linha da seguinte forma:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. Use a sintaxe a seguir:
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
Este exemplo remove a licença **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) das contas de usuário definidas no arquivo de texto C:\My Documents\Accounts.txt.
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

Para remover todas as licenças de todas as contas de usuário existentes, use a seguinte sintaxe:
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

Outra maneira de liberar uma licença é excluir a conta de usuário. Para obter mais informações, consulte [Excluir e restaurar contas de usuário com o PowerShell.](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
  
## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)

