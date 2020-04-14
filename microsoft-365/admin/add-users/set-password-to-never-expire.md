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
ms.openlocfilehash: 04fb2b0c17f695c41df2f8b1277c7918054ae9fe
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240230"
---
# <a name="set-an-individual-users-password-to-never-expire"></a>Definir a senha de um usuário individual para nunca expirar

## <a name="set-the-password-expiration-policy-for-your-organization"></a>Definir a política de expiração de senha para sua organização

1. No centro de administração, vá para a página **configurações** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">segurança & privacidade</a> .
2. Ao lado de **política de senha** , selecione **Editar**. 
3. Se as senhas estiverem definidas para nunca expirar, defina a **opção para desativado**. Você terá a opção de especificar o número de dias até que as senhas expirem.

## <a name="set-the-password-expiration-policy-for-individual-users"></a>Definir a política de expiração de senha para usuários individuais

Um administrador global para um serviço de nuvem da Microsoft pode usar o PowerShell do Azure Active Directory para Graph para definir senhas que não expirem para usuários específicos. Você também pode usar os cmdlets do AzureAD para remover a configuração nunca expira ou para ver quais senhas de usuário estão definidas para nunca expirar.

Este guia se aplica a outros provedores, como o Intune e o Office 365, que também dependem do Azure AD para serviços de identidade e diretório. A expiração da senha é a única parte da política que pode ser alterada.

Para obter mais informações sobre o Azure AD PowerShell para Graph, confira [Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0).

> [!NOTE]
> Somente senhas para contas de usuário que não estão sincronizadas por meio da sincronização de diretórios podem ser configuradas para não expirar. Para obter mais informações sobre a sincronização de diretórios, consulte [Connect ad with Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="how-to-check-the-expiration-policy-for-a-password"></a>Como verificar a política de expiração de uma senha

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

- Para obter um relatório de todos os usuários com o PasswordNeverExpires, em HTML na área de trabalho do usuário atual com o nome **ReportPasswordNeverExpires. html**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
    ```  

- Para obter um relatório de todos os usuários com PasswordNeverExpires, em CSV na área de trabalho do usuário atual com o nome **ReportPasswordNeverExpires. csv**

    ```powershell
    Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
        N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
    } | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
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

### <a name="set-a-password-to-never-expire"></a>Definir uma senha para nunca expirar

Execute um dos seguintes comandos:

- Para definir a senha de um usuário para nunca expirar, execute o seguinte cmdlet usando o UPN ou a ID de usuário do usuário:

    ```powershell
    Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration
    ```

- Para definir as senhas de todos os usuários em uma organização para nunca expirar, execute o seguinte cmdlet:

    ```powershell
    Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration
    ```

> [!WARNING]
> As senhas definidas `-PasswordPolicies DisablePasswordExpiration` como idade ainda com base `pwdLastSet` no atributo. Se você definir as senhas do usuário para nunca expirar e, em seguida, 90 dias por diante, as senhas expirarão. Com base no `pwdLastSet` atributo, se você alterar a expiração `-PasswordPolicies None`para, todas as senhas com `pwdLastSet` mais de 90 dias exigirão que o usuário as altere na próxima vez que entrar. Essa alteração pode afetar um grande número de usuários.