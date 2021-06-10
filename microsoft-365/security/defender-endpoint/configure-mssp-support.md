---
title: Configurar o suporte ao provedor de serviços de segurança gerenciado
description: Tomar as etapas necessárias para configurar a integração do MSSP com o Microsoft Defender para Ponto de Extremidade
keywords: provedor de serviços de segurança gerenciado, mssp, configurar, integração
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
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165244"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="1dc3a-104">Configurar a integração do provedor de serviços de segurança gerenciada</span><span class="sxs-lookup"><span data-stu-id="1dc3a-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1dc3a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1dc3a-105">**Applies to:**</span></span>
- [<span data-ttu-id="1dc3a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1dc3a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1dc3a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1dc3a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1dc3a-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="1dc3a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1dc3a-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1dc3a-110">Você precisará seguir as etapas de configuração a seguir para habilitar a integração do provedor de serviços de segurança gerenciado (MSSP).</span><span class="sxs-lookup"><span data-stu-id="1dc3a-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="1dc3a-111">Os seguintes termos são usados neste artigo para distinguir entre o provedor de serviços e o consumidor de serviço:</span><span class="sxs-lookup"><span data-stu-id="1dc3a-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="1dc3a-112">MSSPs: organizações de segurança que oferecem para monitorar e gerenciar dispositivos de segurança para uma organização.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="1dc3a-113">Clientes MSSP: Organizações que envolvem os serviços de MSSPs.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="1dc3a-114">A integração permitirá que os MSSPs tomem as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="1dc3a-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="1dc3a-115">Obter acesso ao portal de Central de Segurança do Microsoft Defender do cliente MSSP</span><span class="sxs-lookup"><span data-stu-id="1dc3a-115">Get access to MSSP customer's Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="1dc3a-116">Obter notificações por email e</span><span class="sxs-lookup"><span data-stu-id="1dc3a-116">Get email notifications, and</span></span> 
- <span data-ttu-id="1dc3a-117">Buscar alertas por meio de informações de segurança e ferramentas de gerenciamento de eventos (SIEM)</span><span class="sxs-lookup"><span data-stu-id="1dc3a-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="1dc3a-118">Antes que os MSSPs possam tomar essas ações, o cliente MSSP precisará conceder acesso ao locatário do Defender para Ponto de Extremidade para que o MSSP possa acessar o portal.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="1dc3a-119">Normalmente, os clientes do MSSP têm as etapas iniciais de configuração para conceder acesso aos MSSPs ao seu locatário Windows Defender Central de Segurança.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="1dc3a-120">Depois que o acesso é concedido, outras etapas de configuração podem ser feitas pelo cliente MSSP ou pelo MSSP.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="1dc3a-121">Em geral, as etapas de configuração a seguir precisam ser tomadas:</span><span class="sxs-lookup"><span data-stu-id="1dc3a-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="1dc3a-122">**Conceda o acesso do MSSP ao Central de Segurança do Microsoft Defender**</span><span class="sxs-lookup"><span data-stu-id="1dc3a-122">**Grant the MSSP access to Microsoft Defender Security Center**</span></span> <br>
<span data-ttu-id="1dc3a-123">Essa ação precisa ser feita pelo cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="1dc3a-124">Ele concede ao MSSP acesso ao locatário defender para ponto de extremidade do cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="1dc3a-125">**Configurar notificações de alerta enviadas para MSSPs**</span><span class="sxs-lookup"><span data-stu-id="1dc3a-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="1dc3a-126">Essa ação pode ser tomada pelo cliente MSSP ou pelo MSSP.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="1dc3a-127">Isso permite que os MSSPs saibam quais alertas precisam ser endereços para o cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="1dc3a-128">**Buscar alertas do locatário do cliente MSSP para o sistema SIEM**</span><span class="sxs-lookup"><span data-stu-id="1dc3a-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="1dc3a-129">Essa ação é tomada pelo MSSP.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="1dc3a-130">Ele permite que os MSSPs busquem alertas em ferramentas SIEM.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="1dc3a-131">**Buscar alertas do locatário do cliente MSSP usando APIs**</span><span class="sxs-lookup"><span data-stu-id="1dc3a-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="1dc3a-132">Essa ação é tomada pelo MSSP.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="1dc3a-133">Ele permite que os MSSPs busquem alertas usando APIs.</span><span class="sxs-lookup"><span data-stu-id="1dc3a-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="1dc3a-134">Acesso de vários locatários para MSSPs</span><span class="sxs-lookup"><span data-stu-id="1dc3a-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="1dc3a-135">Para obter informações sobre como implementar um acesso delegado de vários locatários, consulte [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span><span class="sxs-lookup"><span data-stu-id="1dc3a-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="1dc3a-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1dc3a-136">Related topics</span></span>
- [<span data-ttu-id="1dc3a-137">Conceder acesso MSSP ao portal</span><span class="sxs-lookup"><span data-stu-id="1dc3a-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="1dc3a-138">Acessar o portal do cliente MSSP</span><span class="sxs-lookup"><span data-stu-id="1dc3a-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="1dc3a-139">Configurar notificações de alerta</span><span class="sxs-lookup"><span data-stu-id="1dc3a-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="1dc3a-140">Buscar alertas do locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="1dc3a-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

