---
title: Definir senha de um usuário individual para nunca expirar
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
description: Saiba como definir que algumas senhas de usuário individuais nunca expirem, usando o Windows PowerShell.
ms.openlocfilehash: 9497dfb5793ddbfc3d6845ec1efba91ad972ea38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646650"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Definir senha de um usuário individual para nunca expirar

Este artigo explica como definir uma senha para que um usuário individual não expire. Você precisa concluir estas etapas usando o PowerShell.

## <a name="before-you-begin"></a>Antes de começar

Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../admin-overview/admin-overview.md). 

Você deve ser um [administrador de administrador ou de senha global](about-admin-roles.md) para executar estas etapas.

Um administrador global para um serviço de nuvem da Microsoft pode usar o [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) para definir senhas que não expirem para usuários específicos. Você também pode usar os cmdlets do [AzureAD](https://docs.microsoft.com/powershell/module/Azuread) para remover a configuração nunca expira ou para ver quais senhas de usuário estão definidas para nunca expirar.

Este guia se aplica a outros provedores, como o Intune e o Microsoft 365, que também dependem do Azure AD para serviços de identidade e diretório. A expiração da senha é a única parte da política que pode ser alterada.

> [!NOTE]
> Somente senhas para contas de usuário que não estão sincronizadas por meio da sincronização de diretórios podem ser configuradas para não expirar. Para obter mais informações sobre a sincronização de diretórios, consulte [Connect ad with Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Como verificar a política de expiração de uma senha

Para obter mais informações sobre o comando Get-AzureADUser no módulo AzureAD, consulte o artigo de referência [Get-AzureADUser](https://docs.microsoft.com/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).

Execute um dos seguintes comandos:

- Para ver se a senha de um único usuário está definida como nunca expirar, execute o seguinte cmdlet usando o UPN (por exemplo, *User@contoso.onmicrosoft.com*) ou a ID de usuário do usuário que você deseja verificar:

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

- Para ver a configuração da **senha nunca expira** para todos os usuários, execute o seguinte cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
     }
    ```

- Para obter um relatório de todos os usuários com o PasswordNeverExpires, em HTML na área de trabalho do usuário atual com o nome  **ReportPasswordNeverExpires.html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Para obter um relatório de todos os usuários com PasswordNeverExpires, em CSV na área de trabalho do usuário atual com o nome **ReportPasswordNeverExpires.csv**

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

- Para definir as senhas de todos os usuários em uma organização para nunca expirar, execute o seguinte cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

### <a name="set-a-password-to-expire"></a>Definir uma senha para expirar

Execute um dos seguintes comandos:

- Para definir a senha de um usuário para que a senha expire, execute o seguinte cmdlet usando o UPN ou a ID do usuário:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Para definir as senhas de todos os usuários da organização de modo que eles expirem, use o seguinte cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

> [!WARNING]
> As contas de usuário configuradas com o `-PasswordPolicies DisablePasswordExpiration` parâmetro ainda envelhecem com base no `pwdLastSet` atributo de conta de usuário. Por exemplo, se você definir senhas do usuário para nunca expirar e, em seguida, 90 ou mais dias, as senhas ainda expirarem. Com base no `pwdLastSet` atributo de conta de usuário, para contas de usuário configuradas com o `-PasswordPolicies None` parâmetro, todas as senhas com `pwdLastSet` mais de 90 dias exigem que o usuário as altere na próxima vez que entrar. Essa alteração pode afetar um grande número de usuários.

## <a name="related-content"></a>Conteúdo relacionado

[Permitir que os usuários redefinam as próprias senhas](../add-users/let-users-reset-passwords.md)

[Redefinir senhas](../add-users/reset-passwords.md)