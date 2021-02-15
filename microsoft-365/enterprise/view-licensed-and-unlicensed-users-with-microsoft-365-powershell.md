---
title: Exibir usuários licenciados e não licenciados do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: Este artigo explica como usar o PowerShell para exibir contas de usuário licenciadas e não licenciadas do Microsoft 365.
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651379"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a><span data-ttu-id="f4e19-103">Exibir usuários licenciados e não licenciados do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4e19-103">View licensed and unlicensed Microsoft 365 users with PowerShell</span></span>

<span data-ttu-id="f4e19-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f4e19-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f4e19-105">As contas de usuário em sua organização do Microsoft 365 podem ter algumas, todas ou nenhuma das licenças disponíveis atribuídas a elas nos planos de licenciamento disponíveis em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f4e19-105">User accounts in your Microsoft 365 organization may have some, all, or none of the available licenses assigned to them from the licensing plans that are available in your organization.</span></span> <span data-ttu-id="f4e19-106">Você pode usar o PowerShell para o Microsoft 365 para encontrar rapidamente os usuários licenciados e não licenciados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f4e19-106">You can use PowerShell for Microsoft 365 to quickly find the licensed and unlicensed users in your organization.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f4e19-107">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="f4e19-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f4e19-108">Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="f4e19-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
<span data-ttu-id="f4e19-109">Para exibir a lista de todas as contas de usuário em sua organização que NÃO foram atribuídas a nenhum dos seus planos de licenciamento (usuários não licenciados), execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f4e19-109">To view the list of all user accounts in your organization that have NOT been assigned any of your licensing plans (unlicensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

<span data-ttu-id="f4e19-110">Para exibir a lista de todas as contas de usuário em sua organização que foram atribuídas a qualquer um dos seus planos de licenciamento (usuários licenciados), execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f4e19-110">To view the list of all user accounts in your organization that have been assigned any of your licensing plans (licensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
><span data-ttu-id="f4e19-111">Para listar todos os usuários em sua assinatura, use o `Get-AzureAdUser -All $true` comando.</span><span class="sxs-lookup"><span data-stu-id="f4e19-111">To list all of the users in your subscription, use the `Get-AzureAdUser -All $true` command.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f4e19-112">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4e19-112">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f4e19-113">Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="f4e19-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="f4e19-114">Para exibir a lista de todas as contas de usuário e seu status de licenciamento em sua organização, execute o seguinte comando no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f4e19-114">To view the list of all user accounts and their licensing status in your organization, run the following command in PowerShell:</span></span>
  
```powershell
Get-MsolUser -All
```

>[!Note]
><span data-ttu-id="f4e19-115">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="f4e19-115">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f4e19-116">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4e19-116">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="f4e19-117">Para visualizar a lista de todas as contas de usuários não licenciados em sua organização, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f4e19-117">To view the list of all unlicensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="f4e19-118">Para visualizar a lista de todas as contas de usuários licenciados em sua organização, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f4e19-118">To view the list of all licensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a><span data-ttu-id="f4e19-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="f4e19-119">See also</span></span>

[<span data-ttu-id="f4e19-120">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4e19-120">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f4e19-121">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4e19-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f4e19-122">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4e19-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
