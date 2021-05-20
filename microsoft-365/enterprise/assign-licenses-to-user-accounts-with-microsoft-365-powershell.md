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
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="6a66a-103">Atribuir licenças de Microsoft 365 a contas de usuário com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a66a-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="6a66a-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6a66a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6a66a-105">Os usuários não podem usar nenhum serviço Microsoft 365 até que sua conta tenha sido atribuída uma licença de um plano de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="6a66a-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="6a66a-106">Você pode usar o PowerShell para atribuir rapidamente licenças a contas não licenciadas.</span><span class="sxs-lookup"><span data-stu-id="6a66a-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="6a66a-107">As contas de usuário devem primeiro ser atribuídas a um local.</span><span class="sxs-lookup"><span data-stu-id="6a66a-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="6a66a-108">Especificar um local é uma parte necessária da criação de uma nova conta de usuário no [centro administrativo Microsoft 365](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="6a66a-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="6a66a-109">As contas sincronizadas a partir de seus serviços de domínio do Active Directory no local não têm por padrão um local especificado.</span><span class="sxs-lookup"><span data-stu-id="6a66a-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="6a66a-110">Você pode configurar um local para essas contas de:</span><span class="sxs-lookup"><span data-stu-id="6a66a-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="6a66a-111">O Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6a66a-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="6a66a-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a66a-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="6a66a-113">O [portal Azure](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) –**Active Directory**  >  **Users** > conta de usuário > **Informações de** Contato de Perfil País ou  >    >  **região**).</span><span class="sxs-lookup"><span data-stu-id="6a66a-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="6a66a-114">[Saiba como atribuir licenças a contas de usuários](../admin/manage/assign-licenses-to-users.md) com o centro administrativo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6a66a-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="6a66a-115">Para obter uma lista de recursos adicionais, consulte [Gerenciar usuários e grupos](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="6a66a-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6a66a-116">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="6a66a-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6a66a-117">Primeiro, [conecte-se ao seu inquilino Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="6a66a-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="6a66a-118">Em seguida, liste os planos de licença para o seu inquilino com este comando.</span><span class="sxs-lookup"><span data-stu-id="6a66a-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="6a66a-119">Em seguida, obtenha o nome de login da conta à qual deseja adicionar uma licença, também conhecida como nome principal do usuário (UPN).</span><span class="sxs-lookup"><span data-stu-id="6a66a-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="6a66a-120">Em seguida, certifique-se de que a conta de usuário tenha um local de uso atribuído.</span><span class="sxs-lookup"><span data-stu-id="6a66a-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="6a66a-121">Se não houver nenhum local de uso atribuído, você pode atribuir um com esses comandos:</span><span class="sxs-lookup"><span data-stu-id="6a66a-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="6a66a-122">Finalmente, especifique o nome do nome de login do usuário e o nome do plano de licença e execute esses comandos.</span><span class="sxs-lookup"><span data-stu-id="6a66a-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6a66a-123">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a66a-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6a66a-124">Por favor, note que começaremos a depreciar este módulo quando a funcionalidade deste módulo estiver disponível no mais novo [Azure Active Directory PowerShell para Graph](/powershell/azuread/v2/azureactivedirectory) módulo.</span><span class="sxs-lookup"><span data-stu-id="6a66a-124">Please note that we will begin to deprecate this module when the functionality of this module is available in the newer [Azure Active Directory PowerShell for Graph](/powershell/azuread/v2/azureactivedirectory) module.</span></span> <span data-ttu-id="6a66a-125">Aconselhamos os clientes que estão criando novos scripts PowerShell a usar o módulo mais novo em vez deste módulo.</span><span class="sxs-lookup"><span data-stu-id="6a66a-125">We advise customers who are creating new PowerShell scripts to use the newer module instead of this module.</span></span>

<span data-ttu-id="6a66a-126">Primeiro, [conecte-se ao seu inquilino Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="6a66a-126">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="6a66a-127">Execute o `Get-MsolAccountSku` comando para visualizar os planos de licenciamento disponíveis e o número de licenças disponíveis em cada plano em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6a66a-127">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="6a66a-128">O número de licenças disponíveis em cada plano é **de Unidades**  -  **de Aviso**  -  **ativas consumidas.**</span><span class="sxs-lookup"><span data-stu-id="6a66a-128">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="6a66a-129">Para obter mais informações sobre planos de licenciamento, licenças e serviços, consulte [licenças e serviços com o PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6a66a-129">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="6a66a-130">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="6a66a-130">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="6a66a-131">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a66a-131">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="6a66a-132">Para encontrar as contas não licenciadas em sua organização, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="6a66a-132">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="6a66a-133">Você só pode atribuir licenças a contas de usuário que tenham a propriedade **UseLocation** definida para um código de país ISO 3166-1 alfa-2 válido.</span><span class="sxs-lookup"><span data-stu-id="6a66a-133">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="6a66a-134">Por exemplo, US para os Estados Unidos e FR para a França.</span><span class="sxs-lookup"><span data-stu-id="6a66a-134">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="6a66a-135">Alguns serviços Microsoft 365 não estão disponíveis em certos países.</span><span class="sxs-lookup"><span data-stu-id="6a66a-135">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="6a66a-136">Para obter mais informações, consulte [Sobre restrições de licença](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="6a66a-136">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="6a66a-137">Para encontrar contas que não tenham um valor **de Localização de uso,** execute este comando.</span><span class="sxs-lookup"><span data-stu-id="6a66a-137">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="6a66a-138">Para definir o valor **de Localização de uso** em uma conta, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="6a66a-138">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="6a66a-139">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6a66a-139">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="6a66a-140">Se você usar o cmdlet **Get-MsolUser** sem usar o parâmetro **-All**, somente as primeiras 500 contas serão retornadas.</span><span class="sxs-lookup"><span data-stu-id="6a66a-140">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="6a66a-141">Atribuindo licenças a contas de usuários</span><span class="sxs-lookup"><span data-stu-id="6a66a-141">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="6a66a-142">Para atribuir uma licença a um usuário, use o seguinte comando no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a66a-142">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="6a66a-143">Este exemplo atribui uma licença do plano de licenciamento **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) ao usuário não licenciado **belindan \@ litwareinc.com:**</span><span class="sxs-lookup"><span data-stu-id="6a66a-143">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="6a66a-144">Para atribuir uma licença a todos os usuários não licenciados, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="6a66a-144">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="6a66a-145">Você não pode atribuir várias licenças a um usuário do mesmo plano de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="6a66a-145">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="6a66a-146">Se você não tiver licenças o suficiente disponíveis, as licenças serão atribuídas aos usuários na ordem em que eles forem retornados pelo cmdlet **Get-MsolUser** até que as licenças disponíveis esgotem.</span><span class="sxs-lookup"><span data-stu-id="6a66a-146">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="6a66a-147">Este exemplo atribui licenças do plano de licenciamento **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) a todos os usuários não licenciados:</span><span class="sxs-lookup"><span data-stu-id="6a66a-147">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="6a66a-148">Este exemplo atribui essas mesmas licenças a usuários não licenciados no departamento de Vendas nos Estados Unidos:</span><span class="sxs-lookup"><span data-stu-id="6a66a-148">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6a66a-149">Mova um usuário para uma assinatura diferente (plano de licença) com o Azure Active Directory PowerShell para Graph módulo</span><span class="sxs-lookup"><span data-stu-id="6a66a-149">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6a66a-150">Primeiro, [conecte-se ao seu inquilino Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="6a66a-150">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="6a66a-151">Em seguida, obtenha o nome de login da conta de usuário para a qual você deseja assinaturas do switch, também conhecido como o nome principal do usuário (UPN).</span><span class="sxs-lookup"><span data-stu-id="6a66a-151">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="6a66a-152">Em seguida, liste as assinaturas (planos de licença) para o seu inquilino com este comando.</span><span class="sxs-lookup"><span data-stu-id="6a66a-152">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="6a66a-153">Em seguida, liste as assinaturas que a conta de usuário tem atualmente com esses comandos.</span><span class="sxs-lookup"><span data-stu-id="6a66a-153">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="6a66a-154">Identifique a assinatura que o usuário tem atualmente (a assinatura FROM) e a assinatura para a qual o usuário está se movendo (a assinatura TO).</span><span class="sxs-lookup"><span data-stu-id="6a66a-154">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="6a66a-155">Finalmente, especifique os nomes de assinatura TO e FROM (números de peças SKU) e execute esses comandos.</span><span class="sxs-lookup"><span data-stu-id="6a66a-155">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="6a66a-156">Você pode verificar a alteração na assinatura da conta de usuário com esses comandos.</span><span class="sxs-lookup"><span data-stu-id="6a66a-156">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="6a66a-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="6a66a-157">See also</span></span>

[<span data-ttu-id="6a66a-158">Gerenciar contas de usuário, licenças e grupos com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a66a-158">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6a66a-159">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a66a-159">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6a66a-160">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6a66a-160">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
