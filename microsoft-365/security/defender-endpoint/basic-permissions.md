---
title: Usar permissões básicas para acessar Central de Segurança do Microsoft Defender
description: Saiba como usar permissões básicas para acessar o portal do Microsoft Defender para Ponto de Extremidade.
keywords: atribuir funções de usuário, atribuir acesso de leitura e gravação, atribuir acesso somente leitura, usuário, funções de usuário, funções
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7c208998e436245c53b90905858b7cf7ebe91d6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290180"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="11b7d-104">Usar permissões básicas para acessar o portal</span><span class="sxs-lookup"><span data-stu-id="11b7d-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="11b7d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="11b7d-105">**Applies to:**</span></span>
- <span data-ttu-id="11b7d-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="11b7d-106">Azure Active Directory</span></span>
- [<span data-ttu-id="11b7d-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="11b7d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="11b7d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="11b7d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="11b7d-109">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="11b7d-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="11b7d-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="11b7d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="11b7d-111">Consulte as instruções abaixo para usar o gerenciamento de permissões básicas.</span><span class="sxs-lookup"><span data-stu-id="11b7d-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="11b7d-112">Você pode usar uma das seguintes soluções:</span><span class="sxs-lookup"><span data-stu-id="11b7d-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="11b7d-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="11b7d-113">Azure PowerShell</span></span>
- <span data-ttu-id="11b7d-114">Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="11b7d-114">Azure portal</span></span>

<span data-ttu-id="11b7d-115">Para controle granular sobre permissões, [alternar para o controle de](rbac.md)acesso baseado em função .</span><span class="sxs-lookup"><span data-stu-id="11b7d-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="11b7d-116">Atribuir acesso ao usuário usando Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="11b7d-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="11b7d-117">Você pode atribuir usuários com um dos seguintes níveis de permissões:</span><span class="sxs-lookup"><span data-stu-id="11b7d-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="11b7d-118">Acesso completo (Leitura e Gravação)</span><span class="sxs-lookup"><span data-stu-id="11b7d-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="11b7d-119">Acesso somente leitura</span><span class="sxs-lookup"><span data-stu-id="11b7d-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="11b7d-120">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="11b7d-120">Before you begin</span></span>

- <span data-ttu-id="11b7d-121">Instale Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11b7d-121">Install Azure PowerShell.</span></span> <span data-ttu-id="11b7d-122">Para obter mais informações, consulte [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span><span class="sxs-lookup"><span data-stu-id="11b7d-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="11b7d-123">Você precisa executar os cmdlets do PowerShell em uma linha de comando elevada.</span><span class="sxs-lookup"><span data-stu-id="11b7d-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="11b7d-124">Conexão seu Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="11b7d-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="11b7d-125">Para obter mais informações, [consulte Conexão-MsolService](/powershell/module/msonline/connect-msolservice).</span><span class="sxs-lookup"><span data-stu-id="11b7d-125">For more information, see [Connect-MsolService](/powershell/module/msonline/connect-msolservice).</span></span>

<span data-ttu-id="11b7d-126">**Acesso total**</span><span class="sxs-lookup"><span data-stu-id="11b7d-126">**Full access**</span></span> <br>
<span data-ttu-id="11b7d-127">Os usuários com acesso total podem fazer logon, exibir todas as informações do sistema e resolver alertas, enviar arquivos para análise profunda e baixar o pacote de integração.</span><span class="sxs-lookup"><span data-stu-id="11b7d-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="11b7d-128">A atribuição de direitos de acesso total requer a adição dos usuários às funções internas "Administrador de Segurança" ou "Administrador Global" do AAD.</span><span class="sxs-lookup"><span data-stu-id="11b7d-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="11b7d-129">**Acesso somente leitura**</span><span class="sxs-lookup"><span data-stu-id="11b7d-129">**Read-only access**</span></span> <br>
<span data-ttu-id="11b7d-130">Os usuários com acesso somente leitura podem fazer logoff, exibir todos os alertas e informações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="11b7d-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="11b7d-131">Eles não poderão alterar estados de alerta, enviar arquivos para análise profunda ou executar operações de alteração de estado.</span><span class="sxs-lookup"><span data-stu-id="11b7d-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="11b7d-132">A atribuição de direitos de acesso somente leitura requer a adição dos usuários à função interna "Leitor de Segurança" do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="11b7d-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="11b7d-133">Use as etapas a seguir para atribuir funções de segurança:</span><span class="sxs-lookup"><span data-stu-id="11b7d-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="11b7d-134">Para **acesso de leitura e** gravação, atribua usuários à função de administrador de segurança usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="11b7d-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="11b7d-135">Para **acesso somente leitura,** atribua usuários à função de leitor de segurança usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="11b7d-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="11b7d-136">Para obter mais informações, [consulte Adicionar ou remover membros do](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)grupo usando Azure Active Directory .</span><span class="sxs-lookup"><span data-stu-id="11b7d-136">For more information, see [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="11b7d-137">Atribuir acesso ao usuário usando o portal do Azure</span><span class="sxs-lookup"><span data-stu-id="11b7d-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="11b7d-138">Para obter mais informações, [consulte Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="11b7d-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="11b7d-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="11b7d-139">Related topic</span></span>

- [<span data-ttu-id="11b7d-140">Gerenciar o acesso ao portal usando RBAC</span><span class="sxs-lookup"><span data-stu-id="11b7d-140">Manage portal access using RBAC</span></span>](rbac.md)
