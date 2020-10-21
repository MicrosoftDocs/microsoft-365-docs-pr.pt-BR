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
ms.openlocfilehash: 9f6fd61396d99245ffeabf757d3cb65c5d5cb85e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646614"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="7fb48-103">Definir um requisito de senha forte para os usuários</span><span class="sxs-lookup"><span data-stu-id="7fb48-103">Set strong password requirement for users</span></span>

<span data-ttu-id="7fb48-104">Este artigo explica como desativar os requisitos de senha forte para os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="7fb48-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="7fb48-105">Os requisitos de senha forte são ativados por padrão na sua organização do Microsoft 365 for Business.</span><span class="sxs-lookup"><span data-stu-id="7fb48-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="7fb48-106">Sua organização pode ter requisitos para desabilitar senhas fortes.</span><span class="sxs-lookup"><span data-stu-id="7fb48-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="7fb48-107">Siga as etapas abaixo para desativar os requisitos de senha forte.</span><span class="sxs-lookup"><span data-stu-id="7fb48-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="7fb48-108">Você precisa concluir estas etapas usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fb48-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7fb48-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7fb48-109">Before you begin</span></span>

<span data-ttu-id="7fb48-110">Este artigo é para pessoas que gerenciam a política de senha de uma empresa, escola ou sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="7fb48-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="7fb48-111">Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fb48-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="7fb48-112">O que é uma conta de administrador?</span><span class="sxs-lookup"><span data-stu-id="7fb48-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="7fb48-113">Você deve ser um [administrador de administrador ou de senha global](about-admin-roles.md) para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7fb48-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="7fb48-114">Você também deve se conectar ao Microsoft 365 com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fb48-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="7fb48-115">Definir senhas fortes</span><span class="sxs-lookup"><span data-stu-id="7fb48-115">Set strong passwords</span></span>

1. <span data-ttu-id="7fb48-116">[Conecte-se ao Microsoft 365 com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7fb48-116">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="7fb48-117">Usando o PowerShell, você pode desativar os requisitos de senha forte para todos os usuários com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7fb48-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="7fb48-118">O userPrincipalName deve estar no formato de entrada no estilo da Internet, onde o nome do usuário é seguido pelo sinal de arroba (@) e um nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="7fb48-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="7fb48-119">Por exemplo: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7fb48-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="7fb48-120">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="7fb48-120">Related content</span></span>

[<span data-ttu-id="7fb48-121">Como se conectar ao Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fb48-121">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="7fb48-122">Saiba mais sobre os comandos do PowerShell MsolUser</span><span class="sxs-lookup"><span data-stu-id="7fb48-122">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="7fb48-123">Mais informações sobre a política de senha</span><span class="sxs-lookup"><span data-stu-id="7fb48-123">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)