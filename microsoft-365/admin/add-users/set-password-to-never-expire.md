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
ms.openlocfilehash: 3d5d65f687a5ed02e0e20ff77482f7bef5b6b695
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173491"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="583e9-103">Definir a senha de um usuário individual para nunca expirar</span><span class="sxs-lookup"><span data-stu-id="583e9-103">Set an individual user's password to never expire</span></span>

## <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="583e9-104">Definir a política de expiração de senha para sua organização</span><span class="sxs-lookup"><span data-stu-id="583e9-104">Set the password expiration policy for your organization</span></span>

1. <span data-ttu-id="583e9-105">No centro de administração, vá para a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">configurações</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="583e9-105">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Settings</a> page.</span></span>
2. <span data-ttu-id="583e9-106">Na parte superior da página configurações, selecione **segurança & privacidade**.</span><span class="sxs-lookup"><span data-stu-id="583e9-106">At the top of the Settings page select **Security & Privacy**.</span></span>
3. <span data-ttu-id="583e9-107">Selecione **Política de expiração de senha**.</span><span class="sxs-lookup"><span data-stu-id="583e9-107">Select **Password expiration policy**.</span></span> 
4. <span data-ttu-id="583e9-108">Se as senhas estiverem definidas para nunca expirar, clique na caixa de seleção ao lado de **definir senhas de usuário para expirar após um número de dias**.</span><span class="sxs-lookup"><span data-stu-id="583e9-108">If passwords are set to never expire, click the check box next to **Set user passwords to expire after a number of days**.</span></span> <span data-ttu-id="583e9-109">Você terá a opção de especificar o número de dias até que as senhas expirem.</span><span class="sxs-lookup"><span data-stu-id="583e9-109">You'll get the option to specify the number of days until passwords expire.</span></span>

## <a name="set-the-password-expiration-policy-for-individual-users"></a><span data-ttu-id="583e9-110">Definir a política de expiração de senha para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="583e9-110">Set the password expiration policy for individual users</span></span>

<span data-ttu-id="583e9-111">Um administrador global para um serviço de nuvem da Microsoft pode usar o [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) para definir senhas que não expirem para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="583e9-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="583e9-112">Você também pode usar os cmdlets do [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) para remover a configuração nunca expira ou para ver quais senhas de usuário estão definidas para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="583e9-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="583e9-113">Este guia se aplica a outros provedores, como o Intune e o Microsoft 365, que também dependem do Azure AD para serviços de identidade e diretório.</span><span class="sxs-lookup"><span data-stu-id="583e9-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="583e9-114">A expiração da senha é a única parte da política que pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="583e9-114">Password expiration is the only part of the policy that can be changed.</span></span>

<span data-ttu-id="583e9-115">Para obter mais informações sobre o Azure AD PowerShell para Graph, confira [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="583e9-115">For more information about Azure AD PowerShell for Graph, see [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).</span></span>

> [!NOTE]
> <span data-ttu-id="583e9-116">Somente senhas para contas de usuário que não estão sincronizadas por meio da sincronização de diretórios podem ser configuradas para não expirar.</span><span class="sxs-lookup"><span data-stu-id="583e9-116">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="583e9-117">Para obter mais informações sobre a sincronização de diretórios, consulte [Connect ad with Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="583e9-117">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

### <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="583e9-118">Como verificar a política de expiração de uma senha</span><span class="sxs-lookup"><span data-stu-id="583e9-118">How to check the expiration policy for a password</span></span>

<span data-ttu-id="583e9-119">Para obter mais informações sobre o comando Get-AzureADUser no módulo AzureAD, consulte o artigo de referência [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="583e9-119">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="583e9-120">Execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="583e9-120">Run one of the following commands:</span></span>

- <span data-ttu-id="583e9-121">Para ver se a senha de um único usuário está definida como nunca expirar, execute o seguinte cmdlet usando o UPN (por exemplo, *User@contoso.onmicrosoft.com*) ou a ID de usuário do usuário que você deseja verificar:</span><span class="sxs-lookup"><span data-stu-id="583e9-121">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="583e9-122">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="583e9-122">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="583e9-123">Para ver a configuração da **senha nunca expira** para todos os usuários, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="583e9-123">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="583e9-124">Para obter um relatório de todos os usuários com o PasswordNeverExpires, em HTML na área de trabalho do usuário atual com o nome **ReportPasswordNeverExpires. html**</span><span class="sxs-lookup"><span data-stu-id="583e9-124">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="583e9-125">Para obter um relatório de todos os usuários com PasswordNeverExpires, em CSV na área de trabalho do usuário atual com o nome **ReportPasswordNeverExpires. csv**</span><span class="sxs-lookup"><span data-stu-id="583e9-125">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="583e9-126">Definir uma senha para expirar</span><span class="sxs-lookup"><span data-stu-id="583e9-126">Set a password to expire</span></span>

<span data-ttu-id="583e9-127">Execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="583e9-127">Run one of the following commands:</span></span>

- <span data-ttu-id="583e9-128">Para definir a senha de um usuário para que a senha expire, execute o seguinte cmdlet usando o UPN ou a ID do usuário:</span><span class="sxs-lookup"><span data-stu-id="583e9-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="583e9-129">Para definir as senhas de todos os usuários da organização de modo que eles expirem, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="583e9-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

### <a name="set-a-password-to-never-expire"></a><span data-ttu-id="583e9-130">Definir uma senha para nunca expirar</span><span class="sxs-lookup"><span data-stu-id="583e9-130">Set a password to never expire</span></span>

<span data-ttu-id="583e9-131">Execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="583e9-131">Run one of the following commands:</span></span>

- <span data-ttu-id="583e9-132">Para definir a senha de um usuário para nunca expirar, execute o seguinte cmdlet usando o UPN ou a ID de usuário do usuário:</span><span class="sxs-lookup"><span data-stu-id="583e9-132">To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="583e9-133">Para definir as senhas de todos os usuários em uma organização para nunca expirar, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="583e9-133">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="583e9-134">As senhas definidas `-PasswordPolicies DisablePasswordExpiration` como idade ainda com base `pwdLastSet` no atributo.</span><span class="sxs-lookup"><span data-stu-id="583e9-134">Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="583e9-135">Se você definir as senhas do usuário para nunca expirar e, em seguida, 90 dias por diante, as senhas expirarão.</span><span class="sxs-lookup"><span data-stu-id="583e9-135">If you set the user passwords to never expire and then 90+ days go by, the passwords expire.</span></span> <span data-ttu-id="583e9-136">Com base no `pwdLastSet` atributo, se você alterar a expiração `-PasswordPolicies None`para, todas as senhas com `pwdLastSet` mais de 90 dias exigirão que o usuário as altere na próxima vez que entrar.</span><span class="sxs-lookup"><span data-stu-id="583e9-136">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="583e9-137">Essa alteração pode afetar um grande número de usuários.</span><span class="sxs-lookup"><span data-stu-id="583e9-137">This change can affect a large number of users.</span></span>
