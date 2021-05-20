---
title: Atribuir licenças de Microsoft 365 a contas de usuário com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: Neste artigo, saiba como usar o PowerShell para atribuir uma licença de Microsoft 365 a usuários não licenciados.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572616"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Atribuir licenças de Microsoft 365 a contas de usuário com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Os usuários não podem usar nenhum serviço Microsoft 365 até que sua conta tenha sido atribuída uma licença de um plano de licenciamento. Você pode usar o PowerShell para atribuir rapidamente licenças a contas não licenciadas. 

As contas de usuário devem primeiro ser atribuídas a um local. Especificar um local é uma parte necessária da criação de uma nova conta de usuário no [centro administrativo Microsoft 365](../admin/add-users/add-users.md). 

As contas sincronizadas a partir de seus serviços de domínio do Active Directory no local não têm por padrão um local especificado. Você pode configurar um local para essas contas de:

- O Centro de administração do Microsoft 365
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - O [portal Azure](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) –**Active Directory**  >  **Users** > conta de usuário > **Informações de** Contato de Perfil País ou  >    >  **região**).

>[!Note]
>[Saiba como atribuir licenças a contas de usuários](../admin/manage/assign-licenses-to-users.md) com o centro administrativo Microsoft 365. Para obter uma lista de recursos adicionais, consulte [Gerenciar usuários e grupos](../admin/add-users/index.yml).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [conecte-se ao seu inquilino Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

Em seguida, liste os planos de licença para o seu inquilino com este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Em seguida, obtenha o nome de login da conta à qual deseja adicionar uma licença, também conhecida como nome principal do usuário (UPN).

Em seguida, certifique-se de que a conta de usuário tenha um local de uso atribuído.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Se não houver nenhum local de uso atribuído, você pode atribuir um com esses comandos:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Finalmente, especifique o nome do nome de login do usuário e o nome do plano de licença e execute esses comandos.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Por favor, note que começaremos a depreciar este módulo quando a funcionalidade deste módulo estiver disponível no mais novo [Azure Active Directory PowerShell para Graph](/powershell/azuread/v2/azureactivedirectory) módulo. Aconselhamos os clientes que estão criando novos scripts PowerShell a usar o módulo mais novo em vez deste módulo.

Primeiro, [conecte-se ao seu inquilino Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Execute o `Get-MsolAccountSku` comando para visualizar os planos de licenciamento disponíveis e o número de licenças disponíveis em cada plano em sua organização. O número de licenças disponíveis em cada plano é **de Unidades**  -  **de Aviso**  -  **ativas consumidas.** Para obter mais informações sobre planos de licenciamento, licenças e serviços, consulte [licenças e serviços com o PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

Para encontrar as contas não licenciadas em sua organização, execute este comando.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Você só pode atribuir licenças a contas de usuário que tenham a propriedade **UseLocation** definida para um código de país ISO 3166-1 alfa-2 válido. Por exemplo, US para os Estados Unidos e FR para a França. Alguns serviços Microsoft 365 não estão disponíveis em certos países. Para obter mais informações, consulte [Sobre restrições de licença](https://go.microsoft.com/fwlink/p/?LinkId=691730).
    
Para encontrar contas que não tenham um valor **de Localização de uso,** execute este comando.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Para definir o valor **de Localização de uso** em uma conta, execute este comando.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Por exemplo:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Se você usar o cmdlet **Get-MsolUser** sem usar o parâmetro **-All**, somente as primeiras 500 contas serão retornadas.

### <a name="assigning-licenses-to-user-accounts"></a>Atribuindo licenças a contas de usuários
    
Para atribuir uma licença a um usuário, use o seguinte comando no PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

Este exemplo atribui uma licença do plano de licenciamento **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ao usuário não licenciado **belindan \@ litwareinc.com:**
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Para atribuir uma licença a todos os usuários não licenciados, execute este comando.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>Você não pode atribuir várias licenças a um usuário do mesmo plano de licenciamento. Se você não tiver licenças o suficiente disponíveis, as licenças serão atribuídas aos usuários na ordem em que eles forem retornados pelo cmdlet **Get-MsolUser** até que as licenças disponíveis esgotem.
>

Este exemplo atribui licenças do plano de licenciamento **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) a todos os usuários não licenciados:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Este exemplo atribui essas mesmas licenças a usuários não licenciados no departamento de Vendas nos Estados Unidos:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Mova um usuário para uma assinatura diferente (plano de licença) com o Azure Active Directory PowerShell para Graph módulo

Primeiro, [conecte-se ao seu inquilino Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Em seguida, obtenha o nome de login da conta de usuário para a qual você deseja assinaturas do switch, também conhecido como o nome principal do usuário (UPN).

Em seguida, liste as assinaturas (planos de licença) para o seu inquilino com este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Em seguida, liste as assinaturas que a conta de usuário tem atualmente com esses comandos.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Identifique a assinatura que o usuário tem atualmente (a assinatura FROM) e a assinatura para a qual o usuário está se movendo (a assinatura TO).

Finalmente, especifique os nomes de assinatura TO e FROM (números de peças SKU) e execute esses comandos.

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

Você pode verificar a alteração na assinatura da conta de usuário com esses comandos.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>Confira também

[Gerenciar contas de usuário, licenças e grupos com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
