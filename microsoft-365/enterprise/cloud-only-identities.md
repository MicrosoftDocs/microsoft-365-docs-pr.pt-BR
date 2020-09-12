---
title: Identidade somente na nuvem do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/09/2020
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
description: Descreve como criar usuários e grupos quando sua assinatura do Microsoft 365 estiver usando a identidade somente de nuvem.
ms.openlocfilehash: 6ec727ea3648f1daa3af42763e5f497715b987a2
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547753"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="8aad9-103">Identidade somente na nuvem do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8aad9-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="8aad9-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8aad9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8aad9-105">Com a identidade somente na nuvem, todos os usuários, grupos e contatos são armazenados no locatário do Azure Active Directory (Azure AD) da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8aad9-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="8aad9-106">Estes são os componentes básicos da identidade somente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="8aad9-106">Here are the basic components of cloud-only identity.</span></span>
 
![Os componentes básicos da identidade somente na nuvem](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="8aad9-108">Os usuários e suas contas de usuário nas organizações podem ser categorizados de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="8aad9-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="8aad9-109">Por exemplo, alguns são funcionários e têm um status permanente.</span><span class="sxs-lookup"><span data-stu-id="8aad9-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="8aad9-110">Alguns são fornecedores, contratadores ou parceiros que têm um status temporário.</span><span class="sxs-lookup"><span data-stu-id="8aad9-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="8aad9-111">Alguns são usuários externos que não têm contas de usuário, mas ainda precisam ter acesso a serviços e recursos específicos para oferecer suporte à interação e à colaboração.</span><span class="sxs-lookup"><span data-stu-id="8aad9-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="8aad9-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="8aad9-112">For example:</span></span>

- <span data-ttu-id="8aad9-113">As contas do locatário representam os usuários em sua organização para os quais você atribui uma licença para os serviços de nuvem</span><span class="sxs-lookup"><span data-stu-id="8aad9-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="8aad9-114">As contas entre empresas (B2B) representam usuários de fora da sua organização que você convida para colaborar</span><span class="sxs-lookup"><span data-stu-id="8aad9-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="8aad9-115">Faça o estoque dos tipos de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8aad9-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="8aad9-116">Quais são os agrupamentos?</span><span class="sxs-lookup"><span data-stu-id="8aad9-116">What are the groupings?</span></span> <span data-ttu-id="8aad9-117">Por exemplo, você pode agrupar usuários por função ou finalidade de alto nível em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8aad9-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="8aad9-p104">Além disso, alguns serviços de nuvem podem ser compartilhados com usuários de fora de sua organização que não tenham contas de usuário. Você também precisará identificar esses grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="8aad9-p104">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="8aad9-120">Você pode usar grupos no Azure AD para várias finalidades que simplificam o gerenciamento de seu ambiente de nuvem.</span><span class="sxs-lookup"><span data-stu-id="8aad9-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="8aad9-121">Por exemplo, com grupos do Azure AD, você pode:</span><span class="sxs-lookup"><span data-stu-id="8aad9-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="8aad9-122">Use o licenciamento baseado em grupo para atribuir licenças para o Microsoft 365 às contas de usuário automaticamente assim que elas forem adicionadas como membros.</span><span class="sxs-lookup"><span data-stu-id="8aad9-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="8aad9-123">Adicionar contas de usuário a grupos específicos de forma dinâmica com base nos atributos da conta de usuário, como nome do departamento.</span><span class="sxs-lookup"><span data-stu-id="8aad9-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="8aad9-124">Provisionar automaticamente os usuários para aplicativos de software como serviço (SaaS) e para proteger o acesso a esses aplicativos com a autenticação multifator (MFA) e outras políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="8aad9-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="8aad9-125">Provisione permissões e níveis de acesso para sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8aad9-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

<span data-ttu-id="8aad9-126">Você cria novos ***usuários*** com:</span><span class="sxs-lookup"><span data-stu-id="8aad9-126">You create new ***users*** with:</span></span>

- [<span data-ttu-id="8aad9-127">O Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8aad9-127">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)
- [<span data-ttu-id="8aad9-128">PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8aad9-128">PowerShell for Microsoft 365</span></span>](create-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="8aad9-129">Você cria novos ***grupos*** com:</span><span class="sxs-lookup"><span data-stu-id="8aad9-129">You create new ***groups*** with:</span></span>

- [<span data-ttu-id="8aad9-130">O Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8aad9-130">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/create-groups/create-groups)
- [<span data-ttu-id="8aad9-131">PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8aad9-131">PowerShell for Microsoft 365</span></span>](manage-microsoft-365-groups-with-powershell.md)


## <a name="next-step-for-cloud-only-identity"></a><span data-ttu-id="8aad9-132">Próxima etapa para identidade somente na nuvem</span><span class="sxs-lookup"><span data-stu-id="8aad9-132">Next step for cloud-only identity</span></span>

[<span data-ttu-id="8aad9-133">Atribuir licenças às contas de usuário</span><span class="sxs-lookup"><span data-stu-id="8aad9-133">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
