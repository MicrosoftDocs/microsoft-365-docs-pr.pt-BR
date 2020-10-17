---
title: Atribuir licenças do Microsoft 365 a contas de usuário com o PowerShell
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
description: Neste artigo, saiba como usar o PowerShell para atribuir uma licença do Microsoft 365 a usuários não licenciados.
ms.openlocfilehash: 8c3165b99477afa14e6d2b0da927b5f64c416ef1
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580935"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="11d47-103">Atribuir licenças do Microsoft 365 a contas de usuário com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="11d47-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="11d47-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="11d47-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="11d47-105">Os usuários não podem usar serviços do Microsoft 365 até que a conta tenha sido atribuída a uma licença de um plano de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="11d47-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="11d47-106">Você pode usar o PowerShell para atribuir licenças rapidamente às contas não licenciadas.</span><span class="sxs-lookup"><span data-stu-id="11d47-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="11d47-107">É necessário atribuir um local às contas de usuário primeiro.</span><span class="sxs-lookup"><span data-stu-id="11d47-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="11d47-108">A especificação de um local é uma parte obrigatória da criação de uma nova conta de usuário no [centro de administração do Microsoft 365](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="11d47-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="11d47-109">As contas sincronizadas de seus serviços de domínio do Active Directory local não possuem um local especificado.</span><span class="sxs-lookup"><span data-stu-id="11d47-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="11d47-110">Você pode configurar um local para estas contas de:</span><span class="sxs-lookup"><span data-stu-id="11d47-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="11d47-111">O Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="11d47-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="11d47-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="11d47-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="11d47-113">O [portal do Azure](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (usuários do**Active Directory**  >  **Users** > conta de usuário > **Profile**  >  **informações**  >  **de contato de perfil país ou região**).</span><span class="sxs-lookup"><span data-stu-id="11d47-113">The [Azure portal](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="11d47-114">[Saiba como atribuir licenças a contas de usuário](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) com o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="11d47-114">[Learn how to assign licenses to user accounts](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="11d47-115">Para obter uma lista de recursos adicionais, consulte [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="11d47-115">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="11d47-116">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="11d47-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="11d47-117">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="11d47-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="11d47-118">Em seguida, liste os planos de licença para seu locatário com este comando.</span><span class="sxs-lookup"><span data-stu-id="11d47-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="11d47-119">Em seguida, obtenha o nome de entrada da conta para a qual você deseja adicionar uma licença, também conhecido como o nome de usuário principal (UPN).</span><span class="sxs-lookup"><span data-stu-id="11d47-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="11d47-120">Em seguida, verifique se a conta de usuário tem um local de uso atribuído.</span><span class="sxs-lookup"><span data-stu-id="11d47-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="11d47-121">Se não houver nenhum local de uso atribuído, você poderá atribuir um com estes comandos:</span><span class="sxs-lookup"><span data-stu-id="11d47-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="11d47-122">Por fim, especifique o nome de entrada do usuário e o nome do plano de licença e execute esses comandos.</span><span class="sxs-lookup"><span data-stu-id="11d47-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="11d47-123">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11d47-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="11d47-124">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="11d47-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="11d47-125">Execute o `Get-MsolAccountSku` comando para exibir os planos de licenciamento disponíveis e o número de licenças disponíveis em cada plano da sua organização.</span><span class="sxs-lookup"><span data-stu-id="11d47-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="11d47-126">O número de licenças disponíveis em cada plano é **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="11d47-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="11d47-127">Para obter mais informações sobre planos de licenciamento, licenças e serviços, consulte [Exibir licenças e serviços com o PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="11d47-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="11d47-128">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="11d47-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="11d47-129">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11d47-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="11d47-130">Para localizar as contas não licenciadas em sua organização, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="11d47-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="11d47-131">Você só pode atribuir licenças a contas de usuário que tenham a propriedade **UsageLocation** definida para um código de país 3166-1 do país de 2 Alpha válido.</span><span class="sxs-lookup"><span data-stu-id="11d47-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="11d47-132">Por exemplo, US para os Estados Unidos e FR para a França.</span><span class="sxs-lookup"><span data-stu-id="11d47-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="11d47-133">Alguns serviços do Microsoft 365 não estão disponíveis em determinados países.</span><span class="sxs-lookup"><span data-stu-id="11d47-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="11d47-134">Para obter mais informações, consulte [about License Restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="11d47-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="11d47-135">Para localizar contas que não tenham um valor **UsageLocation** , execute este comando.</span><span class="sxs-lookup"><span data-stu-id="11d47-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="11d47-136">Para definir o valor **UsageLocation** em uma conta, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="11d47-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="11d47-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="11d47-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="11d47-138">Se você usar o cmdlet **Get-MsolUser** sem usar o parâmetro **-All**, somente as primeiras 500 contas serão retornadas.</span><span class="sxs-lookup"><span data-stu-id="11d47-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="11d47-139">Atribuir licenças a contas de usuário</span><span class="sxs-lookup"><span data-stu-id="11d47-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="11d47-140">Para atribuir uma licença a um usuário, use o seguinte comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11d47-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="11d47-141">Este exemplo atribui uma licença do plano de licenciamento do **litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) ao usuário não licenciado **Pomaria \@ litwareinc.com**:</span><span class="sxs-lookup"><span data-stu-id="11d47-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="11d47-142">Para atribuir uma licença a todos os usuários não licenciados, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="11d47-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="11d47-143">Você não pode atribuir várias licenças a um usuário do mesmo plano de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="11d47-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="11d47-144">Se você não tiver licenças o suficiente disponíveis, as licenças serão atribuídas aos usuários na ordem em que eles forem retornados pelo cmdlet **Get-MsolUser** até que as licenças disponíveis esgotem.</span><span class="sxs-lookup"><span data-stu-id="11d47-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="11d47-145">Este exemplo atribui licenças do plano de licenciamento do **litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) a todos os usuários não licenciados:</span><span class="sxs-lookup"><span data-stu-id="11d47-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="11d47-146">Este exemplo atribui as mesmas licenças a usuários não licenciados no departamento de vendas nos Estados Unidos:</span><span class="sxs-lookup"><span data-stu-id="11d47-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="11d47-147">Mover um usuário para uma assinatura diferente (plano de licença) com o módulo PowerShell do Azure Active Directory para Graph</span><span class="sxs-lookup"><span data-stu-id="11d47-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="11d47-148">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="11d47-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="11d47-149">Em seguida, obtenha o nome de entrada da conta de usuário para a qual você deseja assinaturas de troca, também conhecido como nome de usuário principal (UPN).</span><span class="sxs-lookup"><span data-stu-id="11d47-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="11d47-150">Em seguida, liste as assinaturas (planos de licença) para o seu locatário com este comando.</span><span class="sxs-lookup"><span data-stu-id="11d47-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="11d47-151">Em seguida, liste as assinaturas que a conta de usuário tem atualmente com esses comandos.</span><span class="sxs-lookup"><span data-stu-id="11d47-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="11d47-152">Identifique a assinatura que o usuário tem atualmente (a assinatura de) e a assinatura à qual o usuário está se movendo (a assinatura para).</span><span class="sxs-lookup"><span data-stu-id="11d47-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="11d47-153">Por fim, especifique os nomes de assinatura para e de (números de peça SKU) e execute esses comandos.</span><span class="sxs-lookup"><span data-stu-id="11d47-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="11d47-154">Você pode verificar a alteração na assinatura da conta de usuário com esses comandos.</span><span class="sxs-lookup"><span data-stu-id="11d47-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="11d47-155">Confira também</span><span class="sxs-lookup"><span data-stu-id="11d47-155">See also</span></span>

[<span data-ttu-id="11d47-156">Gerenciar contas de usuário, licenças e grupos com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="11d47-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="11d47-157">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="11d47-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="11d47-158">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="11d47-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
