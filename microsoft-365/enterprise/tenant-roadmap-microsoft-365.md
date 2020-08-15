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
ms.collection: M365-subscription-management
ms.custom: it-pro
description: O roteiro para configurar seus locatários para o Microsoft 365.
ms.openlocfilehash: db7054d1f6afc7e4835507dc6415e0b240918c1f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687473"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="f58c5-103">Roteiro do locatário para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f58c5-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="f58c5-104">O Microsoft 365 locatário é o conjunto de serviços atribuídos à sua organização.</span><span class="sxs-lookup"><span data-stu-id="f58c5-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="f58c5-105">Esse locatário é geralmente associado a um ou mais dos nomes de domínio DNS e atua como um contêiner central para assinaturas diferentes e as licenças que você atribui às contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="f58c5-105">This tenant is typically associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> 

<span data-ttu-id="f58c5-106">Ao criar um locatário do Microsoft 365, você o atribui a uma localização geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="f58c5-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="f58c5-107">Você também pode ter um locatário com vários locais geográficos e mover o locatário de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="f58c5-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="f58c5-108">Uma configuração de locatário bem planejada e executada é crítica para se preparar para os serviços fundamentais de rede e identidade.</span><span class="sxs-lookup"><span data-stu-id="f58c5-108">A well-planned and executed tenant configuration is critical to getting it ready for the foundational services of networking and identity.</span></span>

## <a name="plan"></a><span data-ttu-id="f58c5-109">Plano</span><span class="sxs-lookup"><span data-stu-id="f58c5-109">Plan</span></span>

<span data-ttu-id="f58c5-110">Na fase de planejamento da implementação do locatário:</span><span class="sxs-lookup"><span data-stu-id="f58c5-110">In the planning phase of your tenant implementation:</span></span>

- [<span data-ttu-id="f58c5-111">Entender as assinaturas, as licenças e os locatários do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="f58c5-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="f58c5-112">Entender como usar certificados SSL de terceiros</span><span class="sxs-lookup"><span data-stu-id="f58c5-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="f58c5-113">Acessar guias de configuração no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f58c5-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="f58c5-114">Entender as maneiras como um Microsoft 365 locatário é integrado aos serviços do Azure AD</span><span class="sxs-lookup"><span data-stu-id="f58c5-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="f58c5-115">Planejar o suporte ao aplicativo cliente</span><span class="sxs-lookup"><span data-stu-id="f58c5-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="f58c5-116">Determinar como usar a autenticação moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="f58c5-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="f58c5-117">Planejar atualizações do Office 2007 e do Office 2010</span><span class="sxs-lookup"><span data-stu-id="f58c5-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="f58c5-118">Entender o isolamento do locatário</span><span class="sxs-lookup"><span data-stu-id="f58c5-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="f58c5-119">Obtenha os detalhes sobre o Microsoft 365 Service Assurance</span><span class="sxs-lookup"><span data-stu-id="f58c5-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="f58c5-120">Implantar</span><span class="sxs-lookup"><span data-stu-id="f58c5-120">Deploy</span></span>

<span data-ttu-id="f58c5-121">Na fase de implantação de sua implementação de locatário, [adicione os domínios DNS](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f58c5-121">In the deployment phase of your tenant implementation, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="f58c5-122">Locatários com vários locais geográficos</span><span class="sxs-lookup"><span data-stu-id="f58c5-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="f58c5-123">Com o Microsoft 365 Multi-Geo, sua organização pode expandir sua presença no Microsoft 365 para várias regiões geográficas e/ou países do seu locatário existente.</span><span class="sxs-lookup"><span data-stu-id="f58c5-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="f58c5-124">[Introdução](microsoft-365-multi-geo.md) à compreensão, planejamento, configuração e administração com o Microsoft 365 multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="f58c5-124">[Get started](microsoft-365-multi-geo.md) in understanding, planning, configuring, and then administering with Microsoft 365 Multi-Geo.</span></span>

## <a name="moving-a-tenants-geographic-locations"></a><span data-ttu-id="f58c5-125">Movendo locais geográficos de um locatário</span><span class="sxs-lookup"><span data-stu-id="f58c5-125">Moving a tenant's geographic locations</span></span>

<span data-ttu-id="f58c5-126">A Microsoft continua a abrir os novos locais geográficos do datacenter (GEOS) para serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f58c5-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="f58c5-127">Esses novos datacenters GEOS adicionam capacidade e computam recursos para dar suporte ao crescimento de demanda e uso do cliente.</span><span class="sxs-lookup"><span data-stu-id="f58c5-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="f58c5-128">Além disso, o novo GEOS de datacenter oferece residências de dados geográficos para dados essenciais do cliente.</span><span class="sxs-lookup"><span data-stu-id="f58c5-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="f58c5-129">Introdução à compreensão e à solicitação de uma movimentação geográfica de dados com [a movimentação de dados principais para a nova Geografia do Microsoft 365 datacenter](moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="f58c5-129">Get started in understanding and requesting a geo data move with [Moving core data to new Microsoft 365 datacenter geo](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="f58c5-130">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f58c5-130">Next step</span></span>

<span data-ttu-id="f58c5-131">Inicie o planejamento de locatários com [assinaturas, licenças, contas e locatários](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="f58c5-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

