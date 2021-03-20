---
title: Atribuir licenças do Microsoft 365 a contas de usuário
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
description: Descreve como atribuir licenças do Microsoft 365 a contas de usuário, individualmente ou com base na associação ao grupo.
ms.openlocfilehash: 6bba3cd767787f450840c5cae6c30f2be21bed1b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905435"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="a2c9c-103">Atribuir licenças do Microsoft 365 a contas de usuário</span><span class="sxs-lookup"><span data-stu-id="a2c9c-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="a2c9c-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a2c9c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a2c9c-105">Para o modelo de identidade somente na nuvem, você pode atribuir licenças do Microsoft 365 às contas de usuário à medida que elas são criadas, dependendo de como você as cria.</span><span class="sxs-lookup"><span data-stu-id="a2c9c-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="a2c9c-106">Para o modelo de identidade híbrida, quando as contas de usuário do Active Directory Domain Services (AD DS) são sincronizadas pela primeira vez, elas não são atribuídas automaticamente a um local ou uma licença do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2c9c-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="a2c9c-107">**Você deve configurar cada conta de usuário com um local de usuário antes ou com a atribuição de uma licença.**</span><span class="sxs-lookup"><span data-stu-id="a2c9c-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="a2c9c-108">Em ambos os casos, você deve atribuir uma licença a contas de usuário para que seus usuários possam acessar serviços do Microsoft 365, como email e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a2c9c-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="a2c9c-109">Você pode atribuir licenças a contas de usuário individualmente ou automaticamente por meio da associação ao grupo.</span><span class="sxs-lookup"><span data-stu-id="a2c9c-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="a2c9c-110">Para atribuir licenças do Microsoft 365 a contas de usuário individuais, você pode usar:</span><span class="sxs-lookup"><span data-stu-id="a2c9c-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="a2c9c-111">O Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2c9c-111">The Microsoft 365 admin center</span></span>](../admin/manage/assign-licenses-to-users.md)
- [<span data-ttu-id="a2c9c-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2c9c-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="a2c9c-113">Centro de administração do Azure AD</span><span class="sxs-lookup"><span data-stu-id="a2c9c-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="a2c9c-114">Licenciamento com base em grupo</span><span class="sxs-lookup"><span data-stu-id="a2c9c-114">Group-based licensing</span></span>

<span data-ttu-id="a2c9c-115">Você pode configurar grupos de segurança no Azure AD para atribuir automaticamente licenças de um conjunto de assinaturas a todos os membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="a2c9c-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="a2c9c-116">Isso é conhecido como *licenciamento baseado em grupo*.</span><span class="sxs-lookup"><span data-stu-id="a2c9c-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="a2c9c-117">Se uma conta de usuário for adicionada ou removida do grupo, as licenças das assinaturas do grupo serão automaticamente atribuídas ou não atribuídas à conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="a2c9c-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="a2c9c-118">Verifique se você tem licenças suficientes para todos os membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="a2c9c-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="a2c9c-119">Se você ficar sem licenças, os novos usuários não receberão licenças até que as licenças estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a2c9c-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="a2c9c-120">Você não deve configurar o licenciamento baseado em grupo para grupos que contenham contas do Azure para empresas (B2B).</span><span class="sxs-lookup"><span data-stu-id="a2c9c-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="a2c9c-121">Para obter mais informações, consulte [licenciamento baseado em grupo no Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="a2c9c-121">For more informaion, see [group-based licensing in Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2c9c-122">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a2c9c-122">Next steps</span></span>

<span data-ttu-id="a2c9c-123">Com o conjunto apropriado de contas de usuário que foram atribuídas licenças, agora você está pronto para:</span><span class="sxs-lookup"><span data-stu-id="a2c9c-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="a2c9c-124">Implementar segurança</span><span class="sxs-lookup"><span data-stu-id="a2c9c-124">Implement security</span></span>](../security/office-365-security/security-roadmap.md)
- [<span data-ttu-id="a2c9c-125">Implantar software cliente, como o Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="a2c9c-125">Deploy client software, such as Microsoft 365 Apps</span></span>](/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="a2c9c-126">Configurar o gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a2c9c-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="a2c9c-127">Configurar serviços e aplicativos</span><span class="sxs-lookup"><span data-stu-id="a2c9c-127">Configure services and applications</span></span>](configure-services-and-applications.md)