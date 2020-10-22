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
- m365initiative-coredeploy
ms.custom: it-pro
description: O roteiro para configurar seus locatários para o Microsoft 365.
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656002"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="8cdef-103">Roteiro do locatário para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8cdef-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="8cdef-104">O Microsoft 365 locatário é o conjunto de serviços atribuídos à sua organização.</span><span class="sxs-lookup"><span data-stu-id="8cdef-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="8cdef-105">Normalmente, esse locatário é associado a um ou mais dos nomes de domínio DNS e atua como um contêiner central para assinaturas diferentes e as licenças dentro delas que você atribui às contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="8cdef-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="8cdef-106">Para obter mais informações, consulte [assinaturas, licenças, contas e locatários para ofertas de nuvem da Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="8cdef-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="8cdef-107">Ao criar um locatário do Microsoft 365, você o atribui a uma localização geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="8cdef-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="8cdef-108">Você também pode ter um locatário com vários locais geográficos e mover o locatário de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="8cdef-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="8cdef-109">Para que o seu locatário fique pronto para a identidade, é fundamental planejar e executar cuidadosamente a configuração do locatário.</span><span class="sxs-lookup"><span data-stu-id="8cdef-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="8cdef-110">Configurar seu locatário do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8cdef-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="8cdef-111">Após garantir que sua rede seja otimizada para acessar o Microsoft 365 para os funcionários remotos e locais, suas próximas tarefas grandes estão planejando e, em seguida, configurando o Microsoft 365 locatário para nomes de domínio DNS, serviços comuns e para essa infraestrutura de identidade que oferece suporte à entrada de usuário segura.</span><span class="sxs-lookup"><span data-stu-id="8cdef-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="8cdef-112">Planejar</span><span class="sxs-lookup"><span data-stu-id="8cdef-112">Plan</span></span>

<span data-ttu-id="8cdef-113">Para planejar sua implementação de locatário:</span><span class="sxs-lookup"><span data-stu-id="8cdef-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="8cdef-114">Entender as assinaturas, as licenças e os locatários do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8cdef-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="8cdef-115">Entender como usar certificados SSL de terceiros</span><span class="sxs-lookup"><span data-stu-id="8cdef-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="8cdef-116">Entender as maneiras como um Microsoft 365 locatário é integrado aos serviços do Azure AD</span><span class="sxs-lookup"><span data-stu-id="8cdef-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="8cdef-117">Planejar o suporte ao aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="8cdef-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="8cdef-118">Determinar como usar a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="8cdef-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="8cdef-119">Planejar atualizações do Office 2007 e do Office 2010</span><span class="sxs-lookup"><span data-stu-id="8cdef-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="8cdef-120">Entender o isolamento do locatário</span><span class="sxs-lookup"><span data-stu-id="8cdef-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="8cdef-121">Obtenha os detalhes sobre o Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="8cdef-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="8cdef-122">Implantar</span><span class="sxs-lookup"><span data-stu-id="8cdef-122">Deploy</span></span>

<span data-ttu-id="8cdef-123">Para implantar seu locatário:</span><span class="sxs-lookup"><span data-stu-id="8cdef-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="8cdef-124">Adicione os [domínios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="8cdef-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="8cdef-125">Use os [guias de configuração no centro de administração do Microsoft 365](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="8cdef-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="8cdef-126">Crie sua [infraestrutura de identidade](identity-roadmap-microsoft-365.md) e [proteja suas entradas de usuário](microsoft-365-secure-sign-in.md).</span><span class="sxs-lookup"><span data-stu-id="8cdef-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="8cdef-127">Mover os locais geográficos de um locatário</span><span class="sxs-lookup"><span data-stu-id="8cdef-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="8cdef-128">A Microsoft continua a abrir os novos locais geográficos do datacenter (GEOS) para serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8cdef-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="8cdef-129">Esses novos datacenters GEOS adicionam capacidade e computam recursos para dar suporte ao crescimento de demanda e uso do cliente.</span><span class="sxs-lookup"><span data-stu-id="8cdef-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="8cdef-130">Além disso, o novo GEOS de datacenter oferece residências de dados geográficos para dados essenciais do cliente.</span><span class="sxs-lookup"><span data-stu-id="8cdef-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="8cdef-131">Para obter mais informações, consulte [movendo dados principais para o novo Microsoft 365 datacenter GEOS](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="8cdef-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="8cdef-132">Implantar o Microsoft 365 multigeográfico</span><span class="sxs-lookup"><span data-stu-id="8cdef-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="8cdef-133">Com o Microsoft 365 Multi-Geo, sua organização pode expandir sua presença no Microsoft 365 para várias regiões geográficas e/ou países do seu locatário existente.</span><span class="sxs-lookup"><span data-stu-id="8cdef-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="8cdef-134">Para obter mais informações, consulte [Microsoft 365 multigeo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="8cdef-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="8cdef-135">Gerenciar vários Microsoft 365 locações</span><span class="sxs-lookup"><span data-stu-id="8cdef-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="8cdef-136">Embora ter um único locatário para seu oganization seja ideal, você pode ser uma das muitas organizações que possuem vários locações.</span><span class="sxs-lookup"><span data-stu-id="8cdef-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="8cdef-137">Motivos para vários locações podem incluir fusões e aquisições, você deseja um isolamento administrativo ou você tem uma ti descentralizada.</span><span class="sxs-lookup"><span data-stu-id="8cdef-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="8cdef-138">Se você tiver vários Microsoft 365 locações, consulte estes artigos para obter mais informações sobre:</span><span class="sxs-lookup"><span data-stu-id="8cdef-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="8cdef-139">Colaboração entre locatários</span><span class="sxs-lookup"><span data-stu-id="8cdef-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="8cdef-140">Migração de caixa de correio entre locatários</span><span class="sxs-lookup"><span data-stu-id="8cdef-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="8cdef-141">Migrações de locatário-para-locatário</span><span class="sxs-lookup"><span data-stu-id="8cdef-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="8cdef-142">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="8cdef-142">Next step</span></span>

<span data-ttu-id="8cdef-143">Inicie o planejamento de locatários com [assinaturas, licenças, contas e locatários](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="8cdef-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
