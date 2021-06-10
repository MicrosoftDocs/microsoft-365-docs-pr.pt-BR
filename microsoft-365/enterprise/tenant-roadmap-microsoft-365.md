---
title: Roteiro de locatário para Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: O roteiro para configurar seus locatários para Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909449"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="c4110-103">Roteiro de locatário para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c4110-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="c4110-104">Seu Microsoft 365 locatário é o conjunto de serviços atribuídos à sua organização.</span><span class="sxs-lookup"><span data-stu-id="c4110-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="c4110-105">Normalmente, esse locatário está associado a um ou mais nomes de domínio DNS públicos e age como um contêiner central e isolado para assinaturas diferentes e as licenças dentro delas que você atribui a contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="c4110-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="c4110-106">Para obter mais informações, consulte [Assinaturas, licenças, contas e locatários para ofertas de nuvem da Microsoft.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="c4110-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="c4110-107">Ao criar um Microsoft 365 locatário, atribua-o a uma localização geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="c4110-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="c4110-108">Você também pode ter um locatário com várias localizações geográficas e mover seu locatário de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="c4110-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="c4110-109">Para preparar seu locatário para usuários, grupos, licenças e aplicativos de nuvem, é fundamental planejar e executar cuidadosamente a configuração do locatário.</span><span class="sxs-lookup"><span data-stu-id="c4110-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="c4110-110">Configure o locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4110-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="c4110-111">Depois de garantir que sua rede seja otimizada para acesso ao Microsoft 365 para funcionários locais e remotos, suas próximas grandes tarefas estão planejando e configurando seu locatário do Microsoft 365 para nomes de domínio DNS, serviços comuns e para essa infraestrutura de identidade que dá suporte à entrada segura do usuário.</span><span class="sxs-lookup"><span data-stu-id="c4110-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="c4110-112">Plano</span><span class="sxs-lookup"><span data-stu-id="c4110-112">Plan</span></span>

<span data-ttu-id="c4110-113">Para planejar a implementação do locatário:</span><span class="sxs-lookup"><span data-stu-id="c4110-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="c4110-114">Compreender assinaturas, licenças e locatários Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="c4110-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="c4110-115">Entender como usar certificados SSL de terceiros</span><span class="sxs-lookup"><span data-stu-id="c4110-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="c4110-116">Entenda como um locatário Microsoft 365 está integrado aos serviços do Azure AD</span><span class="sxs-lookup"><span data-stu-id="c4110-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="c4110-117">Planejar o suporte ao aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="c4110-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="c4110-118">Determinar como usar a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="c4110-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="c4110-119">Planejar as Office 2007 e Office 2010</span><span class="sxs-lookup"><span data-stu-id="c4110-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="c4110-120">Compreender o isolamento de locatários</span><span class="sxs-lookup"><span data-stu-id="c4110-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="c4110-121">Implantar</span><span class="sxs-lookup"><span data-stu-id="c4110-121">Deploy</span></span>

<span data-ttu-id="c4110-122">Para implantar seu locatário:</span><span class="sxs-lookup"><span data-stu-id="c4110-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="c4110-123">Adicione os [domínios DNS](../admin/setup/add-domain.md) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c4110-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="c4110-124">Use as [guias de instalação no Microsoft 365 de administração](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="c4110-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="c4110-125">Crie sua infraestrutura [de identidade e](identity-roadmap-microsoft-365.md) proteja suas [insuportações do usuário.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="c4110-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="c4110-126">Mover locais geográficos de um locatário</span><span class="sxs-lookup"><span data-stu-id="c4110-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="c4110-127">A Microsoft continua a abrir novas localizações geográficas do datacenter (geos) para Microsoft 365 serviços.</span><span class="sxs-lookup"><span data-stu-id="c4110-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="c4110-128">Esses novos geos do datacenter adicionam capacidade e recursos de computação para dar suporte à demanda do cliente e ao crescimento do uso.</span><span class="sxs-lookup"><span data-stu-id="c4110-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="c4110-129">Além disso, os novos geos do datacenter oferecem residência de dados no geo para dados principais do cliente.</span><span class="sxs-lookup"><span data-stu-id="c4110-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="c4110-130">Para obter mais informações, consulte [Movendo os dados principais para novas Microsoft 365 de datacenter](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="c4110-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="c4110-131">Implantar Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="c4110-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="c4110-132">Com o Microsoft 365 Multi-Geo, sua organização pode expandir sua presença no Microsoft 365 para várias regiões geográficas e/ou países do seu locatário existente.</span><span class="sxs-lookup"><span data-stu-id="c4110-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="c4110-133">Para mais informações, consulte [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="c4110-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="c4110-134">Gerenciar vários Microsoft 365 locatários</span><span class="sxs-lookup"><span data-stu-id="c4110-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="c4110-135">Embora ter um único locatário para sua oganização seja ideal, você pode ser uma das muitas organizações que têm vários locatários.</span><span class="sxs-lookup"><span data-stu-id="c4110-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="c4110-136">Os motivos podem incluir fusões e aquisições, você deseja isolamento administrativo ou ter uma TI descentralizada.</span><span class="sxs-lookup"><span data-stu-id="c4110-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="c4110-137">Se você tiver vários Microsoft 365 locatários, confira estes artigos para obter mais informações sobre:</span><span class="sxs-lookup"><span data-stu-id="c4110-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="c4110-138">Colaboração entre locatários</span><span class="sxs-lookup"><span data-stu-id="c4110-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="c4110-139">Migração de caixa de correio entre locatários</span><span class="sxs-lookup"><span data-stu-id="c4110-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="c4110-140">Migrações de locatário-para-locatário</span><span class="sxs-lookup"><span data-stu-id="c4110-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="c4110-141">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c4110-141">Next step</span></span>

<span data-ttu-id="c4110-142">Inicie o planejamento de [locatários com Assinaturas, licenças, contas e locatários.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="c4110-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>