---
title: Bloquear contas de usuário do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Como usar o PowerShell para bloquear e desbloquear o acesso às contas do Microsoft 365.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754675"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="925da-103">Bloquear contas de usuário do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="925da-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="925da-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="925da-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="925da-105">Ao bloquear o acesso a uma conta do Microsoft 365, você impede que qualquer pessoa use a conta para entrar e acessar os serviços e dados em sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="925da-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="925da-106">Você pode usar o PowerShell para bloquear o acesso a contas de usuário individuais ou múltiplas.</span><span class="sxs-lookup"><span data-stu-id="925da-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="925da-107">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="925da-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="925da-108">Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="925da-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="925da-109">Bloquear o acesso a contas de usuário individuais</span><span class="sxs-lookup"><span data-stu-id="925da-109">Block access to individual user accounts</span></span>

<span data-ttu-id="925da-110">Use a seguinte sintaxe para bloquear uma conta de usuário individual:</span><span class="sxs-lookup"><span data-stu-id="925da-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="925da-111">O *parâmetro -ObjectID* no cmdlet **Set-AzureAD** aceita o nome de entrada da conta, também conhecido como Nome Principal do Usuário, ou a ID de objeto da conta.</span><span class="sxs-lookup"><span data-stu-id="925da-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="925da-112">Este exemplo bloqueia o acesso à conta de *usuário fabricec@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="925da-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="925da-113">Para desbloquear essa conta de usuário, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="925da-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="925da-114">Para exibir o UPN da conta de usuário com base no nome de exibição do usuário, use os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="925da-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="925da-115">Este exemplo exibe o UPN da conta de usuário para o usuário *Paulo Alsão.*</span><span class="sxs-lookup"><span data-stu-id="925da-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="925da-116">Para bloquear uma conta com base no nome de exibição do usuário, use os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="925da-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="925da-117">Para verificar o status bloqueado de uma conta de usuário, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="925da-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="925da-118">Bloquear várias contas de usuário</span><span class="sxs-lookup"><span data-stu-id="925da-118">Block multiple user accounts</span></span>

<span data-ttu-id="925da-119">Para bloquear o acesso de várias contas de usuário, crie um arquivo de texto que contenha um nome de entrada de conta em cada linha da forma a seguir:</span><span class="sxs-lookup"><span data-stu-id="925da-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="925da-120">Nos comandos a seguir, o arquivo de texto de exemplo *é C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="925da-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="925da-121">Substitua esse nome de arquivo pelo caminho e pelo nome do arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="925da-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="925da-122">Para bloquear o acesso às contas listadas no arquivo de texto, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="925da-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="925da-123">Para desbloquear as contas listadas no arquivo de texto, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="925da-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="925da-124">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="925da-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="925da-125">Primeiro, [conecte-se ao locatário do Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="925da-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="925da-126">Bloquear contas de usuário individuais</span><span class="sxs-lookup"><span data-stu-id="925da-126">Block individual user accounts</span></span>

<span data-ttu-id="925da-127">Use a seguinte sintaxe para bloquear o acesso de uma conta de usuário individual:</span><span class="sxs-lookup"><span data-stu-id="925da-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="925da-128">O PowerShell Core não dá suporte ao módulo Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell que têm *o Msol* no nome.</span><span class="sxs-lookup"><span data-stu-id="925da-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="925da-129">Você precisa executar esses cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="925da-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="925da-130">Este exemplo bloqueia o acesso à conta de usuário *do fabricec \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="925da-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="925da-131">Para desbloquear a conta do usuário, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="925da-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="925da-132">Para verificar o status bloqueado de uma conta de usuário, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="925da-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="925da-133">Bloquear o acesso para várias contas de usuário</span><span class="sxs-lookup"><span data-stu-id="925da-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="925da-134">Primeiro, crie um arquivo de texto que contenha uma conta em cada linha da forma a seguir:</span><span class="sxs-lookup"><span data-stu-id="925da-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="925da-135">Nos comandos a seguir, o arquivo de texto de exemplo *é C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="925da-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="925da-136">Substitua esse nome de arquivo pelo caminho e pelo nome do arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="925da-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="925da-137">Para bloquear o acesso das contas listadas no arquivo de texto, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="925da-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="925da-138">Para desbloquear as contas listadas no arquivo de texto, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="925da-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="925da-139">Veja também</span><span class="sxs-lookup"><span data-stu-id="925da-139">See also</span></span>

[<span data-ttu-id="925da-140">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="925da-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="925da-141">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="925da-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="925da-142">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="925da-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
