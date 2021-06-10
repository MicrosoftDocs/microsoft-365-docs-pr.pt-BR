---
title: Definir a senha de um usuário individual para nunca expirar
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
description: Entre na sua conta de administrador Microsoft 365 para definir algumas senhas de usuário individuais para nunca expirar usando Windows PowerShell.
ms.openlocfilehash: 12c717d8d625b0135f185b1af131db00e9762c73
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635553"
---
# <a name="set-an-individual-users-password-to-never-expire"></a><span data-ttu-id="77892-103">Definir a senha de um usuário individual para nunca expirar</span><span class="sxs-lookup"><span data-stu-id="77892-103">Set an individual user's password to never expire</span></span>

<span data-ttu-id="77892-104">Este artigo explica como definir uma senha para que um usuário individual não expire.</span><span class="sxs-lookup"><span data-stu-id="77892-104">This article explains how to set a password for an individual user to not expire.</span></span> <span data-ttu-id="77892-105">Você precisa concluir essas etapas usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77892-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="77892-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="77892-106">Before you begin</span></span>

<span data-ttu-id="77892-107">Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="77892-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="77892-108">Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="77892-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="77892-109">[O que é uma conta de administrador?](../../business-video/admin-center-overview.md).</span><span class="sxs-lookup"><span data-stu-id="77892-109">[What's an admin account?](../../business-video/admin-center-overview.md).</span></span> 

<span data-ttu-id="77892-110">Você deve ser um [administrador global ou administrador de senha](about-admin-roles.md) para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="77892-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="77892-111">Um administrador global de um serviço de nuvem da Microsoft pode usar o [Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) para Graph definir senhas para não expirar para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="77892-111">A global admin for a Microsoft cloud service can use the [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) to set passwords not to expire for specific users.</span></span> <span data-ttu-id="77892-112">Você também pode usar cmdlets do [AzureAD](/powershell/module/Azuread) para remover a configuração nunca expira ou para ver quais senhas de usuário estão definidas para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="77892-112">You can also use [AzureAD](/powershell/module/Azuread) cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire.</span></span>

<span data-ttu-id="77892-113">Este guia se aplica a outros provedores, como o Intune e o Microsoft 365, que também dependem do Azure AD para serviços de identidade e diretório.</span><span class="sxs-lookup"><span data-stu-id="77892-113">This guide applies to other providers, such as Intune and Microsoft 365, which also rely on Azure AD for identity and directory services.</span></span> <span data-ttu-id="77892-114">A expiração de senha é a única parte da política que pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="77892-114">Password expiration is the only part of the policy that can be changed.</span></span>

> [!NOTE]
> <span data-ttu-id="77892-115">Somente senhas para contas de usuário que não são sincronizadas por meio da sincronização de diretórios podem ser configuradas para não expirar.</span><span class="sxs-lookup"><span data-stu-id="77892-115">Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire.</span></span> <span data-ttu-id="77892-116">Para obter mais informações sobre a sincronização de diretórios, [consulte Conexão AD com o Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="77892-116">For more information about directory synchronization, see [Connect AD with Azure AD](/azure/active-directory/connect/active-directory-aadconnect).</span></span>

## <a name="how-to-check-the-expiration-policy-for-a-password"></a><span data-ttu-id="77892-117">Como verificar a política de expiração para uma senha</span><span class="sxs-lookup"><span data-stu-id="77892-117">How to check the expiration policy for a password</span></span>

<span data-ttu-id="77892-118">Para obter mais informações sobre o Get-AzureADUser no módulo do AzureAD, consulte o artigo de referência [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="77892-118">For more information about the Get-AzureADUser command in the AzureAD module, see the reference article [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).</span></span>

<span data-ttu-id="77892-119">Execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="77892-119">Run one of the following commands:</span></span>

- <span data-ttu-id="77892-120">Para ver se a senha de um único usuário está definida para nunca expirar, execute o seguinte cmdlet usando o UPN (por exemplo, user@contoso.onmicrosoft.com ) ou *a* ID de usuário do usuário que você deseja verificar:</span><span class="sxs-lookup"><span data-stu-id="77892-120">To see if a single user's password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    <span data-ttu-id="77892-121">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="77892-121">Example:</span></span>

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```  

- <span data-ttu-id="77892-122">Para ver a **configuração Senha nunca expira para** todos os usuários, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="77892-122">To see the **Password never expires** setting for all users, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- <span data-ttu-id="77892-123">Para obter um relatório de todos os usuários com PasswordNeverExpires em Html na área de trabalho do usuário atual com nome  **ReportPasswordNeverExpires.html**</span><span class="sxs-lookup"><span data-stu-id="77892-123">To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**</span></span>

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- <span data-ttu-id="77892-124">Para obter um relatório de todos os usuários com PasswordNeverExpires no CSV na área de trabalho do usuário atual com nome **ReportPasswordNeverExpires.csv**</span><span class="sxs-lookup"><span data-stu-id="77892-124">To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**</span></span>

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

- <span data-ttu-id="77892-125">Para definir as senhas de todos os usuários de uma organização para nunca expirar, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="77892-125">To set the passwords of all the users in an organization to never expire, run the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> <span data-ttu-id="77892-126">As contas de usuário configuradas com `-PasswordPolicies DisablePasswordExpiration` o parâmetro ainda têm idade com base no `pwdLastSet` atributo.</span><span class="sxs-lookup"><span data-stu-id="77892-126">User accounts configured with the `-PasswordPolicies DisablePasswordExpiration` parameter still age based on the `pwdLastSet` attribute.</span></span> <span data-ttu-id="77892-127">Com base no atributo, se você alterar a expiração para , todas as senhas com pwdLastSet com mais de 90 dias exigem que o usuário as altere na próxima vez em que `pwdLastSet` `-PasswordPolicies None` entrar.</span><span class="sxs-lookup"><span data-stu-id="77892-127">Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a pwdLastSet older than 90 days require the user to change them the next time they sign in.</span></span> <span data-ttu-id="77892-128">Essa alteração pode afetar um grande número de usuários.</span><span class="sxs-lookup"><span data-stu-id="77892-128">This change can affect a large number of users.</span></span>

### <a name="set-a-password-to-expire"></a><span data-ttu-id="77892-129">Definir uma senha para expirar</span><span class="sxs-lookup"><span data-stu-id="77892-129">Set a password to expire</span></span>

<span data-ttu-id="77892-130">Execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="77892-130">Run one of the following commands:</span></span>

- <span data-ttu-id="77892-131">Para definir a senha de um usuário para que a senha expire, execute o seguinte cmdlet usando o UPN ou a ID do usuário:</span><span class="sxs-lookup"><span data-stu-id="77892-131">To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:</span></span>

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- <span data-ttu-id="77892-132">Para definir as senhas de todos os usuários da organização para que eles expirem, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="77892-132">To set the passwords of all users in the organization so that they expire, use the following cmdlet:</span></span>

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a><span data-ttu-id="77892-133">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="77892-133">Related content</span></span>

<span data-ttu-id="77892-134">[Permitir que os usuários redefinim suas próprias senhas](../add-users/let-users-reset-passwords.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="77892-134">[Let users reset their own passwords](../add-users/let-users-reset-passwords.md) (article)</span></span>\
<span data-ttu-id="77892-135">[Redefinir senhas](../add-users/reset-passwords.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="77892-135">[Reset passwords](../add-users/reset-passwords.md) (article)</span></span>\
<span data-ttu-id="77892-136">[Definir a política de expiração de senha para sua organização](../manage/set-password-expiration-policy.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="77892-136">[Set the password expiration policy for your organization](../manage/set-password-expiration-policy.md) (article)</span></span>