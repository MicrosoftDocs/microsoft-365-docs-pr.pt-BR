---
title: Definir senha de um usuário individual para nunca expirar
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: Saiba como definir que algumas senhas de usuário individuais nunca expirem, usando o Windows PowerShell.
ms.openlocfilehash: 01817aba0de1f5ca5f0b9bdf7feb1d03d72f6a24
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361744"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="0d48c-103">Definir senha de um usuário individual para nunca expirar</span><span class="sxs-lookup"><span data-stu-id="0d48c-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="0d48c-104">Este artigo explica como definir uma senha para que um usuário individual não expire.</span><span class="sxs-lookup"><span data-stu-id="0d48c-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="0d48c-105">Você precisa concluir estas etapas usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d48c-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0d48c-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0d48c-106">Before you begin</span></span>

<span data-ttu-id="0d48c-107">Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="0d48c-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="0d48c-108">Para concluir estas etapas, você precisa entrar com sua conta de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d48c-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="0d48c-109">[O que é uma conta de administrador?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0d48c-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> 

<span data-ttu-id="0d48c-110">Você deve ser um [administrador de administrador ou de senha global](about-admin-roles.md) para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0d48c-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="0d48c-111">Um administrador global para um serviço de nuvem da Microsoft pode usar o [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) para definir senhas que não expirem para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="0d48c-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="0d48c-112">Você também pode usar os cmdlets do [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) para remover a configuração nunca expira ou para ver quais senhas de usuário estão definidas para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="0d48c-112">You can also use [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="0d48c-113">Este guia se aplica a outros provedores, como o Intune e o Microsoft 365, que também dependem do Azure AD para serviços de identidade e diretório.</span><span class="sxs-lookup"><span data-stu-id="0d48c-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="0d48c-114">A expiração da senha é a única parte da política que pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="0d48c-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="0d48c-115">Somente senhas para contas de usuário que não estão sincronizadas por meio da sincronização de diretórios podem ser configuradas para não expirar.</span><span class="sxs-lookup"><span data-stu-id="0d48c-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="0d48c-116">Para obter mais informações sobre a sincronização de diretórios, consulte [Connect ad with Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="0d48c-116">For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="0d48c-117">Como verificar a política de expiração de uma senha</span><span class="sxs-lookup"><span data-stu-id="0d48c-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="0d48c-118">Para obter mais informações sobre o comando Get-AzureADUser no módulo AzureAD, consulte o artigo de referência [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="0d48c-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="0d48c-119">Execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="0d48c-119">Run one of the following commands:</span></span>

- <span data-ttu-id="0d48c-120">Para ver se a senha de um único usuário está definida como nunca expirar, execute o seguinte cmdlet usando o UPN (por exemplo, *User@contoso.onmicrosoft.com*) ou a ID de usuário do usuário que você deseja verificar:</span><span class="sxs-lookup"><span data-stu-id="0d48c-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="0d48c-121">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="0d48c-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="0d48c-122">Para ver a configuração da **senha nunca expira** para todos os usuários, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0d48c-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="0d48c-123">Para obter um relatório de todos os usuários com o PasswordNeverExpires, em HTML na área de trabalho do usuário atual com o nome  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="0d48c-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="0d48c-124">Para obter um relatório de todos os usuários com PasswordNeverExpires, em CSV na área de trabalho do usuário atual com o nome **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="0d48c-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv

## Set a password to never expire

Run one of the following commands:

- To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- <span data-ttu-id="0d48c-125">Para definir as senhas de todos os usuários em uma organização para nunca expirar, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0d48c-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a><span data-ttu-id="0d48c-126">Definir uma senha para expirar</span><span class="sxs-lookup"><span data-stu-id="0d48c-126">Set a password to expire</span></span>

<span data-ttu-id="0d48c-127">Execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="0d48c-127">Run one of the following commands:</span></span>

- <span data-ttu-id="0d48c-128">Para definir a senha de um usuário para que a senha expire, execute o seguinte cmdlet usando o UPN ou a ID do usuário:</span><span class="sxs-lookup"><span data-stu-id="0d48c-128">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="0d48c-129">Para definir as senhas de todos os usuários da organização de modo que eles expirem, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0d48c-129">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> <span data-ttu-id="0d48c-130">As contas de usuário configuradas com o `-PasswordPolicies DisablePasswordExpiration` parâmetro ainda envelhecem com base no `pwdLastSet` atributo de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="0d48c-130">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` user account attribute.</span></span> <span data-ttu-id="0d48c-131">Por exemplo, se você definir senhas do usuário para nunca expirar e, em seguida, 90 ou mais dias, as senhas ainda expirarem.</span><span class="sxs-lookup"><span data-stu-id="0d48c-131">For example, if you set user passwords to never expire and then 90 or more days go by, the passwords still expire.</span></span> <span data-ttu-id="0d48c-132">Com base no `pwdLastSet` atributo de conta de usuário, para contas de usuário configuradas com o `-PasswordPolicies None` parâmetro, todas as senhas com `pwdLastSet` mais de 90 dias exigem que o usuário as altere na próxima vez que entrar. Essa alteração pode afetar um grande número de usuários.</span><span class="sxs-lookup"><span data-stu-id="0d48c-132">Based on the `pwdLastSet` user account attribute, for user accounts configured with the `-PasswordPolicies None` parameter, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in.This change can affect a large number of users.</span></span>

## <a name="related-content"></a><span data-ttu-id="0d48c-133">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="0d48c-133">Related content</span></span>

[<span data-ttu-id="0d48c-134">Permitir que os usuários redefinam as próprias senhas</span><span class="sxs-lookup"><span data-stu-id="0d48c-134">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="0d48c-135">Redefinir senhas</span><span class="sxs-lookup"><span data-stu-id="0d48c-135">Reset passwords</span></span>](../add-users/reset-passwords.md)