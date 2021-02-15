---
title: Desativar requisitos de senha forte para usuários
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
description: Saiba como definir requisitos de senha forte para seus usuários usando o Windows PowerShell.
ms.openlocfilehash: f9a0b76d024cc18552657144e4ccf8de8a72f0d9
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655730"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Desativar requisitos de senha forte para usuários

Este artigo explica como desativar os requisitos de senha forte para seus usuários. Por padrão, os requisitos de senha forte estão ligado em sua organização do Microsoft 365 para empresas. Sua organização pode ter requisitos para desabilitar senhas fortes. Siga as etapas abaixo para desativar os requisitos de senha forte. Você precisa concluir essas etapas usando o PowerShell.

## <a name="before-you-begin"></a>Antes de começar

Este artigo é destinado às pessoas que gerenciam a política de senha para uma empresa, escola ou entidade sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../admin-overview/admin-overview.md) Você deve ser um [administrador global ou administrador de senhas](about-admin-roles.md) para executar estas etapas.

Você também deve se conectar ao Microsoft 365 com o PowerShell.

## <a name="set-strong-passwords"></a>Definir senhas fortes

1. [Conecte-se ao Microsoft 365 com o PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

2. Usando o PowerShell, você pode desativar os requisitos de senha forte para todos os usuários com o seguinte comando:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name. Por exemplo: user@contoso.com.

## <a name="related-content"></a>Conteúdo relacionado

[Como se conectar ao Microsoft 365 com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Mais informações sobre os comandos MsolUser do PowerShell](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Mais informações sobre a política de senha](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)