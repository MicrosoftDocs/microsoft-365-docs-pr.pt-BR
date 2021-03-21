---
title: Desabilitar o acesso aos serviços do Microsoft 365 ao atribuir licenças de usuário
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Saiba como atribuir licenças a contas de usuário e desabilitar planos de serviço específicos ao mesmo tempo usando o PowerShell para o Microsoft 365.
ms.openlocfilehash: 7486968f6f4822047a1697ee1e05129277fd11a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929427"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>Desabilitar o acesso aos serviços do Microsoft 365 ao atribuir licenças de usuário

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

As assinaturas do Microsoft 365 vêm com planos de serviço para serviços individuais. Os administradores do Microsoft 365 geralmente precisam desabilitar determinados planos ao atribuir licenças aos usuários. Com as instruções deste artigo, você pode atribuir uma licença do Microsoft 365 ao desabilitar planos de serviço específicos usando o PowerShell para uma conta de usuário individual ou várias contas de usuário.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use o PowerShell do Azure Active Directory para o módulo do gráfico

Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

Em seguida, liste os planos de licença para seu locatário com este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Em seguida, obter o nome de logon da conta à qual você deseja adicionar uma licença, também conhecida como o nome principal do usuário (UPN).

Em seguida, compile uma lista de serviços para habilitar. Para uma lista completa de planos de licença (também conhecidos como nomes de produtos), seus planos de serviço incluídos e seus nomes amigáveis correspondentes, consulte [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Para o bloco de comando abaixo, preencha o nome principal do usuário da conta de usuário, o número da parte SKU e a lista de planos de serviço para habilitar e remover o texto explicativo e os \< and > caracteres. Em seguida, execute os comandos resultantes no prompt de comando do PowerShell.
  
```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.

Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Em seguida, execute este comando para ver suas assinaturas atuais:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome. Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.
>

Na exibição do  `Get-MsolAccountSku` comando:
  
- **AccountSkuId** é uma assinatura da sua organização em \<OrganizationName> : \<Subscription> formato. O é o valor que você forneceu ao se inscrever no \<OrganizationName> Microsoft 365 e é exclusivo para sua organização. O \<Subscription> valor é para uma assinatura específica. Por exemplo, para litwareinc:ENTERPRISEPACK, o nome da organização é litwareinc e o nome da assinatura é ENTERPRISEPACK (Office 365 Enterprise E3).
    
- **ActiveUnits** é o número de licenças que você comprou para a assinatura.
    
- **WarningUnits** é o número de licenças em uma assinatura que você não renovou e que expirará após o período de carência de 30 dias.
    
- **ConsumedUnits** é o número de licenças atribuídas aos usuários para a assinatura.
    
Observe o AccountSkuId para sua assinatura do Microsoft 365 que contém os usuários que você deseja licenciar. Além disso, verifique se há licenças suficientes para atribuir (subtrair **ConsumedUnits** de **ActiveUnits** ).
  
Em seguida, execute este comando para ver os detalhes sobre os planos de serviço do Microsoft 365 que estão disponíveis em todas as suas assinaturas:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

Na exibição deste comando, determine quais planos de serviço você gostaria de desabilitar ao atribuir licenças aos usuários.
  
Aqui está uma lista parcial de planos de serviço e seus serviços correspondentes do Microsoft 365.

A tabela a seguir mostra os planos de serviço do Microsoft 365 e seus nomes amigáveis para os serviços mais comuns. Sua lista de planos de serviço pode ser diferente. 
  
|**Plano de serviço**|**Descrição**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Aplicativos do Microsoft 365 para empresas *(anteriormente denominado Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Plano 2 do Exchange Online  <br/> |
   
Para uma lista completa de planos de licença (também conhecidos como nomes de produtos), seus planos de serviço incluídos e seus nomes amigáveis correspondentes, consulte [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).
   
Agora que você tem o AccountSkuId e os planos de serviço para desabilitar, você pode atribuir licenças para um usuário individual ou para vários usuários.
  
### <a name="for-a-single-user"></a>Para um único usuário

Para um único usuário, preencha o nome principal do usuário da conta de usuário, o AccountSkuId e a lista de planos de serviço para desabilitar e remover o texto explicativo e os \< and > caracteres. Em seguida, execute os comandos resultantes no prompt de comando do PowerShell.
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

Aqui está um exemplo de bloco de comando para a conta chamada belindan@contoso.com, para a licença contoso:ENTERPRISEPACK, e os planos de serviço a desabilitar são RMS_S_ENTERPRISE, SWAY, INTUNE_O365 e YAMMER_ENTERPRISE:
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a>Para vários usuários

Para executar essa tarefa de administração para vários usuários, crie um arquivo de texto CSV (valor separado por vírgula) que contém os campos UserPrincipalName e UsageLocation. Veja um exemplo:
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

Em seguida, preencha o local dos arquivos CSV de entrada e saída, a ID SKU da conta e a lista de planos de serviço a desabilitar e execute os comandos resultantes no prompt de comando do PowerShell.
  
```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

Este bloco de comando do PowerShell:
  
- Exibe o nome principal do usuário de cada usuário.
    
- Atribui licenças personalizadas a cada usuário.
    
- Cria um arquivo CSV com todos os usuários que foram processados e mostra seu status de licença.
    
## <a name="see-also"></a>Confira também

[Desabilitar o acesso aos serviços do Microsoft 365 com o PowerShell](disable-access-to-services-with-microsoft-365-powershell.md)
  
[Desabilitar o acesso ao Sway com o PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)