---
title: Desativar requisitos fortes de senha para usuários
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
description: Saiba como definir requisitos de senha fortes para seus usuários usando Windows PowerShell.
ms.openlocfilehash: de2f47bb88fe4cb3d00e45698fe006035faa4e5c
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222063"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Desativar requisitos fortes de senha para usuários

Este artigo explica como desativar os requisitos fortes de senha para seus usuários. Por padrão, os requisitos de senha fortes são aados em sua organização do Microsoft 365 para empresas. Sua organização pode ter requisitos para desabilitar senhas fortes. Siga as etapas abaixo para desativar os requisitos fortes de senha. Você precisa concluir essas etapas usando o PowerShell.

## <a name="before-you-begin"></a>Antes de começar

Este artigo é para pessoas que gerenciam a política de senha para empresas, escolas ou entidades sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview) Você deve ser um [administrador global ou administrador de senha](about-admin-roles.md) para executar essas etapas.

Você também deve se conectar ao Microsoft 365 com o PowerShell.

## <a name="set-strong-passwords"></a>Definir senhas fortes

1. [Conecte-se ao Microsoft 365 com o PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

2. Usando o PowerShell, você pode desativar requisitos fortes de senha para todos os usuários com o seguinte comando:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> O userPrincipalName deve estar no formato de logon no estilo Internet, onde o nome do usuário é seguido pelo sinal de at (@) e um nome de domínio. Por exemplo: user@contoso.com.

## <a name="related-content"></a>Conteúdo relacionado

[Como se conectar ao Microsoft 365 com o PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Mais informações sobre comandos do PowerShell MsolUser](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Mais informações sobre a política de senha](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)