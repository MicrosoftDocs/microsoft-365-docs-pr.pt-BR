---
title: 'Etapa 7: Configurar o controle de identidade'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Compreender e configurar o controle de identidade para o locatário do Azure AD.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2020
ms.locfileid: "42543990"
---
# <a name="step-6-configure-identity-governance"></a><span data-ttu-id="3e926-103">Etapa 6: configurar o controle de identidade</span><span class="sxs-lookup"><span data-stu-id="3e926-103">Step 6: Configure identity governance</span></span>

![Fase 2 – Identidade](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="3e926-105">O controle de identidades é sobre proteção, monitoramento e auditoria do acesso a ativos essenciais enquanto garante a produtividade dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="3e926-105">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="3e926-106">Por exemplo, com o controle de identidade, você pode garantir que os usuários certos tenham o acesso apropriado aos recursos necessários e determinar se esse acesso muda com o tempo.</span><span class="sxs-lookup"><span data-stu-id="3e926-106">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="3e926-107">Confira [este artigo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para saber mais sobre o controle de identidade do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3e926-107">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>


<span data-ttu-id="3e926-108">*Isso é opcional e se aplica somente às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3e926-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="3e926-109">Configurar revisões de acesso do Azure AD</span><span class="sxs-lookup"><span data-stu-id="3e926-109">Set up Azure AD access reviews</span></span>

<span data-ttu-id="3e926-110">*Isso é opcional e só se aplica à versão E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3e926-110">*This is optional and only applies to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3e926-111">Nesta etapa, você configurará as revisões de acesso do Azure AD, que permitem que você examine o acesso de um usuário para garantir que apenas as pessoas certas tenham acesso contínuo.</span><span class="sxs-lookup"><span data-stu-id="3e926-111">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="3e926-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3e926-112">For example:</span></span>

- <span data-ttu-id="3e926-113">A medida que um novo funcionárioingressa na sua organização, você precisa garantir que ele tenha o acesso certo para ser produtivo.</span><span class="sxs-lookup"><span data-stu-id="3e926-113">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="3e926-114">Quando esse funcionário se move para outras equipes, locais ou departamentos, você precisa garantir que o acesso a equipes, locais ou departamentos anteriores sejam removidos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3e926-114">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="3e926-115">Quando esse funcionário ou um convidado deixa sua organização, você precisará garantir que seu acesso seja removido.</span><span class="sxs-lookup"><span data-stu-id="3e926-115">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="3e926-116">Isso é especialmente importante se a sua organização está sujeita a auditorias de segurança para determinar se as contas de usuários têm muito acesso, o que pode resultar em multas se estiverem se violar os regulamentos da região ou do setor.</span><span class="sxs-lookup"><span data-stu-id="3e926-116">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="3e926-117">Confira [este artigo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) para saber mais sobre as revisões de acesso do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3e926-117">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="3e926-118">O Azure AD Privileged Identity Management (PIM) fornece controles adicionais adaptados para proteger direitos de acesso para recursos, entre o Azure AD, o Azure e outros serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3e926-118">Azure AD Privileged Identity Management (PIM) provides additional controls tailored to securing access rights for resources, across Azure AD, Azure, and other Microsoft cloud service.</span></span> <span data-ttu-id="3e926-119">O Azure AD PIM fornece um conjunto abrangente de controles de governança para ajudar a proteger os recursos da empresa, como diretório, o Office 365 e as funções de recurso do Azure.</span><span class="sxs-lookup"><span data-stu-id="3e926-119">Azure AD PIM provides a comprehensive set of governance controls to help secure your company's resources such as directory, Office 365, and Azure resource roles.</span></span> <span data-ttu-id="3e926-120">Assim como acontece com outras formas de acesso, as organizações podem usar revisões de acesso para configurar a recertificação recorrente de acesso para todos os usuários nas funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="3e926-120">As with other forms of access, organizations can use access reviews to configure recurring access recertification for all users in administrator roles.</span></span> <span data-ttu-id="3e926-121">O Azure AD PIM só está disponível na versão E5 do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="3e926-121">Azure AD PIM is only available with the E5 version of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="3e926-122">Confira estes artigos para configurar os diferentes tipos de revisões de acesso:</span><span class="sxs-lookup"><span data-stu-id="3e926-122">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="3e926-123">Grupos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="3e926-123">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="3e926-124">Funções do Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3e926-124">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="3e926-125">Funções de recurso do Azure</span><span class="sxs-lookup"><span data-stu-id="3e926-125">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="3e926-126">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-access-reviews) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="3e926-126">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="3e926-127">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="3e926-127">Next step</span></span>

[<span data-ttu-id="3e926-128">Critérios de saída da infraestrutura de identidade</span><span class="sxs-lookup"><span data-stu-id="3e926-128">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

