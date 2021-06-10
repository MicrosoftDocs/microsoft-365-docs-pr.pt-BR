---
title: Use o controle de acesso baseado em função para conceder acesso fino a Central de Segurança do Microsoft Defender
description: Crie funções e grupos em suas operações de segurança para conceder acesso ao portal.
keywords: rbac, role, based, access, control, groups, control, tier, aad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053294"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="a14b5-104">Gerenciar o acesso ao portal usando o controle de acesso baseado em função</span><span class="sxs-lookup"><span data-stu-id="a14b5-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a14b5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a14b5-105">**Applies to:**</span></span>
- <span data-ttu-id="a14b5-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a14b5-106">Azure Active Directory</span></span>
- <span data-ttu-id="a14b5-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="a14b5-107">Office 365</span></span>

> <span data-ttu-id="a14b5-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a14b5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a14b5-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a14b5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="a14b5-110">Usando o controle de acesso baseado em função (RBAC), você pode criar funções e grupos em sua equipe de operações de segurança para conceder acesso apropriado ao portal.</span><span class="sxs-lookup"><span data-stu-id="a14b5-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="a14b5-111">Com base nas funções e grupos que você cria, você tem um controle fino sobre o que os usuários com acesso ao portal podem ver e fazer.</span><span class="sxs-lookup"><span data-stu-id="a14b5-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="a14b5-112">Grandes equipes de operações de segurança distribuídas geográficas geralmente adotam um modelo baseado em camadas para atribuir e autorizar o acesso a portais de segurança.</span><span class="sxs-lookup"><span data-stu-id="a14b5-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="a14b5-113">As camadas típicas incluem os três níveis a seguir:</span><span class="sxs-lookup"><span data-stu-id="a14b5-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="a14b5-114">Camada</span><span class="sxs-lookup"><span data-stu-id="a14b5-114">Tier</span></span> | <span data-ttu-id="a14b5-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="a14b5-115">Description</span></span>
:---|:---
<span data-ttu-id="a14b5-116">Camada 1</span><span class="sxs-lookup"><span data-stu-id="a14b5-116">Tier 1</span></span> | <span data-ttu-id="a14b5-117">**Equipe de operações de segurança local/equipe de IT**</span><span class="sxs-lookup"><span data-stu-id="a14b5-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="a14b5-118">Essa equipe geralmente triagem e investiga alertas contidos em sua localização geográfica e escalona para a Camada 2 nos casos em que uma correção ativa é necessária.</span><span class="sxs-lookup"><span data-stu-id="a14b5-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="a14b5-119">Camada 2</span><span class="sxs-lookup"><span data-stu-id="a14b5-119">Tier 2</span></span> | <span data-ttu-id="a14b5-120">**Equipe de operações de segurança regional**</span><span class="sxs-lookup"><span data-stu-id="a14b5-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="a14b5-121">Essa equipe pode ver todos os dispositivos de sua região e executar ações de correção.</span><span class="sxs-lookup"><span data-stu-id="a14b5-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="a14b5-122">Camada 3</span><span class="sxs-lookup"><span data-stu-id="a14b5-122">Tier 3</span></span> | <span data-ttu-id="a14b5-123">**Equipe de operações de segurança global**</span><span class="sxs-lookup"><span data-stu-id="a14b5-123">**Global security operations team**</span></span> <br> <span data-ttu-id="a14b5-124">Essa equipe consiste em especialistas em segurança e está autorizada a ver e executar todas as ações do portal.</span><span class="sxs-lookup"><span data-stu-id="a14b5-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="a14b5-125">O Defender for Endpoint RBAC foi projetado para dar suporte ao seu modelo de escolha baseado em camada ou função e oferece controle granular sobre quais funções podem ser vistas, dispositivos que podem acessar e ações que podem ser tomadas.</span><span class="sxs-lookup"><span data-stu-id="a14b5-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="a14b5-126">A estrutura do RBAC é centralizada em torno dos seguintes controles:</span><span class="sxs-lookup"><span data-stu-id="a14b5-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="a14b5-127">**Controlar quem pode tomar medidas específicas**</span><span class="sxs-lookup"><span data-stu-id="a14b5-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="a14b5-128">Crie funções personalizadas e controle quais recursos do Defender for Endpoint podem acessar com granularidade.</span><span class="sxs-lookup"><span data-stu-id="a14b5-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="a14b5-129">**Controlar quem pode ver informações sobre grupos ou grupos específicos de dispositivos**</span><span class="sxs-lookup"><span data-stu-id="a14b5-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="a14b5-130">[Crie grupos](machine-groups.md) de dispositivos por critérios específicos, como nomes, marcas, domínios e outros, em seguida, conceda acesso a função a eles usando um grupo de usuários Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a14b5-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="a14b5-131">Para implementar o acesso baseado em função, você precisará definir funções de administrador, atribuir permissões correspondentes e atribuir grupos de usuários do Azure AD atribuídos às funções.</span><span class="sxs-lookup"><span data-stu-id="a14b5-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="a14b5-132">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a14b5-132">Before you begin</span></span>
<span data-ttu-id="a14b5-133">Antes de usar o RBAC, é importante que você entenda as funções que podem conceder permissões e as consequências de ligar o RBAC.</span><span class="sxs-lookup"><span data-stu-id="a14b5-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="a14b5-134">Antes de ativar o recurso, é importante que você tenha uma função de Administrador Global ou uma função de Administrador de Segurança no Azure AD e que você tenha seus grupos do Azure AD prontos para reduzir o risco de ser bloqueado fora do portal.</span><span class="sxs-lookup"><span data-stu-id="a14b5-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="a14b5-135">Quando você faz logon pela Central de Segurança do Microsoft Defender, você tem acesso total ou somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a14b5-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="a14b5-136">Direitos de acesso completo são concedidos aos usuários com funções de Administrador de Segurança ou Administrador Global no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a14b5-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="a14b5-137">O acesso somente leitura é concedido aos usuários com uma função de Leitor de Segurança no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a14b5-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="a14b5-138">Alguém com uma função de administrador do Defender para Ponto de Extremidade Global tem acesso irrestrito a todos os dispositivos, independentemente da associação do grupo de dispositivos e das atribuições de grupos de usuários do Azure AD</span><span class="sxs-lookup"><span data-stu-id="a14b5-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="a14b5-139">Inicialmente, somente aqueles com direitos de Administrador Global do Azure AD ou Administrador de Segurança poderão criar e atribuir funções no Central de Segurança do Microsoft Defender, portanto, é importante ter os grupos certos prontos no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a14b5-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="a14b5-140">**A ação do controle de acesso baseado em função fará com que os usuários com permissões somente leitura (por exemplo, usuários atribuídos à função de leitor de Segurança do Azure AD) percam acesso até que sejam atribuídos a uma função.**</span><span class="sxs-lookup"><span data-stu-id="a14b5-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="a14b5-141">Os usuários com permissões de administrador são atribuídos automaticamente à função de administrador global interna padrão do Defender para o Ponto de Extremidade com permissões completas.</span><span class="sxs-lookup"><span data-stu-id="a14b5-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="a14b5-142">Depois de optar por usar o RBAC, você pode atribuir usuários adicionais que não sejam Azure AD Global ou Administradores de Segurança à função de administrador global do Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="a14b5-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="a14b5-143">Depois de optar por usar o RBAC, não é possível reverter para as funções iniciais como quando você fez logor pela primeira vez no portal.</span><span class="sxs-lookup"><span data-stu-id="a14b5-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="a14b5-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a14b5-144">Related topic</span></span>
- [<span data-ttu-id="a14b5-145">Criar e gerenciar grupos de dispositivos no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a14b5-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
