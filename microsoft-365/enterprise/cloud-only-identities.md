---
title: Microsoft 365 identidade somente na nuvem
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
description: Descreve como criar usuários e grupos quando sua assinatura Microsoft 365 está usando a identidade somente na nuvem.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327922"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="1e8e0-103">Microsoft 365 identidade somente na nuvem</span><span class="sxs-lookup"><span data-stu-id="1e8e0-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="1e8e0-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1e8e0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1e8e0-105">Com a identidade somente na nuvem, todos os usuários, grupos e contatos são armazenados no locatário do Azure Active Directory (Azure AD) de sua assinatura Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="1e8e0-106">Aqui estão os componentes básicos da identidade somente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-106">Here are the basic components of cloud-only identity.</span></span>
 
![Os componentes básicos da identidade somente na nuvem](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="1e8e0-108">Os usuários e suas contas de usuário nas organizações podem ser categorizados de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="1e8e0-109">Por exemplo, alguns são funcionários e têm um status permanente.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="1e8e0-110">Alguns são fornecedores, contratados ou parceiros que têm um status temporário.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="1e8e0-111">Alguns são usuários externos que não têm contas de usuário, mas ainda devem ter acesso a serviços e recursos específicos para suportar a interação e a colaboração.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="1e8e0-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1e8e0-112">For example:</span></span>

- <span data-ttu-id="1e8e0-113">As contas do locatário representam os usuários em sua organização para os quais você atribui uma licença para os serviços de nuvem</span><span class="sxs-lookup"><span data-stu-id="1e8e0-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="1e8e0-114">As contas entre empresas (B2B) representam usuários de fora da sua organização que você convida para colaborar</span><span class="sxs-lookup"><span data-stu-id="1e8e0-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="1e8e0-115">Fazer um estoque dos tipos de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="1e8e0-116">Quais são os grupos?</span><span class="sxs-lookup"><span data-stu-id="1e8e0-116">What are the groupings?</span></span> <span data-ttu-id="1e8e0-117">Por exemplo, você pode agrupar usuários por função de alto nível ou finalidade para sua organização.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="1e8e0-p104">Além disso, alguns serviços de nuvem podem ser compartilhados com usuários de fora de sua organização que não tenham contas de usuário. Você também precisará identificar esses grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-p104">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="1e8e0-120">Você pode usar grupos no Azure AD para várias finalidades que simplificam o gerenciamento do seu ambiente de nuvem.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="1e8e0-121">Por exemplo, com grupos do Azure AD, você pode:</span><span class="sxs-lookup"><span data-stu-id="1e8e0-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="1e8e0-122">Use o licenciamento baseado em grupo para atribuir licenças Microsoft 365 suas contas de usuário automaticamente assim que elas são adicionadas como membros.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="1e8e0-123">Adicione contas de usuário a grupos específicos dinamicamente com base nos atributos da conta de usuário, como o nome do departamento.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="1e8e0-124">Provisione automaticamente usuários para aplicativos SaaS (Software as a Service) e proteja o acesso a esses aplicativos com autenticação multifacional (MFA) e outras políticas de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="1e8e0-125">Provisione permissões e níveis de acesso para sites de equipe SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1e8e0-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

## <a name="next-steps-for-cloud-only-identity"></a><span data-ttu-id="1e8e0-126">Próximas etapas para a identidade somente na nuvem</span><span class="sxs-lookup"><span data-stu-id="1e8e0-126">Next steps for cloud-only identity</span></span>

- [<span data-ttu-id="1e8e0-127">Gerenciar contas de usuário</span><span class="sxs-lookup"><span data-stu-id="1e8e0-127">Manage user accounts</span></span>](manage-microsoft-365-accounts.md)
- [<span data-ttu-id="1e8e0-128">Atribuir licenças às contas de usuário</span><span class="sxs-lookup"><span data-stu-id="1e8e0-128">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
- [<span data-ttu-id="1e8e0-129">Gerenciar grupos e associações de grupo</span><span class="sxs-lookup"><span data-stu-id="1e8e0-129">Manage groups and group membership</span></span>](manage-microsoft-365-groups.md)
- [<span data-ttu-id="1e8e0-130">Gerenciar senhas de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="1e8e0-130">Manage user account passwords</span></span>](manage-microsoft-365-passwords.md)
