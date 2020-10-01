---
title: Gerenciar o Microsoft 365 Identity Governance
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
description: Saiba como usar os recursos de governança de identidade do Microsoft 365.
ms.openlocfilehash: d5bcafb5b452e693bf3ff706c436a9986eeeae76
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328479"
---
# <a name="manage-microsoft-365-identity-governance"></a><span data-ttu-id="3fc18-103">Gerenciar o Microsoft 365 Identity Governance</span><span class="sxs-lookup"><span data-stu-id="3fc18-103">Manage Microsoft 365 identity governance</span></span>

<span data-ttu-id="3fc18-104">O controle de identidades é sobre proteção, monitoramento e auditoria do acesso a ativos essenciais enquanto garante a produtividade dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="3fc18-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="3fc18-105">Por exemplo, com o controle de identidade, você pode garantir que os usuários certos tenham o acesso apropriado aos recursos necessários e determinar se esse acesso muda com o tempo.</span><span class="sxs-lookup"><span data-stu-id="3fc18-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="3fc18-106">Para obter mais informações, consulte esta [visão geral do controle de identidade do Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span><span class="sxs-lookup"><span data-stu-id="3fc18-106">For more information, See this [overview of identity governance for Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).</span></span>

## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="3fc18-107">Configurar revisões de acesso do Azure AD</span><span class="sxs-lookup"><span data-stu-id="3fc18-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="3fc18-108">As revisões do Azure AD Access permitem que você revise o acesso de um usuário para garantir que apenas as pessoas certas tenham acesso contínuo.</span><span class="sxs-lookup"><span data-stu-id="3fc18-108">Azure AD access reviews allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="3fc18-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3fc18-109">For example:</span></span>

- <span data-ttu-id="3fc18-110">A medida que um novo funcionárioingressa na sua organização, você precisa garantir que ele tenha o acesso certo para ser produtivo.</span><span class="sxs-lookup"><span data-stu-id="3fc18-110">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="3fc18-111">Quando esse funcionário se move para outras equipes, locais ou departamentos, você precisa garantir que o acesso a equipes, locais ou departamentos anteriores sejam removidos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3fc18-111">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="3fc18-112">Quando esse funcionário ou um convidado deixa sua organização, você precisará garantir que seu acesso seja removido.</span><span class="sxs-lookup"><span data-stu-id="3fc18-112">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="3fc18-113">Isso é especialmente importante se a sua organização está sujeita a auditorias de segurança para determinar se as contas de usuários têm muito acesso, o que pode resultar em multas se estiverem se violar os regulamentos da região ou do setor.</span><span class="sxs-lookup"><span data-stu-id="3fc18-113">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="3fc18-114">Para obter mais informações, consulte [visão geral das revisões do Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span><span class="sxs-lookup"><span data-stu-id="3fc18-114">For more information, see the [overview of access reviews](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview).</span></span>

<span data-ttu-id="3fc18-115">O Azure AD Privileged Identity Management (PIM) fornece controles adicionais adaptados para proteger direitos de acesso para recursos, entre o Azure AD, o Azure e outros serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3fc18-115">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="3fc18-116">O Azure AD PIM fornece um conjunto abrangente de controles de governança para ajudar a proteger os recursos da empresa, como diretório, o Office 365 e as funções de recurso do Azure.</span><span class="sxs-lookup"><span data-stu-id="3fc18-116">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="3fc18-117">Assim como acontece com outras formas de acesso, as organizações podem usar revisões de acesso para configurar a recertificação recorrente de acesso para todos os usuários nas funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="3fc18-117">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="3fc18-118">O Azure AD PIM só está disponível na versão E5 do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3fc18-118">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="3fc18-119">Confira estes artigos para configurar os diferentes tipos de revisões de acesso:</span><span class="sxs-lookup"><span data-stu-id="3fc18-119">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="3fc18-120">Grupos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="3fc18-120">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="3fc18-121">Funções do Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3fc18-121">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="3fc18-122">Funções de recurso do Azure</span><span class="sxs-lookup"><span data-stu-id="3fc18-122">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a><span data-ttu-id="3fc18-123">Configurar o gerenciamento de qualificação do Azure AD</span><span class="sxs-lookup"><span data-stu-id="3fc18-123">Set up Azure AD entitlement management</span></span>

<span data-ttu-id="3fc18-124">Wiht gerenciamento de direitos do Azure AD, você pode gerenciar o ciclo de vida de identidade e acesso em escala automatizando fluxos de trabalho de solicitação de acesso, atribuições de acesso, revisões e expiração.</span><span class="sxs-lookup"><span data-stu-id="3fc18-124">Wiht Azure AD entitlement management, you can manage the identity and access lifecycle at scale by automating access request workflows, access assignments, reviews, and expiration.</span></span>

<span data-ttu-id="3fc18-125">Seus funcionários precisam acessar vários grupos, aplicativos e sites para realizar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="3fc18-125">Your employees need access to various groups, applications, and sites to perform their job.</span></span> <span data-ttu-id="3fc18-126">O gerenciamento desse acesso pode ser desafiador porque os requisitos mudam, novos aplicativos são adicionados ou os usuários precisam de direitos de acesso adicionais.</span><span class="sxs-lookup"><span data-stu-id="3fc18-126">Managing this access can be challenging because requirements change, new applications are added, or users need additional access rights.</span></span> <span data-ttu-id="3fc18-127">Ao colaborar com outras organizações, talvez você não saiba quem, na outra organização, precisa acessar os recursos da sua organização, e os usuários externos não saberão quais aplicativos, grupos ou sites sua organização está usando.</span><span class="sxs-lookup"><span data-stu-id="3fc18-127">When you collaborate with other organizations, you may not know who in the other organization needs access to your organization's resources, and outside users won't know what applications, groups, or sites your organization is using.</span></span>

<span data-ttu-id="3fc18-128">O gerenciamento de direitos do Azure AD pode ajudá-lo a gerenciar com mais eficiência o acesso a grupos, aplicativos e sites do SharePoint para usuários internos e externos.</span><span class="sxs-lookup"><span data-stu-id="3fc18-128">Azure AD entitlement management can help you more efficiently manage access to groups, applications, and SharePoint sites for internal and outside users.</span></span>
 
<span data-ttu-id="3fc18-129">Para obter mais informações, consulte a [visão geral do gerenciamento de qualificação do Azure ad](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span><span class="sxs-lookup"><span data-stu-id="3fc18-129">For more information, see the [overview of Azure AD entitlement management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).</span></span>
