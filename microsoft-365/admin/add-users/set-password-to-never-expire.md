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
ms.openlocfilehash: a0b247f4b736ecccab57398e1e7131f0a06a2958
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286256"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Definir a senha de um usuário individual para nunca expirar

Este artigo explica como definir uma senha para que um usuário individual não expire. Você precisa concluir essas etapas usando o PowerShell.

## <a name="before-you-begin"></a>Antes de começar

Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../../business-video/admin-center-overview.md).

Você deve ser um [administrador global ou administrador de senha](about-admin-roles.md) para executar essas etapas.

Um administrador global de um serviço de nuvem da Microsoft pode usar o [Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2) para Graph definir senhas para não expirar para usuários específicos. Você também pode usar cmdlets do [AzureAD](/powershell/module/Azuread) para remover a configuração nunca expira ou para ver quais senhas de usuário estão definidas para nunca expirar.

Este guia se aplica a outros provedores, como o Intune e o Microsoft 365, que também dependem do Azure AD para serviços de identidade e diretório. A expiração de senha é a única parte da política que pode ser alterada.

> [!NOTE]
> Somente senhas para contas de usuário que não são sincronizadas por meio da sincronização de diretórios podem ser configuradas para não expirar. Para obter mais informações sobre a sincronização de diretórios, [consulte Conexão AD com o Azure AD](/azure/active-directory/connect/active-directory-aadconnect).

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Como verificar a política de expiração para uma senha

Para obter mais informações sobre o Get-AzureADUser no módulo do AzureAD, consulte o artigo de referência [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser).

Execute um dos seguintes comandos:

- Para ver se a senha de um único usuário está definida para nunca expirar, execute o seguinte cmdlet usando o UPN (por exemplo, user@contoso.onmicrosoft.com ) ou *a* ID de usuário do usuário que você deseja verificar:

    ```powershell
    Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

    Exemplo:

    ```powershell
    Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    }
    ```

- Para ver a **configuração Senha nunca expira para** todos os usuários, execute o seguinte cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Para obter um relatório de todos os usuários com PasswordNeverExpires em Html na área de trabalho do usuário atual com nome  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```

- Para obter um relatório de todos os usuários com PasswordNeverExpires no CSV na área de trabalho do usuário atual com nome **ReportPasswordNeverExpires.csv**

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

- Para definir as senhas de todos os usuários de uma organização para nunca expirar, execute o seguinte cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> As contas de usuário configuradas com `-PasswordPolicies DisablePasswordExpiration` o parâmetro ainda têm idade com base no `pwdLastSet` atributo. Com base no atributo, se você alterar a expiração para , todas as senhas com pwdLastSet com mais de 90 dias exigem que o usuário as altere na próxima vez em que `pwdLastSet` `-PasswordPolicies None` entrar. Essa alteração pode afetar um grande número de usuários.

### <a name="set-a-password-to-expire"></a>Definir uma senha para expirar

Execute um dos seguintes comandos:

- Para definir a senha de um usuário para que a senha expire, execute o seguinte cmdlet usando o UPN ou a ID do usuário:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Para definir as senhas de todos os usuários da organização para que eles expirem, use o seguinte cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Conteúdo relacionado

[Permitir que os usuários redefinim suas próprias senhas](../add-users/let-users-reset-passwords.md) (artigo)\
[Redefinir senhas](../add-users/reset-passwords.md) (artigo)\
[Definir a política de expiração de senha para sua organização](../manage/set-password-expiration-policy.md) (artigo)