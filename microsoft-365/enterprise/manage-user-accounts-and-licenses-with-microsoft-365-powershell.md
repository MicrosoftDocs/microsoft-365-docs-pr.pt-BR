---
title: Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
description: Neste artigo, saiba como gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell.
ms.openlocfilehash: a262cbb62cd457e3a22550af2f773551cf67bb43
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695376"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="c5036-103">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5036-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="c5036-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c5036-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c5036-105">Uma das tarefas principais de qualquer administrador do Microsoft 365 é o gerenciamento de contas de usuário, licenças e grupos.</span><span class="sxs-lookup"><span data-stu-id="c5036-105">One of the primary tasks of any Microsoft 365 administrator is managing user accounts, licenses, and groups.</span></span> <span data-ttu-id="c5036-106">Embora você possa realizar a maioria dos aspectos dessas tarefas no centro de administração do Microsoft 365, outras tarefas são muito mais rápidas e fáceis com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c5036-106">Although you can accomplish most aspects of these tasks in the Microsoft 365 admin center, other tasks are much quicker and easier with PowerShell.</span></span> 

<span data-ttu-id="c5036-107">Para obter mais informações, consulte estes tópicos.</span><span class="sxs-lookup"><span data-stu-id="c5036-107">For more information, see these topics.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="c5036-108">Contas de usuário</span><span class="sxs-lookup"><span data-stu-id="c5036-108">User accounts</span></span>

- [<span data-ttu-id="c5036-109">Criar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="c5036-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5036-110">Exibir contas de usuário</span><span class="sxs-lookup"><span data-stu-id="c5036-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5036-111">Configurar as propriedades de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="c5036-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5036-112">Atribuir funções a contas de usuário</span><span class="sxs-lookup"><span data-stu-id="c5036-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5036-113">Excluir e restaurar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="c5036-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5036-114">Bloquear contas de usuário</span><span class="sxs-lookup"><span data-stu-id="c5036-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="c5036-115">Licenças e serviços</span><span class="sxs-lookup"><span data-stu-id="c5036-115">Licenses and services</span></span>
- [<span data-ttu-id="c5036-116">Exibir licenças e serviços</span><span class="sxs-lookup"><span data-stu-id="c5036-116">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5036-117">Exibir usuários licenciados e não licenciados</span><span class="sxs-lookup"><span data-stu-id="c5036-117">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5036-118">Atribuir licenças às contas de usuário</span><span class="sxs-lookup"><span data-stu-id="c5036-118">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5036-119">Exibir detalhes da licença e serviço da conta</span><span class="sxs-lookup"><span data-stu-id="c5036-119">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5036-120">Desabilitar o acesso aos serviços</span><span class="sxs-lookup"><span data-stu-id="c5036-120">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="c5036-121">Desabilitar o acesso ao Sway</span><span class="sxs-lookup"><span data-stu-id="c5036-121">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="c5036-122">Desabilitar o acesso aos serviços na atribuição de licenças de usuário</span><span class="sxs-lookup"><span data-stu-id="c5036-122">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="c5036-123">Remover licenças de contas de usuário</span><span class="sxs-lookup"><span data-stu-id="c5036-123">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="c5036-124">Grupos</span><span class="sxs-lookup"><span data-stu-id="c5036-124">Groups</span></span>
- [<span data-ttu-id="c5036-125">Manter associação de grupo</span><span class="sxs-lookup"><span data-stu-id="c5036-125">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c5036-126">Gerenciar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c5036-126">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)

