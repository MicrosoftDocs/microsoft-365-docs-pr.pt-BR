---
title: Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/13/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 26b9ff81-93b0-4251-beaf-3c9f1d7c80c8
description: Saiba como gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell.
ms.openlocfilehash: d3745b9365c67615efe32881408d1a717b8dbbed
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371531"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="b49a3-103">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="b49a3-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="b49a3-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b49a3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b49a3-105">Os administradores do Microsoft 365 precisam gerenciar contas, licenças e grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="b49a3-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="b49a3-106">Embora seja possível realizar a maioria dessas tarefas no centro de administração do Microsoft 365, algumas são mais fáceis no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b49a3-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="b49a3-107">Para obter mais informações, consulte os seguintes artigos.</span><span class="sxs-lookup"><span data-stu-id="b49a3-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="b49a3-108">Contas de usuário</span><span class="sxs-lookup"><span data-stu-id="b49a3-108">User accounts</span></span>

- [<span data-ttu-id="b49a3-109">Criar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="b49a3-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-110">Exibir contas de usuário</span><span class="sxs-lookup"><span data-stu-id="b49a3-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-111">Configurar as propriedades de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="b49a3-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-112">Atribuir funções a contas de usuário</span><span class="sxs-lookup"><span data-stu-id="b49a3-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-113">Excluir e restaurar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="b49a3-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-114">Bloquear contas de usuário</span><span class="sxs-lookup"><span data-stu-id="b49a3-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-115">Senhas</span><span class="sxs-lookup"><span data-stu-id="b49a3-115">Passwords</span></span>](manage-passwords-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="b49a3-116">Licenças e serviços</span><span class="sxs-lookup"><span data-stu-id="b49a3-116">Licenses and services</span></span>
- [<span data-ttu-id="b49a3-117">Exibir licenças e serviços</span><span class="sxs-lookup"><span data-stu-id="b49a3-117">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-118">Exibir usuários licenciados e não licenciados</span><span class="sxs-lookup"><span data-stu-id="b49a3-118">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-119">Atribuir licenças às contas de usuário</span><span class="sxs-lookup"><span data-stu-id="b49a3-119">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-120">Exibir detalhes da licença e serviço da conta</span><span class="sxs-lookup"><span data-stu-id="b49a3-120">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-121">Desabilitar o acesso aos serviços</span><span class="sxs-lookup"><span data-stu-id="b49a3-121">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="b49a3-122">Desabilitar o acesso ao Sway</span><span class="sxs-lookup"><span data-stu-id="b49a3-122">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="b49a3-123">Desabilitar o acesso aos serviços na atribuição de licenças de usuário</span><span class="sxs-lookup"><span data-stu-id="b49a3-123">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="b49a3-124">Remover licenças de contas de usuário</span><span class="sxs-lookup"><span data-stu-id="b49a3-124">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="b49a3-125">Grupos</span><span class="sxs-lookup"><span data-stu-id="b49a3-125">Groups</span></span>
- [<span data-ttu-id="b49a3-126">Gerenciar grupos de segurança</span><span class="sxs-lookup"><span data-stu-id="b49a3-126">Manage security groups</span></span>](manage-security-groups-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-127">Manter Associação de grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="b49a3-127">Maintain security group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="b49a3-128">Gerenciar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b49a3-128">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
