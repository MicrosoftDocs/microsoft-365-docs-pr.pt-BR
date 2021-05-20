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
description: Faça login em sua conta de administração Microsoft 365 para definir algumas senhas individuais de usuário para nunca expirar usando Windows PowerShell.
ms.openlocfilehash: 0747e0bfe8a7389db554d5d6a7f685605e013306
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571920"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Definir a senha de um usuário individual para nunca expirar

Este artigo explica como definir uma senha para um usuário individual não expirar. Você tem que completar essas etapas usando o PowerShell.

## <a name="before-you-begin"></a>Antes de começar

Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../../business-video/admin-center-overview.md). 

Você deve ser [um administrador global ou administrador de senhas](about-admin-roles.md) para executar essas etapas.

Um administrador global de um serviço de nuvem da Microsoft pode usar o [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2?view=azureadps-2.0) para definir senhas para não expirar para usuários específicos. Você também pode usar cmdlets [AzureAD](/powershell/module/Azuread) para remover a configuração sem expiração ou para ver quais senhas de usuário estão definidas para nunca expirar.

Este guia se aplica a outros provedores, como Intune e Microsoft 365, que também contam com o Azure AD para serviços de identidade e diretório. A expiração da senha é a única parte da política que pode ser alterada.

> [!NOTE]
> Somente senhas para contas de usuário que não são sincronizadas através da sincronização do diretório podem ser configuradas para não expirar. Para obter mais informações sobre sincronização do diretório, consulte [Conexão AD com o Azure AD](/azure/active-directory/connect/active-directory-aadconnect).

## <a name="how-to-check-the-expiration-policy-for-a-password"></a>Como verificar a política de expiração de uma senha

Para obter mais informações sobre o comando Get-AzureADUser no módulo AzureAD, consulte o artigo de referência [Get-AzureADUser](/powershell/module/Azuread/Get-AzureADUser?view=azureadps-2.0).

Execute um dos seguintes comandos:

- Para ver se a senha de um único usuário está definida para nunca expirar, execute o seguinte cmdlet usando o UPN (por exemplo, *user@contoso.onmicrosoft.com*) ou o ID de usuário do usuário que você deseja verificar:

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

- Para ver a **senha nunca expira** a configuração para todos os usuários, execute o seguinte cmdlet:

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

- Para obter um relatório de todos os usuários com PasswordNeverExpires em CSV na área de trabalho do usuário atual com nome **ReportPasswordNeverExpires.csv**

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

> [!WARNING]
> Contas de usuário configuradas com o `-PasswordPolicies DisablePasswordExpiration` parâmetro ainda envelhecem com base no `pwdLastSet` atributo. Com base no `pwdLastSet` atributo, se você alterar a expiração para `-PasswordPolicies None` , todas as senhas que têm um pwdLastSet com mais de 90 dias exigem que o usuário as altere na próxima vez que fizer login. Essa mudança pode afetar um grande número de usuários.

### <a name="set-a-password-to-expire"></a>Defina uma senha para expirar

Execute um dos seguintes comandos:

- Para definir a senha de um usuário para que a senha expire, execute o seguinte cmdlet usando o UPN ou o ID de usuário do usuário:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None
    ```

- Para definir as senhas de todos os usuários da organização para que eles expirem, use o seguinte cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None
    ```

## <a name="related-content"></a>Conteúdo relacionado

[Permitir aos usuários redefinir suas próprias senhas](../add-users/let-users-reset-passwords.md) (artigo)

[Redefinir senhas](../add-users/reset-passwords.md) (artigo)