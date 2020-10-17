---
title: Definir um requisito de senha forte para os usuários
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
description: Saiba como definir os requisitos de senha forte para seus usuários, usando o Windows PowerShell.
ms.openlocfilehash: 1230ff4b4235ac5acbc28aa823506dfa5af26c2d
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48581012"
---
# <a name="set-strong-password-requirement-for-users"></a>Definir um requisito de senha forte para os usuários

Este artigo explica como definir os requisitos de senha forte para os seus usuários. Você precisa concluir estas etapas usando o PowerShell.

## <a name="before-you-begin"></a>Antes de começar

Este artigo é para pessoas que gerenciam a política de senha de uma empresa, escola ou sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../admin-overview/admin-overview.md). Você deve ser um [administrador de administrador ou de senha global](about-admin-roles.md) para executar estas etapas.

Você também deve se conectar ao Microsoft 365 com o PowerShell.

## <a name="set-strong-passwords"></a>Definir senhas fortes

1. [Conecte-se ao Microsoft 365 com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Usando o PowerShell, você pode desabilitar senhas fortes para usuários específicos com este comando:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> O userPrincipalName deve estar no formato de entrada no estilo da Internet, onde o nome do usuário é seguido pelo sinal de arroba (@) e um nome de domínio. Por exemplo: user@contoso.com.

## <a name="related-content"></a>Conteúdo relacionado

[Como se conectar ao Microsoft 365 com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Saiba mais sobre os comandos do PowerShell MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Mais informações sobre a política de senha](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)