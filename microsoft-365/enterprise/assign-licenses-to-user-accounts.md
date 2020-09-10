---
title: Atribuir licenças do Microsoft 365 a contas de usuário
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Descreve como atribuir licenças do Microsoft 365 a contas de usuário, individualmente ou com base na associação de grupo.
ms.openlocfilehash: e132a8c2d65c401899624b9d255050385f2cb721
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417093"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="fcd79-103">Atribuir licenças do Microsoft 365 a contas de usuário</span><span class="sxs-lookup"><span data-stu-id="fcd79-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="fcd79-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fcd79-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fcd79-105">Para o modelo de identidade somente na nuvem, você pode atribuir licenças do Microsoft 365 a contas de usuário à medida que elas são criadas, dependendo de como você as cria.</span><span class="sxs-lookup"><span data-stu-id="fcd79-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="fcd79-106">Para o modelo de identidade híbrida, quando as contas de usuário dos serviços de domínio Active Directory (AD DS) são sincronizadas pela primeira vez, elas não recebem automaticamente uma licença do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fcd79-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license.</span></span> <span data-ttu-id="fcd79-107">Primeiro você deve configurar cada conta de usuário com um local de usuário.</span><span class="sxs-lookup"><span data-stu-id="fcd79-107">You must first configure each user account with a user location.</span></span>

<span data-ttu-id="fcd79-108">Em ambos os casos, você deve atribuir uma licença às contas de usuário para que seus usuários possam acessar os serviços do Microsoft 365, como email e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fcd79-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="fcd79-109">Você pode atribuir licenças a contas de usuário individualmente ou automaticamente através da Associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="fcd79-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="fcd79-110">Para atribuir licenças do Microsoft 365 a contas de usuário individuais, você pode usar:</span><span class="sxs-lookup"><span data-stu-id="fcd79-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="fcd79-111">O Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fcd79-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="fcd79-112">PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fcd79-112">PowerShell for Microsoft 365</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="fcd79-113">Para atribuição de licença automática, confira [Licenciamento baseado em grupo no Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="fcd79-113">For automatic license assignment, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="fcd79-114">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="fcd79-114">Next steps</span></span>

<span data-ttu-id="fcd79-115">Com o conjunto completo de contas de usuário às quais foram atribuídas licenças, agora você está pronto para:</span><span class="sxs-lookup"><span data-stu-id="fcd79-115">With the full set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="fcd79-116">Implementar a segurança</span><span class="sxs-lookup"><span data-stu-id="fcd79-116">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="fcd79-117">Implantar software cliente, como o Microsoft 365 aplicativos</span><span class="sxs-lookup"><span data-stu-id="fcd79-117">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="fcd79-118">Configurar mobilidade básica e segurança no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fcd79-118">Set up Basic Mobility and Security in Microsoft 365</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [<span data-ttu-id="fcd79-119">Configurar serviços e aplicativos</span><span class="sxs-lookup"><span data-stu-id="fcd79-119">Configure services and applications</span></span>](configure-services-and-applications.md)
