---
title: Excluir contas de usuário do Microsoft 365 com o PowerShell
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
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Saiba como usar módulos diferentes no PowerShell para excluir contas de usuário do Microsoft 365.
ms.openlocfilehash: 39bf57fe7e7aad1bdc9915e503107ad799515030
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754535"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="20b4e-103">Excluir contas de usuário do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="20b4e-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="20b4e-104">Você pode usar o PowerShell para Microsoft 365 para excluir e restaurar contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="20b4e-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="20b4e-105">Saiba como [restaurar uma conta de usuário](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) usando o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20b4e-105">Learn how to [restore a user account](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="20b4e-106">Para obter uma lista de recursos adicionais, consulte [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="20b4e-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="20b4e-107">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="20b4e-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="20b4e-108">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="20b4e-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="20b4e-109">Depois de se conectar, use a seguinte sintaxe para remover uma conta de usuário individual:</span><span class="sxs-lookup"><span data-stu-id="20b4e-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="20b4e-110">Este exemplo remove a conta de usuário *fabricec \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="20b4e-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="20b4e-111">O parâmetro *-ObjectID* no cmdlet **Remove-AzureADUser** aceita o nome de entrada da conta, também conhecido como o nome principal do usuário ou a ID de objeto da conta.</span><span class="sxs-lookup"><span data-stu-id="20b4e-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="20b4e-112">Para exibir o nome da conta com base no nome do usuário, use os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="20b4e-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="20b4e-113">Este exemplo exibe o nome da conta do usuário *Carlos Lima*.</span><span class="sxs-lookup"><span data-stu-id="20b4e-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="20b4e-114">Para remover uma conta com base no nome de exibição do usuário, use os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="20b4e-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="20b4e-115">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20b4e-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="20b4e-116">Quando você exclui uma conta de usuário através do módulo do Microsoft Azure Active Directory para Windows PowerShell, a conta não é excluída permanentemente.</span><span class="sxs-lookup"><span data-stu-id="20b4e-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="20b4e-117">Você pode restaurar a conta de usuário excluída no prazo de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="20b4e-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="20b4e-118">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="20b4e-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="20b4e-119">Para excluir uma conta de usuário, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="20b4e-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="20b4e-120">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para o módulo e cmdlets do Windows PowerShell com o *MSol* em seu nome.</span><span class="sxs-lookup"><span data-stu-id="20b4e-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="20b4e-121">Execute estes cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20b4e-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="20b4e-122">Este exemplo exclui a conta de usuário *BelindaN@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="20b4e-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="20b4e-123">Para restaurar uma conta de usuário excluída no período de tolerância de 30 dias, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="20b4e-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="20b4e-124">Este exemplo restaura a conta excluída \* \@ litwareinc.com\*.</span><span class="sxs-lookup"><span data-stu-id="20b4e-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="20b4e-125">Para ver a lista de usuários excluídos que pode ser restaurados, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="20b4e-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="20b4e-126">Se o nome UPN (nome principal do usuário) original da conta de usuário for usado por outra conta, use o parâmetro _NewUserPrincipalName_ no lugar de _UserPrincipalName_ para especificar um UPN diferente ao restaurar a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="20b4e-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="20b4e-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="20b4e-127">See also</span></span>

[<span data-ttu-id="20b4e-128">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="20b4e-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="20b4e-129">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="20b4e-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="20b4e-130">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20b4e-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
