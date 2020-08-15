---
title: Desabilitar o acesso aos serviços do Microsoft 365 enquanto atribui licenças de usuário
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
ms.openlocfilehash: b027c805638284a78d4e49f4c65518be02e60392
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687140"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="df8d5-103">Desabilitar o acesso aos serviços do Microsoft 365 enquanto atribui licenças de usuário</span><span class="sxs-lookup"><span data-stu-id="df8d5-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="df8d5-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="df8d5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="df8d5-105">As assinaturas do Microsoft 365 vêm com planos de serviço para serviços individuais.</span><span class="sxs-lookup"><span data-stu-id="df8d5-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="df8d5-106">Os administradores do Microsoft 365 geralmente precisam desabilitar determinados planos ao atribuir licenças aos usuários.</span><span class="sxs-lookup"><span data-stu-id="df8d5-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="df8d5-107">Com as instruções deste artigo, você pode atribuir uma licença do Microsoft 365 enquanto desabilita os planos de serviço específicos usando o PowerShell para uma conta de usuário individual ou várias contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="df8d5-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="df8d5-108">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="df8d5-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="df8d5-109">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="df8d5-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="df8d5-110">Em seguida, liste os planos de licença para seu locatário com este comando.</span><span class="sxs-lookup"><span data-stu-id="df8d5-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="df8d5-111">Em seguida, obtenha o nome de entrada da conta para a qual você deseja adicionar uma licença, também conhecido como o nome de usuário principal (UPN).</span><span class="sxs-lookup"><span data-stu-id="df8d5-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="df8d5-112">Em seguida, compile uma lista de serviços a serem habilitados.</span><span class="sxs-lookup"><span data-stu-id="df8d5-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="df8d5-113">Para obter uma lista completa de planos de licença (também conhecidos como nomes de produtos), seus planos de serviço incluídos e seus nomes amigáveis correspondentes, confira [nomes de produtos e identificadores de planos de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="df8d5-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="df8d5-114">Para o bloco de comando abaixo, preencha o nome principal do usuário da conta de usuário, o número de peça do SKU e a lista de planos de serviço para habilitar e remover o texto explicativo e os \< and > caracteres.</span><span class="sxs-lookup"><span data-stu-id="df8d5-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="df8d5-115">Em seguida, execute os comandos resultantes no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df8d5-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
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

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="df8d5-116">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df8d5-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="df8d5-117">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="df8d5-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="df8d5-118">Em seguida, execute este comando para ver suas assinaturas atuais:</span><span class="sxs-lookup"><span data-stu-id="df8d5-118">Next, run this command to see your current subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="df8d5-119">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="df8d5-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="df8d5-120">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df8d5-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="df8d5-121">Na exibição do  `Get-MsolAccountSku` comando:</span><span class="sxs-lookup"><span data-stu-id="df8d5-121">In the display of the  `Get-MsolAccountSku` command:</span></span>
  
- <span data-ttu-id="df8d5-122">**AccountSkuId** é uma assinatura da sua organização em \<OrganizationName> : \<Subscription> Format.</span><span class="sxs-lookup"><span data-stu-id="df8d5-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="df8d5-123">O \<OrganizationName> é o valor que você forneceu quando registrou no Microsoft 365 e é exclusivo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="df8d5-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="df8d5-124">O \<Subscription> valor é para uma assinatura específica.</span><span class="sxs-lookup"><span data-stu-id="df8d5-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="df8d5-125">Por exemplo, para litwareinc: ENTERPRISEPACK, o nome da organização é litwareinc e o nome da assinatura é ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="df8d5-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>
    
- <span data-ttu-id="df8d5-126">**ActiveUnits** é o número de licenças que você comprou para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="df8d5-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>
    
- <span data-ttu-id="df8d5-127">**WarningUnits** é o número de licenças em uma assinatura que você não renovou e que expirarão após o período de cortesia de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="df8d5-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="df8d5-128">**ConsumedUnits** é o número de licenças que você atribuiu aos usuários para a assinatura.</span><span class="sxs-lookup"><span data-stu-id="df8d5-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>
    
<span data-ttu-id="df8d5-129">Observe o AccountSkuId para sua assinatura do Microsoft 365 que contém os usuários que você deseja licenciar.</span><span class="sxs-lookup"><span data-stu-id="df8d5-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="df8d5-130">Além disso, verifique se há licenças suficientes para atribuir (subtrair **ConsumedUnits** de **ActiveUnits** ).</span><span class="sxs-lookup"><span data-stu-id="df8d5-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits** ).</span></span>
  
<span data-ttu-id="df8d5-131">Em seguida, execute este comando para ver os detalhes sobre os planos de serviço do Microsoft 365 que estão disponíveis em todas as suas assinaturas:</span><span class="sxs-lookup"><span data-stu-id="df8d5-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="df8d5-132">Na exibição desse comando, determine quais planos de serviço você deseja desabilitar ao atribuir licenças aos usuários.</span><span class="sxs-lookup"><span data-stu-id="df8d5-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>
  
<span data-ttu-id="df8d5-133">Veja a seguir uma lista parcial de planos de serviço e seus serviços do Microsoft 365 correspondentes.</span><span class="sxs-lookup"><span data-stu-id="df8d5-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="df8d5-134">A tabela a seguir mostra os planos de serviço do Microsoft 365 e seus nomes amigáveis para os serviços mais comuns.</span><span class="sxs-lookup"><span data-stu-id="df8d5-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="df8d5-135">Sua lista de planos de serviço pode ser diferente.</span><span class="sxs-lookup"><span data-stu-id="df8d5-135">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="df8d5-136">**Plano de serviço**</span><span class="sxs-lookup"><span data-stu-id="df8d5-136">**Service plan**</span></span>|<span data-ttu-id="df8d5-137">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="df8d5-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="df8d5-138">Sway</span><span class="sxs-lookup"><span data-stu-id="df8d5-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="df8d5-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df8d5-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="df8d5-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="df8d5-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="df8d5-141">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="df8d5-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="df8d5-142">Microsoft 365 Apps for Enterprise *(anteriormente chamado Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="df8d5-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="df8d5-143">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="df8d5-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="df8d5-144">Office</span><span class="sxs-lookup"><span data-stu-id="df8d5-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="df8d5-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="df8d5-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="df8d5-146">Plano 2 do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="df8d5-146">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="df8d5-147">Para obter uma lista completa de planos de licença (também conhecidos como nomes de produtos), seus planos de serviço incluídos e seus nomes amigáveis correspondentes, confira [nomes de produtos e identificadores de planos de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="df8d5-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
   
<span data-ttu-id="df8d5-148">Agora que você tem o AccountSkuId e os planos de serviço para desabilitar, é possível atribuir licenças para um usuário individual ou para vários usuários.</span><span class="sxs-lookup"><span data-stu-id="df8d5-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>
  
### <a name="for-a-single-user"></a><span data-ttu-id="df8d5-149">Para um único usuário</span><span class="sxs-lookup"><span data-stu-id="df8d5-149">For a single user</span></span>

<span data-ttu-id="df8d5-150">Para um único usuário, preencha o nome principal do usuário da conta de usuário, o AccountSkuId e a lista de planos de serviço para desabilitar e remover o texto explicativo e os \< and > caracteres.</span><span class="sxs-lookup"><span data-stu-id="df8d5-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="df8d5-151">Em seguida, execute os comandos resultantes no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df8d5-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="df8d5-152">Aqui está um exemplo de bloco de comando para a conta chamada belindan@contoso.com, para a licença contoso: ENTERPRISEPACK e os planos de serviço a serem desabilitados são RMS_S_ENTERPRISE, SWAY, INTUNE_O365 e YAMMER_ENTERPRISE:</span><span class="sxs-lookup"><span data-stu-id="df8d5-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="df8d5-153">Para vários usuários</span><span class="sxs-lookup"><span data-stu-id="df8d5-153">For multiple users</span></span>

<span data-ttu-id="df8d5-154">Para executar essa tarefa de administração para vários usuários, crie um arquivo de texto de valor separado por vírgula (CSV) que contenha os campos UserPrincipalName e UsageLocation.</span><span class="sxs-lookup"><span data-stu-id="df8d5-154">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields.</span></span> <span data-ttu-id="df8d5-155">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="df8d5-155">Here is an example:</span></span>
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="df8d5-156">Em seguida, preencha o local dos arquivos CSV de entrada e saída, a ID SKU da conta e a lista de planos de serviço a serem desabilitados e, em seguida, execute os comandos resultantes no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df8d5-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>
  
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

<span data-ttu-id="df8d5-157">Este bloco de comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="df8d5-157">This PowerShell command block:</span></span>
  
- <span data-ttu-id="df8d5-158">Exibe o nome principal do usuário de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="df8d5-158">Displays the user principal name of each user.</span></span>
    
- <span data-ttu-id="df8d5-159">Atribui licenças personalizadas a cada usuário.</span><span class="sxs-lookup"><span data-stu-id="df8d5-159">Assigns customized licenses to each user.</span></span>
    
- <span data-ttu-id="df8d5-160">Cria um arquivo CSV com todos os usuários que foram processados e mostra o status da licença.</span><span class="sxs-lookup"><span data-stu-id="df8d5-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="df8d5-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="df8d5-161">See also</span></span>

[<span data-ttu-id="df8d5-162">Desabilitar o acesso aos serviços do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="df8d5-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="df8d5-163">Desabilitar o acesso ao Sway com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="df8d5-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="df8d5-164">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="df8d5-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="df8d5-165">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="df8d5-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
