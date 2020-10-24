---
title: Atribuir funções a contas de usuário do Microsoft 365 com o PowerShell
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: Neste artigo, saiba como usar com rapidez e facilidade o PowerShell para a Microsoft 365 para atribuir funções de administrador às contas de usuário.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754193"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="1f83f-103">Atribuir funções de administrador às contas de usuário do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f83f-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="1f83f-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1f83f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1f83f-105">Você pode facilmente atribuir funções às contas de usuário usando o PowerShell para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f83f-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="1f83f-106">Saiba como  [atribuir funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) a contas de usuário com o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f83f-106">Learn how to  [assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="1f83f-107">Para obter uma lista de recursos adicionais, consulte [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="1f83f-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1f83f-108">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="1f83f-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1f83f-109">Primeiro, use uma conta de administrador global para [se conectar ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="1f83f-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="1f83f-110">Em seguida, identifique o nome de entrada da conta de usuário que você deseja adicionar a uma função (exemplo: fredsm \@ contoso.com).</span><span class="sxs-lookup"><span data-stu-id="1f83f-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="1f83f-111">Isso também é conhecido como nome de usuário principal (UPN).</span><span class="sxs-lookup"><span data-stu-id="1f83f-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="1f83f-112">Em seguida, determine o nome da função.</span><span class="sxs-lookup"><span data-stu-id="1f83f-112">Next, determine the name of the role.</span></span> <span data-ttu-id="1f83f-113">Consulte [permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="1f83f-113">See [administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="1f83f-114">Preste atenção nas anotações deste artigo.</span><span class="sxs-lookup"><span data-stu-id="1f83f-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="1f83f-115">Alguns nomes de função são diferentes para o PowerShell do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1f83f-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="1f83f-116">Por exemplo, a função de *administrador do SharePoint* no centro de administração do Microsoft 365 é *administrador de serviços do SharePoint* no PowerShell do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1f83f-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="1f83f-117">Em seguida, preencha os nomes de entrada e de função e execute estes comandos:</span><span class="sxs-lookup"><span data-stu-id="1f83f-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="1f83f-118">Veja um exemplo de um conjunto de comandos concluído que atribui a função de administrador de serviços do SharePoint à conta *polindan \@ contoso.com* :</span><span class="sxs-lookup"><span data-stu-id="1f83f-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="1f83f-119">Para exibir a lista de nomes de usuário para uma função de administrador específica, use estes comandos.</span><span class="sxs-lookup"><span data-stu-id="1f83f-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1f83f-120">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f83f-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1f83f-121">Primeiro, use uma conta de administrador global para [se conectar ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1f83f-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="1f83f-122">Para uma alteração de função única</span><span class="sxs-lookup"><span data-stu-id="1f83f-122">For a single role change</span></span>

<span data-ttu-id="1f83f-123">As maneiras mais comuns de especificar a conta de usuário é usar o nome de exibição ou o nome de email, que também é conhecido como o nome de entrada ou o nome de usuário principal (UPN).</span><span class="sxs-lookup"><span data-stu-id="1f83f-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="1f83f-124">Exibir nomes de contas de usuário</span><span class="sxs-lookup"><span data-stu-id="1f83f-124">Display names of user accounts</span></span>

<span data-ttu-id="1f83f-125">Se você estiver acostumado a trabalhar com os nomes de exibição das contas de usuário, determine as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1f83f-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="1f83f-126">A conta de usuário que você deseja configurar</span><span class="sxs-lookup"><span data-stu-id="1f83f-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="1f83f-127">Para especificar a conta de usuário, você deve determinar seu nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="1f83f-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="1f83f-128">Para obter uma lista completa das contas, use este comando:</span><span class="sxs-lookup"><span data-stu-id="1f83f-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="1f83f-129">Este comando lista o nome de exibição de suas contas de usuário, classificados pelo nome de exibição, uma tela por vez.</span><span class="sxs-lookup"><span data-stu-id="1f83f-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="1f83f-130">Você pode filtrar a lista em um conjunto menor usando o cmdlet **Where** .</span><span class="sxs-lookup"><span data-stu-id="1f83f-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="1f83f-131">Confira o seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="1f83f-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="1f83f-132">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para o módulo e cmdlets do Windows PowerShell com o *MSol* em seu nome.</span><span class="sxs-lookup"><span data-stu-id="1f83f-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="1f83f-133">Execute estes cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f83f-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="1f83f-134">Este comando lista apenas as contas de usuário para as quais o nome de exibição começa com "John".</span><span class="sxs-lookup"><span data-stu-id="1f83f-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="1f83f-135">A função que você deseja atribuir</span><span class="sxs-lookup"><span data-stu-id="1f83f-135">The role you want to assign</span></span>
    
    <span data-ttu-id="1f83f-136">Para exibir a lista de funções de administrador disponíveis que podem ser atribuídas a contas de usuário, use este comando:</span><span class="sxs-lookup"><span data-stu-id="1f83f-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="1f83f-137">Depois de determinar o nome de exibição da conta e o nome da função, use estes comandos para atribuir a função à conta:</span><span class="sxs-lookup"><span data-stu-id="1f83f-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="1f83f-138">Cole os comandos no bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="1f83f-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="1f83f-139">Para as variáveis *$dispName* e *$roleName* , substitua o texto da descrição por seus valores.</span><span class="sxs-lookup"><span data-stu-id="1f83f-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="1f83f-140">Remova os \< and > caracteres, mas mantenha as aspas.</span><span class="sxs-lookup"><span data-stu-id="1f83f-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="1f83f-141">Cole as linhas modificadas na janela módulo do Microsoft Azure Active Directory para Windows PowerShell para executá-las.</span><span class="sxs-lookup"><span data-stu-id="1f83f-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="1f83f-142">Como alternativa, você pode usar o ambiente de script integrado (ISE) do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f83f-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="1f83f-143">Veja um exemplo de um conjunto de comandos concluído:</span><span class="sxs-lookup"><span data-stu-id="1f83f-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="1f83f-144">Nomes de entrada de contas de usuário</span><span class="sxs-lookup"><span data-stu-id="1f83f-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="1f83f-145">Se você estiver acostumado a trabalhar com os nomes de entrada ou UPNs de contas de usuário, determine as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1f83f-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="1f83f-146">O UPN da conta do usuário</span><span class="sxs-lookup"><span data-stu-id="1f83f-146">The user account's UPN</span></span>
    
    <span data-ttu-id="1f83f-147">Se você não souber o UPN, use este comando:</span><span class="sxs-lookup"><span data-stu-id="1f83f-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="1f83f-148">Este comando lista o UPN de suas contas de usuário, classificados por UPN, uma tela por vez.</span><span class="sxs-lookup"><span data-stu-id="1f83f-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="1f83f-149">Você pode usar o cmdlet **Where** para filtrar a lista.</span><span class="sxs-lookup"><span data-stu-id="1f83f-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="1f83f-150">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="1f83f-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="1f83f-151">Este comando lista apenas as contas de usuário para as quais o nome de exibição começa com "John".</span><span class="sxs-lookup"><span data-stu-id="1f83f-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="1f83f-152">A função que você deseja atribuir</span><span class="sxs-lookup"><span data-stu-id="1f83f-152">The role you want to assign</span></span>
    
    <span data-ttu-id="1f83f-153">Para exibir a lista de funções disponíveis que você pode atribuir às contas de usuário, use este comando:</span><span class="sxs-lookup"><span data-stu-id="1f83f-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="1f83f-154">Depois de ter o UPN da conta e o nome da função, use estes comandos para atribuir a função à conta:</span><span class="sxs-lookup"><span data-stu-id="1f83f-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="1f83f-155">Copie os comandos e cole-os no bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="1f83f-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="1f83f-156">Para as variáveis **$upnName** e **$roleName** .</span><span class="sxs-lookup"><span data-stu-id="1f83f-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="1f83f-157">Substitua o texto da descrição por seus valores.</span><span class="sxs-lookup"><span data-stu-id="1f83f-157">Replace the description text with their values.</span></span> <span data-ttu-id="1f83f-158">Remova os \< and > caracteres, mas mantenha as aspas.</span><span class="sxs-lookup"><span data-stu-id="1f83f-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="1f83f-159">Cole as linhas modificadas no módulo Microsoft Azure Active Directory para Windows PowerShell janela para executá-las.</span><span class="sxs-lookup"><span data-stu-id="1f83f-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="1f83f-160">Como alternativa, você pode usar o Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="1f83f-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="1f83f-161">Veja um exemplo de um conjunto de comandos concluído:</span><span class="sxs-lookup"><span data-stu-id="1f83f-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="1f83f-162">Várias alterações de função</span><span class="sxs-lookup"><span data-stu-id="1f83f-162">Multiple role changes</span></span>

<span data-ttu-id="1f83f-163">Para várias alterações de função, determine as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1f83f-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="1f83f-164">Quais contas de usuário você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="1f83f-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="1f83f-165">Você pode usar os métodos da seção anterior para coletar o conjunto de nomes de exibição ou UPNs.</span><span class="sxs-lookup"><span data-stu-id="1f83f-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="1f83f-166">Quais funções você deseja atribuir a cada conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="1f83f-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="1f83f-167">Para exibir a lista de funções disponíveis que você pode atribuir às contas de usuário, use este comando:</span><span class="sxs-lookup"><span data-stu-id="1f83f-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="1f83f-168">Em seguida, crie um arquivo de texto de valor separado por vírgula (CSV) que tenha os campos nome de exibição ou UPN e nome da função.</span><span class="sxs-lookup"><span data-stu-id="1f83f-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="1f83f-169">Você pode fazer isso facilmente no Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="1f83f-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="1f83f-170">Veja um exemplo de nomes para exibição:</span><span class="sxs-lookup"><span data-stu-id="1f83f-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="1f83f-171">Em seguida, preencha o local do arquivo CSV e execute os comandos resultantes no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f83f-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="1f83f-172">Veja um exemplo de UPNs:</span><span class="sxs-lookup"><span data-stu-id="1f83f-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="1f83f-173">Em seguida, preencha o local do arquivo CSV e execute os comandos resultantes no prompt de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f83f-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="1f83f-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="1f83f-174">See also</span></span>

- [<span data-ttu-id="1f83f-175">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f83f-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1f83f-176">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f83f-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="1f83f-177">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f83f-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
