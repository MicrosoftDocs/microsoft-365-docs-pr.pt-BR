---
title: Bloquear Microsoft 365 contas de usuário com o PowerShell
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
description: Como usar o PowerShell para bloquear e desbloquear o acesso a Microsoft 365 contas.
ms.openlocfilehash: 90d712cdb6eb34d0588fc262e3a02673accfbd9e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287216"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="22942-103">Bloquear Microsoft 365 contas de usuário com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="22942-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="22942-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="22942-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="22942-105">Quando você bloqueia o acesso a uma conta Microsoft 365, impede que qualquer pessoa use a conta para entrar e acessar os serviços e dados em sua Microsoft 365 organização.</span><span class="sxs-lookup"><span data-stu-id="22942-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="22942-106">Você pode usar o PowerShell para bloquear o acesso a contas de usuário individuais ou múltiplas.</span><span class="sxs-lookup"><span data-stu-id="22942-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="22942-107">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="22942-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="22942-108">Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="22942-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="22942-109">Bloquear o acesso a contas de usuário individuais</span><span class="sxs-lookup"><span data-stu-id="22942-109">Block access to individual user accounts</span></span>

<span data-ttu-id="22942-110">Use a seguinte sintaxe para bloquear uma conta de usuário individual:</span><span class="sxs-lookup"><span data-stu-id="22942-110">Use the following syntax to block an individual user account:</span></span>

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="22942-111">O *parâmetro -ObjectID* no cmdlet **Set-AzureAD** aceita o nome de entrada da conta, também conhecido como Nome principal do usuário ou a ID do objeto da conta.</span><span class="sxs-lookup"><span data-stu-id="22942-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>

<span data-ttu-id="22942-112">Este exemplo bloqueia o acesso à conta de *usuário fabricec@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="22942-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="22942-113">Para desbloquear essa conta de usuário, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="22942-113">To unblock this user account, run the following command:</span></span>

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="22942-114">Para exibir o UPN da conta de usuário com base no nome de exibição do usuário, use os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="22942-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="22942-115">Este exemplo exibe o UPN da conta de usuário para o usuário  *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="22942-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="22942-116">Para bloquear uma conta com base no nome de exibição do usuário, use os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="22942-116">To block an account based on the user's display name, use the following commands:</span></span>

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="22942-117">Para verificar o status bloqueado de uma conta de usuário, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="22942-117">To check the blocked status of a user account use the following command:</span></span>

```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="22942-118">Bloquear várias contas de usuário</span><span class="sxs-lookup"><span data-stu-id="22942-118">Block multiple user accounts</span></span>

<span data-ttu-id="22942-119">Para bloquear o acesso a várias contas de usuário, crie um arquivo de texto que contenha um nome de entrada de conta em cada linha como esta:</span><span class="sxs-lookup"><span data-stu-id="22942-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="22942-120">Nos comandos a seguir, o arquivo de texto de *exemplo é C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="22942-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="22942-121">Substitua esse nome de arquivo pelo caminho e o nome do arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="22942-121">Replace this file name with the path and file name of your text file.</span></span>

<span data-ttu-id="22942-122">Para bloquear o acesso às contas listadas no arquivo de texto, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="22942-122">To block access to the accounts listed in the text file, run the following command:</span></span>

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

<span data-ttu-id="22942-123">Para desbloquear as contas listadas no arquivo de texto, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="22942-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="22942-124">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22942-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="22942-125">Primeiro, [conecte-se ao seu Microsoft 365 locatário](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="22942-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="block-individual-user-accounts"></a><span data-ttu-id="22942-126">Bloquear contas de usuário individuais</span><span class="sxs-lookup"><span data-stu-id="22942-126">Block individual user accounts</span></span>

<span data-ttu-id="22942-127">Use a seguinte sintaxe para bloquear o acesso a uma conta de usuário individual:</span><span class="sxs-lookup"><span data-stu-id="22942-127">Use the following syntax to block access for an individual user account:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="22942-128">O PowerShell Core não dá suporte ao módulo Microsoft Azure Active Directory para Windows PowerShell e cmdlets que têm *Msol* em seu nome.</span><span class="sxs-lookup"><span data-stu-id="22942-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="22942-129">Você precisa executar esses cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22942-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="22942-130">Este exemplo bloqueia o acesso ao fabricec da conta *de \@ usuário litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="22942-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="22942-131">Para desbloquear a conta do usuário, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="22942-131">To unblock the user account, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="22942-132">Para verificar o status bloqueado de uma conta de usuário, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="22942-132">To check the blocked status of a user account run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="22942-133">Bloquear o acesso a várias contas de usuário</span><span class="sxs-lookup"><span data-stu-id="22942-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="22942-134">Primeiro, crie um arquivo de texto que contenha uma conta em cada linha como esta:</span><span class="sxs-lookup"><span data-stu-id="22942-134">First, create a text file that contains one account on each line like this:</span></span>

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="22942-135">Nos comandos a seguir, o arquivo de texto de *exemplo é C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="22942-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="22942-136">Substitua esse nome de arquivo pelo caminho e o nome do arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="22942-136">Replace this file name with the path and file name of your text file.</span></span>

<span data-ttu-id="22942-137">Para bloquear o acesso às contas listadas no arquivo de texto, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="22942-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="22942-138">Para desbloquear as contas listadas no arquivo de texto, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="22942-138">To unblock the accounts listed in the text file, run the following command:</span></span>

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="22942-139">Veja também</span><span class="sxs-lookup"><span data-stu-id="22942-139">See also</span></span>

[<span data-ttu-id="22942-140">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="22942-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[<span data-ttu-id="22942-141">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="22942-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="22942-142">Introdução ao Windows PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22942-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
