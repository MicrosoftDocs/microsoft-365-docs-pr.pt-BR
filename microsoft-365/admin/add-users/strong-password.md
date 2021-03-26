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
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="e3bfd-103">Desativar requisitos fortes de senha para usuários</span><span class="sxs-lookup"><span data-stu-id="e3bfd-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="e3bfd-104">Este artigo explica como desativar os requisitos fortes de senha para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="e3bfd-105">Por padrão, os requisitos de senha fortes são aados em sua organização do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="e3bfd-106">Sua organização pode ter requisitos para desabilitar senhas fortes.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="e3bfd-107">Siga as etapas abaixo para desativar os requisitos fortes de senha.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="e3bfd-108">Você precisa concluir essas etapas usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e3bfd-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e3bfd-109">Before you begin</span></span>

<span data-ttu-id="e3bfd-110">Este artigo é para pessoas que gerenciam a política de senha para empresas, escolas ou entidades sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="e3bfd-111">Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="e3bfd-112">O que é uma conta de administrador?</span><span class="sxs-lookup"><span data-stu-id="e3bfd-112">What's an admin account?</span></span>](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview) <span data-ttu-id="e3bfd-113">Você deve ser um [administrador global ou administrador de senha](about-admin-roles.md) para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="e3bfd-114">Você também deve se conectar ao Microsoft 365 com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="e3bfd-115">Definir senhas fortes</span><span class="sxs-lookup"><span data-stu-id="e3bfd-115">Set strong passwords</span></span>

1. <span data-ttu-id="e3bfd-116">[Conecte-se ao Microsoft 365 com o PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="e3bfd-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="e3bfd-117">Usando o PowerShell, você pode desativar requisitos fortes de senha para todos os usuários com o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e3bfd-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="e3bfd-118">O userPrincipalName deve estar no formato de logon no estilo Internet, onde o nome do usuário é seguido pelo sinal de at (@) e um nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="e3bfd-119">Por exemplo: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e3bfd-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="e3bfd-120">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="e3bfd-120">Related content</span></span>

[<span data-ttu-id="e3bfd-121">Como se conectar ao Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3bfd-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="e3bfd-122">Mais informações sobre comandos do PowerShell MsolUser</span><span class="sxs-lookup"><span data-stu-id="e3bfd-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="e3bfd-123">Mais informações sobre a política de senha</span><span class="sxs-lookup"><span data-stu-id="e3bfd-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)