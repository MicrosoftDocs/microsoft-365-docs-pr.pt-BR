---
title: Gerenciar Microsoft 365 de identidade
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Saiba mais sobre como usar Microsoft 365 de governança de identidade.
ms.openlocfilehash: 6a97ca24c609724a2cab93feec9e90f25d3361e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910949"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="47f17-103">Gerenciar Microsoft 365 de identidade</span><span class="sxs-lookup"><span data-stu-id="47f17-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="47f17-104">O controle de identidades é sobre proteção, monitoramento e auditoria do acesso a ativos essenciais enquanto garante a produtividade dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="47f17-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="47f17-105">Por exemplo, com o controle de identidade, você pode garantir que os usuários certos tenham o acesso apropriado aos recursos necessários e determinar se esse acesso muda com o tempo.</span><span class="sxs-lookup"><span data-stu-id="47f17-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="47f17-106">Para obter mais informações, consulte esta visão geral da governança de [identidade para Azure Active Directory (Azure AD)](/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="47f17-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="47f17-107">Configurar revisões de acesso do Azure AD</span><span class="sxs-lookup"><span data-stu-id="47f17-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="47f17-108">As análises de acesso ao Azure AD permitem que você revise o acesso de um usuário para garantir que apenas as pessoas certas tenham acesso contínuo.</span><span class="sxs-lookup"><span data-stu-id="47f17-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="47f17-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="47f17-109">For example:</span></span>

- <span data-ttu-id="47f17-110">A medida que um novo funcionárioingressa na sua organização, você precisa garantir que ele tenha o acesso certo para ser produtivo.</span><span class="sxs-lookup"><span data-stu-id="47f17-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="47f17-111">Quando esse funcionário se move para outras equipes, locais ou departamentos, você precisa garantir que o acesso a equipes, locais ou departamentos anteriores sejam removidos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="47f17-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="47f17-112">Quando esse funcionário ou um convidado deixa sua organização, você precisará garantir que seu acesso seja removido.</span><span class="sxs-lookup"><span data-stu-id="47f17-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="47f17-113">Isso é especialmente importante se a sua organização está sujeita a auditorias de segurança para determinar se as contas de usuários têm muito acesso, o que pode resultar em multas se estiverem se violar os regulamentos da região ou do setor.</span><span class="sxs-lookup"><span data-stu-id="47f17-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="47f17-114">Para obter mais informações, consulte a [visão geral das avaliações de acesso.](/azure/active-directory/governance/access-reviews-overview)</span><span class="sxs-lookup"><span data-stu-id="47f17-114">For more information, see the [overview of access reviews](/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="47f17-115">Confira estes artigos para configurar os diferentes tipos de revisões de acesso:</span><span class="sxs-lookup"><span data-stu-id="47f17-115">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="47f17-116">Grupos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="47f17-116">Groups and apps</span></span>](/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="47f17-117">Funções do Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="47f17-117">Azure AD roles</span></span>](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="47f17-118">Funções de recurso do Azure</span><span class="sxs-lookup"><span data-stu-id="47f17-118">Azure resource roles</span></span>](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="47f17-119">Configurar o gerenciamento de direitos do Azure AD</span><span class="sxs-lookup"><span data-stu-id="47f17-119">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="47f17-120">Gerenciamento de direitos do Wiht Azure AD, você pode gerenciar a identidade e o ciclo de vida de acesso em escala automatizando fluxos de trabalho de solicitação de acesso, atribuições de acesso, análises e expiração.</span><span class="sxs-lookup"><span data-stu-id="47f17-120">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="47f17-121">Seus funcionários precisam de acesso a vários grupos, aplicativos e sites para executar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="47f17-121">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="47f17-122">Gerenciar esse acesso pode ser um desafio porque os requisitos mudam, novos aplicativos são adicionados ou os usuários precisam de direitos de acesso adicionais.</span><span class="sxs-lookup"><span data-stu-id="47f17-122">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="47f17-123">Quando você colabora com outras organizações, talvez não saiba quem na outra organização precisa de acesso aos recursos da sua organização, e usuários externos não saberão quais aplicativos, grupos ou sites sua organização está usando.</span><span class="sxs-lookup"><span data-stu-id="47f17-123">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="47f17-124">O gerenciamento de direitos do Azure AD pode ajudá-lo a gerenciar com mais eficiência o acesso a grupos, aplicativos e sites SharePoint para usuários internos e externos.</span><span class="sxs-lookup"><span data-stu-id="47f17-124">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="47f17-125">Para obter mais informações, consulte a visão geral do gerenciamento de direitos do [Azure AD.](/azure/active-directory/governance/entitlement-management-overview)</span><span class="sxs-lookup"><span data-stu-id="47f17-125">For more information, see the [overview of Azure AD entitlement management](/azure/active-directory/governance/entitlement-management-overview).</span></span>