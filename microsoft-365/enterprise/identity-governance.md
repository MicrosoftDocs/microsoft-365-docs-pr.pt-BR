---
title: 'Etapa 7: Configurar o controle de identidade'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Compreender e configurar o controle de identidade para o locatário do Azure AD.
ms.openlocfilehash: 1c0eab574e5436dd0c88a0b46d1916281bcf0577
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047354"
---
# <a name="step-7-configure-identity-governance"></a><span data-ttu-id="b1329-103">Etapa 7: Configurar o controle de identidade</span><span class="sxs-lookup"><span data-stu-id="b1329-103">Step 7: Configure identity governance</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="b1329-104">O controle de identidades é sobre proteção, monitoramento e auditoria do acesso a ativos essenciais enquanto garante a produtividade dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="b1329-104">Identity governance is all about protecting, monitoring, and auditing access to critical assets while ensuring employee productivity.</span></span> <span data-ttu-id="b1329-105">Por exemplo, com o controle de identidade, você pode garantir que os usuários certos tenham o acesso apropriado aos recursos necessários e determinar se esse acesso muda com o tempo.</span><span class="sxs-lookup"><span data-stu-id="b1329-105">For example, with identity governance, you can ensure that the right users have the right access to the right resources and determine if that access changes over time.</span></span>

<span data-ttu-id="b1329-106">Confira [este artigo](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para saber mais sobre o controle de identidade para o Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b1329-106">See [this article](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for more information about identity governance for Azure Active Directory (Azure AD).</span></span>

<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a><span data-ttu-id="b1329-107">Configurar revisões de acesso do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b1329-107">Set up Azure AD access reviews</span></span>

<span data-ttu-id="b1329-108">*Isso é opcional e só se aplica à versão E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b1329-108">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b1329-109">Nesta etapa, você configurará as revisões de acesso do Azure AD, que permitem que você examine o acesso de um usuário para garantir que apenas as pessoas certas tenham acesso contínuo.</span><span class="sxs-lookup"><span data-stu-id="b1329-109">In this step, you'll set up Azure AD access reviews, which allow you to review a user's access to ensure only the right people have continued access.</span></span> <span data-ttu-id="b1329-110">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b1329-110">For example:</span></span>

- <span data-ttu-id="b1329-111">A medida que um novo funcionárioingressa na sua organização, você precisa garantir que ele tenha o acesso certo para ser produtivo.</span><span class="sxs-lookup"><span data-stu-id="b1329-111">As a new employee joins your organization, you need to ensure they have the right access to be productive.</span></span>
- <span data-ttu-id="b1329-112">Quando esse funcionário se move para outras equipes, locais ou departamentos, você precisa garantir que o acesso a equipes, locais ou departamentos anteriores sejam removidos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b1329-112">As that employee moves to other teams, locations, or departments, you need to ensure that their access to previous teams, locations, or departments are removed as needed.</span></span>
- <span data-ttu-id="b1329-113">Quando esse funcionário ou um convidado deixa sua organização, você precisará garantir que seu acesso seja removido.</span><span class="sxs-lookup"><span data-stu-id="b1329-113">When that employee or a guest leaves your organization, you need to ensure their access is removed.</span></span>

<span data-ttu-id="b1329-114">Isso é especialmente importante se a sua organização está sujeita a auditorias de segurança para determinar se as contas de usuários têm muito acesso, o que pode resultar em multas se estiverem se violar os regulamentos da região ou do setor.</span><span class="sxs-lookup"><span data-stu-id="b1329-114">This is especially important if your organization is subject to security audits to determine if user accounts have too much access, which could result in fines if in violation of industry or regional regulations.</span></span>

<span data-ttu-id="b1329-115">Confira [este artigo](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) para saber mais sobre as revisões de acesso do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b1329-115">See [this article](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) for more information about Azure AD access reviews.</span></span>

<span data-ttu-id="b1329-116">Confira estes artigos para configurar os diferentes tipos de revisões de acesso:</span><span class="sxs-lookup"><span data-stu-id="b1329-116">See these articles to configure different types of access reviews:</span></span>

- [<span data-ttu-id="b1329-117">Grupos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="b1329-117">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="b1329-118">Funções do Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b1329-118">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="b1329-119">Funções de recurso do Azure</span><span class="sxs-lookup"><span data-stu-id="b1329-119">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="b1329-120">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-access-reviews) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="b1329-120">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-access-reviews) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="b1329-121">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b1329-121">Next step</span></span>

[<span data-ttu-id="b1329-122">Critérios de saída da infraestrutura de identidade</span><span class="sxs-lookup"><span data-stu-id="b1329-122">Identity infrastructure exit criteria</span></span>](identity-exit-criteria.md)

