---
title: Roteiro do locatário para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365initiative-coredeploy
ms.custom: it-pro
description: O roteiro para configurar seus locatários para o Microsoft 365.
ms.openlocfilehash: e4b2af9143070caa1ebd8fd66ef9f367f85d3bb9
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357905"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="b677a-103">Roteiro do locatário para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b677a-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="b677a-104">O Microsoft 365 locatário é o conjunto de serviços atribuídos à sua organização.</span><span class="sxs-lookup"><span data-stu-id="b677a-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="b677a-105">Normalmente, esse locatário é associado a um ou mais dos nomes de domínio DNS e atua como um contêiner central para assinaturas diferentes e as licenças dentro delas que você atribui às contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="b677a-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="b677a-106">Ao criar um locatário do Microsoft 365, você o atribui a uma localização geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="b677a-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="b677a-107">Você também pode ter um locatário com vários locais geográficos e mover o locatário de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="b677a-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="b677a-108">Para que o seu locatário fique pronto para os serviços fundamentais de rede e identidade, é fundamental planejar e executar cuidadosamente a configuração do locatário.</span><span class="sxs-lookup"><span data-stu-id="b677a-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="b677a-109">Planejar</span><span class="sxs-lookup"><span data-stu-id="b677a-109">Plan</span></span>

<span data-ttu-id="b677a-110">Para planejar sua implementação de locatário:</span><span class="sxs-lookup"><span data-stu-id="b677a-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="b677a-111">Entender as assinaturas, as licenças e os locatários do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="b677a-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="b677a-112">Entender como usar certificados SSL de terceiros</span><span class="sxs-lookup"><span data-stu-id="b677a-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="b677a-113">Entender as maneiras como um Microsoft 365 locatário é integrado aos serviços do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b677a-113">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="b677a-114">Planejar o suporte ao aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="b677a-114">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="b677a-115">Determinar como usar a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="b677a-115">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="b677a-116">Planejar atualizações do Office 2007 e do Office 2010</span><span class="sxs-lookup"><span data-stu-id="b677a-116">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="b677a-117">Entender o isolamento do locatário</span><span class="sxs-lookup"><span data-stu-id="b677a-117">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="b677a-118">Obtenha os detalhes sobre o Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="b677a-118">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="b677a-119">Implantar</span><span class="sxs-lookup"><span data-stu-id="b677a-119">Deploy</span></span>

<span data-ttu-id="b677a-120">Para implantar seu locatário, [adicione os domínios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) para sua organização e use os [guias de configuração no centro de administração do Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="b677a-120">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization and use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="b677a-121">Locatários com vários locais geográficos</span><span class="sxs-lookup"><span data-stu-id="b677a-121">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="b677a-122">Com o Microsoft 365 Multi-Geo, sua organização pode expandir sua presença no Microsoft 365 para várias regiões geográficas e/ou países do seu locatário existente.</span><span class="sxs-lookup"><span data-stu-id="b677a-122">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="b677a-123">Para obter informações sobre o Microsoft 365 multigeo, incluindo como planejar, configurar e administrar, [comece aqui](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="b677a-123">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="b677a-124">Mover os locais geográficos de um locatário</span><span class="sxs-lookup"><span data-stu-id="b677a-124">Move a tenant's geographic locations</span></span>

<span data-ttu-id="b677a-125">A Microsoft continua a abrir os novos locais geográficos do datacenter (GEOS) para serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b677a-125">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="b677a-126">Esses novos datacenters GEOS adicionam capacidade e computam recursos para dar suporte ao crescimento de demanda e uso do cliente.</span><span class="sxs-lookup"><span data-stu-id="b677a-126">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="b677a-127">Além disso, o novo GEOS de datacenter oferece residências de dados geográficos para dados essenciais do cliente.</span><span class="sxs-lookup"><span data-stu-id="b677a-127">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="b677a-128">Para obter informações sobre a geografia do Microsoft 365 datacenter, incluindo como solicitar uma movimentação de dados geográfica, [comece aqui](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="b677a-128">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="b677a-129">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b677a-129">Next step</span></span>

<span data-ttu-id="b677a-130">Inicie o planejamento de locatários com [assinaturas, licenças, contas e locatários](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="b677a-130">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

