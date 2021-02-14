---
title: Exibir a licença da conta do Microsoft 365 e os detalhes do serviço com o PowerShell
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
- LIL_Placement
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: Explica como usar o PowerShell para determinar os serviços do Microsoft 365 que foram atribuídos aos usuários.
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687511"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a><span data-ttu-id="8d66c-103">Exibir a licença da conta do Microsoft 365 e os detalhes do serviço com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d66c-103">View Microsoft 365 account license and service details with PowerShell</span></span>

<span data-ttu-id="8d66c-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8d66c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8d66c-105">No Microsoft 365, as licenças de planos de licenciamento (também chamados de SKUs ou planos do Microsoft 365) dão aos usuários acesso aos serviços do Microsoft 365 definidos para esses planos.</span><span class="sxs-lookup"><span data-stu-id="8d66c-105">In Microsoft 365, licenses from licensing plans (also called SKUs or Microsoft 365 plans) give users access to the Microsoft 365 services that are defined for those plans.</span></span> <span data-ttu-id="8d66c-106">No entanto, um usuário pode não ter acesso a todos os serviços disponíveis em uma licença que está atribuída atualmente a ele.</span><span class="sxs-lookup"><span data-stu-id="8d66c-106">However, a user might not have access to all the services that are available in a license that's currently assigned to them.</span></span> <span data-ttu-id="8d66c-107">Você pode usar o PowerShell para o Microsoft 365 para exibir o status dos serviços em contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="8d66c-107">You can use PowerShell for Microsoft 365 to view the status of services on user accounts.</span></span> 

<span data-ttu-id="8d66c-108">Para obter mais informações sobre planos de licenciamento, licenças e serviços, consulte [Exibir licenças e serviços com o PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="8d66c-108">For more information about licensing plans, license, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="8d66c-109">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="8d66c-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="8d66c-110">Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="8d66c-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="8d66c-111">Em seguida, liste os planos de licença para seu locatário com este comando.</span><span class="sxs-lookup"><span data-stu-id="8d66c-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="8d66c-112">Use estes comandos para listar os serviços disponíveis em cada plano de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="8d66c-112">Use these commands to list the services that are available in each licensing plan.</span></span>

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

<span data-ttu-id="8d66c-113">Use estes comandos para listar as licenças atribuídas a uma conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="8d66c-113">Use these commands to list the licenses that are assigned to a user account.</span></span>

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="8d66c-114">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d66c-114">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="8d66c-115">Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="8d66c-115">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="8d66c-116">Em seguida, execute este comando para listar os planos de licenciamento disponíveis em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8d66c-116">Next, run this command to list the licensing plans that are available in your organization.</span></span> 

```powershell
Get-MsolAccountSku
```
>[!Note]
><span data-ttu-id="8d66c-117">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="8d66c-117">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="8d66c-118">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d66c-118">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="8d66c-119">Em seguida, execute este comando para listar os serviços disponíveis em cada plano de licenciamento e a ordem na qual eles estão listados (o número de índice).</span><span class="sxs-lookup"><span data-stu-id="8d66c-119">Next, run this command to list the services that are available in each licensing plan, and the order in which they are listed (the index number).</span></span>

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
<span data-ttu-id="8d66c-120">Use este comando para listar as licenças atribuídas a um usuário e a ordem na qual elas estão listadas (o número de índice).</span><span class="sxs-lookup"><span data-stu-id="8d66c-120">Use this command to list the licenses that are assigned to a user, and the order in which they are listed (the index number).</span></span>

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a><span data-ttu-id="8d66c-121">Para exibir serviços de uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="8d66c-121">To view services for a user account</span></span>

<span data-ttu-id="8d66c-122">Para exibir todos os serviços do Microsoft 365 aos quais um usuário tem acesso, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="8d66c-122">To view all the Microsoft 365 services that a user has access to, use the following syntax:</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

<span data-ttu-id="8d66c-123">Este exemplo mostra os serviços aos quais o usuário BelindaN@litwareinc.com tem acesso.</span><span class="sxs-lookup"><span data-stu-id="8d66c-123">This example shows the services to which the user BelindaN@litwareinc.com has access.</span></span> <span data-ttu-id="8d66c-124">Isso mostra os serviços associados a todas as licenças atribuídas à conta dela.</span><span class="sxs-lookup"><span data-stu-id="8d66c-124">This shows the services that are associated with all licenses that are assigned to her account.</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

<span data-ttu-id="8d66c-125">Este exemplo mostra os serviços aos quais a usuária BrendaF@litwareinc.com tem acesso a partir da primeira licença atribuída à conta dela (o número de índice é 0).</span><span class="sxs-lookup"><span data-stu-id="8d66c-125">This example shows the services that user BelindaN@litwareinc.com has access to from the first license that's assigned to her account (the index number is 0).</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

<span data-ttu-id="8d66c-126">Para exibir todos os serviços de um usuário que recebeu várias *licenças,* use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="8d66c-126">To view all the services for a user who has been assigned *multiple licenses*, use the following syntax:</span></span>

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a><span data-ttu-id="8d66c-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="8d66c-127">See also</span></span>

[<span data-ttu-id="8d66c-128">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d66c-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8d66c-129">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d66c-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8d66c-130">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8d66c-130">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
