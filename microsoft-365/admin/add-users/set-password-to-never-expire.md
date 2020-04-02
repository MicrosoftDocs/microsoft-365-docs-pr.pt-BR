---
title: Definir a senha de um usuário individual para nunca expirar
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Saiba como definir que algumas senhas de usuário individuais nunca expirem, usando o Windows PowerShell.
ms.openlocfilehash: 275fedf7bf4e52320b769689516ad39a31c63ea1
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105730"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="7546c-103">Definir a senha de um usuário individual para nunca expirar</span><span class="sxs-lookup"><span data-stu-id="7546c-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="7546c-104">Definir a política de expiração de senha para sua organização</span><span class="sxs-lookup"><span data-stu-id="7546c-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="7546c-105">No centro de administração, vá para a página **configurações** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">segurança & privacidade</a> .</span><span class="sxs-lookup"><span data-stu-id="7546c-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
2. <span data-ttu-id="7546c-106">Ao lado de **política de senha** , selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7546c-106">Next to **Password policy** select **Edit**.</span></span> 
3. <span data-ttu-id="7546c-107">Se as senhas estiverem definidas para nunca expirar, defina a **opção para desativado**.</span><span class="sxs-lookup"><span data-stu-id="7546c-107">If passwords are set to never expire, set the toggle to **Off**.</span></span> <span data-ttu-id="7546c-108">Você terá a opção de especificar o número de dias até que as senhas expirem.</span><span class="sxs-lookup"><span data-stu-id="7546c-108">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="7546c-109">Definir a política de expiração de senha para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="7546c-109">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="7546c-110">Um administrador global para um serviço de nuvem da Microsoft pode usar o módulo Microsoft Azure AD para Windows PowerShell para definir senhas que não expirem para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="7546c-110">A global admin for a Microsoft cloud service can use the Microsoft Azure AD Module for Windows PowerShell to set passwords not to expire for specific users.</span></span> <span data-ttu-id="7546c-111">Você também pode usar os cmdlets do Windows PowerShell para remover a configuração nunca expira ou para ver quais senhas de usuário estão definidas para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="7546c-111">You can also use Windows PowerShell cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="7546c-112">Este guia se aplica a outros provedores, como o Intune e o Office 365, que também dependem do Azure AD para serviços de identidade e diretório.</span><span class="sxs-lookup"><span data-stu-id="7546c-112">This guide applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="7546c-113">A expiração da senha é a única parte da política que pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="7546c-113">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="7546c-114">Somente senhas para contas de usuário que não estão sincronizadas por meio da sincronização de diretórios podem ser configuradas para não expirar.</span><span class="sxs-lookup"><span data-stu-id="7546c-114">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="7546c-115">Para obter mais informações sobre a sincronização de diretórios, consulte [Connect ad with Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="7546c-115">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="7546c-116">Como verificar a política de expiração de uma senha</span><span class="sxs-lookup"><span data-stu-id="7546c-116">How to check the expiration policy for a password</span></span>
<span data-ttu-id="7546c-117">Execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="7546c-117">Run one of the following commands:</span></span>

- <span data-ttu-id="7546c-118">Para ver se a senha de um único usuário está definida como nunca expirar, execute o seguinte cmdlet usando o UPN (por exemplo, *User@contoso.onmicrosoft.com*) ou a ID de usuário do usuário que você deseja verificar:</span><span class="sxs-lookup"><span data-stu-id="7546c-118">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="7546c-119">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="7546c-119">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="7546c-120">Para ver a configuração da **senha nunca expira** para todos os usuários, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7546c-120">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="7546c-121">Para obter um relatório de todos os usuários com o PasswordNeverExpires, em HTML na área de trabalho do usuário atual com o nome **ReportPasswordNeverExpires. html**</span><span class="sxs-lookup"><span data-stu-id="7546c-121">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="7546c-122">Para obter um relatório de todos os usuários com PasswordNeverExpires, em CSV na área de trabalho do usuário atual com o nome **ReportPasswordNeverExpires. csv**</span><span class="sxs-lookup"><span data-stu-id="7546c-122">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="7546c-123">Definir uma senha para expirar</span><span class="sxs-lookup"><span data-stu-id="7546c-123">Set a password to expire</span></span>

<span data-ttu-id="7546c-124">Execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="7546c-124">Run one of the following commands:</span></span>

- <span data-ttu-id="7546c-125">Para definir a senha de um usuário para que a senha expire, execute o seguinte cmdlet usando o UPN ou a ID do usuário:</span><span class="sxs-lookup"><span data-stu-id="7546c-125">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="7546c-126">Para definir as senhas de todos os usuários da organização de modo que eles expirem, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7546c-126">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="7546c-127">Definir uma senha para nunca expirar</span><span class="sxs-lookup"><span data-stu-id="7546c-127">Set a password to never expire</span></span>

<span data-ttu-id="7546c-128">Execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="7546c-128">Run one of the following commands:</span></span>

- <span data-ttu-id="7546c-129">Para definir a senha de um usuário para nunca expirar, execute o seguinte cmdlet usando o UPN ou a ID de usuário do usuário:</span><span class="sxs-lookup"><span data-stu-id="7546c-129">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="7546c-130">Para definir as senhas de todos os usuários em uma organização para nunca expirar, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7546c-130">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="7546c-131">As senhas definidas `-PasswordPolicies DisablePasswordExpiration` como idade ainda com base `pwdLastSet` no atributo.</span><span class="sxs-lookup"><span data-stu-id="7546c-131">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="7546c-132">Se você definir as senhas do usuário para nunca expirar e, em seguida, 90 dias por diante, as senhas expirarão.</span><span class="sxs-lookup"><span data-stu-id="7546c-132">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="7546c-133">Com base no `pwdLastSet` atributo, se você alterar a expiração `-PasswordPolicies None`para, todas as senhas com `pwdLastSet` mais de 90 dias exigirão que o usuário as altere na próxima vez que entrar.</span><span class="sxs-lookup"><span data-stu-id="7546c-133">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="7546c-134">Essa alteração pode afetar um grande número de usuários.</span><span class="sxs-lookup"><span data-stu-id="7546c-134">This change can affect a large number of users.</span></span>