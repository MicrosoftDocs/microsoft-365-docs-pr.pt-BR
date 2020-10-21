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
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626138"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="43bb8-103">Definir um requisito de senha forte para os usuários</span><span class="sxs-lookup"><span data-stu-id="43bb8-103">Set strong password requirement for users</span></span>

<span data-ttu-id="43bb8-104">Este artigo explica como definir os requisitos de senha forte para os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="43bb8-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="43bb8-105">Você precisa concluir estas etapas usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43bb8-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="43bb8-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="43bb8-106">Before you begin</span></span>

<span data-ttu-id="43bb8-107">Este artigo é para pessoas que gerenciam a política de senha de uma empresa, escola ou sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="43bb8-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="43bb8-108">Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="43bb8-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="43bb8-109">[O que é uma conta de administrador?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="43bb8-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="43bb8-110">Você deve ser um [administrador de administrador ou de senha global](about-admin-roles.md) para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="43bb8-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="43bb8-111">Você também deve se conectar ao Microsoft 365 com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="43bb8-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="43bb8-112">Definir senhas fortes</span><span class="sxs-lookup"><span data-stu-id="43bb8-112">Set strong passwords</span></span>

1. <span data-ttu-id="43bb8-113">[Conecte-se ao Microsoft 365 com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="43bb8-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="43bb8-114">Usando o PowerShell, você pode ativar os requisitos de senha forte para todos os usuários com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="43bb8-114">Using PowerShell, you can turn on strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> <span data-ttu-id="43bb8-115">O userPrincipalName deve estar no formato de entrada no estilo da Internet, onde o nome do usuário é seguido pelo sinal de arroba (@) e um nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="43bb8-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="43bb8-116">Por exemplo: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="43bb8-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="43bb8-117">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="43bb8-117">Related content</span></span>

[<span data-ttu-id="43bb8-118">Como se conectar ao Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="43bb8-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="43bb8-119">Saiba mais sobre os comandos do PowerShell MsolUser</span><span class="sxs-lookup"><span data-stu-id="43bb8-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="43bb8-120">Mais informações sobre a política de senha</span><span class="sxs-lookup"><span data-stu-id="43bb8-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)